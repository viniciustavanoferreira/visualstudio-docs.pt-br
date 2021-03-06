---
title: Criar um aplicativo Node.js e React
description: Neste tutorial, você cria um aplicativo usando ferramentas Node.js para Visual Studio
ms.custom: ''
ms.date: 4/21/2020
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: c6813e0ad482bb211269c9da3950842dda7f6abd
ms.sourcegitcommit: a7f781d5a089e6aab6b073a07f3d4d2967af8aa6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81760087"
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>Tutorial: Criar um aplicativo Node.js e React no Visual Studio

O Visual Studio permite que você crie um projeto do Node.js com facilidade e aproveite o IntelliSense e outros recursos internos compatíveis com Node.js. Neste tutorial para Visual Studio, você cria um projeto de aplicativo Web Node.js de um modelo do Visual Studio. Em seguida, você cria um aplicativo simples usando o React.

Neste tutorial, você aprenderá como:
> [!div class="checklist"]
> * Criar um projeto Node.js
> * Adicionar pacotes npm
> * Adicionar código React ao seu aplicativo
> * Transcompilar JSX
> * Anexar o depurador

## <a name="before-you-begin"></a>Antes de começar

Aqui está algumas perguntas frequentes rápidas para apresentar alguns conceitos principais.

### <a name="what-is-nodejs"></a>O que é o Node.js?

O Node.js é um ambiente de runtime do JavaScript do servidor que executa o JavaScript no servidor.

### <a name="what-is-npm"></a>O que é o npm?

npm é o gerenciador de pacotes padrão do Node.js. O gerenciador de pacotes facilita para os programadores publicar e compartilhar o código-fonte das bibliotecas do Node.js e foi projetado para simplificar a instalação, a atualização e a desinstalação de bibliotecas.

### <a name="what-is-react"></a>O que é React?

O React é uma estrutura de front-end para criar uma interface do usuário.

### <a name="what-is-jsx"></a>O que é o JSX?

O JSX é uma extensão da sintaxe de JavaScript, normalmente usada com o React para descrever os elementos de interface do usuário. O código JSX deve ser transcompilado para JavaScript simples antes que possa ser executado em um navegador.

### <a name="what-is-webpack"></a>O que é o webpack?

O webpack empacota arquivos JavaScript para que eles possam ser executados em um navegador. Ele também pode transformar ou empacotar outros recursos e ativos. Geralmente, é usado para especificar um compilador, como Babel ou TypeScript, para transcompilar código JSX ou TypeScript para JavaScript simples.

## <a name="prerequisites"></a>Pré-requisitos

* Você precisa ter o Visual Studio instalado e a carga de trabalho de desenvolvimento de Node.js.

    ::: moniker range=">=vs-2019"
    Se você ainda não instalou o Visual Studio 2019, acesse a página [de downloads](https://visualstudio.microsoft.com/downloads/) do Visual Studio para instalá-lo gratuitamente.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Se você ainda não instalou o Visual Studio 2017, acesse a página [de downloads](https://visualstudio.microsoft.com/downloads/) do Visual Studio para instalá-lo gratuitamente.
    ::: moniker-end

    Se você precisa instalar a carga de trabalho, mas já tem o Visual Studio, vá para **Ferramentas** > **Obter Ferramentas e Recursos...**, que abre o Visual Studio Installer. Escolha a carga de trabalho **Desenvolvimento de Node.js** e, em seguida, selecione **Modificar**.

    ![Carga de trabalho Node.js no instalador do VS](../ide/media/quickstart-nodejs-workload.png)

* Você precisa ter o runtime do Node.js instalado.

    Este tutorial foi testado com a versão 12.6.2.

    Se você não o tiver instalado, recomendamos que você instale a versão LTS do site [node.js](https://nodejs.org/en/download/) para melhor compatibilidade com frameworks e bibliotecas externas. O Node.js é construído para arquiteturas de 32 bits e 64 bits. As ferramentas Node.js no Visual Studio, incluídas na carga de trabalho do Node.js, suportam ambas as versões. Apenas um é necessário e o instalador Node.js suporta apenas um sendo instalado por vez.
    
    Em geral, o Visual Studio detecta automaticamente o runtime do Node.js instalado. Se ele não detectar um tempo de execução instalado, você poderá configurar seu projeto para referenciar o tempo de execução instalado na página de propriedades (depois de criar um projeto, clique com o botão direito do mouse no nó do projeto, escolha **Propriedades**e defina o **caminho Node.exe**). Você pode usar uma instalação global do Node.js ou pode especificar o caminho para um intérprete local em cada um de seus projetos Node.js. 

## <a name="create-a-project"></a>Criar um projeto

Primeiro, crie um projeto de aplicativo Web Node.js.

1. Abra o Visual Studio.

1. Criar um novo projeto.

    ::: moniker range=">=vs-2019"
    Pressione **Esc** para fechar a janela de início. Digite **Ctrl + Q** para abrir a caixa de pesquisa, **digite Node.js,** em seguida, escolha **Blank Node.js Web Application - JavaScript**. (Embora este tutorial use o compilador TypeScript, as etapas exigem que você comece com o modelo **JavaScript.)**
    
    Na caixa de diálogo que aparece, escolha **Criar**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Na barra de menu superior, escolha **Arquivo** > **Novo** > **Projeto**. No painel esquerdo da caixa de diálogo **Novo Projeto**, expanda **JavaScript** e escolha **Node.js**. No painel central, escolha **Aplicativo Web Node.js em Branco**, digite o nome **NodejsWebAppBlank** e escolha **OK**.
    ::: moniker-end
    Se você não ver o modelo de projeto **Dode.js Web Application em branco,** você deve adicionar a carga de trabalho **de desenvolvimento Node.js.** Confira instruções detalhadas nos [Pré-requisitos](#prerequisites).

    O Visual Studio cria a nova solução e abre seu projeto.

    ![Projeto Node.js no Gerenciador de Soluções](../javascript/media/tutorial-nodejs-react-project-structure.png)

    (1) Realçado em **negrito** no projeto, usando o nome fornecido na caixa de diálogo **Novo Projeto**. No sistema de arquivos, este projeto é representado por um arquivo *.njsproj* na pasta do projeto. Você pode definir propriedades e variáveis de ambiente associadas ao projeto clicando com o botão direito do mouse no projeto e escolhendo **Propriedades**. Você pode fazer o ciclo com outras ferramentas de desenvolvimento, porque o arquivo de projeto não faz alterações personalizadas na fonte do projeto Node.js.

    (2) No nível superior, há uma solução que, por padrão, tem o mesmo nome do projeto. Uma solução, representada por um arquivo *.sln* no disco, é um contêiner para um ou mais projetos relacionados.

    (3) O nó do npm mostra os pacotes npm instalados. Clique com o botão direito do mouse no nó do npm para pesquisar e instalar pacotes npm usando uma caixa de diálogo ou instalar e atualizar pacotes usando as configurações de *package.json* e as opções de clique com o botão direito do mouse no nó do npm.

    (4) *package.json* é um arquivo usado pelo npm para gerenciar versões e dependências de pacote para os pacotes instalados localmente. Para obter mais informações, consulte [Gerenciar pacotes npm](../javascript/npm-package-management.md).

    (5) Arquivos de projeto como *server.js* aparecem no nó do projeto. *server.js* é o arquivo de inicialização do projeto e é por isso que ele é exibido em **negrito**. Defina o arquivo de inicialização clicando com o botão direito do mouse em um arquivo no projeto e selecionando **Definir como arquivo de inicialização do Node.js**.

## <a name="add-npm-packages"></a>Adicionar pacotes npm

Este aplicativo requer um número de módulos npm para ser executado corretamente.

* react
* react-dom
* express
* caminho
* ts-loader
* typescript
* webpack
* webpack-cli

1. No Gerenciador de Soluções (painel direito), clique com botão direito do mouse no nó **npm** do projeto e escolha **Instalar Novos Pacotes npm**.

    Na caixa de diálogo **Instalar Novos Pacotes npm**, você pode optar por instalar a versão mais recente do pacote ou especificar uma versão. Se você optar por instalar a versão atual desses pacotes, mas encontrar erros inesperados mais tarde, você pode querer instalar as versões exatas do pacote descritas mais tarde nessas etapas.

1. Na caixa de diálogo **Instalar Novos Pacotes npm**, procure o pacote react e selecione **Instalar Pacote** para instalá-lo.

    ![Instalar pacotes npm](../javascript/media/tutorial-nodejs-react-install-package.png)

    Selecione a janela de **Saída** para ver o progresso da instalação do pacote (selecione **Npm** no campo **Mostrar saída de**). Quando instalado, o pacote é exibido sob o nó **npm**.

    O arquivo *package.json* do projeto é atualizado com as informações do novo pacote, incluindo a versão do pacote.

1. Em vez de usar a interface do usuário para pesquisar e adicionar o restante dos pacotes um de cada vez, cole o seguinte código em *package.json*. Para fazer isso, adicione uma seção `dependencies` com este código:

    ```json
    "dependencies": {
      "express": "~4.17.1",
      "path": "~0.12.7",
      "react": "~16.13.1",
      "react-dom": "~16.13.1",
      "ts-loader": "~7.0.1",
      "typescript": "~3.8.3",
      "webpack": "~4.42.1",
      "webpack-cli": "~3.3.11"
    }
    ```

    Se já houver uma seção `dependencies` em sua versão do modelo em branco, basta substituí-la pelo código JSON anterior. Para obter mais informações sobre o uso deste arquivo, consulte [a configuração package.json](../javascript/configure-packages-with-package-json.md).

1. Salve as alterações.

1. Clique com o botão direito do mouse no nó **npm** em seu projeto e escolha **Instalar pacotes npm**.

    Este comando executa diretamente o comando npm install.

    No painel inferior, escolha a janela de **Saída** para ver o progresso da instalação dos pacotes. A instalação pode levar alguns minutos e talvez você não veja os resultados imediatamente. Para ver a saída, verifique se marcou **Npm** no campo **Mostrar saída de** na janela de **Saída**.

    Estes são os módulos npm que aparecem no Gerenciador de Soluções após a instalação.

    ![Pacotes npm](../javascript/media/tutorial-nodejs-react-npm-modules-installed.png)

    > [!NOTE]
    > Se você preferir instalar pacotes npm usando a linha de comando, clique com o botão direito do mouse no nó do projeto e escolha **Abrir Prompt de Comando Aqui**. Usar comandos padrão do Node.js para instalar pacotes.

## <a name="add-project-files"></a>Adicionar arquivos de projeto

Nestas etapas, você adiciona quatro novos arquivos ao seu projeto.

* *app.tsx*
* *webpack-config.js*
* *Index.html*
* *tsconfig.json*

Para este aplicativo simples, você pode adicionar novos arquivos de projeto à raiz do projeto. (Na maioria dos aplicativos, normalmente você adiciona os arquivos a subpastas e ajusta adequadamente as referências do caminho relativo).

1. No Gerenciador de Soluções, clique com o botão direito do mouse no projeto **NodejsWebAppBlank** e escolha **Adicionar** > **Novo Item**.

1. Na caixa de diálogo **Adicionar novo item,** escolha **o arquivo TypeScript JSX,** digite o nome *app.tsx*e selecione **Adicionar** ou **OK**.

1. Repita essas etapas para adicionar *webpack-config.js*. Em vez de um arquivo JSX TypeScript, escolha **Arquivo JavaScript**.

1. Repita as mesmas etapas para adicionar *index.html* ao projeto. Em vez de um arquivo JavaScript, escolha **Arquivo HTML**.

1. Repita as mesmas etapas para adicionar *tsconfig.json* ao projeto. Em vez de um arquivo JavaScript, escolha **Arquivo de Configuração JSON do TypeScript**.

## <a name="add-app-code"></a>Adicionar código do aplicativo

1. Abra *server.js* e substitua o código existente pelo seguinte código:

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   O código anterior usa o Express para iniciar o Node.js como seu servidor de aplicativos Web. Esse código define a porta como o número da porta configurado nas propriedades do projeto (por padrão, a porta é configurada como 1337 nas propriedades). Para abrir as propriedades do projeto, clique com o botão direito do mouse no Gerenciador de Soluções e escolha **Propriedades**.

1. Abra *app.tsx* e adicione o seguinte código:

    ```javascript
    declare var require: any

    var React = require('react');
    var ReactDOM = require('react-dom');

    export class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    O código anterior usa a sintaxe JSX e o React para exibir uma mensagem simples.

1. Abra *index.html* e substitua a seção **body** pelo código a seguir:

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    Esta página HTML carrega *app-bundle.js*, que contém o código de JSX e React transcompilado para JavaScript simples. Atualmente, *app-bundle.js* é um arquivo vazio. Na próxima seção, você configura opções para transcompilar o código.

## <a name="configure-webpack-and-typescript-compiler-options"></a>Configurar webpack e opções do compilador TypeScript

Nas etapas anteriores, você adicionou *webpack-config.js* ao projeto. Em seguida, você adiciona o código de configuração do webpack. Você adicionará uma configuração de webpack simples que especifica um arquivo de entrada (*app.tsx*) e um arquivo de saída (*app-bundle.js*) para agrupar e transcompilar JSX para JavaScript simples. Para transcompilar, você também configura algumas opções do compilador TypeScript. Esse código é uma configuração básica que serve como uma introdução ao webpack e ao compilador TypeScript.

1. No Gerenciador de Soluções, abra *webpack-config.js* e adicione o código a seguir.

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    O código de configuração do webpack instrui o webpack a usar o carregador de TypeScript para transcompilar o JSX.

1. Abra *tsconfig.json* e substitua o código padrão pelo seguinte código, que especifica as opções do compilador TypeScript:

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    *app.tsx* é especificado como o arquivo de origem.

## <a name="transpile-the-jsx"></a>Transcompilar o JSX

1. No Gerenciador de Soluções, clique com o botão direito do mouse no nó do projeto e escolha **Abrir Prompt de Comando Aqui**.

1. No prompt de comando, digite o seguinte comando:

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    A janela do prompt de comando mostra o resultado.

    ![Execute o webpack](../javascript/media/tutorial-nodejs-react-run-webpack-cmd.png)

    Se encontrar erros em vez da saída anterior, você precisará resolvê-para que seu aplicativo funcione. Se as versões de seu pacote npm forem diferentes das versões mostradas neste tutorial, isso poderá ser uma fonte de erros. Uma maneira de corrigir erros é usar as versões exatas mostradas nas etapas anteriores. Além disso, se uma ou mais dessas versões de pacote tiver sido preterida e gerar um erro, talvez você precise instalar uma versão mais recente para corrigir erros. Para obter informações sobre como usar *package.json* para controlar as versões do pacote de npm, confira [Configuração de package.json](../javascript/configure-packages-with-package-json.md).

1. No Solution Explorer, clique com o botão direito do mouse no nó do projeto e escolha **Adicionar** > **pasta existente,** em seguida, escolha a pasta *dist* e escolha **Selecionar pasta**.

    O Visual Studio adiciona a pasta *dist* ao projeto que contém *app-bundle.js* e *app-bundle.js.map*.

1. Abra *app-bundle.js* para ver o código JavaScript transcompilado.

1. Caso seja solicitado que você recarregue os arquivos modificados externamente, selecione **Sim para Todos**.

    ![Carregar arquivos modificados](../javascript/media/tutorial-nodejs-react-reload-files.png)

Cada vez que fizer alterações em *app.tsx*, você precisará executar novamente o comando webpack. Para automatizar esta etapa, adicione um script de build para transcompilar o JSX.

## <a name="add-a-build-script-to-transpile-the-jsx"></a>Adicionar um script de build para transcompilar o JSX

Do Visual Studio 2019 em diante, é necessário um script de build. Em vez de transcompilar o JSX na linha de comando (conforme mostrado na seção anterior), é possível transcompilar o JSX ao compilar com base no Visual Studio.

* Abra *package.json* e adicione a seguinte seção após a seção `dependencies`:

   ```json
   "scripts": {
    "build": "webpack-cli app.tsx --config webpack-config.js"
   }
   ```

## <a name="run-the-app"></a>Executar o aplicativo

1. Selecione **o Web Server (Google Chrome)** ou o Web Server **(Microsoft Edge)** como o destino de depuração atual.

    ::: moniker range=">=vs-2019"
    ![Selecione o Chrome como destino de depuração](../javascript/media/vs-2019/tutorial-nodejs-react-debug-target.png)
    ::: moniker-end
    ::: moniker range="vs-2017"
    ![Selecione o Chrome como destino de depuração](../javascript/media/tutorial-nodejs-react-debug-target.png)
    ::: moniker-end

    Se o Chrome estiver disponível em seu computador, mas não aparecer como uma opção, escolha **Procurar com** na lista suspensa de destinos de depuração e selecione Chrome como o destino padrão de navegador (escolha **Definir como padrão**).

1. Para executar o aplicativo, pressione **F5** (**Depurar** > **Iniciar Depuração**) ou no botão de seta verde.

    É aberta uma janela do console do Node.js mostrando a porta na qual o depurador está escutando.

    O Visual Studio inicia o aplicativo iniciando o arquivo de inicialização, *server.js*.

    ![Execute o React no navegador](../javascript/media/tutorial-nodejs-react-running-react.png)

1. Feche a janela do navegador.

1. Feche a janela do console.

## <a name="set-a-breakpoint-and-run-the-app"></a>Defina um ponto de interrupção e execute o aplicativo

1. Em *server.js*, clique na medianiz à esquerda da declaração `staticPath` para definir um ponto de interrupção:

    ![Definir um ponto de interrupção](../javascript/media/tutorial-nodejs-react-set-breakpoint.png)

    Pontos de interrupção são o recurso mais básico e essencial da depuração confiável. Um ponto de interrupção indica quando o Visual Studio deve suspender o código em execução para que você possa examinar os valores das variáveis ou o comportamento de memória ou se uma ramificação de código está sendo executada ou não.

1. Para executar o aplicativo, pressione **F5** (**Depurar** > **Iniciar Depuração**).

    O depurador pausa no ponto de interrupção definido (a instrução atual é marcada em amarelo). Agora, você pode inspecionar o estado do aplicativo passando o mouse sobre as variáveis que estão no escopo, usando as janelas do depurador, como **Locais** e **Inspecionar**.

1. Pressione **F5** para continuar o aplicativo.

1. Se você quiser usar as ferramentas do Chrome Developer ou F12 para o Microsoft Edge, **pressione F12**. Você pode usar essas ferramentas para examinar o DOM e interagir com o aplicativo usando o Console do JavaScript.

1. Feche o navegador da Web e o console.

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>Defina e atinja um ponto de interrupção no código do React do lado do cliente

Na seção anterior, você anexou o depurador ao código do Node.js do lado do servidor. Para anexar o depurador do Visual Studio e atingir pontos de interrupção no código do React lado do cliente, o depurador precisa de ajuda para identificar o processo correto. Esta é uma maneira de permitir isso.

### <a name="prepare-the-browser-for-debugging"></a>Prepare o navegador para depuração

::: moniker range=">=vs-2019"
Para este cenário, use o Microsoft Edge (Chromium), atualmente chamado **Microsoft Edge Beta** no IDE, ou Chrome.
::: moniker-end
::: moniker range="vs-2017"
Para este cenário, use o Chrome.
::: moniker-end

1. Feche todas as janelas para o navegador alvo.

   Outras instâncias do navegador podem impedir que o navegador seja aberto com a depuração ativada. (As extensões do navegador podem estar executando e impedindo o modo de depuração total, então você pode precisar abrir o Gerenciador de tarefas para encontrar instâncias inesperadas do Chrome.)

   ::: moniker range=">=vs-2019"
   Para o Microsoft Edge (Chromium), também desligue todas as instâncias do Chrome. Como ambos os navegadores compartilham a base de código de cromo, isso dá os melhores resultados.
   ::: moniker-end

2. Inicie seu navegador com a depuração ativada.

    ::: moniker range=">=vs-2019"
    A partir do Visual Studio 2019, você pode definir `--remote-debugging-port=9222` o sinalizador no lançamento do navegador selecionando Procurar **com...** > na barra de ferramentas **Debug,** depois escolhendo **Adicionar**, e, em seguida, definir o sinalizador no campo **Argumentos.** Use um nome amigável diferente para o navegador, como **Edge com Depuração** ou **Chrome com Depuração**. Para obter detalhes, confira [Notas sobre a versão](/visualstudio/releases/2019/release-notes-v16.2).

    ![Defina seu navegador para abrir com a depuração ativada](../javascript/media/tutorial-nodejs-react-edge-with-debugging.png)

    Alternativamente, abra o comando **Executar** a partir do **botão** Iniciar do Windows (clique com o botão direito do mouse e escolha **Executar),** e digite o seguinte comando:

    `msedge --remote-debugging-port=9222`

    ou

    `chrome.exe --remote-debugging-port=9222`
    ::: moniker-end

    ::: moniker range="vs-2017"
    Abra o comando **Executar** do botão **Iniciar** do Windows (clique com o botão direito do mouse e escolha **Executar**) e digite o seguinte comando:

    `chrome.exe --remote-debugging-port=9222`
    ::: moniker-end

    Isso inicia o seu navegador com a depuração ativada.

    O aplicativo ainda não está sendo executado, então você recebe uma página de navegador vazia.

### <a name="attach-the-debugger-to-client-side-script"></a>Anexar o depurador ao script do lado do cliente

1. Mude para o Visual Studio e, em seguida, defina um ponto de ruptura em seu código-fonte, seja *app-bundle.js* ou *app.tsx*.

    Para *app-bundle.js,* defina o `render()` ponto de ruptura na função como mostrado na ilustração a seguir:

    ![Definir um ponto de interrupção](../javascript/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

    Para encontrar `render()` a função no arquivo transpiledo *app-bundle.js,* use **Ctrl**+**F** **(Editar** > **encontrar e substituir o** > **quick find**).

    Para *app.tsx,* defina o `render()` ponto de `return` partida dentro da função, na declaração.

    ![Definir um ponto de interrupção](../javascript/media/tutorial-nodejs-react-set-breakpoint-in-tsx-file.png)

2. Se você estiver definindo o ponto de breakpoint no arquivo *.tsx* (em vez *de app-bundle.js),* você precisa atualizar *webpack-config.js*. Substitua o código a seguir:

    ```javascript
    output: {
        filename: "./app-bundle.js",
    },
    ```

    por este código:

    ```javascript
    output: {
        filename: "./app-bundle.js",
        devtoolModuleFilenameTemplate: '[resource-path]'  // removes the webpack:/// prefix
    },
    ```

    Esta é uma configuração somente de desenvolvimento para permitir a depuração no Visual Studio. Essa configuração permite que você sobreponha as referências geradas no arquivo do mapa de origem, *app-bundle.js.map*, ao construir o aplicativo. Por padrão, as referências do webpack no arquivo do mapa de origem incluem o prefixo *webpack:///,* que impede o Visual Studio de encontrar o arquivo de origem, *app.tsx*. Especificamente, quando você faz essa alteração, a referência ao arquivo de origem, *app.tsx*, é alterada de *webpack:///./app.tsx* para *./app.tsx*, o que permite a depuração.

3. Selecione seu navegador de destino como alvo de depuração no Visual Studio e pressione **Ctrl**+**F5** **(Debug** > **Start Without Debugging)** para executar o aplicativo no navegador.

    ::: moniker range=">=vs-2019"
    Se você criou uma configuração de navegador com um nome amigável, escolha-o como seu destino de depuração.
    ::: moniker-end

    O aplicativo será aberto em uma nova guia do navegador.

4. Escolha **Depurar** > **anexar ao processo**.

    > [!TIP]
    > A partir do Visual Studio 2017, uma vez anexado ao processo pela primeira vez seguindo essas etapas, você pode rapidamente reconectar ao mesmo processo, escolhendo **Debug** > **Reattach to Process**.

5. Na caixa de diálogo **Anexar ao processo,** obtenha uma lista filtrada de instâncias do navegador às as que você pode anexar.

    ::: moniker range=">=vs-2019"
    No Visual Studio 2019, escolha o depurador correto para o seu navegador de destino, **JavaScript (Chrome)** ou **JavaScript (Microsoft Edge - Chromium)** no **Attach to** field, **digite cromo** ou **borda** na caixa de filtro para filtrar os resultados da pesquisa.
    ::: moniker-end
    ::: moniker range="vs-2017"
    No Visual Studio 2017, escolha o **código Webkit** no campo **Anexar ao** campo, digite **cromo** na caixa de filtro para filtrar os resultados da pesquisa.
    ::: moniker-end

6. Selecione o processo do navegador com a porta host correta (host local neste exemplo) e selecione **'Anexar '''''''''''''**

    A porta (1337) também pode aparecer no campo **Título** para ajudá-lo a selecionar a instância correta do navegador.

    ::: moniker range=">=vs-2019"
    O exemplo a seguir mostra como isso parece para o navegador Microsoft Edge (Chromium).

    ![Anexar ao processo](../javascript/media/tutorial-nodejs-react-attach-to-process-edge.png)
    ::: moniker-end
    ::: moniker range="vs-2017"
    ![Anexar ao processo](../javascript/media/tutorial-nodejs-react-attach-to-process.png)

    Você sabe que o depurador foi anexado corretamente quando o Explorador do DOM e o Console do JavaScript são abertos no Visual Studio. Essas ferramentas de depuração são semelhantes às Ferramentas para Desenvolvedores do Chrome e às Ferramentas F12 do Microsoft Edge.
    ::: moniker-end

    > [!TIP]
    > Se o depurador não for anexado e a mensagem "Não é possível anexar ao processo. Uma operação não é legal no estado atual.", use o Gerenciador de tarefas para fechar todas as instâncias do navegador de destino antes de iniciar o navegador no modo de depuração. As extensões do navegador podem estar sendo executados e impedindo o modo de depuração total.

7. Como o código com o ponto de interrupção já foi executado, atualize a página do navegador para atingir o ponto de interrupção.

    Enquanto estiver em pausa no depurador, você pode examinar o estado do aplicativo passando o mouse sobre as variáveis e usando as janelas do depurador. Você pode avançar o depurador percorrendo o código (**F5**, **F10** e **F11**). Para obter mais informações sobre recursos básicos de depuração, consulte [Primeiro, veja o depurador](../debugger/debugger-feature-tour.md).

    Você pode atingir o ponto de ruptura em *app-bundle.js* ou em sua localização mapeada no *app.tsx,* dependendo de quais passos você seguiu anteriormente, juntamente com seu ambiente e estado do navegador. De qualquer forma, você pode percorrer o código e examinar as variáveis.

   * Se você precisar entrar no código em *app.tsx* e não conseguir, use **Anexar ao Processo**, conforme descrito nas etapas anteriores para anexar o depurador. Certifique-se de que seu ambiente está configurado corretamente:

      * Você fechou todas as instâncias do navegador, incluindo extensões do Chrome (usando o Gerenciador de tarefas), para que você possa executar o navegador no modo de depuração. Certifique-se de iniciar o navegador no modo de depuração.

      * Certifique-se de que o arquivo do mapa de origem inclua uma referência a *./app.tsx* e não *webpack:///./app.tsx,* o que impede que o depurador do Visual Studio localize *o app.tsx*.
       Alternativamente, se você precisar invadir o código no *app.tsx* e `debugger;` não conseguir fazê-lo, tente usar a declaração em *app.tsx*, ou defina pontos de interrupção nas Ferramentas do Desenvolvedor Chrome (ou Ferramentas F12 para microsoft edge) em vez disso.

   * Se você precisar invadir o código no *app-bundle.js* e não conseguir fazê-lo, remova o arquivo do mapa de origem, *app-bundle.js.map*.

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Implantar o aplicativo no Serviço de Aplicativo do Linux](../javascript/publish-nodejs-app-azure.md)
