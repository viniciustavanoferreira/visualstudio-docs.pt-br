---
title: Tour do Visual Studio para Mac
description: O Visual Studio para Mac fornece um ambiente de desenvolvimento integrado para compilar aplicativos .NET no macOS, incluindo sites ASP.NET Core e projetos Xamarin para iOS, Android, Mac e Xamarin.Forms.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 12/13/2019
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.custom: video
ms.openlocfilehash: f7686efae903912b64d8692a823d6e82592cbec9
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "75405826"
---
# <a name="visual-studio-2019-for-mac-tour"></a>Tour do Visual Studio 2019 para Mac

O Visual Studio para Mac é um _ambiente de desenvolvimento integrado_ do .NET no Mac que você pode usar para editar, depurar e compilar o código e, em seguida, publicar um aplicativo. Além de recursos esperados, tais como o editor e o depurador padrão, o Visual Studio para Mac inclui compiladores, ferramentas de preenchimento de código, designers gráficos e controle do código-fonte para facilitar o processo de desenvolvimento de software.

O Visual Studio para Mac dá suporte a muitos dos mesmos tipos de arquivo que seu equivalente do Windows, tais como arquivos `.csproj`, `.fsproj`, ou `.sln`. Ele também dá suporte a recursos como EditorConfig, o que significa que você pode usar o IDE que melhor funciona para você.
Criar, abrir e desenvolver um aplicativo será uma experiência familiar para qualquer pessoa que já tenha usado o Visual Studio no Windows. Além disso, o Visual Studio para Mac emprega muitas das ferramentas avançadas que fazem do seu equivalente no Windows um IDE tão avançado. A Roslyn Compiler Platform é usada para refatoração e IntelliSense. Seu sistema de projeto e o mecanismo de construção usam o MSBuild, e seu editor de origem usa a mesma base que o Visual Studio no Windows. Ele usa os mesmos mecanismos de depuração para aplicativos Xamarin e .NET Core, e os mesmos designers para Xamarin.iOS e Xamarin.Android.

## <a name="what-can-i-do-in-visual-studio-for-mac"></a>O que posso fazer no Visual Studio para Mac

O Visual Studio para Mac é compatível com os seguintes tipos de desenvolvimento:

- ASP.NET aplicativos web Core com C#, F#e suporte para páginas Razor, JavaScript e TypeScript
- Aplicativo de console .NET Core com C# ou F#
- Jogos do Unity multiplataforma e aplicativos com C#
- Aplicativos Android, iOS, tvOS e watchOS no Xamarin com o C# ou F# e XAML
- Aplicativos da área de trabalho Cocoa no C# ou F#

Este artigo explora várias seções do Visual Studio para Mac, mostrando alguns dos recursos que o tornam uma ferramenta avançada para criar esses aplicativos.

## <a name="ide-tour"></a>Tour do IDE

O Visual Studio para Mac está organizado em várias seções para gerenciar configurações e arquivos de aplicativo, criar código do aplicativo e depuração.

## <a name="getting-started"></a>Introdução

Ao iniciar o Visual Studio 2019 para Mac, os novos usuários verão uma janela de entrada. Entre com sua conta Microsoft para ativar uma licença paga (se tiver uma) ou um link para assinaturas do Azure. Você pode pressionar **Eu vou fazer isso mais tarde** e fazer login mais tarde através do Visual Studio > Assinar **no** item do menu:

![Entre na sua conta da Microsoft](media/ide-tour-2019-start-signin.png)

Em seguida, você terá a opção de personalizar o IDE selecionando seus atalhos de teclado preferidos: Visual Studio para Mac, Visual Studio, Visual Studio Code ou Xcode:

![Selecione seus atalhos de teclado favoritos](media/ide-tour-2019-keyboard-shortcut.png)

Usuários conectados verão a nova _janela de início_, que mostra uma lista de projetos recentes e botões para abrir um projeto existente ou criar um novo:

![Escolher entre projetos recentes ou criar algo novo](media/ide-tour-2019-start-projects.png)

## <a name="solutions-and-projects"></a>Soluções e projetos

A imagem abaixo mostra o Visual Studio para Mac com um aplicativo carregado:

![Visual Studio para Mac com um aplicativo carregado](media/ide-tour-image17.png)

As seções a seguir fornecem uma visão geral das principais áreas no Visual Studio para Mac.

## <a name="solution-pad"></a>Painel de Soluções

O Painel de Soluções organiza os projetos em uma solução:

![Projetos organizados no Painel de Soluções](media/ide-tour-image18.png)

É aqui que os arquivos para o código-fonte, recursos, interface do usuário e dependências são organizados em Projetos específicos da plataforma.

Para saber mais sobre como usar os Projetos e Soluções no Visual Studio para Mac, veja o artigo [Projetos e Soluções](/visualstudio/mac/projects-and-solutions).

## <a name="assembly-references"></a>Referências de assembly

As referências de assembly para cada projeto estão disponíveis na pasta Referências:

![Pasta Referências no painel de soluções](media/ide-tour-image19.png)

As referências adicionais são adicionadas usando a caixa de diálogo **Editar Referências**, que é exibida clicando duas vezes na pasta Referências ou selecionando **Editar Referências** em suas ações de menu de contexto:

![Caixa de diálogo Editar Referências](media/ide-tour-image20.png)

Para saber mais sobre como usar Referências no Visual Studio para Mac, veja o artigo [Gerenciando referências em um projeto](/visualstudio/mac/managing-references-in-a-project).

## <a name="dependencies--packages"></a>Dependências/pacotes

Todas as dependências externas usadas em seu aplicativo são armazenadas nas pastas Dependências ou Pacotes, dependendo se você está em um projeto .Net Core ou Xamarin.iOS/Xamarin.Android. Geralmente, eles são fornecidos na forma de um NuGet.

NuGet é o gerenciador de pacote mais popular para desenvolvimento .NET. Com a compatibilidade do NuGet no Visual Studio, você pode facilmente pesquisar e adicionar pacotes ao seu projeto para o aplicativo.

Para adicionar uma dependência ao seu aplicativo, clique com botão direito do mouse sobre a pasta Dependências / Pacotes e selecione **Adicionar Pacotes**:

![Adicionar um pacote NuGet](media/ide-tour-image21.png)

As informações sobre como usar um pacote do NuGet em um aplicativo podem ser encontradas no artigo [Incluindo um projeto NuGet em seu projeto](/visualstudio/mac/nuget-walkthrough).

## <a name="source-editor"></a>Editor de Código-fonte

Independentemente de se você estiver escrevendo em C#, XAML ou Javascript, o editor de código compartilha os mesmos componentes principais com o Visual Studio Windows, com uma interface de usuário totalmente nativa.

Isso traz algumas das seguintes características:

* Interface do usuário macOS (baseada em Cocoa) nativa (dicas de ferramenta, superfície do editor, adornos de margem, renderização de texto, IntelliSense)
* Filtragem do tipo IntelliSense e "mostrar itens de importação"
* Suporte para entradas de texto nativas
* Suporte à linguagem RTL/BiDi
* Roslyn 3
* Suporte a vários cursores
* Quebra automática de linha
* IU IntelliSense atualizada
* Melhor encontrar/substituir
* Suporte a snippet 
* Formatar seleção
* Lâmpadas inline

Para obter mais informações sobre como usar o Editor de Origem no Visual Studio para Mac, consulte a documentação do [Editor de](/visualstudio/mac/source-editor) Origem.

Para manter as abas visíveis o tempo todo, você pode aproveitar para fixá-los. Isso garante que toda vez que você lançar um projeto, a guia que você precisa sempre aparecerá. Para fixar uma guia, passar o mouse sobre a guia e clicar no ícone do _pino:_

![Fixando uma guia](media/ide-tour-tabpin.png)

## <a name="refactoring"></a>Refatoração

O Visual Studio para Mac fornece duas maneiras úteis de refatorar o código: ações de contexto e análise de código-fonte. Leia mais sobre elas no artigo [Refatoração](/visualstudio/mac/refactoring).

## <a name="debugging"></a>Depuração

O Visual Studio for Mac possui depuradores que suportam projetos .NET Core, .NET Framework, Unity e Xamarin. O Visual Studio for Mac usa o depurador .NET Core e o Mono Soft Debugger, permitindo que o IDE depura código gerenciado em todas as plataformas. Para saber mais adicionais sobre a depuração, visite o artigo [Depuração](/visualstudio/mac/debugging).

O depurador contém visualizadores ricos para tipos especiais, como cordas, cores, URLs, bem como tamanhos, coordenadas e curvas bézier.

Para saber mais sobre visualizações de dados do depurador, visite o artigo [Visualizações de dados](/visualstudio/mac/data-visualizations).

## <a name="version-control"></a>Controle de versão

O Visual Studio para Mac integra-se aos sistemas de controle do código-fonte Git e Subversion. Projetos com controle do código-fonte são marcados com o branch listado ao lado do nome da Solução:

![Nome do branch para indicar o projeto com controle do código-fonte](media/ide-tour-image22.png)

Os arquivos com alterações não confirmadas têm uma anotação em seus ícones no Painel de Soluções, como mostrado na imagem abaixo:

![Arquivos não confirmados no painel de soluções](media/ide-tour-image23.png)

Para saber mais sobre como usar o controle de versão no Visual Studio, veja o artigo [Controle de Versão](/visualstudio/mac/version-control).

## <a name="next-steps"></a>Próximas etapas

- [Instale o Visual Studio para Mac](installation.md)
- [Examinar as cargas de trabalho disponíveis](workloads.md)

## <a name="related-video"></a>Vídeo relacionados

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Overview/player]

## <a name="see-also"></a>Confira também

- [IDE do Visual Studio (no Windows)](/visualstudio/ide/visual-studio-ide)
