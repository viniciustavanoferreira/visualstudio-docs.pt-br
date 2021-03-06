---
title: 'Instruções passo a passo: criando um aplicativo de dados de N camadas'
ms.date: 09/08/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: a88f0382a93027cc952dfe44f0027e6ab1076a45
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75916502"
---
# <a name="walkthrough-create-an-n-tier-data-application"></a>Walkthrough: criar um aplicativo de dados de n camadas
Os aplicativos de dados de *N camadas* são aplicativos que acessam dados e são separados em várias *camadas* lógicas. A separação de componentes de aplicativos em camadas discretas aumenta a capacidade de manutenção e a escalabilidade do aplicativo. Isso é feito pela adoção com mais facilidade de novas tecnologias que podem ser aplicadas a uma única camada, sem precisar reprojetar toda a solução. A arquitetura de N camadas inclui uma camada de apresentação, uma camada intermediária e uma camada de dados. A camada intermediária geralmente inclui uma camada de acesso a dados, uma camada lógica de negócios e componentes compartilhados, tais como autenticação e validação. A camada de dados inclui um banco de dados relacional. Os aplicativos de N camadas geralmente armazenam informações confidenciais na camada de acesso a dados da camada intermediária para manter o isolamento de usuários finais que acessam a camada de apresentação. Para obter mais informações, consulte [visão geral de aplicativos de dados de N camadas](../data-tools/n-tier-data-applications-overview.md).

Uma maneira de separar as várias camadas em um aplicativo de N camadas é criar projetos discretos para cada camada que você deseja incluir em seu aplicativo. Os conjuntos de dados digitados contêm uma propriedade `DataSet Project` que determina quais projetos o conjunto de dados gerado e o código `TableAdapter` devem acessar.

Esse passo a passo demonstra como separar o conjunto de dados e o código `TableAdapter` em projetos de biblioteca de classes discretas usando o **Designer de Conjunto de Dados**. Depois de separar o conjunto de dados e o código do TableAdapter, você cria um [Windows Communication Foundation serviços e WCF Data Services no serviço do Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) para chamar a camada de acesso a dados. Por fim, você cria um aplicativo Windows Forms como a camada de apresentação. Essa camada acessa dados do serviço de dados.

Durante este passo a passos, você executa as seguintes etapas:

- Crie uma nova solução de n camadas que contenha vários projetos.

- Adicionar dois projetos de bibliotecas de classes na solução de N camadas.

- Criar um conjunto de dados tipado usando o **Assistente de Configuração de Fonte de Dados**.

- Separe os [TableAdapters](create-and-configure-tableadapters.md) gerados e o código do DataSet em projetos discretos.

- Criar um serviço do Windows Communication Foundation (WCF) a ser chamado na camada de acesso a dados.

- Criar funções no serviço para recuperar dados da camada de acesso a dados.

- Criar um aplicativo do Windows Forms para servir como a camada de apresentação.

- Criar controles do Windows Forms associados à fonte de dados.

- Gravar código para preencher as tabelas de dados.

![link para vídeo](../data-tools/media/playvideo.gif) para uma versão em vídeo deste tópico, consulte [vídeo de instruções: Criando um aplicativo de dados de N camadas](/previous-versions/visualstudio/visual-studio-2008/cc178916(v=vs.90)).

## <a name="prerequisites"></a>{1&gt;{2&gt;Pré-requisitos&lt;2}&lt;1}
Este passo a passos usa SQL Server Express LocalDB e o banco de dados de exemplo Northwind.

1. Se você não tiver SQL Server Express LocalDB, instale-o na [SQL Server Express página de download](https://www.microsoft.com/sql-server/sql-server-editions-express)ou por meio do **instalador do Visual Studio**. No **instalador do Visual Studio**, você pode instalar o SQL Server Express o LocalDB como parte da carga de **trabalho de desenvolvimento da desktop .net** ou como um componente individual.

2. Instale o banco de dados de exemplo Northwind seguindo estas etapas:

    1. No Visual Studio, abra a janela **pesquisador de objetos do SQL Server** . (O**pesquisador de objetos do SQL Server** é instalado como parte da carga de trabalho de **armazenamento e processamento de dados** no instalador do Visual Studio.) Expanda o nó **SQL Server** . Clique com o botão direito do mouse na instância do LocalDB e selecione **nova consulta**.

       Uma janela do editor de consultas é aberta.

    2. Copie o [script do Transact-SQL Northwind](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) para a área de transferência. Esse script T-SQL cria o banco de dados Northwind a partir do zero e o preenche com os mesmos.

    3. Cole o script T-SQL no editor de consultas e, em seguida, escolha o botão **executar** .

       Após um curto período, a consulta terminará de ser executada e o banco de dados Northwind será criado.

## <a name="create-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>Criar a solução de n camadas e a biblioteca de classes para armazenar o conjunto de os (DataEntityTier)
A primeira etapa deste passo a passo é criar uma solução e dois projetos de biblioteca de classes. A primeira biblioteca de classes contém o conjunto de dados (a classe de `DataSet` de tipos gerada e as tabelas de tabela que mantêm o aplicativo). Este projeto é usado como a camada de entidade de dados do aplicativo e geralmente está localizada na camada intermediária. O conjunto de os cria o conjunto de um DataSet inicial e separa automaticamente o código nas duas bibliotecas de classes.

> [!NOTE]
> Dê o nome correto ao projeto e à solução antes de clicar em **OK**. Isso facilitará a conclusão deste passo a passo.

### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>Para criar a solução de N camadas e a biblioteca de classes DataEntityTier

1. No Visual Studio, no menu **Arquivo**, selecione **Novo** > **Projeto**.

2. Expanda **o C# Visual** ou **Visual Basic** no painel esquerdo e, em seguida, selecione **área de trabalho do Windows**.

3. No painel central, selecione o tipo de projeto **biblioteca de classes** .

4. Nomeie o projeto como **DataEntityTier**.

5. Nomeie a solução **NTierWalkthrough**e escolha **OK**.

     Uma solução NTierWalkthrough que contém o projeto DataEntityTier é criada e adicionada ao **Gerenciador de Soluções**.

## <a name="create-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>Create the class library to hold the TableAdapters (DataAccessTier)
A próxima etapa após a criação do projeto DataEntityTier é criar outro projeto de biblioteca de classes. This project holds the generated TableAdapters and is called the *data access tier* of the application. A camada de acesso a dados contém as informações necessárias para se conectar ao banco de dados e geralmente está localizada na camada intermediária.

### <a name="to-create-a-separate-class-library-for-the-tableadapters"></a>To create a separate class library for the TableAdapters

1. Clique com o botão direito do mouse na solução no **Gerenciador de Soluções** e escolha **Adicionar** > **Novo Projeto**.

2. In the **New Project** dialog box, in the middle pane, select **Class Library**.

3. Name the project **DataAccessTier** and choose **OK**.

     O projeto DataAccessTier é criado e adicionado à solução NTierWalkthrough.

## <a name="create-the-dataset"></a>Create the Dataset
A próxima etapa é criar um conjunto de dados tipado. Typed datasets are created with both the dataset class (including `DataTables` classes) and the `TableAdapter` classes in a single project. (All classes are generated into a single file.) When you separate the dataset and TableAdapters into different projects, it is the dataset class that is moved to the other project, leaving the `TableAdapter` classes in the original project. Therefore, create the dataset in the project that will ultimately contain the TableAdapters (the DataAccessTier project). You create the dataset by using the **Data Source Configuration Wizard**.

> [!NOTE]
> É preciso ter acesso ao banco de dados de exemplo Northwind para criar a conexão. For information about how to set up the Northwind sample database, see [How to: Install sample databases](../data-tools/installing-database-systems-tools-and-samples.md).

### <a name="to-create-the-dataset"></a>Para criar o conjunto de dados

1. Select the **DataAccessTier** in **Solution Explorer**.

2. On the **Data** menu, select **Show Data Sources**.

   A janela **Fontes de Dados** é aberta.

3. Na janela **Fontes de Dados**, selecione **Adicionar Nova Fonte de Dados** para iniciar o **Assistente de Configuração de Fonte de Dados**.

4. On the **Choose a Data Source Type** page, select **Database** and then select **Next**.

5. Na página **Escolha a Conexão de Dados**, execute uma das seguintes ações:

     Se uma conexão de dados com o banco de dados de exemplo Northwind estiver disponível na lista suspensa, selecione-o.

     - ou -

     Select **New Connection** to open the **Add Connection** dialog box.

6. If the database requires a password, select the option to include sensitive data, and then choose **Next**.

    > [!NOTE]
    > Se você escolheu um arquivo do banco de dados local (em vez de se conectar ao SQL Server), talvez seja perguntado se deseja adicionar o arquivo ao projeto. Choose **Yes** to add the database file to the project.

7. Select **Next** on the **Save the Connection String to the Application Configuration File** page.

8. Expanda o nó **Tabelas** na página **Escolher Objetos do Banco de Dados**.

9. Select the check boxes for the **Customers** and **Orders** tables, and then choose **Finish**.

     NorthwindDataSet é adicionado ao projeto DataAccessTier e aparece na janela **Fontes de Dados**.

## <a name="separate-the-tableadapters-from-the-dataset"></a>Separate the TableAdapters from the Dataset
Depois de criar o conjunto de dados, separe a classe do conjunto de dados gerada a partir dos TableAdapters. Você faz isso ao configurar a propriedade **Projeto do Conjunto de Dados** para o nome do projeto que armazenará a classe do conjunto de dados separada.

### <a name="to-separate-the-tableadapters-from-the-dataset"></a>Para separar os TableAdapters do Conjunto de Dados

1. Clique duas vezes em **NorthwindDataSet.xsd** no **Gerenciador de Soluções** para abrir o conjunto de dados no **Designer de Conjunto de Dados**.

2. Select an empty area on the designer.

3. Localize o nó **Projeto do Conjunto de Dados** na janela **Propriedades**.

4. In the **DataSet Project** list, select **DataEntityTier**.

5. No menu **Build**, selecione **Compilar Solução**.

   O conjunto de dados e os TableAdapters são separados em dois projetos de biblioteca de classes. The project that originally contained the whole dataset (`DataAccessTier`) now contains only the TableAdapters. The project designated in the **DataSet Project** property (`DataEntityTier`) contains the typed dataset: *NorthwindDataSet.Dataset.Designer.vb* (or *NorthwindDataSet.Dataset.Designer.cs*).

> [!NOTE]
> Quando você separa os conjuntos de dados e os TableAdapters (configurando a propriedade **Projeto de Conjunto de Dados**), as classes dos conjuntos de dados parciais existentes no projeto não são movidas automaticamente. As classes parciais do conjunto de dados existentes devem ser movidas manualmente para o projeto do conjunto de dados.

## <a name="create-a-new-service-application"></a>Create a New Service Application
This walkthrough demonstrates how to access the data access tier by using a WCF service, so let's create a new WCF service application.

### <a name="to-create-a-new-wcf-service-application"></a>Para criar um novo aplicativo de Serviço WCF

1. Clique com o botão direito do mouse na solução no **Gerenciador de Soluções** e escolha **Adicionar** > **Novo Projeto**.

2. In the **New Project** dialog box, in the left-hand pane, select **WCF**. In the middle pane, select **WCF Service Library**.

3. Name the project **DataService** and select **OK**.

     O projeto DataService é criado e adicionado à solução NTierWalkthrough.

## <a name="create-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>Create methods in the data access tier to return the customers and orders data
The data service has to call two methods in the data access tier: `GetCustomers` and `GetOrders`. These methods return the Northwind `Customers` and `Orders` tables. Create the `GetCustomers` and `GetOrders` methods in the `DataAccessTier` project.

### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>Para criar um método na camada de acesso a dados que retorna a tabela Clientes

1. In **Solution Explorer**, double-click **NorthwindDataset.xsd** to open the dataset.

2. Right-click **CustomersTableAdapter** and click **Add Query**.

3. Na página **Escolher um Tipo de Comando**, mantenha o valor padrão de **Usar instruções SQL** e clique em **Próximo**.

4. Na página **Escolher um Tipo de Consulta**, mantenha o valor padrão de **SELECT que retorna linhas** e clique em **Próximo**.

5. Na página **Especificar uma instrução SQL SELECT**, mantenha a consulta padrão e clique em **Próximo**.

6. Na página **Escolher Métodos a Serem Gerados**, digite **GetCustomers** para o **Nome do método** na seção **Retornar uma DataTable**.

7. Clique em **Finalizar**.

### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>Para criar um método na camada de acesso a dados que retorna a tabela Pedidos

1. Clique com o botão direito do mouse em **OrdersTableAdapter** e clique em **Adicionar Consulta**.

2. Na página **Escolher um Tipo de Comando**, mantenha o valor padrão de **Usar instruções SQL** e clique em **Próximo**.

3. Na página **Escolher um Tipo de Consulta**, mantenha o valor padrão de **SELECT que retorna linhas** e clique em **Próximo**.

4. Na página **Especificar uma instrução SQL SELECT**, mantenha a consulta padrão e clique em **Próximo**.

5. Na página **Escolher Métodos a Serem Gerados**, digite **GetOrders** para o **Nome do método** na seção **Retornar uma DataTable**.

6. Clique em **Finalizar**.

7. No menu **Compilar**, clique em **Compilar Solução**.

## <a name="add-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>Add a reference to the data entity and data access tiers to the data service
Como o serviço de dados requer informações do conjunto de dados e dos TableAdapters, adicione referências aos projetos **DataEntityTier** e **DataAccessTier**.

### <a name="to-add-references-to-the-data-service"></a>Para adicionar referência aos serviço de dados

1. Clique com o botão direito do mouse em **DataService** no **Gerenciador de Soluções** e clique em **Adicionar Referência**.

2. Clique na guia **Projetos** na caixa de diálogo **Adicionar Referência**.

3. Escolha os projetos **DataAccessTier** e **DataEntityTier**.

4. Clique em **OK**.

## <a name="add-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>Add functions to the service to call the GetCustomers and GetOrders methods in the data access tier
Agora que a camada de acesso a dados contém os métodos para retornar dados, crie métodos no serviço de dados para chamar os métodos na camada de acesso a dados.

> [!NOTE]
> Para projetos C#, adicione uma referência ao assembly `System.Data.DataSetExtensions` para que o código a seguir seja compilado.

### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>Para criar as funções GetCustomers e GetOrders no serviço de dados

1. No projeto **DataService**, clique duas vezes em **IService1.vb** ou **IService1.cs**.

2. Adicione o seguinte código no comentário **Adicionar suas operações de serviço aqui**:

    ```vb
    <OperationContract()> _
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable

    <OperationContract()> _
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable
    ```

    ```csharp
    [OperationContract]
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();

    [OperationContract]
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();
    ```

3. No projeto DataService, clique duas vezes em **Service1.vb** (ou **Service1.cs**).

4. Adicione o seguinte código à classe **Service1**:

    ```vb
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
        Return CustomersTableAdapter1.GetCustomers()
    End Function

    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
        Return OrdersTableAdapter1.GetOrders()
    End Function
    ```

    ```csharp
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
             CustomersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();
        return CustomersTableAdapter1.GetCustomers();
    }
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
             OrdersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();
        return OrdersTableAdapter1.GetOrders();
    }
    ```

5. No menu **Compilar**, clique em **Compilar Solução**.

## <a name="create-a-presentation-tier-to-display-data-from-the-data-service"></a>Create a presentation tier to display data from the data service
Now that the solution contains the data service that has methods, which call into the data access tier, create another project that calls into the data service and present the data to users. Neste passo a passo, crie um aplicativo do Windows Forms, o qual será a camada de apresentação do aplicativo de N camadas.

### <a name="to-create-the-presentation-tier-project"></a>Para criar o projeto da camada de apresentação

1. Clique com o botão direito do mouse na solução no **Gerenciador de Soluções** e escolha **Adicionar** > **Novo Projeto**.

2. In the **New Project** dialog box, in the left-hand pane, select **Windows Desktop**. In the middle pane, select **Windows Forms App**.

3. Nomeie o projeto como **PresentationTier** e clique em **OK**.

    O projeto PresentationTier é criado e adicionado à solução NTierWalkthrough.

## <a name="set-the-presentationtier-project-as-the-startup-project"></a>Set the PresentationTier project as the startup project
Vamos definir o projeto **PresentationTier** como o projeto de inicialização para a solução, porque ele é o aplicativo cliente real que apresenta e interage com os dados.

### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>Para configurar o novo projeto de camada de apresentação como o projeto de inicialização

- Em **Gerenciador de Soluções**, clique com o botão direito do mouse em **PresentationTier** e clique em **Definir como Projeto de Inicialização**.

## <a name="add-references-to-the-presentation-tier"></a>Adicionar referências à camada de apresentação
O aplicativo cliente PresentationTier requer uma referência de serviço para o serviço de dados para acessar os métodos no serviço. Além disso, uma referência ao conjunto de dados é necessária para permitir o compartilhamento de tipos pelo serviço WCF. Até que você habilite o compartilhamento de tipo por meio do serviço de dados, o código adicionado à classe de DataSet parcial não estará disponível para a camada de apresentação. Como você normalmente adiciona código, como código de validação para os eventos de alteração de linha e coluna de uma tabela de dados, é provável que você queira acessar esse código do cliente.

### <a name="to-add-a-reference-to-the-presentation-tier"></a>Para adicionar uma referência à camada de apresentação

1. Em **Gerenciador de soluções**, clique com o botão direito do mouse em **PresentationTier** e selecione **Adicionar referência**.

2. Na caixa de diálogo **Adicionar referência** , selecione a guia **projetos** .

3. Selecione **DataEntityTier** e escolha **OK**.

### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>Para adicionar uma referência de serviço à camada de apresentação

1. Em **Gerenciador de soluções**, clique com o botão direito do mouse em **PresentationTier** e selecione **Adicionar referência de serviço**.

2. Na caixa de diálogo **Adicionar referência de serviço** , selecione **descobrir**.

3. Selecione **Service1** e escolha **OK**.

    > [!NOTE]
    > Se você tiver vários serviços no computador atual, selecione o serviço que você criou anteriormente neste passo a passos (o serviço que contém os métodos `GetCustomers` e `GetOrders`).

## <a name="add-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>Adicione DataGridViews ao formulário para exibir os dados retornados pelo serviço de dados
Depois de adicionar a referência de serviço ao serviço de dados, a janela **Fontes de Dados** é preenchida automaticamente com os dados retornados pelo serviço.

### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>Para adicionar duas associações de dados DataGridViews ao formulário

1. No **Gerenciador de Soluções**, escolha o projeto **PresentationTier**.

2. Na janela **Fontes de Dados**, expanda **NorthwindDataSet** e localize o nó **Clientes**.

3. Arraste o nó **Clientes** para Form1.

4. Na janela **Fontes de Dados**, expanda o nó **Clientes** e localize o nó **Pedidos** relacionado (o nó **Pedidos** aninhado no nó **Clientes**).

5. Arraste o nó **Pedidos** relacionado para Form1.

6. Crie um manipulador de eventos `Form1_Load` ao clicar duas vezes em uma área vazia do formulário.

7. Adicione o seguinte código ao manipulador de eventos do `Form1_Load`.

    ```vb
    Dim DataSvc As New ServiceReference1.Service1Client
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)
    ```

    ```csharp
    ServiceReference1.Service1Client DataSvc =
        new ServiceReference1.Service1Client();
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());
    ```

## <a name="increase-the-maximum-message-size-allowed-by-the-service"></a>Aumentar o tamanho máximo de mensagem permitido pelo serviço
O valor padrão para `maxReceivedMessageSize` não é grande o suficiente para manter os dados recuperados das tabelas `Customers` e `Orders`. Nas etapas a seguir, você aumentará o valor para 6553600. Você altera o valor no cliente, que atualiza automaticamente a referência de serviço.

> [!NOTE]
> O menor tamanho padrão se destina a limitar a exposição para ataques de negação de serviço (DoS). Para obter mais informações, consulte <xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>.

### <a name="to-increase-the-maxreceivedmessagesize-value"></a>Para aumentar o valor maxReceivedMessageSize

1. No **Gerenciador de Soluções**, clique duas vezes no arquivo **app.config** no projeto **PresentationTier**.

2. Encontre o atributo de tamanho **maxReceivedMessage** e altere o valor para `6553600`.

## <a name="test-the-application"></a>Testar o aplicativo
Execute o aplicativo pressionando **F5**. Os dados das tabelas `Customers` e `Orders` são recuperados do serviço de dados e exibidos no formulário.

## <a name="next-steps"></a>{1&gt;{2&gt;Próximas etapas&lt;2}&lt;1}
Dependendo dos requisitos do aplicativo, existem várias etapas que você talvez queira realizar após salvar os dados relacionados no aplicativo baseado em Windows. Por exemplo, você poderia fazer as seguintes melhorias a este aplicativo:

- Adicionar validação ao conjunto de dados.

- Adicionar métodos adicionais ao serviço para atualizar dados novamente no banco de dados.

## <a name="see-also"></a>Veja também

- [Trabalhando com conjuntos de dados em aplicativos de N camadas](../data-tools/work-with-datasets-in-n-tier-applications.md)
- [Atualização hierárquica](../data-tools/hierarchical-update.md)
- [Acessando dados no Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
