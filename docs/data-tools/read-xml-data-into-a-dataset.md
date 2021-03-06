---
title: Ler dados XML em um conjunto de dados
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reading XML
- data access [Visual Studio], XML data
- reading files, XML
- data [Visual Studio], reading from XML files
- reading data, XML files
- XML [Visual Studio], reading
- XML documents, reading
- datasets [Visual Basic], reading XML data
ms.assetid: fae72958-0893-47d6-b3dd-9d42418418e4
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 5f89645b9d5ec8ab0f69fad4fea5a399d8e6764d
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586322"
---
# <a name="read-xml-data-into-a-dataset"></a>Ler dados XML em um conjunto de dados

O ADO.NET fornece métodos simples para trabalhar com dados XML. Neste tutorial, você cria um aplicativo do Windows que carrega dados XML em um DataSet. Em seguida, o DataSet é exibido em um controle <xref:System.Windows.Forms.DataGridView>. Por fim, um esquema XML baseado no conteúdo do arquivo XML é exibido em uma caixa de texto.

## <a name="create-a-new-project"></a>Crie um novo projeto

Crie um novo projeto de **aplicativo Windows Forms** para C# o ou o Visual Basic. Nomeie o projeto **ReadingXML**.

## <a name="generate-the-xml-file-to-be-read-into-the-dataset"></a>Gerar o arquivo XML a ser lido no conjunto de

Como este passo a passos se concentra na leitura de dados XML em um conjunto, o conteúdo de um arquivo XML é fornecido.

1. No menu **Projeto**, selecione **Adicionar Novo Item**.

2. Selecione **arquivo XML**, nomeie o arquivo **Authors. xml**e, em seguida, selecione **Adicionar**.

   O arquivo XML é carregado no designer e está pronto para edição.

3. Cole os seguintes dados XML no editor abaixo da declaração XML:

   ```xml
   <Authors_Table>
     <authors>
       <au_id>172-32-1176</au_id>
       <au_lname>White</au_lname>
       <au_fname>Johnson</au_fname>
       <phone>408 496-7223</phone>
       <address>10932 Bigge Rd.</address>
       <city>Menlo Park</city>
       <state>CA</state>
       <zip>94025</zip>
       <contract>true</contract>
     </authors>
     <authors>
       <au_id>213-46-8915</au_id>
       <au_lname>Green</au_lname>
       <au_fname>Margie</au_fname>
       <phone>415 986-7020</phone>
       <address>309 63rd St. #411</address>
       <city>Oakland</city>
       <state>CA</state>
       <zip>94618</zip>
       <contract>true</contract>
     </authors>
     <authors>
       <au_id>238-95-7766</au_id>
       <au_lname>Carson</au_lname>
       <au_fname>Cheryl</au_fname>
       <phone>415 548-7723</phone>
       <address>589 Darwin Ln.</address>
       <city>Berkeley</city>
       <state>CA</state>
       <zip>94705</zip>
       <contract>true</contract>
     </authors>
     <authors>
       <au_id>267-41-2394</au_id>
       <au_lname>Hunter</au_lname>
       <au_fname>Anne</au_fname>
       <phone>408 286-2428</phone>
       <address>22 Cleveland Av. #14</address>
       <city>San Jose</city>
       <state>CA</state>
       <zip>95128</zip>
       <contract>true</contract>
     </authors>
     <authors>
       <au_id>274-80-9391</au_id>
       <au_lname>Straight</au_lname>
       <au_fname>Dean</au_fname>
       <phone>415 834-2919</phone>
       <address>5420 College Av.</address>
       <city>Oakland</city>
       <state>CA</state>
       <zip>94609</zip>
       <contract>true</contract>
     </authors>
   </Authors_Table>
   ```

4. No menu **arquivo** , selecione **salvar Authors. xml**.

## <a name="create-the-user-interface"></a>Criar a interface do usuário

A interface do usuário para esse aplicativo consiste no seguinte:

- Um controle de <xref:System.Windows.Forms.DataGridView> que exibe o conteúdo do arquivo XML como dados.

- Um controle de <xref:System.Windows.Forms.TextBox> que exibe o esquema XML para o arquivo XML.

- Dois controles de <xref:System.Windows.Forms.Button>.

  - Um botão lê o arquivo XML no conjunto de e o exibe no controle de <xref:System.Windows.Forms.DataGridView>.

  - Um segundo botão extrai o esquema do conjunto de um e por meio de um <xref:System.IO.StringWriter> exibe-o no controle de <xref:System.Windows.Forms.TextBox>.

### <a name="to-add-controls-to-the-form"></a>Para adicionar controles ao formulário

1. Abra `Form1` no modo de exibição de design.

2. Na **caixa de ferramentas**, arraste os seguintes controles para o formulário:

    - Um controle de <xref:System.Windows.Forms.DataGridView>

    - Um controle de <xref:System.Windows.Forms.TextBox>

    - Dois controles de <xref:System.Windows.Forms.Button>

3. Defina as propriedades a seguir:

    |Controle|propriedade|Configuração|
    |-------------|--------------|-------------|
    |`TextBox1`|**Multilinha**|`true`|
    ||**ScrollBars**|**Vertical**|
    |`Button1`|**Nome**|`ReadXmlButton`|
    ||**Texto**|`Read XML`|
    |`Button2`|**Nome**|`ShowSchemaButton`|
    ||**Texto**|`Show Schema`|

## <a name="create-the-dataset-that-receives-the-xml-data"></a>Criar o DataSet que recebe os dados XML

Nesta etapa, você cria um novo conjunto de conjuntos chamado `authors`. Para obter mais informações sobre conjuntos de dados, consulte [ferramentas de DataSet no Visual Studio](../data-tools/dataset-tools-in-visual-studio.md).

1. Em **Gerenciador de soluções**, selecione o arquivo de origem para o **Form1**e, em seguida, selecione o botão **Designer de exibição** na barra de ferramentas **Gerenciador de soluções** .

2. Na [caixa de ferramentas, guia Data](../ide/reference/toolbox-data-tab.md), arraste um **conjunto** de dados para **Form1**.

3. Na caixa de diálogo **Adicionar conjunto** de texto, selecione **conjunto de tipos não tipado**e, em seguida, selecione **OK**.

     **DataSet1** é adicionado à bandeja de componentes.

4. Na janela **Propriedades** , defina o **nome** e as propriedades de <xref:System.Data.DataSet.DataSetName%2A> para`AuthorsDataSet`.

## <a name="create-the-event-handler-to-read-the-xml-file-into-the-dataset"></a>Criar o manipulador de eventos para ler o arquivo XML no conjunto de

O botão **ler XML** lê o arquivo XML no conjunto de os. Em seguida, ele define as propriedades no controle de <xref:System.Windows.Forms.DataGridView> que o associam ao DataSet.

1. Em **Gerenciador de soluções**, selecione **Form1**e, em seguida, selecione o botão **Designer de exibição** na barra de ferramentas **Gerenciador de soluções** .

2. Selecione o botão **ler XML** .

     O **Editor de código** é aberto no manipulador de eventos `ReadXmlButton_Click`.

3. Digite o código a seguir no manipulador de eventos `ReadXmlButton_Click`:

     [!code-csharp[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_1.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_1.vb)]

4. No código do manipulador de eventos `ReadXMLButton_Click`, altere a entrada `filepath =` para o caminho correto.

## <a name="create-the-event-handler-to-display-the-schema-in-the-textbox"></a>Criar o manipulador de eventos para exibir o esquema na caixa de texto

O botão **Mostrar esquema** cria um objeto <xref:System.IO.StringWriter> que é preenchido com o esquema e é exibido no controle de <xref:System.Windows.Forms.TextBox>.

1. Em **Gerenciador de soluções**, selecione **Form1**e, em seguida, selecione o botão **Designer de exibição** .

2. Selecione o botão **Mostrar esquema** .

     O **Editor de código** é aberto no manipulador de eventos `ShowSchemaButton_Click`.

3. Cole o código a seguir no manipulador de eventos `ShowSchemaButton_Click`.

     [!code-csharp[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_2.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_2.vb)]

## <a name="test-the-form"></a>Testar o formulário

Agora, é possível testar o formulário para garantir que ele se comporta da forma esperada.

1. Selecione **F5** para executar o aplicativo.

2. Selecione o botão **ler XML** .

     O DataGridView exibe o conteúdo do arquivo XML.

3. Selecione o botão **Mostrar esquema** .

     A caixa de texto exibe o esquema XML para o arquivo XML.

## <a name="next-steps"></a>{1&gt;{2&gt;Próximas etapas&lt;2}&lt;1}

Este tutorial ensina os conceitos básicos da leitura de um arquivo XML em um conjunto de um, bem como a criação de um esquema com base no conteúdo do arquivo XML. Aqui estão algumas tarefas que você pode fazer em seguida:

- Edite os dados no DataSet e grave-os de volta como XML. Para obter mais informações, consulte <xref:System.Data.DataSet.WriteXml%2A>.

- Edite os dados no DataSet e grave-os em um banco de dados.

## <a name="see-also"></a>Veja também

- [Acessar dados no Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
- [Ferramentas XML no Visual Studio](../xml-tools/xml-tools-in-visual-studio.md)
