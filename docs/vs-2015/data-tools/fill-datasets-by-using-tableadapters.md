---
title: Preencher conjuntos de valores usando TableAdapters | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- datasets [Visual Basic]
- datasets [Visual Basic], loading data
- data retrieval
- retrieving data
- datasets [Visual Basic], filling
- data [Visual Studio], retrieving
- data [Visual Studio], datasets
ms.assetid: 55f3bfbe-db78-4486-add3-c62f49e6b9a0
caps.latest.revision: 35
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5fd1dcf464b7628e345845ca9f371ef6de1efe88
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672349"
---
# <a name="fill-datasets-by-using-tableadapters"></a>Preencher conjuntos de dados usando TableAdapters
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Um componente TableAdapter preenche um DataSet com dados do banco de dados, com base em uma ou mais consultas ou procedimentos armazenados que você especificar. Os TableAdapters também podem executar adições, atualizações e exclusões no banco de dados para manter as alterações que você faz no DataSet. Você também pode emitir comandos globais que não estão relacionados a nenhuma tabela específica.

> [!NOTE]
> Os TableAdapters são gerados pelos designers do Visual Studio. Se você estiver criando conjuntos de itens programaticamente, use DataAdapter, que é uma classe .NET Framework.

 Para obter informações detalhadas sobre as operações do TableAdapter, você pode pular diretamente para um destes tópicos:

|Tópico|Descrição|
|-----------|-----------------|
|[Criar e configurar TableAdapters](../data-tools/create-and-configure-tableadapters.md)|Como usar os designers para criar e configurar TableAdapters|
|[Criar consultas TableAdapter parametrizadas](../data-tools/create-parameterized-tableadapter-queries.md)|Como permitir que os usuários forneçam argumentos para procedimentos ou consultas do TableAdapter|
|[Acessar diretamente o banco de dados com um TableAdapter](../data-tools/directly-access-the-database-with-a-tableadapter.md)|Como usar os métodos DbDirect de TableAdapters|
|[Desligar restrições ao preencher um conjunto de dados](../data-tools/turn-off-constraints-while-filling-a-dataset.md)|Como trabalhar com restrições de chave estrangeira ao atualizar dados|
|[Como estender a funcionalidade de um TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md)|Como adicionar código personalizado a TableAdapters|
|[Ler dados XML em um conjunto de dados](../data-tools/read-xml-data-into-a-dataset.md)|Como trabalhar com XML|

## <a name="tableadapters-overview"></a>Visão geral de TableAdapters
 Os TableAdapters são componentes gerados pelo designer que se conectam a um banco de dados, executam consultas ou procedimentos armazenados e preenchem sua DataTable com os dados retornados. Os TableAdapters também enviam dados atualizados do seu aplicativo de volta para o banco de dados. Você pode executar Quantas consultas desejar em um TableAdapter, desde que elas retornem dados que estejam de acordo com o esquema da tabela com a qual o TableAdapter está associado. O diagrama a seguir mostra como os TableAdapters interagem com bancos de dados e outros objetos na memória:

 ![Fluxo de dados em um aplicativo cliente](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")

 Embora os TableAdapters sejam projetados com o **Designer de conjunto de dados**, as classes do TableAdapter não são geradas como classes aninhadas de <xref:System.Data.DataSet>. Eles estão localizados em namespaces separados que são específicos para cada conjunto de informações. Por exemplo, se você tiver um conjunto de um DataSet chamado `NorthwindDataSet`, os TableAdapters associados a <xref:System.Data.DataTable>s no `NorthwindDataSet` estarão no namespace `NorthwindDataSetTableAdapters`. Para acessar um TableAdapter específico de forma programática, você deve declarar uma nova instância do TableAdapter. Por exemplo:

 [!code-csharp[VbRaddataTableAdapters#7](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Class1.cs#7)]
 [!code-vb[VbRaddataTableAdapters#7](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Class1.vb#7)]

## <a name="associated-datatable-schema"></a>Esquema DataTable associado
 Quando você cria um TableAdapter, usa a consulta inicial ou o procedimento armazenado para definir o esquema do <xref:System.Data.DataTable> associado do TableAdapter. Você executa essa consulta inicial ou procedimento armazenado chamando o método de `Fill` do TableAdapter (que preenche o <xref:System.Data.DataTable> associado do TableAdapter). As alterações feitas na consulta principal do TableAdapter são refletidas no esquema da tabela de dados associada. Por exemplo, remover uma coluna da consulta principal também remove a coluna da tabela de dados associada. Se qualquer consulta adicional no TableAdapter usar instruções SQL que retornam colunas que não estão na consulta principal, o designer tentará sincronizar as alterações de coluna entre a consulta principal e as consultas adicionais. Para obter mais informações, consulte [como: editar TableAdapters](https://msdn.microsoft.com/library/ca178745-e35a-45f1-a395-23cddfd8f855).

## <a name="tableadapter-update-commands"></a>Comandos de atualização do TableAdapter
 A funcionalidade de atualização de um TableAdapter depende da quantidade de informações disponíveis na consulta principal no assistente TableAdapter. Por exemplo, os TableAdapters que são configurados para buscar valores de várias tabelas (junções), valores escalares, exibições ou os resultados de funções de agregação não são criados inicialmente com a capacidade de enviar atualizações de volta para o banco de dados subjacente. No entanto, você pode configurar os comandos INSERT, UPDATE e DELETE manualmente na janela **Propriedades** .

## <a name="tableadapter-queries"></a>consultas TableAdapter
 ![TableAdapter com várias consultas](../data-tools/media/tableadapter.gif "TableAdapter")

 Os TableAdapters podem conter várias consultas para preencher suas tabelas de dados associadas. Você pode definir tantas consultas para um TableAdapter quanto seu aplicativo exigir, desde que cada consulta retorne dados que estejam de acordo com o mesmo esquema da tabela de dados associada. Esse recurso permite que um TableAdapter carregue resultados diferentes com base em diferentes critérios.

 Por exemplo, se seu aplicativo contiver uma tabela com nomes de clientes, você poderá criar uma consulta que preencha a tabela com cada nome de cliente que começa com uma determinada letra e outra que preencha a tabela com todos os clientes que estão localizados no mesmo estado. Para preencher uma tabela de `Customers` com clientes em um determinado Estado, você pode criar uma consulta `FillByState` que usa um parâmetro para o valor de estado da seguinte maneira: `SELECT * FROM Customers WHERE State = @State`. Você executa a consulta chamando o método `FillByState` e passando o valor do parâmetro como este: `CustomerTableAdapter.FillByState("WA")`.

 Além de adicionar consultas que retornam dados do mesmo esquema que a tabela de dados do TableAdapter, você pode adicionar consultas que retornam valores escalares (únicos). Por exemplo, uma consulta que retorna uma contagem de clientes (`SELECT Count(*) From Customers`) é válida para um `CustomersTableAdapter,` mesmo que os dados retornados não estejam de acordo com o esquema da tabela.

## <a name="clearbeforefill-property"></a>Propriedade ClearBeforeFill
 Por padrão, sempre que você executa uma consulta para preencher uma tabela de dados do TableAdapter, os dados existentes são apagados e somente os resultados da consulta são carregados na tabela. Defina a propriedade `ClearBeforeFill` do TableAdapter como `false` se você quiser adicionar ou mesclar os dados retornados de uma consulta para os dados existentes em uma tabela de dados. Independentemente de você limpar os dados, você precisará enviar explicitamente atualizações de volta para o banco de dado, se desejar mantê-los. Portanto, lembre-se de salvar as alterações nos dados na tabela antes de executar outra consulta que preenche a tabela. Para obter mais informações, consulte [atualizar dados usando um TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md).

## <a name="tableadapter-inheritance"></a>Herança do TableAdapter
 Os TableAdapters estendem a funcionalidade de adaptadores de dados padrão encapsulando uma classe de <xref:System.Data.Common.DataAdapter> configurada? qualifyHint = false & AutoUpgrade = true. Por padrão, o TableAdapter herda da classe <xref:System.ComponentModel.Component> e não pode ser convertido na classe <xref:System.Data.Common.DataAdapter>. A conversão de um TableAdapter para a classe de <xref:System.Data.Common.DataAdapter> resulta em um erro de <xref:System.InvalidCastException>? qualifyHint = false & AutoUpgrade = true. Para alterar a classe base de um TableAdapter, você pode digitar uma classe que deriva de <xref:System.ComponentModel.Component> na propriedade da **classe base** do TableAdapter no **Designer de conjunto de dados**.

## <a name="tableadapter-methods-and-properties"></a>Métodos e propriedades do TableAdapter
 A classe TableAdapter não faz parte do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Isso significa que você não pode procurar na documentação ou no **pesquisador de objetos**. Ele é criado em tempo de design quando você usa um dos assistentes mencionados anteriormente. O nome atribuído a um TableAdapter quando você o cria é baseado no nome da tabela com a qual você está trabalhando. Por exemplo, quando você cria um TableAdapter com base em uma tabela em um banco de dados chamado `Orders`, o TableAdapter é denominado `OrdersTableAdapter`. O nome de classe do TableAdapter pode ser alterado usando a propriedade **Name** na **Designer de conjunto de dados**.

 A seguir estão os métodos comumente usados e as propriedades de TableAdapters:

|Membro|Descrição|
|------------|-----------------|
|`TableAdapter.Fill`|Popula a tabela de dados associada do TableAdapter com os resultados do comando SELECT do TableAdapter.|
|`TableAdapter.Update`|Envia as alterações de volta ao banco de dados e retorna um inteiro que representa o número de linhas afetadas pela atualização. Para obter mais informações, consulte [atualizar dados usando um TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md).|
|`TableAdapter.GetData`|Retorna um novo <xref:System.Data.DataTable> que é preenchido com dados.|
|`TableAdapter.Insert`|Cria uma nova linha na tabela de dados. Para obter mais informações, consulte [inserir novos registros em um banco de dados](../data-tools/insert-new-records-into-a-database.md).|
|`TableAdapter.ClearBeforeFill`|Determina se uma tabela de dados é esvaziada antes de chamar um dos métodos `Fill`.|

## <a name="tableadapter-update-method"></a>Método de atualização do TableAdapter
 Os TableAdapters usam comandos de dados para ler e gravar no banco de dado. A consulta `Fill` inicial do TableAdapter (principal) é usada como a base para criar o esquema da tabela de dados associada, bem como os comandos `InsertCommand`, `UpdateCommand` e `DeleteCommand` associados ao método `TableAdapter.Update`. Chamar o método `Update` de um TableAdapter executa as instruções que foram criadas quando o TableAdapter foi originalmente configurado, não uma das consultas adicionais que foi adicionada com o **Assistente de configuração de consulta do TableAdapter**.

 Quando você usa um TableAdapter, ele executa efetivamente as mesmas operações com os comandos que você normalmente executaria. Por exemplo, quando você chama o método de `Fill` do adaptador, o adaptador executa o comando de dados em sua propriedade `SelectCommand` e usa um leitor de dados (por exemplo, <xref:System.Data.SqlClient.SqlDataReader>) para carregar o conjunto de resultados na tabela de dados. Da mesma forma, quando você chama o método de `Update` do adaptador, ele executa o comando apropriado (nas propriedades `UpdateCommand`, `InsertCommand` e `DeleteCommand`) para cada registro alterado na tabela de dados.

> [!NOTE]
> Se houver informações suficientes na consulta principal, os comandos `InsertCommand`, `UpdateCommand` e `DeleteCommand` serão criados por padrão quando o TableAdapter for gerado. Se a consulta principal do TableAdapter for mais do que uma instrução SELECT de tabela única, é possível que o designer não consiga gerar `InsertCommand`, `UpdateCommand` e `DeleteCommand`. Se esses comandos não forem gerados, você poderá receber um erro ao executar o método `TableAdapter.Update`.

## <a name="tableadapter-generatedbdirectmethods"></a>GenerateDbDirectMethods do TableAdapter
 Além de `InsertCommand`, `UpdateCommand` e `DeleteCommand`, os TableAdapters são criados com métodos que podem ser executados diretamente no banco de dados. Esses métodos (`TableAdapter.Insert`, `TableAdapter.Update` e `TableAdapter.Delete`) podem ser chamados diretamente para manipular dados no banco de dado. Isso significa que você pode chamar esses métodos individuais do seu código em vez de chamar `TableAdapter.Update` para lidar com as inserções, atualizações e exclusões que estão pendentes para a tabela de dados associada.

 Se você não quiser criar esses métodos diretos, defina a propriedade **GenerateDBDirectMethods** do TableAdapter como `false` (na janela **Propriedades** ). Consultas adicionais que são adicionadas ao TableAdapter são consultas autônomas — elas não geram esses métodos.

## <a name="tableadapter-support-for-nullable-types"></a>Suporte do TableAdapter para tipos anuláveis
 Os TableAdapters oferecem suporte a tipos anuláveis `Nullable(Of T)` e `T?`. Para obter mais informações sobre tipos que permitem valor nulo no Visual Basic, consulte [Tipos de valores que permitem valor nulo](https://msdn.microsoft.com/library/9ac3b602-6f96-4e6d-96f7-cd4e81c468a6). Para obter mais informações sobre tipos anuláveis no C#, consulte [usando tipos anuláveis](https://msdn.microsoft.com/library/0bacbe72-ce15-4b14-83e1-9c14e6380c28).

## <a name="security"></a>Segurança
 Quando você usa comandos de dados com uma propriedade `CommandType` definida como <xref:System.Data.CommandType>, verifique cuidadosamente as informações enviadas de um cliente antes de passá-las para o banco de dados. Usuários maliciosos podem tentar enviar (injetar) instruções SQL modificadas ou adicionais para obter acesso não autorizado ou para danificar o banco de dados. Antes de transferir a entrada do usuário para um banco de dados, sempre verifique se as informações são válidas. Uma prática recomendada é sempre usar consultas parametrizadas ou procedimentos armazenados quando possível.

## <a name="see-also"></a>Consulte também
 [Ferramentas de conjunto de dados no Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
