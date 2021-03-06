---
title: Consultar conjuntos de dados
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 7b1a91cf-8b5a-4fc0-ac36-0dc2d336fa1b
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 4080866de58e17c5e11ed01d61740c2f83aed9a7
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586335"
---
# <a name="query-datasets"></a>Consultar conjuntos de dados
Para pesquisar registros específicos em um conjunto de informações, use o método `FindBy` na DataTable, escreva sua própria instrução foreach para executar um loop sobre a coleção de linhas da tabela ou use [LINQ to DataSet](/dotnet/framework/data/adonet/linq-to-dataset).

## <a name="dataset-case-sensitivity"></a>Diferenciação de maiúsculas e minúsculas
Em um conjunto de dados, os nomes de tabela e coluna não diferenciam maiúsculas de minúsculas por padrão — ou seja, uma tabela em um conjunto de dados chamada "Customers" também pode ser referida como "Customers". Isso corresponde às convenções de nomenclatura em muitos bancos de dados, incluindo SQL Server. No SQL Server, o comportamento padrão é que os nomes dos elementos de dados não podem ser diferenciados somente por maiúsculas e minúsculas.

> [!NOTE]
> Ao contrário dos conjuntos de dados, os documentos XML diferenciam maiúsculas de minúsculas e, portanto, os nomes dos elementos de dado definidos em esquemas diferenciam maiúsculas de minúsculas. Por exemplo, o protocolo de esquema permite que o esquema defina uma tabela chamada "Customers" e uma tabela diferente chamada "Customers". Isso pode resultar em colisões de nome quando um esquema que contém elementos que diferem somente por maiúsculas e minúsculas é usado para gerar uma classe de conjunto de resultados.

No entanto, a diferenciação de maiúsculas e minúsculas pode ser um fator em como os dados são interpretados no DataSet. Por exemplo, se você filtrar dados em uma tabela de DataSet, os critérios de pesquisa poderão retornar resultados diferentes, dependendo se a comparação diferencia maiúsculas de minúsculas. Você pode controlar a diferenciação de maiúsculas e minúsculas de filtragem, pesquisa e classificação definindo a propriedade de <xref:System.Data.DataSet.CaseSensitive%2A> do conjunto de propriedades. Todas as tabelas no conjunto de um DataSet herdam o valor dessa propriedade por padrão. (Você pode substituir essa propriedade para cada tabela individual definindo a propriedade de <xref:System.Data.DataTable.CaseSensitive%2A> da tabela.)

## <a name="locate-a-specific-row-in-a-data-table"></a>Localizar uma linha específica em uma tabela de dados

#### <a name="to-find-a-row-in-a-typed-dataset-with-a-primary-key-value"></a>Para localizar uma linha em um dataset tipado com um valor de chave primária

- Para localizar uma linha, chame o método de `FindBy` fortemente tipado que usa a chave primária da tabela.

     No exemplo a seguir, a coluna `CustomerID` é a chave primária da tabela `Customers`. Isso significa que o método `FindBy` gerado é `FindByCustomerID`. O exemplo mostra como atribuir um <xref:System.Data.DataRow> específico a uma variável usando o método `FindBy` gerado.

     [!code-csharp[VbRaddataEditing#18](../data-tools/codesnippet/CSharp/query-datasets_1.cs)]
     [!code-vb[VbRaddataEditing#18](../data-tools/codesnippet/VisualBasic/query-datasets_1.vb)]

#### <a name="to-find-a-row-in-an-untyped-dataset-with-a-primary-key-value"></a>Para localizar uma linha em um conjunto de um DataSet não tipado com um valor de chave primária

- Chame o método <xref:System.Data.DataRowCollection.Find%2A> de uma coleção de <xref:System.Data.DataRowCollection>, passando a chave primária como um parâmetro.

     O exemplo a seguir mostra como declarar uma nova linha chamada `foundRow` e atribuir a ela o valor de retorno do método <xref:System.Data.DataRowCollection.Find%2A>. Se a chave primária for encontrada, o conteúdo do índice de coluna 1 será exibido em uma caixa de mensagem.

     [!code-csharp[VbRaddataEditing#19](../data-tools/codesnippet/CSharp/query-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#19](../data-tools/codesnippet/VisualBasic/query-datasets_2.vb)]

## <a name="find-rows-by-column-values"></a>Localizar linhas por valores de coluna

#### <a name="to-find-rows-based-on-the-values-in-any-column"></a>Para localizar linhas com base nos valores de qualquer coluna

- As tabelas de dados são criadas com o método <xref:System.Data.DataTable.Select%2A>, que retorna uma matriz de <xref:System.Data.DataRow>s com base na expressão passada para o método <xref:System.Data.DataTable.Select%2A>. Para obter mais informações sobre como criar expressões válidas, consulte a seção "sintaxe de expressão" da página sobre a propriedade <xref:System.Data.DataColumn.Expression%2A>.

     O exemplo a seguir mostra como usar o método <xref:System.Data.DataTable.Select%2A> da <xref:System.Data.DataTable> para localizar linhas específicas.

     [!code-csharp[VbRaddataEditing#20](../data-tools/codesnippet/CSharp/query-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#20](../data-tools/codesnippet/VisualBasic/query-datasets_3.vb)]

## <a name="access-related-records"></a>Acessar registros relacionados
Quando as tabelas em um conjunto de registros estão relacionadas, um objeto <xref:System.Data.DataRelation> pode tornar os registros relacionados disponíveis em outra tabela. Por exemplo, um conjunto de um DataSet contendo `Customers` e `Orders` tabelas podem ser disponibilizados.

Você pode usar um objeto <xref:System.Data.DataRelation> para localizar registros relacionados chamando o método <xref:System.Data.DataRow.GetChildRows%2A> de um <xref:System.Data.DataRow> na tabela pai. Esse método retorna uma matriz de registros filho relacionados. Ou, você pode chamar o método <xref:System.Data.DataRow.GetParentRow%2A> de um <xref:System.Data.DataRow> na tabela filho. Esse método retorna uma única <xref:System.Data.DataRow> da tabela pai.

Esta página fornece exemplos usando datasets tipados. Para obter informações sobre como navegar em relações em conjuntos de dados não tipados, consulte [navegando em DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations).

> [!NOTE]
> Se você estiver trabalhando em um aplicativo Windows Forms e usando os recursos de vinculação de dados para exibir dados, o formulário gerado pelo designer poderá fornecer funcionalidade suficiente para seu aplicativo. Para obter mais informações, confira [Associar controles a dados no Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md). Especificamente, consulte [relações em conjuntos de](relationships-in-datasets.md)os.

Os exemplos de código a seguir demonstram como navegar pelas relações para cima e para baixo em conjuntos de valores tipados. Os exemplos de código usam <xref:System.Data.DataRow>s tipados (`NorthwindDataSet.OrdersRow`) e os métodos de*PrimaryKey* (`FindByCustomerID`) de FindBy gerados para localizar uma linha desejada e retornar os registros relacionados. Os exemplos são compilados e executados corretamente somente se você tiver:

- Uma instância de um conjunto de uma chamada `NorthwindDataSet` com uma tabela `Customers`.

- Uma tabela `Orders`.

- Uma relação chamada `FK_Orders_Customers`relacionando as duas tabelas.

Além disso, ambas as tabelas precisam ser preenchidas com dados para que todos os registros sejam retornados.

#### <a name="to-return-the-child-records-of-a-selected-parent-record"></a>Para retornar os registros filho de um registro pai selecionado

- Chame o método <xref:System.Data.DataRow.GetChildRows%2A> de uma linha de dados de `Customers` específica e retorne uma matriz de linhas da tabela `Orders`:

     [!code-csharp[VbRaddataDatasets#6](../data-tools/codesnippet/CSharp/query-datasets_4.cs)]
     [!code-vb[VbRaddataDatasets#6](../data-tools/codesnippet/VisualBasic/query-datasets_4.vb)]

#### <a name="to-return-the-parent-record-of-a-selected-child-record"></a>Para retornar o registro pai de um registro filho selecionado

- Chame o método <xref:System.Data.DataRow.GetParentRow%2A> de uma linha de dados de `Orders` específica e retorne uma única linha da tabela `Customers`:

     [!code-csharp[VbRaddataDatasets#7](../data-tools/codesnippet/CSharp/query-datasets_5.cs)]
     [!code-vb[VbRaddataDatasets#7](../data-tools/codesnippet/VisualBasic/query-datasets_5.vb)]

## <a name="see-also"></a>Veja também

- [Ferramentas de conjunto de dados no Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
