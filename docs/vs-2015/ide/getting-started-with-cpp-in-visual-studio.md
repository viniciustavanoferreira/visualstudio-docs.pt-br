---
title: Introdução à linguagem C++
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 99c73344-86ba-4b08-9e15-f6111cc04185
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 001b394d86e56b172bb1a50c335bd8ba5bcacb15
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72645623"
---
# <a name="getting-started-with-c-in-visual-studio"></a>Introdução à linguagem C++ no Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ao concluir esta explicação passo a passo, você estará familiarizado com várias ferramentas e caixas de diálogo que poderá usar ao desenvolver aplicativos com o Visual Studio. Você criará um aplicativo simples no estilo "Hello, World" enquanto aprende mais sobre o trabalho no IDE (ambiente de desenvolvimento integrado).

 Esse tópico contém as seguintes seções:

 [Entrar no Visual Studio](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_Configure)

 [Criar um aplicativo simples](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_CreateApp)

 [Adicionar código ao aplicativo](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_AddCode)

 [Depurar e testar o aplicativo](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_DebugTest)

 [Criar uma versão de lançamento do aplicativo](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_BuildRelease)

## <a name="BKMK_Configure"></a> Entrar no Visual Studio
 Quando você iniciar o Visual Studio pela primeira vez, terá a chance de entrar usando uma conta da Microsoft, como do Live ou do Outlook. Entrar permite que suas configurações sejam sincronizadas em todos os seus dispositivos. Para obter mais informações, consulte [Entrando no Visual Studio](../ide/signing-in-to-visual-studio.md)

 Figura 1: IDE do Visual Studio

 ![Configurações do IDE com o Visual C&#43;&#43; aplicadas](../ide/media/c-ide-defaultenvironmentlayout.png "|::ref1::|")

 Depois de abrir o Visual Studio, você poderá ver as três partes básicas do IDE: janelas de ferramenta, menus e barras de ferramentas e o espaço da janela principal. As janelas de ferramentas estão encaixadas nos lados esquerdo e direito da janela do aplicativo, com **Início Rápido**, a barra de menus e a barra de ferramentas padrão na parte superior. O centro da janela do aplicativo contem a **Página Inicial**. Quando você abre uma solução ou um projeto, editores e designers aparecem neste espaço. Ao desenvolver um aplicativo, você passará a maior parte do seu tempo nessa área central.

## <a name="BKMK_CreateApp"></a> Criar um aplicativo simples
 Quando você cria um aplicativo no Visual Studio, primeiro cria um projeto e uma solução. Para este exemplo, você criará um aplicativo de console do Windows.

#### <a name="to-create-a-console-app"></a>Para criar um aplicativo do console

1. Na barra de menus, escolha **Arquivo**, **Novo**, **Projeto**.

    ![Na barra de menus, escolha Arquivo, Novo, Projeto](../ide/media/exploreide-filenewproject.png "|::ref2::|")

2. Na categoria **Visual C++** , escolha o modelo **Aplicativo do Console Win32** e nomeie o projeto como `GreetingsConsoleApp`.

    ![Modelo Aplicativo do Console Win32](../ide/media/c-ide-newprojectdlg.png "|::ref3::|")

3. Quando o Assistente de Aplicativo Win32 aparecer, escolha o botão **Finalizar**.

    ![Assistente de aplicativo de console do Win32](../ide/media/c-ide-win32consoleappwizard.png "|::ref4::|")

   O projeto e a solução GreetingsConsoleApp, com os arquivos básicos para um aplicativo de console Win32, são criados e automaticamente carregados no **Gerenciador de Soluções**. O arquivo GreetingsConsoleApp.cpp é aberto no editor de códigos. Os seguintes itens aparecem no **Gerenciador de Soluções**:

   Figura 4: Itens do projeto

   ![Arquivos para a solução no Gerenciador de Soluções](../ide/media/c-ide-solutioncontents.png "|::ref5::|")

## <a name="BKMK_AddCode"></a> Adicionar código ao aplicativo
 Em seguida, você adicionará código para exibir a palavra “Hello” na janela do console.

#### <a name="to-display-hello-in-the-console-window"></a>Para exibir “Hello” na janela do console

1. No arquivo GreetingsConsoleApp.cpp, insira uma linha em branco antes da linha `return 0;` e então insira o código a seguir:

    ```
    cout << "Hello\n";
    ```

     Uma pequena linha vermelha aparecerá em `cout`. Uma mensagem de erro aparecerá se você apontar para ele.

     ![Texto de erro para o cout](../ide/media/c-ide-couterror.png "|::ref6::|")

     A mensagem de erro também aparece na janela **Lista de Erros**. Você pode exibir a janela, na barra de menus, escolhendo **Exibir**, **Lista de Erros**.

     [cout](https://msdn.microsoft.com/library/d87db6c3-e4e1-4d09-9ec5-458f55018257) está incluído no arquivo de cabeçalho \<iostream\>.

2. Para incluir o cabeçalho iostream, digite o seguinte código após `#include "stdafx.h"`:

    ```
    #include \<iostream\>
    using namespace std;
    ```

     Você provavelmente observou que apareceu uma caixa quando o código foi inserido, fornecendo sugestões para os caracteres inseridos. Essa caixa é parte do IntelliSense do C++, que fornece prompts de codificação, incluindo a listagem de classes ou membros da interface e informações de parâmetro. Você também pode usar snippets de código, que são blocos de código predefinidos. Para obter mais informações, consulte [Usando IntelliSense](../ide/using-intellisense.md) e [Snippets de código](../ide/code-snippets.md).

     A pequena linha vermelha em `cout` desaparecerá quando você corrigir o erro.

3. Salve as alterações no arquivo.

     ![Código que corrige o erro cout](../ide/media/c-ide-coutfix.png "|::ref7::|")

## <a name="BKMK_DebugTest"></a> Depurar e testar o aplicativo
 Você pode depurar o GreetingsConsoleApp para ver se a palavra "Hello" aparece na janela do console.

#### <a name="to-debug-the-application"></a>Para depurar o aplicativo

- Inicie o depurador.

     ![Comando Iniciar Depuração no menu Depurar](../ide/media/exploreide-startdebugging.png "|::ref8::|")

     O depurador inicia e executa o código. A janela de console (uma janela separada que se parece com um prompt de comando) é exibida por alguns segundos mas fecha rapidamente quando o depurador interrompe a execução. Para ver o texto, você precisa definir um ponto de interrupção para interromper a execução do programa.

#### <a name="to-add-a-breakpoint"></a>Para adicionar um ponto de interrupção

1. Adicione um ponto de interrupção da barra de menus na linha `return 0;`. Você também pode clicar na margem esquerda para definir um ponto de interrupção.

    ![Comando Ativar/Desativar ponto de interrupção no menu Depurar](../ide/media/exploreide-togglebreakpoint.png "|::ref9::|")

    Um círculo vermelho aparece ao lado da linha de código na margem da extrema esquerda da janela do editor.

2. Pressione a tecla F5 para iniciar a depuração.

    O depurador é iniciado e uma janela de console aparece mostrando a palavra **Hello**.

    ![Texto de saudação na janela do prompt de comando do Windows](../ide/media/c-ide-hellocommandwindow.png "|::ref10::|")

3. Pressione SHIFT + F5 para parar a depuração.

   Para obter mais informações, consulte [Projetos de console](../debugger/debugging-preparation-console-projects.md).

## <a name="BKMK_BuildRelease"></a> Criar uma versão de lançamento do aplicativo
 Agora que você verificou que tudo está funcionando, já pode preparar uma versão de lançamento do aplicativo.

#### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Para limpar os arquivos de solução e criar uma versão de lançamento

1. Da barra de menus, exclua os arquivos intermediários e os arquivos de saída criados durante compilações anteriores.

    ![O comando Limpar Solução no menu Compilar](../ide/media/exploreide-cleansolution.png "|::ref11::|")

2. Altere a configuração de build para GreetingsConsoleApp de **Depuração** para **Versão**.

    ![Criar uma versão de lançamento do aplicativo](../ide/media/c-ide-changingbuildtorelease.png "|::ref12::|")

3. Compile a solução.

    ![Comando Compilar Solução no menu Compilar](../ide/media/exploreide-buildsolution.png "|::ref13::|")

   Parabéns por concluir este passo a passo! Se desejar explorar mais exemplos, consulte [Amostras do Visual Studio](../ide/visual-studio-samples.md).

## <a name="see-also"></a>Veja também
 [Passo a passo: Criar um aplicativo simples](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md) [Dicas de produtividade](../ide/productivity-tips-for-visual-studio.md) [Exemplos do Visual Studio](../ide/visual-studio-samples.md) [Introdução ao desenvolvimento com o Visual Studio](../ide/get-started-developing-with-visual-studio.md)
