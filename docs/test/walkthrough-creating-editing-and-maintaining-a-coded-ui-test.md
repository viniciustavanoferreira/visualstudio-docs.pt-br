---
title: Criar um teste de IU codificado
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: f1e22a39035e5d3500f4dd45481319e1daecfa04
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75592055"
---
# <a name="walkthrough-create-edit-and-maintain-a-coded-ui-test"></a>Passo a passo: Criar, editar e manter um teste de IU codificado

Neste passo a passo, você saberá como criar, editar e manter um teste de IU codificado para testar um aplicativo WPF (Windows Presentation Framework). O passo a passo fornece soluções para corrigir os testes que foram interrompidos por vários problemas de tempo e refatoração de controles.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="create-a-wpf-app"></a>Criar um aplicativo WPF

1. Crie um projeto **Aplicativo WPF (.NET Framework)** e dê ao projeto o nome **SimpleWPFApp**.

     O **WPF Designer** é aberto e exibe a MainWindow do projeto.

2. Se a caixa de ferramentas não estiver aberta, abra-a. Escolha o menu **Exibir** e, em seguida, escolha **Caixa de ferramentas**.

3. Na seção **Todos os Controles do WPF**, arraste um controle **Button**, **CheckBox** e **ProgressBar** para a MainWindow na superfície de design.

4. Selecione o controle de **Botão**. Na janela **Propriedades**, altere o valor da propriedade **Nome** de \<No Name> para button1. Em seguida, altere o valor da propriedade **Conteúdo** de Button para Start.

5. Selecione o controle **ProgressBar**. Na janela **Propriedades**, altere o valor da propriedade **Nome** de \<No Name> para progressBar1. Em seguida, altere o valor da propriedade **Máximo** de **100** para **10000**.

6. Selecione o controle **Caixa de Seleção**. Na janela **Propriedades**, altere o valor da propriedade **Nome** de \<No Name> para checkBox1 e desmarque a propriedade **IsEnabled**.

     ![Aplicativo WPF simples](../test/media/codedui_wpfapp.png)

7. Clique duas vezes no controle de botão para adicionar um manipulador de eventos de clique.

     O *MainWindow.xmal.cs* é exibido no Editor de Códigos com o cursor no novo método button1_Click.

8. Na parte superior da classe MainWindow, adicione um delegado. O delegado será usado para a barra de progresso. Para adicionar o delegado, adicione o seguinte código:

    ```csharp
    public partial class MainWindow : Window
    {
            private delegate void ProgressBarDelegate(System.Windows.DependencyProperty dp, Object value);

        public MainWindow()
        {

            InitializeComponent();
        }
    ```

9. No método button1_Click, adicione o seguinte código:

    ```csharp
    private void button1_Click(object sender, RoutedEventArgs e)
    {
        double progress = 0;

        ProgressBarDelegate updatePbDelegate =
            new ProgressBarDelegate(progressBar1.SetValue);

        do
        {
            progress ++;

            Dispatcher.Invoke(updatePbDelegate,
                System.Windows.Threading.DispatcherPriority.Background,
                new object[] { ProgressBar.ValueProperty, progress });
            progressBar1.Value = progress;
        }
        while (progressBar1.Value != progressBar1.Maximum);

        checkBox1.IsEnabled = true;
    }
    ```

10. Salve o arquivo.

### <a name="run-the-wpf-app"></a>Executar o aplicativo WPF

1. No menu **Debug,** selecione **Iniciar depuração** ou pressione **F5**.

2. Observe que o controle da caixa de seleção está desabilitado. Escolha **Iniciar**.

     Em alguns segundos, a barra de progresso deve estar 100% concluída.

3. Agora é possível selecionar o controle da caixa de seleção.

4. Feche o SimpleWPFApp.

## <a name="create-a-shortcut-to-the-wpf-app"></a>Criar um atalho para o aplicativo WPF

1. Localize o aplicativo SimpleWPFApp criado anteriormente.

2. Crie um atalho na área de trabalho para o aplicativo SimpleWPFApp. Clique com o botão direito do mouse *SimpleWPFApp.exe* e escolha **Copiar**. Na área de trabalho, clique com o botão direito do mouse e escolha **Colar atalho**.

    > [!TIP]
    > Um atalho para o aplicativo facilita adicionar ou modificar testes de IU codificados para seu aplicativo, porque permite iniciá-lo rapidamente.

## <a name="create-a-coded-ui-test-for-simplewpfapp"></a>Criar um teste de IU codificado para SimpleWPFApp

1. No **Gerenciador de Soluções**, clique com o botão direito do mouse na solução e escolha **Adicionar** > **Novo Projeto**.

2. Pesquise o modelo de **Projeto de Teste de IU Codificado**, selecione-o e continue pelas etapas até o projeto ser criado.

   > [!NOTE]
   > Se você não ver o modelo **coded UI Test Project,** você precisa [instalar o componente de teste de iu codificado](../test/use-ui-automation-to-test-your-code.md#install-the-coded-ui-test-component).

     O novo projeto de teste de IU codificado chamado **CodedUITestProject1** é adicionado à sua solução e a caixa de diálogo **Gerar Código para Teste de IU Codificado** é exibida.

1. Selecione a opção **Gravar ações, editar o mapa de IU ou adicionar asserções** e escolha **OK**.

     A caixa de diálogo **UIMap – Construtor de Teste de IU Codificado** é exibida, e a janela do Visual Studio é minimizada.

     Para obter mais informações sobre as opções da caixa de diálogo, confira [Criar testes de IU codificados](../test/use-ui-automation-to-test-your-code.md).

1. Escolha **Iniciar Gravação** na caixa de diálogo **UIMap – Construtor de Teste de IU Codificado**.

     ![Iniciar gravação](../test/media/cuit_builder_record.png)

     Se necessário, será possível pausar a gravação, por exemplo, se você tiver que lidar com um email recebido.

     ![Pausar a gravação](../test/media/cuit_.png)

    > [!WARNING]
    > Todas as ações realizadas na área de trabalho serão registradas. Pause a gravação se estiver realizando ações que possam levar à exclusão de dados confidenciais na gravação.

1. Abra o SimpleWPFApp usando o atalho da área de trabalho.

     Como antes, observe que o controle da caixa de seleção está desabilitado.

1. No SimpleWPFApp, escolha **Iniciar**.

     Em alguns segundos, a barra de progresso deve estar 100% concluída.

1. Marque o controle de caixa de seleção, que agora está habilitado.

1. Feche o aplicativo SimpleWPFApp.

1. Na caixa de diálogo **UIMap – Construtor de teste de IU codificado**, escolha **Gerar Código**.

1. Na caixa **Nome do método**, digite **SimpleAppTest** e escolha **Adicionar e gerar**. Em alguns segundos, o teste de IU codificado é exibido e adicionado à solução.

1. Fechar **UIMap - Construtor de testes de ida e rei codificado**.

     O arquivo *CodedUITest1.cs* aparece no editor de código.

1. Salve seu projeto.

### <a name="run-the-test"></a>Executar o teste

1. No menu **Teste,** escolha **o Windows** e escolha **Test Explorer**.

2. No menu **Build,** escolha **Build Solution**.

3. No arquivo *CodedUITest1.cs,* localize o método **CodedUITestMethod,** clique com o botão direito do mouse e **selecione Executar testes**ou execute o teste no **Test Explorer**.

   Durante a execução do teste de IU codificado, o SimpleWPFApp permanece visível. Ele conduz as etapas realizadas no procedimento anterior. No entanto, quando o teste tenta selecionar a caixa de seleção para o controle da caixa de seleção, a janela **Resultados do teste** mostra que o teste falhou. Isso ocorre porque o teste tenta marcar a caixa de seleção, mas não sabe que o controle de caixa de seleção permanece desabilitado até a barra de progresso ficar 100% concluída. Você pode corrigir esse e outros problemas semelhantes usando os vários métodos `UITestControl.WaitForControlXXX()` que estão disponíveis para testes de IU codificados. O próximo procedimento demonstrará o uso do método `WaitForControlEnabled()` para corrigir o problema que causou a falha desse teste. Para obter mais informações, confira [Fazer os testes de IU codificados aguardarem eventos específicos durante a reprodução](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).

## <a name="edit-and-rerun-the-coded-ui-test"></a>Editar e executar novamente o teste de IU codificado

1. Na janela **Test Explorer,** selecione o teste com falha e na seção **StackTrace,** escolha o primeiro link para **UIMap.SimpleAppTest()**

2. O *arquivo UIMap.Designer.cs* abre com o ponto de erro destacado no código:

    ```csharp
    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

3. Para corrigir esse problema, você pode fazer o teste de IU codificado esperar o controle CheckBox ser habilitado antes de continuar nessa linha usando o método `WaitForControlEnabled()`.

    > [!WARNING]
    > Não modifique o *arquivo UIMap.Designer.cs.* Quaisquer alterações que você fizer no código serão substituídas sempre que você gerar código usando o **UIMap – Construtor de Teste de IU Codificado**. Se precisar modificar um método registrado, copie-o para o arquivo *UIMap.cs* e renomeie-o. O arquivo *UIMap.cs* pode ser usado para substituir métodos e propriedades no arquivo *UIMapDesigner.cs*. É necessário remover a referência ao método original no arquivo *CodedUITest.cs* e substituí-la pelo nome do método renomeado.

4. No **Solution Explorer,** *localize uIMap.uitest* em seu projeto de teste de ida e vida codificada.

5. Abra o menu de atalho de *UIMap.uitest* e escolha **Abrir**.

     O teste de IU codificado é exibido no Editor de Teste de IU Codificado. Agora você pode ver e editar o teste de IU codificado.

6. No painel **Ação de interface do usuário**, selecione o método de teste (SimpleAppTest) que você deseja mover para o arquivo *UIMap.cs* ou *UIMap.vb*. Mover o método para um arquivo diferente permitirá que um código personalizado seja adicionado que não será substituído quando o código de teste for recompilado.

7. Escolha o botão **Mover Código** na barra de ferramentas do Editor de testes **da UI codificada.**

8. Uma caixa de diálogo do Microsoft Visual Studio é exibida. Ela avisa que o método será movido do arquivo *UIMap.uitest* para o arquivo *UIMap.cs* e que não será mais possível editar o método usando o Editor de Teste de IU Codificado. Escolha **Sim**.

     O método de teste é removido do arquivo *UIMap.uitest* e não é mais exibido no painel Ações de Interface do Usuário. Para editar o arquivo de teste movido, abra o arquivo *UIMap.cs* do **Solution Explorer**.

9. Na barra de ferramentas do Visual Studio, escolha **Salvar**.

     As atualizações do método de teste são salvas no arquivo *UIMap.Designer.*

    > [!WARNING]
    > Depois de mover o método, você não pode mais editá-lo usando o Editor de Teste de IU Codificado. Você deve adicionar seu código personalizado e mantê-lo usando o Editor de Códigos.

10. Renomear o método de `SimpleAppTest()` para `ModifiedSimpleAppTest()`

11. Adicione o seguinte usando a instrução para o arquivo:

    ```csharp
    using Microsoft.VisualStudio.TestTools.UITesting.WpfControls;
    ```

12. Adicione o seguinte método `WaitForControlEnabled()` antes da linha de código problemática identificada anteriormente:

    ```csharp
    uICheckBoxCheckBox.WaitForControlEnabled();

    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

13. No arquivo *CodedUITest1.cs,* localize o método **CodedUITestMethod** e comente ou renomeie a referência ao método original SimpleAppTest() e, em seguida, substitua-a pelo novo ModifiedSimpleAppTest():

    ```csharp
    [TestMethod]
            public void CodedUITestMethod1()
            {
                // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
                // For more information on generated code, see http://go.microsoft.com/fwlink/?LinkId=179463
                //this.UIMap.SimpleAppTest();
                this.UIMap.ModifiedSimpleAppTest();
            }
    ```

14. No menu **Compilar**, escolha **Compilar Solução**.

15. Clique com o botão direito do mouse no método **CodedUITestMethod** e selecione **Executar Testes**.

16. Desta vez, o teste de iu codificado completa com sucesso todas as etapas do teste, e **o Passed** é exibido na janela Do Explorador **de Testes.**

## <a name="refactor-a-control-in-simplewpfapp"></a>Refatorar um controle em SimpleWPFApp

1. No arquivo *MainWindow.xaml,* no designer, selecione o controle do botão.

2. Na parte superior da janela **Propriedades,** altere o valor da propriedade **Nome** do **botão1** para **o botãoA**.

3. No menu **Compilar**, escolha **Compilar Solução**.

4. No **Test Explorer,** execute **CodedUITestMethod1**.

     O teste falha porque o teste de IU codificado não consegue localizar o controle button mapeado originalmente no UIMap como button1. A refatoração pode afetar os teste de IU codificados dessa forma.

5. No **Gerenciador de Testes**, na seção **StackTrace**, escolha o primeiro link ao lado de **UIMpa.ModifiedSimpleAppTest()**.

     O arquivo *UIMap.cs* é aberto. O ponto de erro é realçado no código:

    ```csharp
    // Click 'Start' button
    Mouse.Click(uIStartButton, new Point(27, 10));
    ```

     Observe que a linha de código anterior neste procedimento está usando `UiStartButton`, que é o nome do UIMap antes de ser refatorado.

     Para corrigir o problema, você pode adicionar o controle refatorado ao UIMap usando o **Coded UI Test Builder**. Você pode atualizar o código do teste para usar o código, como demonstrado no próximo procedimento.

## <a name="map-refactored-control-rerun-the-test"></a>Mapear controle refatorado executar o teste novamente

1. No arquivo *CodedUITest1.cs,* no método **CodedUITestMethod1(),** clique com o botão direito do mouse, selecione **Gerar código para teste de iu codificado** e, em seguida, escolha Usar Construtor de Teste de **II codificado**.

     O **UIMap - Coded UI Test Builder** é exibido.

2. Usando o atalho na área de trabalho criado anteriormente, execute o aplicativo SimpleWPFApp criado antes.

3. Na caixa de diálogo **UIMap – Construtor de Teste de IU Codificado**, arraste a ferramenta de fios para o botão **Iniciar** em SimpleWPFApp.

     O botão **Iniciar** está contido em uma caixa azul. O **Construtor de Teste de IU Codificado** demora alguns segundos para processar os dados do controle selecionado e para exibir as propriedades do controle. Observe que o valor de **AutomationUId** é **buttonA**.

4. Nas propriedades do controle, escolha a seta no canto superior esquerdo para expandir o Mapa de Controles de IU. Observe que **UIStartButton1** está selecionado.

5. Na barra de ferramentas, escolha **Adicionar controle para o Mapa de Controles de IU**.

     O status na parte inferior da janela verifica a ação exibindo **O controle selecionado foi adicionado ao mapa de controles de IU**.

6. Na caixa de diálogo **UIMap – Construtor de teste de IU codificado**, escolha **Gerar Código**.

     A caixa de diálogo **Construtor de Teste de IU Codificado – Gerar código** aparece com uma nota indicando que nenhum novo método é necessário e que o código será gerado somente para as alterações no mapa de controles de interface do usuário.

7. Escolha **Gerar**.

8. Feche o SimpleWPFApp.

9. Fechar **UIMap - Construtor de testes de ida e rei codificado**.

10. No **Solution Explorer,** abra o arquivo *UIMap.Designer.cs.*

11. No arquivo *UIMap.Designer.cs*, localize a propriedade **UIStartButton1**. Observe que `SearchProperties` está definido como `"buttonA"`:

    ```csharp
    public WpfButton UIStartButton1
            {
                get
                {
                    if ((this.mUIStartButton1 == null))
                    {
                        this.mUIStartButton1 = new WpfButton(this);
                        #region Search Criteria
                        this.mUIStartButton1.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
                        this.mUIStartButton1.WindowTitles.Add("MainWindow");
                        #endregion
                    }
                    return this.mUIStartButton1;
                }
            }
    ```

     Agora você pode modificar o teste de IU codificado para usar o controle recém-mapeado. Conforme indicado no procedimento anterior, caso deseje substituir métodos ou propriedades no teste de IU codificado, faça isso no arquivo *UIMap.cs*.

12. No *arquivo UIMap.cs,* adicione um construtor `SearchProperties` e `UIStartButton` especifique `AutomationID` o imóvel para usar o imóvel com um valor de`"buttonA":`

    ```csharp
    public UIMap()
            {
                this.UIMainWindowWindow.UIStartButton.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
            }
    ```

13. No menu **Compilar**, escolha **Compilar Solução**.

14. No **Test Explorer,** execute **CodedUITestMethod1**.

     Dessa vez, o teste de IU codificado conclui com sucesso todas as etapas do teste. Na janela **Resultados do Teste**, você verá um status **Aprovado**.

## <a name="videos"></a>vídeos

![link para vídeo](../data-tools/media/playvideo.gif) [Introdução aos testes de IU codificados](https://onedrive.live.com/?id=2DB0E1EFE1C1D3B8%21110&cid=2DB0E1EFE1C1D3B8)

## <a name="faq"></a>Perguntas frequentes

[Perguntas frequentes sobre testes de IU codificados](https://social.msdn.microsoft.com/Forums/vsautotest/3a74dd2c-cef8-4923-abbf-7a91f489e6c4/faqs)

## <a name="see-also"></a>Confira também

- [Usar a automação da interface do usuário para testar o código](../test/use-ui-automation-to-test-your-code.md)
- [Configurações e plataformas compatíveis para testes de IU codificados e gravações de ação](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Editar testes de IU codificados usando o editor de teste de IU codificado](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)
