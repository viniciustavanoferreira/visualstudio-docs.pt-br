---
title: 'Tutorial: Comece com C# e ASP.NET Core'
titleSuffix: ''
description: Saiba como criar um aplicativo Web do ASP.NET Core no Visual Studio com C#, passo a passo.
ms.custom: seodec18, get-started
ms.date: 05/29/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: CSharp
author: ornellaalt
ms.author: ornella
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: ef41e28d994f27f66f616623d1b2c9798b65ede4
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "77580056"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>Tutorial: Introdução ao C# e ao ASP.NET Core no Visual Studio

Neste tutorial para desenvolvimento em C# com ASP.NET Core usando o Visual Studio, você criará um aplicativo Web ASP.NET Core em C#, fará alterações, explorará alguns recursos do IDE e então executará o aplicativo.

## <a name="before-you-begin"></a>Antes de começar

### <a name="install-visual-studio"></a>Instalar Visual Studio

::: moniker range="vs-2017"

Se você ainda não instalou o Visual Studio, vá para a página [de downloads](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) do Visual Studio para instalá-lo gratuitamente.

::: moniker-end

::: moniker range="vs-2019"

Se você ainda não instalou o Visual Studio, vá para a página [de downloads](https://visualstudio.microsoft.com/downloads) do Visual Studio para instalá-lo gratuitamente.

::: moniker-end

### <a name="update-visual-studio"></a>Atualizar o Visual Studio

Se você já tiver instalado o Visual Studio, verifique se está executando a versão mais recente. Para obter mais informações sobre como atualizar sua instalação, consulte o Update Visual Studio para a página [de lançamento mais recente.](../../install/update-visual-studio.md)

### <a name="choose-your-theme-optional"></a>Escolher o tema (opcional)

Este tutorial inclui capturas de tela que usam o tema escuro. Se você não estiver usando o tema escuro, mas quiser usá-lo, confira a página [Personalizar o IDE e o Editor do Visual Studio](../../ide/quickstart-personalize-the-ide.md) para saber como.

## <a name="create-a-project"></a>Criar um projeto

Primeiro, você criará um projeto ASP.NET Core. O tipo de projeto vem com todos os arquivos de modelo necessários para um site totalmente funcional, mesmo antes que você adicione qualquer coisa.

::: moniker range="vs-2017"

1. Abra o Visual Studio 2017.

2. Na barra de menu superior, escolha **Arquivo** > **Novo** > **Projeto**.

3. Na caixa de diálogo **Novo Projeto** no painel esquerdo, expanda **Visual C#**, expanda **Web** e escolha **.NET Core**. No painel central, escolha **Aplicativo Web ASP.NET Core**. Em seguida, nomeie o arquivo *MyCoreApp* e escolha **OK**.

   ![Modelo de projeto do aplicativo Web do ASP.NET Core na caixa de diálogo Novo projeto no IDE do Visual Studio](media/csharp-aspnet-choose-template-name-razor-mycoreapp-file.png)

### <a name="add-a-workload-optional"></a>Adicionar uma carga de trabalho (opcional)

Se o modelo de projeto **Aplicativo Web do ASP.NET Core** não for exibido, você poderá obtê-lo adicionando a carga de trabalho **Desenvolvimento ASP.NET e Web**. Você pode adicionar essa carga de trabalho de uma das duas maneiras, dependendo de quais atualizações do Visual Studio 2017 estão instaladas no seu computador.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Opção 1: usar a caixa de diálogo Novo Projeto

1. Clique no link **Abrir o Instalador do Visual Studio** no painel esquerdo da caixa de diálogo **Novo Projeto**. (Dependendo das suas configurações de exibição, talvez seja necessário rolar para vê-la.)

   ![Clique no link Abrir Instalador do Visual Studio na caixa de diálogo Novo Projeto](../media/open-visual-studio-installer-mycoreapp.png)

1. O Instalador do Visual Studio é iniciado. Escolha a carga de trabalho **ASP.NET e desenvolvimento para a Web** e, em seguida, selecione **Modificar**.

   ![Carga de trabalho de desenvolvimento multiplaforma do .NET Core no Instalador do Visual Studio](../media/tutorial-aspnet-workload.png)

   (Talvez você precise fechar o Visual Studio antes de continuar a instalar a nova carga de trabalho.)

#### <a name="option-2-use-the-tools-menu-bar"></a>Opção 2: usar a barra de menus Ferramentas

1. Cancele a caixa de diálogo **Novo Projeto**. Em seguida, na barra de menu superior, escolha **Ferramentas** > **Obter Ferramentas e Recursos**.

1. O Instalador do Visual Studio é iniciado. Escolha a carga de trabalho **ASP.NET e desenvolvimento para a Web** e, em seguida, selecione **Modificar**.

   (Talvez você precise fechar o Visual Studio antes de continuar a instalar a nova carga de trabalho.)

### <a name="add-a-project-template"></a>Adicionar um modelo de projeto

1. Na caixa de diálogo **Novo Aplicativo Web ASP.NET Core**, escolha o modelo de projeto **Aplicativo Web**.

1. Verifique se o **ASP.NET Core 2.1** aparece no menu suspenso superior. Em seguida, escolha **OK**.

   ![Caixa de diálogo Novo Aplicativo Web ASP.NET Core](media/new-project-csharp-aspnet-razor-web-app.png)

   > [!NOTE]
   > Se você não vir o **ASP.NET Core 2.1** no menu suspenso superior, verifique se você está executando a versão mais recente do Visual Studio. Para obter mais informações sobre como atualizar sua instalação, consulte o Update Visual Studio para a página [de lançamento mais recente.](../../install/update-visual-studio.md)

::: moniker-end

::: moniker range="vs-2019"

1. Na janela inicial, escolha **Criar um novo projeto**.

   ![Exibir a janela 'Criar um novo projeto'](../../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na janela **Criar um novo projeto**, insira ou digite *ASP.NET* na caixa de pesquisa. Em seguida, escolha **C#** na lista Linguagem de programação e, em seguida, escolha **Windows** na lista Plataforma.

   Depois de aplicar os filtros de linguagem de programação e plataforma, escolha o modelo **Aplicativo Web ASP.NET Core (.NET Core)** e, em seguida, escolha **Avançar**.

   ![Escolher o modelo de C# para o Aplicativo Web ASP.NET Core](./media/vs-2019/csharp-create-new-project-search-aspnet-core-filtered.png)

   > [!NOTE]
   > Se não vir o modelo **Aplicativo Web ASP.NET Core**, você poderá instalá-lo da janela **Criar um novo projeto**. Na mensagem **Não encontrou o que precisa?**, escolha o link **Instalar mais ferramentas e recursos**.
   >
   > ![O link 'Instalar mais ferramentas e recursos' da mensagem 'Não encontrou o que precisa?' na janela 'Criar novo projeto'](../../get-started/media/vs-2019/not-finding-what-looking-for.png)
   >
   > Em seguida, no Instalador do Visual Studio, escolha a carga de trabalho de **desenvolvimento Web e ASP.NET**.
   >
   > ![Carga de trabalho de desenvolvimento multiplaforma do .NET Core no Instalador do Visual Studio](../../get-started/media/aspnet-core-web-dev-workload.png)
   >
   > Depois disso, escolha o botão **Modificar** no Instalador do Visual Studio. Se você for solicitado a salvar seu trabalho, faça isso. Em seguida, escolha **Continuar** para instalar a carga de trabalho. Em seguida, retorne para a etapa 2 deste procedimento para "[Criar um projeto](#create-a-project)".

1. Na janela **Configurar seu novo projeto**, digite ou insira *MyCoreApp* na caixa **Nome do projeto**. Em seguida, escolha **Criar**.

   ![Na janela "Configurar seu novo projeto", dê ao projeto o nome 'MyCoreApp'](./media/vs-2019/csharp-name-your-aspnet-mycoreapp-project.png)

1. Na **janela Criar uma nova janela ASP.NET Do Aplicativo da Web,** verifique se **ASP.NET Core 3.0** aparece no menu suspenso superior. Em seguida, escolha **Aplicativo Web**, que inclui Razor Pages de exemplo. Em seguida, escolha **Criar**.

   ![A janela 'Criar um novo Aplicativo Web ASP.NET Core'](./media/vs-2019/csharp-create-aspnet-razor-pages-app.png)

   O Visual Studio abre seu novo projeto.

::: moniker-end

### <a name="about-your-solution"></a>Sobre sua solução

Esta solução segue o padrão de design da **Página do Razor**. Ele é diferente do padrão de design [Model-View-Controller (MVC)](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x) que é simplificado para incluir o código do modelo e do controlador na própria página do Razor.

::: moniker range="vs-2017"
## <a name="tour-your-solution"></a>Fazer tour da sua solução

 1. O modelo de projeto cria uma solução com um único projeto ASP.NET Core chamado _MyCoreApp_. Escolha a guia **Gerenciador de Soluções** para exibir seu conteúdo.

    ![A solução do Gerenciador de Soluções do ASP.NET no Visual Studio para o Razor Pages é denominada MyCoreApp](media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Expanda a pasta **Páginas** e depois *About.cshtml*.

     ![O arquivo About.cshtml no Gerenciador de Soluções do Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtml.png)

 1. Visualize o arquivo **About.cshtml** no editor de códigos.

     ![Visualizar o arquivo About.cshtml no editor de códigos do Visual Studio](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code.png)

 1. Escolha o arquivo **About.cshtml.cs**.

     ![Escolher o arquivo About.cs no editor de códigos do Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtmlcs.png)

 1. Visualize o arquivo **About.cs** no editor de códigos.

     ![Visualizar o arquivo About.cshtml no editor de códigos do Visual Studio](media/csharp-aspnet-razor-aboutcshtmlcs-mycoreapp-code.png)

 1. O projeto também contém a pasta **wwwroot** que é a raiz do site. Expanda a pasta para exibir seu conteúdo.

     ![Pasta wwwroot no Gerenciador de Soluções no Visual Studio](media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    Você pode colocar o conteúdo do site estático, como CSS, imagens e bibliotecas JavaScript, diretamente nos caminhos em que deseja.

 1. O projeto também contém arquivos de configuração que gerenciam o aplicativo web em tempo de execução. A [configuração](/aspnet/core/fundamentals/configuration) de aplicativo padrão é armazenada em *appsettings.json*. No entanto, você pode substituir essas configurações usando *appsettings.Development.json*. Expanda o arquivo **appsettings.json** para exibir o arquivo **appsettings.Development.json**.

     ![Arquivos de configuração no Gerenciador de Soluções no Visual Studio](media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## <a name="run-debug-and-make-changes"></a>Executar, depurar e fazer alterações

1. Escolha o botão **IIS Express** no IDE para compilar e executar o aplicativo no modo de Depuração. Como alternativa, pressione **F5** ou escolha **Depurar** > **Iniciar depuração** na barra de menus.

     ![Selecionar o botão IIS Express no Visual Studio](media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > Se você receber uma mensagem de erro que diz **Não conseguir se conectar ao servidor web 'IIS Express',** feche o Visual Studio e abra-a usando a opção Executar como **administrador** a partir do menu de clique siou ou contexto. Em seguida, execute o aplicativo novamente.
     >
     > Você também pode obter uma mensagem perguntando se deseja aceitar um certificado SSL do IIS Express. Para exibir o código em um navegador da Web, escolha **Sim** e, em seguida, escolha **Sim** se você receber uma mensagem de aviso de segurança de acompanhamento.

1. O Visual Studio abre uma janela do navegador. Você deve vê-los na **Página Inicial** e nas páginas **Sobre** e **Contato** na barra de menus. (Se isso não ocorrer, escolha o item de menu "hambúrguer" para exibi-los).

    ![Selecione o item de menu "hambúrguer" na barra de menu em seu aplicativo web](media/csharp-aspnet-razor-browser-page.png)

1. Escolha **Sobre** na barra de menus.

   ![Selecione Sobre na barra de menus da janela do navegador do seu aplicativo](media/csharp-aspnet-razor-browser-page-about-menu.png)

   Entre outras coisas, a página **Sobre** no navegador renderiza o texto definido no arquivo *About.cshtml*.

   ![Exiba o texto na página Sobre](media/csharp-aspnet-razor-browser-page-about.png)

1. Retorne ao Visual Studio e pressione **Shift+F5** para interromper o modo de Depuração. Isso também fecha o projeto na janela do navegador.

1. No Visual Studio, escolha **About.cshtml**. Em seguida, exclua a palavra _adicional_ e, em seu lugar, adicione as palavras _arquivo e diretório_.

    ![Alterar o texto no arquivo About.cshtml](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code-changed.png)

1. Escolha **About.cshtml.cs**. Em seguida, limpe as diretivas `using` na parte superior do arquivo usando o seguinte atalho:

   Escolha uma das diretivas `using` esmaecidas, e será exibida a lâmpada [Ações Rápidas](../../ide/quick-actions.md) logo abaixo da seta ou na margem esquerda. Escolha a lâmpada e, em seguida, escolha **Remover Usings Desnecessários**.

   ![Remover usos desnecessários no arquivo About.cshtml.cs](media/csharp-aspnet-razor-remove-unnecessary-usings.png)

     O Visual Studio exclui as diretivas `using` desnecessárias do arquivo.

1. Em seguida, no método `OnGet()`, altere o corpo para o código a seguir:

     ```csharp
     public void OnGet()
     {
         string directory = Environment.CurrentDirectory;
         Message = String.Format("Your directory is {0}.", directory);
     }
    ```

1. Observe que dois sublinhados ondulados são exibidos sob **Ambiente** e **Cadeia de caracteres**. Os sublinhados ondulados são exibidos porque esses tipos não estão no escopo.

   ![Os erros são marcados com sublinhados ondulados no método OnGet](media/csharp-aspnet-razor-add-new-on-get-method.png)

    Abra a barra de ferramentas **Lista de Erros** para ver os mesmos erros listados. (Se a barra de ferramentas **Lista de Erros** não for exibida, escolha **Exibir** > **Lista de Erros** na barra de menus superior.)

   ![Lista de Erros no Visual Studio](media/csharp-aspnet-razor-error-list.png)

1. Vamos corrigir isso. No editor de códigos, coloque o cursor na linha que contém o erro e escolha a lâmpada Ações Rápidas na margem esquerda. No menu suspenso, escolha **using System;** para adicionar essa diretiva no topo do arquivo e resolver os erros.

   ![Adicionar a diretiva "using System;"](media/csharp-aspnet-razor-add-usings.png)

1. Pressione **Ctrl**+**S** para salvar suas alterações e pressione **F5** para abrir seu projeto no navegador da Web.

1. Na parte superior do site, escolha **Sobre** para ver as alterações.

   ![Exibir a página Sobre atualizada que inclui o texto alterado](media/csharp-aspnet-razor-browser-page-about-changed.png)

1. Feche o navegador da Web, **pressione shift**+**F5** para parar o modo Debug e, em seguida, feche o Visual Studio.

::: moniker-end

::: moniker range=">=vs-2019"

## <a name="tour-your-solution"></a>Fazer tour da sua solução

 1. O modelo de projeto cria uma solução com um único projeto ASP.NET Core chamado _MyCoreApp_. Escolha a guia **Gerenciador de Soluções** para exibir seu conteúdo.

    ![A solução do Gerenciador de Soluções do ASP.NET no Visual Studio para o Razor Pages é denominada MyCoreApp](media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Expanda a pasta **Páginas.**

     ![A pasta Páginas no Solution Explorer](media/vs-2019/csharp-aspnet-solution-explorer-pages.png)

 1. Exibir o arquivo **Index.cshtml** no editor de código.

     ![Exibir o arquivo Index.cshtml no editor de código sateliteria visual studio](media/vs-2019/csharp-aspnet-index-cshtml.png)

 1. Cada arquivo .cshtml tem um arquivo de código associado. Para abrir o arquivo de código no editor, expanda o nó **Index.cshtml** no Solution Explorer e escolha o **arquivo Index.cshtml.cs.**

     ![Escolha o arquivo Index.cshtml.cs no editor de códigos do Visual Studio](media/vs-2019/csharp-aspnet-choose-index-cshtml.png)

 1. Veja o arquivo **Index.cshtml.cs** no editor de código.

     ![Visualizar o arquivo About.cshtml no editor de códigos do Visual Studio](media/vs-2019/csharp-aspnet-index-cshtml-editing.png)

 1. O projeto também contém a pasta **wwwroot** que é a raiz do site. Expanda a pasta para exibir seu conteúdo.

     ![Pasta wwwroot no Gerenciador de Soluções no Visual Studio](media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    Você pode colocar o conteúdo do site estático, como CSS, imagens e bibliotecas JavaScript, diretamente nos caminhos em que deseja.

 1. O projeto também contém arquivos de configuração que gerenciam o aplicativo web em tempo de execução. A [configuração](/aspnet/core/fundamentals/configuration) de aplicativo padrão é armazenada em *appsettings.json*. No entanto, você pode substituir essas configurações usando *appsettings.Development.json*. Expanda o arquivo **appsettings.json** para exibir o arquivo **appsettings.Development.json**.

     ![Arquivos de configuração no Gerenciador de Soluções no Visual Studio](media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## <a name="run-debug-and-make-changes"></a>Executar, depurar e fazer alterações

1. Escolha o botão **IIS Express** no IDE para compilar e executar o aplicativo no modo de Depuração. Como alternativa, pressione **F5** ou escolha **Depurar** > **Iniciar depuração** na barra de menus.

     ![Selecionar o botão IIS Express no Visual Studio](media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > Se você receber uma mensagem de erro que diz **Não conseguir se conectar ao servidor web 'IIS Express',** feche o Visual Studio e abra-a usando a opção Executar como **administrador** a partir do menu de clique siou ou contexto. Em seguida, execute o aplicativo novamente.
     >
     > Você também pode obter uma mensagem perguntando se deseja aceitar um certificado SSL do IIS Express. Para exibir o código em um navegador da Web, escolha **Sim** e, em seguida, escolha **Sim** se você receber uma mensagem de aviso de segurança de acompanhamento.

1. O Visual Studio abre uma janela do navegador. Em seguida, você deve ver **Home**e **páginas de privacidade** na barra de menus.

1. Escolha **Privacidade** na barra de menus.

   A página **Privacidade** no navegador renderiza o texto definido no arquivo *Privacy.cshtml.*

   ![Exibir o texto na página Privacidade](media/vs-2019/csharp-aspnet-browser-page-privacy.png)

1. Retorne ao Visual Studio e pressione **Shift+F5** para interromper o modo de Depuração. Isso também fecha o projeto na janela do navegador.

1. No Visual Studio, abra **Privacy.cshtml** para edição. Em seguida, exclua as palavras _Use esta página para detalhar a política de privacidade do seu site_ e, em seu lugar, adicione as palavras que esta página está em construção a partir de _ @ViewData["TimeStamp"]_.

    ![Alterar o texto no arquivo Privacy.cshtml](media/vs-2019/csharp-aspnet-privacy-cshtml-code-changed.png)

1. Agora, vamos fazer uma mudança de código. Escolha **Privacy.cshtml.cs**. Em seguida, limpe as diretivas `using` na parte superior do arquivo usando o seguinte atalho:

   Escolha uma das diretivas `using` esmaecidas, e será exibida a lâmpada [Ações Rápidas](../../ide/quick-actions.md) logo abaixo da seta ou na margem esquerda. Escolha a lâmpada e, em seguida, paire sobre **Remover usos desnecessários**.

   ![Remover usos desnecessários no arquivo Privacy.cshtml.cs](media/vs-2019/csharp-aspnet-remove-unnecessary-usings.png)

   Agora escolha **Alterações de visualização** para ver o que vai mudar.

   ![Visualizar alterações](media/vs-2019/csharp-aspnet-preview-changes.png)

   Escolha **Aplicar**. O Visual Studio exclui as diretivas `using` desnecessárias do arquivo.

1. Em seguida, no método `OnGet()`, altere o corpo para o código a seguir:

     ```csharp
     public void OnGet()
     {
        string dateTime = DateTime.Now.ToShortDateString();
        ViewData["TimeStamp"] = dateTime;
     }
    ```

1. Observe que dois sublinhados ondulados aparecem em **DateTime**. Os sublinhados ondulados aparecem porque este tipo não está no escopo.

   ![Os erros são marcados com sublinhados ondulados no método OnGet](media/vs-2019/csharp-aspnet-add-new-onget-method.png)

    Abra a barra de ferramentas **Lista de Erros** para ver os mesmos erros listados. (Se a barra de ferramentas **Lista de Erros** não for exibida, escolha **Exibir** > **Lista de Erros** na barra de menus superior.)

   ![Lista de Erros no Visual Studio](media/vs-2019/csharp-aspnet-error-list.png)

1. Vamos corrigir isso. No editor de códigos, coloque o cursor na linha que contém o erro e escolha a lâmpada Ações Rápidas na margem esquerda. No menu suspenso, escolha **using System;** para adicionar essa diretiva no topo do arquivo e resolver os erros.

   ![Adicionar a diretiva "using System;"](media/vs-2019/csharp-aspnet-add-usings.png)

1. Pressione **F5** para abrir seu projeto no navegador da Web.

1. Na parte superior do site, escolha **Privacidade** para visualizar suas alterações.

   ![Exibir a página de privacidade atualizada que inclui as alterações que você fez](media/vs-2019/csharp-aspnet-browser-page-privacy-changed.png)

1. Feche o navegador da Web, **pressione shift**+**F5** para parar o modo Debug e, em seguida, feche o Visual Studio.
::: moniker-end

## <a name="quick-answers-faq"></a>Perguntas frequentes com respostas rápidas

Aqui estão algumas perguntas frequentes rápidas para destacar alguns conceitos principais.

### <a name="what-is-c"></a>O que é C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) é uma linguagem de programação fortemente tipada e orientada a objeto projetada para ser robusta e fácil de aprender.

### <a name="what-is-aspnet-core"></a>O que é ASP.NET Core?

O ASP.NET Core é uma estrutura de software livre e de multiplataforma para a compilação de aplicativos modernos conectados à Internet, como serviços e aplicativos Web. Aplicativos ASP.NET Core podem ser executados no .NET Core ou o .NET Framework. Você pode desenvolver e executar aplicativos ASP.NET Core de multiplataforma no Windows, Mac e Linux. O ASP.NET Core é um software livre no [GitHub](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>O que é o Visual Studio?

Visual Studio é um pacote de desenvolvimento integrado de ferramentas de produtividade para desenvolvedores. Pense nele como um programa que você pode usar para criar programas e aplicativos.

## <a name="next-steps"></a>Próximas etapas

Parabéns por concluir este tutorial. Esperamos que você tenha aprendido um pouco sobre o C#, o ASP.NET Core e o IDE do Visual Studio. Para saber mais sobre como criar um aplicativo Web ou site em C# com o ASP.NET, continue com os tutoriais a seguir:

> [!div class="nextstepaction"]
> [Crie um aplicativo web Razor Pages com ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>Confira também

[Publicar seu aplicativo Web no Serviço de Aplicativo do Azure usando o Visual Studio](../../deployment/quickstart-deploy-to-azure.md)
