---
title: Desenvolvimento Móvel Multiplataforma no Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 10/17/2019
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 8202717a-e990-45cf-b092-438651ccb38a
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- multiple
ms.openlocfilehash: c7f40f656b533949748a7eb2ab88ea3d2b1d5923
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "78234976"
---
# <a name="cross-platform-mobile-development-in-visual-studio"></a>Desenvolvimento móvel multiplataforma no Visual Studio

É possível criar aplicativos para dispositivos Android, iOS e Windows usando o Visual Studio.  Ao projetar seu aplicativo, use as ferramentas do Visual Studio para adicionar serviços conectados com facilidade, como Office 365, Serviço de Aplicativo do Azure e Application Insights.

Compile seus aplicativos usando o C# e o .NET Framework, HTML e JavaScript ou o C++. Compartilhe código, cadeias de caracteres, imagens e, em alguns casos, até mesmo a interface do usuário.

Se você desejar criar um jogo ou aplicativo gráfico imersivo, instale as ferramentas do Visual Studio para Unity e aproveite todos os recursos de produtividade avançados do Visual Studio com o Unity, o mecanismo popular de jogos/elementos gráficos multiplataforma e o ambiente de desenvolvimento para aplicativos executados no iOS, Android, Windows e em outras plataformas.

## <a name="build-an-app-for-android-ios-and-windows-net-framework"></a>Compilar um aplicativo para Android, iOS e Windows (.NET Framework)

![Dispositivos](../cross-platform/media/homedevices.png "HomeDevices")

Com as Ferramentas do Visual Studio para Xamarin, é possível ter o Android, o iOS e o Windows como destino na mesma solução, compartilhando o código e, até mesmo, a interface do usuário.

|**Saiba mais**|
|--------------------|
|[Instalar o Visual Studio](https://visualstudio.microsoft.com/vs/community/) (VisualStudio.com)|
|[Saiba mais sobre o Xamarin no Visual Studio](https://visualstudio.microsoft.com/xamarin/) (VisualStudio.com)|
|[Documentação de desenvolvimento de aplicativos móveis do Xamarin](/xamarin/) |
|[DevOps com aplicativos Xamarin](/xamarin/tools/ci/devops/) |
|[Conheça os aplicativos do Universal Windows no Visual Studio](https://visualstudio.microsoft.com/vs/universal-windows-platform/) (VisualStudio.com)|
|[Saiba mais sobre as semelhanças entre o Swift e o C#](https://aka.ms/scposter) (download.microsoft.com)|

### <a name="target-android-ios-and-windows-from-a-single-code-base"></a><a name="AndroidHTML"></a> Ter o Android, iOS e Windows como destino por meio de uma única base de código

 Você pode criar aplicativos nativos para Android, iOS e Windows usando C# ou F# (o Visual Basic não é suportado no momento).  Para começar, instale o Visual Studio, selecione a opção Desenvolvimento Móvel com a opção **.NET** no instalador.

 Se você já tiver o Visual Studio instalado, execute o **Visual Studio Installer** e selecione o mesmo Desenvolvimento Móvel com a opção **.NET** para Xamarin (conforme acima).

 Quando terminar, os modelos de projeto serão exibidos na caixa de diálogo **Novo Projeto**. A maneira mais fácil de encontrar modelos do Xamarin é simplesmente pesquisar em “Xamarin”.

 O Xamarin expõe a funcionalidade nativa do Android, do iOS e do Windows como classes e métodos do .NET. Isso significa que os aplicativos têm acesso completo a APIs nativas e controles nativos e são tão dinâmicos quanto os aplicativos escritos nas linguagens da plataforma nativa.

 Depois de criar um projeto, você aproveitará todos os recursos de produtividade do Visual Studio. Por exemplo, você usará um designer para criar suas páginas e usará o IntelliSense para explorar as APIs nativas das plataformas móveis. Quando estiver pronto para executar o aplicativo e ver a aparência dele, use o emulador do SDK do Android e execute aplicativos do Windows nativamente. Também é possível usar dispositivos Android e Windows vinculados diretamente. Para projetos do iOS, conecte-se a um Mac em rede e inicie o emulador do iOS no Visual Studio ou conecte-se a um dispositivo vinculado.

#### <a name="design-one-set-of-pages-that-render-across-all-devices-by-using-xamarinforms"></a>Criar um conjunto de páginas que são renderizadas em todos os dispositivos usando o Xamarin.Forms

 Dependendo da complexidade do design dos aplicativos, você pode considerar criá-lo usando os modelos do *Xamarin.Forms* no grupo **Aplicativos Móveis** dos modelos do projeto. O Xamarin.Forms é um kit de ferramentas de interface do usuário que permite criar uma única interface que pode ser compartilhada entre o Android, iOS e Windows.  Ao compilar uma solução do Xamarin.Forms, você terá um aplicativo Android, um aplicativo iOS e um aplicativo Windows. Para obter mais detalhes, confira [Saiba mais sobre o desenvolvimento móvel com o Xamarin](/xamarin/cross-platform/get-started/introduction-to-mobile-development/) e [Documentação do Xamarin.Forms](/xamarin/xamarin-forms/).

#### <a name="share-code-between-android-ios-and-windows-apps"></a><a name="ShareHTML"></a> Compartilhar código entre aplicativos Android, iOS e Windows

 Se você não estiver usando o Xamarin.Forms e optar por criar para cada plataforma individualmente, compartilhe a maior parte do código que não é da interface do usuário entre os projetos de plataforma (Android, iOS e Windows). Isso inclui qualquer lógica de negócios, integração de nuvem, acesso a banco de dados ou qualquer outro código destinado ao .NET Framework. O único código que não pode ser compartilhado é aquele que é destinado a uma plataforma específica.

 ![Compartilhar código entre Windows, iOS e Android UIs](../cross-platform/media/sharecode.png "ShareCode")

 Você pode compartilhar o código usando um projeto compartilhado, um projeto de Biblioteca de Classes Portátil ou ambos. Você pode achar que alguns códigos ficam melhores em um projeto compartilhado e outros em um projeto de Biblioteca de Classes Portátil.

|**Saiba mais**|
|--------------------|
|[Opções de compartilhamento de código](/xamarin/cross-platform/app-fundamentals/code-sharing/) (Xamarin) |
|[Opções de compartilhamento de código com o .NET](/dotnet/standard/cross-platform/) |

### <a name="target-windows-10-devices"></a><a name="WindowsHTML"></a>Destino aos dispositivos Windows 10

 ![Dispositivos Windows](../cross-platform/media/windowsdevices.png "Dispositivos Windows")

 Se você desejar criar um único aplicativo que se destina a toda a amplitude de dispositivos Windows 10, crie um aplicativo universal do Windows. Você criará o aplicativo usando um único projeto e as páginas serão renderizadas corretamente, independentemente de qual dispositivo seja usado para exibi-las.

 Comece com um modelo de projeto de aplicativo UWP (Plataforma Universal do Windows). Crie as páginas visualmente e, em seguida, abra-as em uma janela de visualização para ver como são exibidas em vários tipos de dispositivos. Se você não gostar de como uma página é exibida em um dispositivo, poderá otimizá-la para que ela se ajuste melhor ao tamanho da tela, à resolução ou a várias orientações, como modo paisagem ou retrato. Você pode fazer tudo isso usando as janelas de ferramentas intuitivas e as opções de menu facilmente acessíveis no Visual Studio. Quando estiver pronto para executar o aplicativo e executar o código em etapas, você encontrará todos os emuladores e simuladores de dispositivo para diferentes tipos de dispositivos juntos em uma lista suspensa localizada na barra de ferramentas **Padrão**.

|**Saiba mais**|
|--------------------|
|[Introdução à Plataforma Universal do Windows](/windows/uwp/get-started/universal-application-platform-guide)|
|[Crie seu primeiro aplicativo](/windows/uwp/get-started/your-first-app)|
|[Desenvolver aplicativos para a UWP (Plataforma Universal do Windows)](../cross-platform/develop-apps-for-the-universal-windows-platform-uwp.md)|
|[Migrar aplicativos para a UWP (Plataforma Universal do Windows)](https://msdn.microsoft.com/library/mt148501.aspx)|

::: moniker range="vs-2017"

## <a name="build-an-app-for-android-ios-and-windows-htmljavascript"></a><a name="HTML"></a>Construa um aplicativo para Android, iOS e Windows (HTML/JavaScript)

 ![Dispositivos Windows, iOS e Android](../cross-platform/media/homedevices.png "Dispositivos Windows, iOS e Android")

 Se você é desenvolvedor da Web e está familiarizado com HTML e JavaScript, pode direcionar ao Windows, Android e iOS usando as Ferramentas do Visual Studio para Apache Cordova. Esses aplicativos podem ser destinados às três plataformas e você pode criá-los usando as habilidades e os processos com os quais está mais familiarizado.

 O Apache Cordova é uma estrutura que inclui um modelo de plug-in. Esse modelo de plug-in fornece uma única API do JavaScript que pode ser usada para acessar as funcionalidades de dispositivo nativas de todas as três plataformas (Android, iOS e Windows).

 Como essas APIs são multiplataforma, é possível compartilhar a maior parte do que você escreve entre todas as três plataformas. Isso reduz os custos de desenvolvimento e manutenção. Além disso, não é necessário começar do zero. Se você já criou outros tipos de aplicativos Web, poderá compartilhar esses arquivos com o aplicativo Cordova sem precisar modificar ou criá-los novamente de nenhuma maneira.

 ![Aplicativos híbridos de vários dispositivos com JavaScript](../cross-platform/media/multidevicehybridapps.png "Aplicativos híbridos de vários dispositivos com JavaScript")

 Para começar, instale o Visual Studio e escolha a funcionalidade **Desenvolvimento móvel com JavaScript** durante a instalação. As ferramentas do Cordova instalam automaticamente todos os softwares de terceiros necessários para criar seu aplicativo multiplataforma.

 Depois de instalar a extensão, abra o Visual Studio e crie um projeto **Aplicativo em Branco (Apache Cordova)**. Em seguida, é possível desenvolver seu aplicativo usando o JavaScript ou o Typescript. Também é possível adicionar plug-ins para estender a funcionalidade do aplicativo e as APIs de plug-ins são exibidas no IntelliSense à medida que o código é escrito.

 Quando estiver pronto para executar o aplicativo e executar o código em etapas, escolha um emulador, como o emulador Apache Ripple ou o Android Emulator, um navegador ou um dispositivo que você já conectou diretamente ao computador. Em seguida, inicie o aplicativo. Se você estiver desenvolvendo seu aplicativo em um computador Windows, poderá executá-lo nele mesmo. Todas essas opções são criadas no Visual Studio como parte das Ferramentas do Visual Studio para Apache Cordova.

 Os modelos de projeto para a criação de aplicativos UWP (Plataforma Universal do Windows) ainda estão disponíveis no Visual Studio. Portanto, sinta-se à vontade para usá-los se pretende ter somente dispositivos Windows como destino. Se você decidir ter como destino o Android e o iOS posteriormente, poderá portar o código para um projeto do Cordova.

|**Saiba mais**|
|--------------------|
|[Instalar o Visual Studio](https://visualstudio.microsoft.com/vs/community/) (VisualStudio.com)|
|[Introdução às Ferramentas do Visual Studio para Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/)|
|[Saiba mais sobre o Emulador do Visual Studio para Android](https://visualstudio.microsoft.com/vs/msft-android-emulator/) (VisualStudio.com)|

::: moniker-end

<a name="CPP"></a>

## <a name="build-an-app-for-android-ios-and-windows-c"></a>Crie um aplicativo para Android, iOS e Windows (C++)

![Use&#43;&#43; C para construir para Android, iOS e Windows](../cross-platform/media/cross_plat_cpp_intro_image.png "Cross_Plat_CPP_Intro_Image")

 Primeiro, instale o Visual Studio e o Mobile Development com carga de trabalho **C++.** Em seguida, você pode construir um aplicativo de atividade nativa para Android, ou um aplicativo que tenha como alvo o Windows ou iOS. Você pode segmentar Android, iOS e Windows na mesma solução se quiser e, em seguida, compartilhar código entre eles usando uma biblioteca compartilhada estática ou dinâmica entre plataformas.

 Se você precisar criar um aplicativo para o Android que precisa de algum tipo de manipulação avançada de elementos gráficos, como um jogo, poderá usar o C++ para fazer isso. Comece com o projeto **Aplicativo de Atividade Nativa (Android).** Este projeto tem suporte completo na cadeia de ferramentas Clang.

 ![Modelo de projeto de atividade nativa](../cross-platform/media/cross-plat_cpp_native.png "Modelo de projeto de atividade nativa")

 Quando estiver pronto para executar o aplicativo e ver a aparência dele, use o Android Emulator. É rápido, confiável e fácil de instalar e configurar.

 É possível ainda compilar um aplicativo direcionado a toda a amplitude de dispositivos Windows 10 usando o C++ e um modelo de projeto de aplicativo da Plataforma Universal do Windows (UWP). Leia mais sobre isso na seção [Ter dispositivos Windows 10 como destino](#WindowsHTML) mostrada anteriormente neste tópico.

 Você pode compartilhar o código C++ entre Android, iOS e Windows criando uma biblioteca compartilhada estática ou dinâmica.

 ![Bibliotecas estáticas e dinâmicas compartilhadas](../cross-platform/media/cross_plat_cpp_libraries.png "Bibliotecas estáticas e dinâmicas compartilhadas")

 Você pode consumir essa biblioteca em um projeto Windows, iOS ou Android, como os descritos anteriormente nesta seção. Você pode também consumi-la em um aplicativo compilado usando o Xamarin, Java ou qualquer linguagem que permite invocar funções em uma DLL não gerenciada.

 Ao escrever o código nessas bibliotecas, é possível usar o IntelliSense para explorar as APIs nativas das plataformas Android e Windows. Esses projetos de biblioteca são totalmente integrados com o depurador do Visual Studio, para que você defina pontos de interrupção, execute o código em etapas, encontre e corrija problemas usando todos os recursos avançados do depurador.

|**Saiba mais**|
|--------------------|
|[Baixe Visual Studio](https://visualstudio.microsoft.com/downloads/) (VisualStudio.com)|
|[Instale o desenvolvimento móvel multiplataforma com C++](/cpp/cross-platform/install-visual-cpp-for-cross-platform-mobile-development)|
|[Saiba mais sobre como usar C++ para segmentar várias plataformas](https://visualstudio.microsoft.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[Instale o que você precisa e crie um aplicativo de atividade nativo C++ para Android](/cpp/cross-platform/create-an-android-native-activity-app)|
|[Saiba mais sobre o compartilhamento de código C++ com aplicativos Android e Windows](https://visualstudio.microsoft.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[Exemplos de desenvolvimento móvel multiplataforma para C++](/cpp/cross-platform/cross-platform-mobile-development-examples)|

<a name="Unity"></a>

## <a name="build-a-cross-platform-game-for-android-ios-and-windows-by-using-visual-studio-tools-for-unity"></a>Compilar um jogo multiplataforma para o Android, o iOS e o Windows usando as ferramentas do Visual Studio para Unity

 As Ferramentas do Visual Studio para Unity são uma extensão gratuita do Visual Studio que integram as ferramentas avançadas de edição de código, produtividade e depuração do Visual Studio ao *Unity*, o mecanismo popular de jogos/elementos gráficos de plataforma cruzada e o ambiente de desenvolvimento para aplicativos imersivos destinados a Windows, iOS, Android e outras plataformas, incluindo a Web.

 ![Ambiente de desenvolvimento VSTU](../cross-platform/media/vstu_overview.png "Visual Studio Tools for Unity")

 Com o VSTU (Ferramentas do Visual Studio para Unity), é possível usar o Visual Studio para escrever scripts de jogo e editor em C# e, em seguida, usar seu depurador avançado para encontrar e corrigir erros. A última versão do VSTU traz suporte para o Unity 2018.1 e inclui a coloração de sintaxe da linguagem de sombreador ShaderLab do Unity, uma melhor sincronização com o Unity, uma depuração mais avançada e uma geração de código aprimorada para o assistente MonoBehavior. O VSTU também leva seus arquivos de projeto do Unity, mensagens do console e a capacidade de iniciar seu jogo para o Visual Studio, para que você possa gastar menos tempo mudando do e para o Editor do Unity durante a escrita do código.

|**Saiba mais**|
|--------------------|
|[Saiba mais sobre como criar jogos do Unity com o Visual Studio](https://visualstudio.microsoft.com/vs/features/game-development/#tab-4b0d0be8de5f65564ad)|
|[Leia mais sobre as Ferramentas do Visual Studio para Unity](../cross-platform/visual-studio-tools-for-unity.md) |
|[Começar a usar as Ferramentas do Visual Studio para Unity](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) |
|[Leia mais sobre as últimas melhorias à Visualização das Ferramentas do Visual Studio para Unity 2.0](https://devblogs.microsoft.com/visualstudio/visual-studio-tools-for-unity-2-0-preview/) (blog do Visual Studio)|
|[Assista a um vídeo de introdução à Visualização das Ferramentas do Visual Studio para Unity 2.0](https://www.bing.com/videos/search?q=visual+studio+tools+for+unity&qs=n&form=QBVLPG&pq=visual+studio+tools+for+unity&sc=6-29&sp=-1&sk=#view=detail&mid=0A13177F0BC7463A24080A13177F0BC7463A2408) (Vídeo)|
|[Saiba mais sobre o Unity](https://unity.com/) (site do Unity)|

## <a name="see-also"></a>Confira também

- [Adicionar APIs do Office 365 a um projeto do Visual Studio](/office/developer-program/office-365-developer-program)
- [Serviços de Aplicativos do Azure – Aplicativos Móveis](https://azure.microsoft.com/services/app-service/mobile/)
- [Visual Studio App Center](/appcenter)
