---
title: Criando uma linguagem específica de domínio baseada em Windows Forms | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 452318ff-8ecf-46d0-8ca0-4013d0cdafaf
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cea3b76575e1da2e846e230580c6cfa50ef9b207
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651273"
---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Criando uma linguagem específica do domínio baseada no Windows Forms
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode usar Windows Forms para exibir o estado de um modelo de DSL (linguagem específica de domínio), em vez de usar um diagrama DSL. Este tópico orienta você pela Associação de um formulário do Windows a uma DSL, usando o [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] visualização e o SDK de modelagem.

 ![&#45;WPF&#45;de DSL 2](../modeling/media/dsl-wpf-2.png "DSL-WPF-2") Uma instância de DSL, mostrando uma interface do usuário do Windows Form e o Gerenciador de modelos.

## <a name="creating-a-windows-forms-dsl"></a>Criando um Windows Forms DSL
 O modelo DSL **mínimo do WinForm designer** cria uma DSL mínima que você pode modificar de acordo com seus próprios requisitos.

#### <a name="to-create-a-minimal-winforms-dsl"></a>Para criar uma DSL mínima do WinForms

1. Crie uma DSL a partir do modelo de **designer do WinForm mínimo** .

    Neste tutorial, os seguintes nomes são assumidos:

   |                       |                 |
   |-----------------------|-----------------|
   | Nome da solução e DSL |     FarmApp     |
   |       espaço de nome       | Company. FarmApp |

2. Experimente o exemplo inicial que o modelo fornece:

   1. Transforme todos os modelos.

   2. Compile e execute o exemplo (**Ctrl + F5**).

   3. Na instância experimental do Visual Studio, abra o arquivo `Sample` no projeto de depuração.

        Observe que ele é exibido em um controle de Windows Forms.

        Você também pode ver os elementos do modelo exibidos no Gerenciador.

        Adicione alguns elementos no formulário ou no Gerenciador e observe que eles aparecem na outra exibição.

   Na instância principal do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], observe os seguintes pontos sobre a solução de DSL:

- `DslDefinition.dsl` não contém elementos de diagrama. Isso ocorre porque você não usará diagramas de DSL para exibir modelos de instância dessa DSL. Em vez disso, você associará um formulário do Windows ao modelo e os elementos no formulário exibirão o modelo.

- Além dos projetos `Dsl` e `DslPackage`, a solução contém um terceiro projeto chamado `UI.` projeto de**interface do usuário** contém a definição de um controle de Windows Forms. `DslPackage` depende `UI` e `UI` depende `Dsl`.

- No projeto `DslPackage`, `UI\DocView.cs` contém o código que exibe o controle de Windows Forms que é definido no projeto `UI`.

- O projeto `UI` contém um exemplo funcional de um controle de formulário associado à DSL. No entanto, ele não funcionará quando você tiver alterado a definição de DSL. O projeto `UI` contém:

  - Uma classe de Windows Forms chamada `ModelViewControl`.

  - Um arquivo chamado `DataBinding.cs` que contém uma definição parcial adicional de `ModelViewControl`. Para ver seu conteúdo, em **Gerenciador de soluções**, abra o menu de atalho para o arquivo e escolha **Exibir código**.

### <a name="about-the-ui-project"></a>Sobre o projeto de interface do usuário
 Ao atualizar o arquivo de definição de DSL para definir sua própria DSL, você precisará atualizar o controle no projeto `UI` para exibir sua DSL. Ao contrário dos projetos `Dsl` e `DslPackage`, o projeto de `UI` de exemplo não é gerado do `DslDefinitionl.dsl`. Você pode adicionar arquivos. tt para gerar o código, se desejar, embora isso não seja abordado neste passo a passos.

## <a name="updating-the-dsl-definition"></a>Atualizando a definição de DSL
 A definição de DSL a seguir é usada neste passo a passos.

 ![WPF&#45;&#45;de DSL 1](../modeling/media/dsl-wpf-1.png "DSL-WPF-1")

#### <a name="to-update-the-dsl-definition"></a>Para atualizar a definição de DSL

1. Abra DslDefinition. DSL no designer de DSL.

2. Excluir o **exemploelement**

3. Renomeie a classe de domínio **ExampleModel** para `Farm`.

     Forneça as propriedades de domínio adicionais chamadas `Size` do tipo **Int32**e `IsOrganic` do tipo **booliano**.

    > [!NOTE]
    > Se você excluir a classe de domínio raiz e, em seguida, criar uma nova raiz, precisará redefinir a propriedade da classe raiz do editor. No **Gerenciador de DSL**, selecione **Editor**. Em seguida, no janela Propriedades, defina a **classe raiz** como `Farm`.

4. Use a ferramenta de **classe de domínio nomeada** para criar as seguintes classes de domínio:

    - `Field` – forneça uma propriedade de domínio adicional chamada `Size`.

    - `Animal` – na janela Propriedades, defina o **modificador de herança** como **abstrato**.

5. Use a ferramenta de **classe de domínio** para criar as seguintes classes:

    - `Sheep`

    - `Goat`

6. Use a ferramenta de **herança** para fazer `Goat` e `Sheep` herdar de `Animal`.

7. Use a ferramenta de **incorporação** para inserir `Field` e `Animal` em `Farm`.

8. Talvez você queira organizar o diagrama. Para reduzir o número de elementos duplicados, use o comando **trazer subárvore aqui** no menu de atalho dos elementos folha.

9. **Transforme todos os modelos** na barra de ferramentas de Gerenciador de soluções.

10. Compile o projeto **DSL** .

    > [!NOTE]
    > Neste estágio, os outros projetos não serão compilados sem erros. No entanto, desejamos criar o projeto DSL para que seu assembly esteja disponível para o assistente de fonte de dados.

## <a name="updating-the-ui-project"></a>Atualizando o projeto de interface do usuário
 Agora você pode criar um novo controle de usuário que exibirá as informações armazenadas no modelo DSL. A maneira mais fácil de conectar o controle de usuário ao modelo é por meio de associações de dados. O tipo de adaptador de ligação de dados chamado **ModelingBindingSource** foi projetado especificamente para conectar DSLs a interfaces não VMSDK.

#### <a name="to-define-your-dsl-model-as-a-data-source"></a>Para definir o modelo de DSL como uma fonte de dados

1. No menu **dados** , escolha **mostrar fontes de dados**.

     A janela **Fontes de Dados** é aberta.

     Escolha **Adicionar nova fonte de dados**. O **Assistente de Configuração de Fonte de Dados** é aberto.

2. Escolha **objeto**, **Avançar**.

     Expanda **DSL**, **Company. FarmApp**e selecione **farm**, que é a classe raiz do seu modelo. Escolha **Concluir**.

     No Gerenciador de Soluções, o projeto de **interface do usuário** agora contém **Properties\DataSources\Farm.DataSource**

     As propriedades e relações de sua classe de modelo aparecem na janela fontes de dados.

     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png "DslWpf-3")

#### <a name="to-connect-your-model-to-a-form"></a>Para conectar seu modelo a um formulário

1. No projeto de **interface do usuário** , exclua todos os arquivos. cs existentes.

2. Adicione um novo arquivo de **controle de usuário** chamado `FarmControl` ao projeto **da interface do** usuário.

3. Na janela **fontes de dados** , no menu suspenso no **farm**, escolha **detalhes**.

    Deixe as configurações padrão para as outras propriedades.

4. Abra FarmControl.cs no modo de exibição de design.

    Arraste **farm** da janela Data Sources para FarmControl.

    Um conjunto de controles é exibido, um para cada propriedade. As propriedades da relação não geram controles.

5. Exclua **farmBindingNavigator**. Isso também é gerado automaticamente no designer de `FarmControl`, mas não é útil para esse aplicativo.

6. Usando a caixa de ferramentas, crie duas instâncias de **DataGridView**e nomeie-as `AnimalGridView` e `FieldGridView`.

   > [!NOTE]
   > Uma etapa alternativa é arrastar os itens animais e Fields da janela fontes de dados para o controle. Essa ação cria automaticamente grades de dados e associações entre o modo de exibição de grade e a fonte de dados. No entanto, essa associação não funciona corretamente para DSLs. Portanto, é melhor criar manualmente as grades de dados e associações.

7. Se a caixa de ferramentas não contiver a ferramenta **ModelingBindingSource** , adicione-a. No menu de atalho da guia **dados** , escolha **escolher itens**. Na caixa de diálogo **escolher itens da caixa de ferramentas** , selecione **ModelingBindingSource** na **guia .NET Framework**.

8. Usando a caixa de ferramentas, crie duas instâncias de **ModelingBindingSource**e nomeie-as `AnimalBinding` e `FieldBinding`.

9. Defina a propriedade **DataSource** de cada **ModelingBindingSource** como **farmBindingSource**.

     Defina a propriedade **DataMember** como **animais** ou **Fields**.

10. Defina as propriedades de **DataSource** de `AnimalGridView` como `AnimalBinding` e de `FieldGridView` como `FieldBinding`.

11. Ajuste o layout do controle de farm para o seu gosto.

    O **ModelingBindingSource** é um adaptador que executa várias funções específicas para DSLs:

- Ele encapsula as atualizações em uma transação do repositório VMSDK.

   Por exemplo, quando o usuário exclui uma linha da grade de exibição de dados, uma associação regular resultaria em uma exceção de transação.

- Isso garante que, quando o usuário selecionar uma linha, a janela Propriedades exibirá as propriedades do elemento de modelo correspondente, em vez da linha de grade de dados.

  ![DslWpf4](../modeling/media/dslwpf4.png "DslWpf4") Esquema de links entre fontes de dados e exibições.

#### <a name="to-complete-the-bindings-to-the-dsl"></a>Para concluir as ligações para a DSL

1. Adicione o seguinte código em um arquivo de código separado no projeto de **interface do usuário** :

    ```csharp
    using System.ComponentModel;
    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.Design;

    namespace Company.FarmApp
    {
      partial class FarmControl
      {
        public IContainer Components { get { return components; } }

        /// <summary>Binds the WinForms data source to the DSL model.
        /// </summary>
        /// <param name="nodelRoot">The root element of the model.</param>
        public void DataBind(ModelElement modelRoot)
        {
          WinFormsDataBindingHelper.PreInitializeDataSources(this);
          this.farmBindingSource.DataSource = modelRoot;
          WinFormsDataBindingHelper.InitializeDataSources(this);
        }
      }
    }
    ```

2. No projeto **DslPackage** , edite **DslPackage\DocView.tt** para atualizar a seguinte definição de variável:

    ```csharp
    string viewControlTypeName = "FarmControl";
    ```

## <a name="testing-the-dsl"></a>Testando a DSL
 A solução DSL agora pode ser criada e executada, embora você queira adicionar mais melhorias posteriormente.

#### <a name="to-test-the-dsl"></a>Para testar a DSL

1. Criar e executar a solução.

2. Na instância experimental do Visual Studio, abra o arquivo de **exemplo** .

3. No **FarmApp Explorer**, abra o menu de atalho no nó raiz do **farm** e escolha **Adicionar novo pastor**.

     `Goat1` aparece na exibição **animais** .

    > [!WARNING]
    > Você deve usar o menu de atalho no nó do **farm** , não no nó **animais** .

4. Selecione o nó raiz do **farm** e exiba suas propriedades.

     Na exibição de formulário, altere o **nome** ou o **tamanho** do farm.

     Quando você navega para fora de cada campo no formulário, a propriedade correspondente é alterada no janela Propriedades.

## <a name="enhancing-the-dsl"></a>Aprimorando a DSL

#### <a name="to-make-the-properties-update-immediately"></a>Para fazer com que as propriedades sejam atualizadas imediatamente

1. No modo de exibição de design de FarmControl.cs, selecione um campo simples, como nome, tamanho ou isorgânica.

2. No janela Propriedades, expanda **DataBindings** e abra **(avançado)** .

     Na caixa de diálogo **formatação e Associação avançada** , em **modo de atualização da fonte de dados**, escolha **OnPropertyChanged**.

3. Criar e executar a solução.

     Verifique se, quando você altera o conteúdo do campo, a propriedade correspondente do modelo de farm é alterada imediatamente.

#### <a name="to-provide-add-buttons"></a>Para fornecer botões de adição

1. No modo de exibição de design de FarmControl.cs, use a caixa de ferramentas para criar um botão no formulário.

    Edite o nome e o texto do botão, por exemplo, para `New Sheep`.

2. Abra o código por trás do botão (por exemplo, clicando duas vezes nele).

    Edite-o da seguinte maneira:

   ```csharp
   private void NewSheepButton_Click(object sender, EventArgs e)
   {
     using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
     {
       elementOperations.MergeElementGroup(farm,
         new ElementGroup(new Sheep(farm.Partition)));
       t.Commit();
     }
   }

   // The following code is shared with other add buttons:
   private ElementOperations operationsCache = null;
   private ElementOperations elementOperations
   {
     get
     {
       if (operationsCache == null)
       {
         operationsCache = new ElementOperations(farm.Store, farm.Partition);
       }
       return operationsCache;
     }
   }
   private Farm farm
   {
     get { return this.farmBindingSource.DataSource as Farm; }
   }

   ```

    Você também precisará inserir a seguinte diretiva:

   ```csharp

   using Microsoft.VisualStudio.Modeling;

   ```

3. Adicione botões semelhantes para Goats e campos.

4. Criar e executar a solução.

5. Verifique se o botão novo adiciona um item. O novo item deve aparecer no FarmApp Explorer e no modo de exibição de grade de dados apropriado.

    Você deve ser capaz de editar o nome do elemento no modo de exibição de grade de dados. Você também pode excluí-lo de lá.

   ![WPF&#45;&#45;de DSL 2](../modeling/media/dsl-wpf-2.png "DSL-WPF-2")

### <a name="about-the-code-to-add-an-element"></a>Sobre o código para adicionar um elemento
 Para os novos botões de elemento, o código alternativo a seguir é um pouco mais simples.

```csharp
private void NewSheepButton_Click(object sender, EventArgs e)
{
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
  {
    farm.Animals.Add(new Sheep(farm.Partition)); ;
    t.Commit();
  }
}

```

 No entanto, esse código não define um nome padrão para o novo item. Ele não executa nenhuma mesclagem personalizada que você possa ter definido nas **diretivas de mesclagem de elementos** da DSL e não executa nenhum código de mesclagem personalizado que possa ter sido definido.

 Portanto, recomendamos que você use <xref:Microsoft.VisualStudio.Modeling.ElementOperations> para criar novos elementos. Para obter mais informações, consulte [Personalizando a criação e movimentação do elemento](../modeling/customizing-element-creation-and-movement.md).

## <a name="see-also"></a>Consulte também
 [Como definir um](../modeling/how-to-define-a-domain-specific-language.md) código de escrita de linguagem específica de domínio [para personalizar um](../modeling/writing-code-to-customise-a-domain-specific-language.md) [SDK de modelagem de linguagem específica de domínio para Visual Studio-linguagens específicas de domínio](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)
