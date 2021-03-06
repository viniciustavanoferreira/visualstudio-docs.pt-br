---
title: Acessar dados em documentos no servidor
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], accessing on server
- data access [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ab033120c0913bbae33458c5a2d0b53972364581
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255774"
---
# <a name="access-data-in-documents-on-the-server"></a>Acessar dados em documentos no servidor
  Você pode programar contra os dados em uma personalização em nível de documento sem precisar usar o modelo de objeto do Microsoft Office Word ou Microsoft Office Excel. Isso significa que você pode acessar os dados contidos em um documento em um servidor que não tenha o Word ou o Excel instalado. Por exemplo, o código em um servidor (por exemplo, em [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] uma página) pode personalizar os dados em um documento e enviar o documento personalizado para um usuário final. Quando o usuário final abre o documento, o código de vinculação de dados no assembly da solução associa os dados personalizados ao documento. Isso é possível porque os dados no documento são separados da interface do usuário. Para obter mais informações, consulte [dados armazenados em cache em personalizações em nível de documento](../vsto/cached-data-in-document-level-customizations.md).

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="cache-data-for-use-on-a-server"></a>Armazenar dados em cache para uso em um servidor
 Para armazenar em cache um objeto de dados em um documento, marque <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> -o com o atributo em tempo de `StartCaching` design ou use o método de um item de host em tempo de execução. Quando você armazena em cache um objeto de dados em um [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] documento, o serializa o objeto em uma cadeia de caracteres XML armazenada no documento. Os objetos devem atender a certos requisitos para serem qualificados para o Caching. Para obter mais informações, consulte [armazenar dados em cache](../vsto/caching-data.md).

 O código do servidor pode manipular qualquer objeto de dados no cache de dados. Controles que são associados a instâncias de dados em cache são sincronizados com a interface do usuário, para que qualquer alteração no servidor feita aos dados seja exibida automaticamente quando o documento for aberto no cliente.

## <a name="access-data-in-the-cache"></a>Acessar dados no cache
 Você pode acessar dados no cache de aplicativos fora do escritório, por exemplo, de um aplicativo de console, um aplicativo Windows Forms ou uma página da Web. O aplicativo que acessa os dados armazenados em cache deve ter confiança total; um aplicativo Web que tem confiança parcial não pode inserir, recuperar ou alterar dados armazenados em cache em um documento do Office.

 O cache de dados pode ser acessado por meio de uma hierarquia de <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> coleções que são <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> expostas pela propriedade da classe:

- A <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> propriedade retorna um <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>, que contém todos os dados armazenados em cache em uma personalização no nível do documento.

- Cada <xref:Microsoft.VisualStudio.Tools.Applications.CachedData> um contém um ou <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> mais objetos. Um <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> contém todos os objetos de dados armazenados em cache que são definidos dentro de uma única classe.

- Cada <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> um contém um ou <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> mais objetos. Um <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> representa um único objeto de dados em cache.

  O exemplo de código a seguir demonstra como acessar uma cadeia de caracteres armazenada em cache na `Sheet1` classe de um projeto de pasta de trabalho do Excel. Este exemplo faz parte de um exemplo maior que é fornecido para o <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> método.

  [!code-csharp[Trin_ServerDocument#12](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#12)]
  [!code-vb[Trin_ServerDocument#12](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#12)]

## <a name="modify-data-in-the-cache"></a>Modificar dados no cache
 Para modificar um objeto de dados em cache, você normalmente executa as seguintes etapas:

1. Desserializar a representação XML do objeto em cache em uma nova instância do objeto. Você pode acessar o XML usando a <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> propriedade <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> do que representa o objeto de dados em cache.

2. Faça as alterações nessa cópia.

3. Serialize o objeto alterado de volta para o cache de dados usando uma das seguintes opções:

    - Se você quiser serializar automaticamente as alterações, use o <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> método. Esse método usa o formato **DiffGram** para serializar <xref:System.Data.DataTable> <xref:System.Data.DataSet>, e os objetos dataset tipados no cache de dados. O formato **DiffGram** garante que as alterações no cache de dados em um documento offline sejam enviadas para o servidor corretamente.

    - Se você quiser executar sua própria serialização para alterações em dados armazenados em cache, poderá gravar diretamente na <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> propriedade. Especifique o formato **DiffGram** se você usar um <xref:System.Data.Common.DataAdapter> para atualizar um banco de dados com as alterações feitas em data <xref:System.Data.DataTable>em um <xref:System.Data.DataSet>DataSet, ou digitado. Caso contrário, <xref:System.Data.Common.DataAdapter> o irá atualizar o banco de dados adicionando novas linhas em vez de modificar as linhas existentes.

### <a name="modify-data-without-deserializing-the-current-value"></a>Modificar dados sem desserializar o valor atual
 Em alguns casos, talvez você queira modificar o valor do objeto armazenado em cache sem primeiro desserializar o valor atual. Por exemplo, você pode fazer isso se estiver alterando o valor de um objeto que tem um tipo simples, como uma cadeia de caracteres ou um inteiro, ou se estiver inicializando um <xref:System.Data.DataSet> cache em um documento em um servidor. Nesses casos, você pode usar o <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> método sem primeiro desserializar o valor atual do objeto armazenado em cache.

 O exemplo de código a seguir demonstra como alterar o valor de uma cadeia de caracteres armazenada em cache na `Sheet1` classe de um projeto de pasta de trabalho do Excel. Este exemplo faz parte de um exemplo maior que é fornecido para o <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> método.

 [!code-csharp[Trin_ServerDocument#11](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#11)]
 [!code-vb[Trin_ServerDocument#11](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#11)]

### <a name="modify-null-values-in-the-data-cache"></a>Modificar valores nulos no cache de dados
 O cache de dados não armazena objetos que têm o valor **NULL** quando o documento é salvo e fechado. Essa limitação tem várias consequências quando você modifica os dados armazenados em cache:

- Se você definir qualquer objeto no cache de dados para o valor **NULL**, todos os objetos no cache de dados serão definidos automaticamente como **NULL** quando o documento for aberto, e todo o cache de dados será limpo quando o documento for salvo e fechado. Ou seja, todos os objetos armazenados em cache serão removidos do cache de dados e a <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> coleção estará vazia.

- Se você criar uma solução com objetos **nulos** no cache de dados e quiser inicializar esses objetos usando a <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> classe antes que o documento seja aberto pela primeira vez, você deverá certificar-se de inicializar todos os objetos no cache de dados. Se você inicializar apenas alguns dos objetos, todos os objetos serão definidos como **nulos** quando o documento for aberto e todo o cache de dados será limpo quando o documento for salvo e fechado.

## <a name="access-typed-datasets-in-the-cache"></a>Acessar conjuntos de linhas tipados no cache
 Se você quiser acessar os dados em um dataset tipado tanto de uma solução do Office quanto de um aplicativo fora do escritório, como um aplicativo Windows Forms ou um [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] projeto, você deve definir o conjunto de dados tipado em um assembly separado que é referenciado em ambos projeto. Se você adicionar o conjunto de dados tipado a cada projeto usando o assistente de **configuração da fonte de dados** ou o **Designer de Conjunto de Dados**, o .NET Framework tratará os conjuntos de dados tipados nos dois projetos como tipos diferentes. Para obter mais informações sobre como criar conjuntos de dados tipados, consulte [criar e configurar conjuntos de dados no Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md).

## <a name="see-also"></a>Consulte também

- [Acessar dados em documentos no servidor](../vsto/accessing-data-in-documents-on-the-server.md)
- [Dados armazenados em cache em personalizações em nível de documento](../vsto/cached-data-in-document-level-customizations.md)