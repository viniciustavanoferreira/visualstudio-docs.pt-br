---
title: Criar um Windows Form para pesquisar dados
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms, searching data
- Windows Forms, displaying data
- parameters, displaying filtered data
- data [Visual Studio], parameterizing queries
- data [Visual Studio], searching
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: df6f2245f06a594e35febe07d5aab2d7e83c48fd
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586803"
---
# <a name="create-a-windows-form-to-search-data"></a>Criar um Windows Form para pesquisar dados

Um cenário de aplicativo comum exibirá dados selecionados em um formulário. Por exemplo, você pode querer exibir os pedidos de um cliente específico ou os detalhes de um pedido específico. Nesse cenário, um usuário insere informações em um formulário e uma consulta é executada com a entrada do usuário como parâmetro, ou seja, os dados são selecionados com base em uma consulta parametrizada. A consulta retorna apenas os dados que satisfazem os critérios inseridos pelo usuário. Este passo a passo mostra como criar uma consulta que retorna clientes de uma cidade específica, como mudar a interface do usuário para que os usuários possam inserir o nome de uma cidade e pressionar um botão para executar a consulta.

O uso de consultas parametrizadas ajuda a tornar seu aplicativo eficiente, permitindo que o banco de dados funcione melhor, filtrando registros rapidamente. Por outro lado, se você solicitar uma tabela de banco de dados inteira, transferi-la pela rede e usar a lógica do aplicativo para encontrar os registros que deseja, o aplicativo poderá ficar lento e ineficiente.

Você pode adicionar consultas parametrizadas a qualquer TableAdapter (e controles para aceitar valores de parâmetro e executar a consulta), usando a caixa de diálogo **search criteria Builder** . Abra a caixa de diálogo selecionando o comando **Adicionar Consulta** no menu **Dados** (ou em qualquer marcação inteligente de TableAdapter).

As tarefas ilustradas neste passo a passo incluem:

- Criando e configurando a fonte de dados em seu aplicativo com o assistente de **configuração de fonte de dados** .

- Definindo o tipo de descartação dos itens na janela **fontes de dados** .

- Criar controles que exibem dados arrastando itens da janela **Fontes de Dados** para um formulário.

- Adicionar controles para exibir os dados no formulário.

- Concluindo a caixa de diálogo **Construtor de critérios de pesquisa** .

- Inserindo parâmetros no formulário e executando a consulta parametrizada.

## <a name="prerequisites"></a>{1&gt;{2&gt;Pré-requisitos&lt;2}&lt;1}

Este passo a passos usa SQL Server Express LocalDB e o banco de dados de exemplo Northwind.

1. Se você não tiver SQL Server Express LocalDB, instale-o na [SQL Server Express página de download](https://www.microsoft.com/sql-server/sql-server-editions-express)ou por meio do **instalador do Visual Studio**. No **instalador do Visual Studio**, você pode instalar o SQL Server Express LocalDB como parte da carga de trabalho de **armazenamento e processamento de dados** ou como um componente individual.

2. Instale o banco de dados de exemplo Northwind seguindo estas etapas:

    1. No Visual Studio, abra a janela **pesquisador de objetos do SQL Server** . (O Pesquisador de Objetos do SQL Server é instalado como parte da carga de trabalho de **armazenamento e processamento de dados** no **instalador do Visual Studio**.) Expanda o nó **SQL Server** . Clique com o botão direito do mouse na instância do LocalDB e selecione **nova consulta**.

       Uma janela do editor de consultas é aberta.

    2. Copie o [script do Transact-SQL Northwind](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) para a área de transferência. Esse script T-SQL cria o banco de dados Northwind a partir do zero e o preenche com os mesmos.

    3. Cole o script T-SQL no editor de consultas e, em seguida, escolha o botão **executar** .

       Após um curto período, a consulta terminará de ser executada e o banco de dados Northwind será criado.

## <a name="create-the-windows-forms-application"></a>Criar o aplicativo Windows Forms

Crie um novo projeto de **aplicativo Windows Forms** para C# o ou o Visual Basic. Nomeie o projeto **WindowsSearchForm**.

## <a name="create-the-data-source"></a>Criar a fonte de dados

Esta etapa cria uma fonte de dados por meio de um banco de dados usando o assistente de **Configuração de Fonte de Dados**:

1. Para abrir a janela **fontes de dados** , no menu **dados** , clique em **mostrar fontes de dados**.

2. Na janela **Fontes de Dados**, selecione **Adicionar Nova Fonte de Dados** para iniciar o assistente de **Configuração de Fonte de Dados**.

3. Selecione **Banco de Dados** na página **Escolher um Tipo de Fonte de Dados** e, em seguida, clique em **Avançar**.

4. Na página **Escolha a Conexão de Dados**, faça o seguinte:

    - Se uma conexão de dados com o banco de dados de exemplo Northwind estiver disponível na lista suspensa, selecione-o.

    - Selecione **Nova Conexão** para inicializar a caixa de diálogo **Adicionar/Modificar Conexão**.

5. Se o banco de dados exigir uma senha, selecione a opção para incluir dados confidenciais e, em seguida, clique em **Avançar**.

6. Na página **salvar cadeia de conexão no arquivo de configuração do aplicativo** , clique em **Avançar**.

7. Na página **escolher seus objetos de banco de dados** , expanda o nó **tabelas** .

8. Selecione a tabela **Clientes** e clique em **Concluir**.

     O **NorthwindDataSet** é adicionado ao seu projeto e a tabela **Clientes** aparece na janela **Fontes de Dados**.

## <a name="create-the-form"></a>Criar o formulário

Você pode criar controles de associação de dados arrastando itens da janela **Fontes de Dados** para um formulário:

1. Expanda o nó **Clientes** na janela **Fontes de Dados**.

2. Arraste o nó **Clientes** da janela **Fontes de Dados** para o formulário.

     Um <xref:System.Windows.Forms.DataGridView> e uma faixa de ferramentas (<xref:System.Windows.Forms.BindingNavigator>) para navegação em registros são exibidos no formulário. Um [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource> e <xref:System.Windows.Forms.BindingNavigator> são exibidos na bandeja de componentes.

## <a name="add-parameterization-search-functionality-to-the-query"></a>Adicionar parametrização (funcionalidade de pesquisa) à consulta

Você pode adicionar uma cláusula WHERE à consulta original usando a caixa de diálogo **search criteria Builder** :

1. Selecione o controle <xref:System.Windows.Forms.DataGridView> e escolha **Adicionar Consulta** no menu **Dados**.

2. Digite **FillByCity** na nova área de **nome de consulta** na caixa de diálogo Construtor de **critérios de pesquisa** .

3. Adicione `WHERE City = @City` à consulta na área **Texto da Consulta**.

     A consulta deve ser semelhante ao seguinte:

     ```sql
     SELECT CustomerID, CompanyName, ContactName, ContactTitle,
          Address, City, Region, PostalCode, Country, Phone, Fax
     FROM Customers
     WHERE City = @City
     ```

    > [!NOTE]
    > As fontes de dados Access e OLE DB usam o ponto de interrogação ('? ') para denotar parâmetros, portanto, a cláusula WHERE ficaria assim: `WHERE City = ?`.

4. Clique em **OK** para fechar a caixa de diálogo **Construtor de Critérios de Pesquisa**.

     Um **FillByCityToolStrip** é adicionado ao formulário.

## <a name="test-the-application"></a>Testar o aplicativo

Executar o aplicativo abre o formulário e o torna pronto para pegar o parâmetro como entrada:

1. Pressione **F5** para executar o aplicativo.

2. Digite **Londres** na caixa de texto **Cidade** e clique em **FillByCity**.

     A grade de dados é populada com clientes que atendem aos critérios. Neste exemplo, a grade de dados exibe os clientes que têm o valor **Londres** na coluna **Cidade**.

## <a name="next-steps"></a>{1&gt;{2&gt;Próximas etapas&lt;2}&lt;1}

Dependendo dos requisitos de aplicativo, existem várias etapas que você talvez queira realizar após criar um formulário parametrizado. Entre algumas das melhorias que você poderia fazer nessa explicação passo a passo estão:

- Adicionar controles que exibem dados relacionados. Para obter mais informações, consulte [relações em conjuntos de](relationships-in-datasets.md)dados.

- Editando o conjunto de dados para adicionar ou remover objetos de banco de dados. Para obter mais informações, consulte [Create and configure datasets (Criar e configurar conjuntos de dados)](../data-tools/create-and-configure-datasets-in-visual-studio.md).

## <a name="see-also"></a>Veja também

- [Associando controles do Windows Forms a dados no Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
