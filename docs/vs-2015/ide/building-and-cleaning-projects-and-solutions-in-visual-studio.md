---
title: Criar soluções de projetos limpos
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.BuildProjectPicker
- vs.batchbuild
helpviewer_keywords:
- Clean Solution command
- builds [Visual Studio], managing
- solution build configurations, starting
- Build Solution command
- project build configurations, starting
- build configurations, starting
- project build configurations, dependencies
- Rebuild Solution command
- solution build configurations, build order
- builds [Visual Studio], preparing
ms.assetid: 710891fd-379e-42c2-a84b-44a7af694ca0
caps.latest.revision: 37
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 15f2817b6fd0aee312ff41af218d01ad80bc785e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72620565"
---
# <a name="building-and-cleaning-projects-and-solutions-in-visual-studio"></a>Compilando e limpando projetos e soluções no Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Usando os procedimentos neste tópico, é possível criar, recriar ou limpar todos ou alguns projetos ou itens de projeto em uma solução. Para ver um tutorial passo a passo, consulte [Instruções passo a passo: criando um aplicativo](../ide/walkthrough-building-an-application.md).

> [!NOTE]
> A interface do usuário na sua edição do Visual Studio pode ser diferente do que este tópico descreve, dependendo das suas configurações ativas. Para alterar as configurações, abra o menu **Ferramentas** e escolha **Importar e Exportar Configurações**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).

## <a name="to-build-rebuild-or-clean-an-entire-solution"></a>Para criar, recriar ou limpar uma solução inteira

1. No **Gerenciador de Soluções**, escolha ou abra a solução.

2. Na barra de menus, escolha **Compilar** e, em seguida, escolha um dos comandos a seguir:

    - Escolha **Compilar** ou **Compilar Solução** para compilar somente esses componentes e arquivos de projeto e componentes que foram alterados desde o build mais recente.

        > [!NOTE]
        > O comando **Compilar** torna-se **Compilar Solução** quando uma solução inclui mais de um projeto.

    - Escolha **Recompilar Solução** para "limpar" a solução e, em seguida, crie todos os arquivos de projeto e componentes.

    - Escolha **Limpar Solução** para excluir arquivos de saída e intermediários. Com apenas os arquivos de projeto e de componente restantes, novas instâncias dos arquivos de saída e intermediários podem ser criadas.

## <a name="to-build-or-rebuild-a-single-project"></a>Para compilar ou recompilar um único projeto

1. No **Gerenciador de Soluções**, escolha ou abra o projeto.

2. Na barra de menus, escolha **Compilar** e, em seguida, escolha **Compilar** _ProjectName_ ou **Recompilar** _ProjectName_.

    - Escolha **Compilar** _ProjectName_ para compilar somente os componentes de projeto alterados desde o build mais recente.

    - Escolha **Recompilar** _ProjectName_ para "limpar" o projeto e, em seguida, compile os arquivos de projeto e todos os componentes do projeto.

## <a name="to-build-only-the-startup-project-and-its-dependencies"></a>Para compilar apenas o projeto de inicialização e suas dependências

1. Na barra de menus, escolha **Ferramentas**, **Opções**.

2. Na caixa de diálogo **Opções**, expanda o nó **Projetos e Soluções** e, em seguida, escolha a página **Compilar e Executar**.

    A caixa de diálogo **Compilar e Executar, Projetos e Soluções, Opções** é aberta.

3. Marque a caixa de seleção **Compilar apenas projetos de inicialização e dependências ao Executar**.

    Quando essa caixa de seleção estiver marcada, somente o projeto de inicialização atual e suas dependências serão compilados quando você executar qualquer uma das seguintes etapas:

   - Na barra de menus, escolha **depurar**  > **Iniciar Depuração** (F5).

   - Na barra de menus, escolha **compilar**  > **Compilar solução** (Ctrl + Shift + B).

     Quando essa caixa de seleção estiver desmarcada, todos os projetos, suas dependências e os arquivos de solução serão compilados quando você executar um dos comandos anteriores. Por padrão, essa caixa de seleção está desmarcada.

## <a name="to-build-only-the-selected-visual-c-project"></a>Para compilar somente o projeto Visual C++ selecionado

1. Escolha um projeto [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] e, em seguida, na barra de menus, escolha **Compilar**, **Somente Projeto** e um dos seguintes comandos:

   - **Somente build** *ProjectName*

   - **Somente Recompilação** *ProjectName*

   - **Somente Limpeza** *ProjectName*

   - **Somente Vinculação** *ProjectName*

     Esses comandos são aplicáveis somente ao projeto [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] escolhido, sem compilar, recompilar, limpar ou vincular as dependências do projeto ou os arquivos de solução. Dependendo da sua versão do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], o submenu **Somente Projeto** pode conter mais comandos.

## <a name="to-compile-multiple-c-project-items"></a>Para compilar vários itens de projeto C++

1. Em **Gerenciador de Soluções**, escolha vários arquivos que possam ter ações compiladas, abra o menu de atalho para um desses arquivos e, em seguida, escolha **Compilar**.

     Se os arquivos tiverem dependências, os arquivos serão compilados em ordem de dependência. A operação de compilação falhará se os arquivos exigirem um cabeçalho pré-compilado que não está disponível quando você compila. A operação de compilação usa a configuração de solução ativa atual.

## <a name="to-stop-a-build"></a>Para interromper um build

1. Execute uma das seguintes etapas:

    - Na barra de menus, escolha **Compilar**, **Cancelar**.

    - Escolha as teclas Ctrl + Break.

## <a name="see-also"></a>Consulte também
 [Como exibir, salvar e configurar arquivos de log de compilação](../ide/how-to-view-save-and-configure-build-log-files.md) [obtendo logs de compilação](../msbuild/obtaining-build-logs-with-msbuild.md) [compilando e criando](../ide/compiling-and-building-in-visual-studio.md) [noções básicas sobre configurações de compilação](../ide/understanding-build-configurations.md) [depurar e liberar configurações do projeto](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e) [referência C/C++ Build ](https://msdn.microsoft.com/library/100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d) [Opções de linha de comando do devenv](../ide/reference/devenv-command-line-switches.md) [soluções e projetos](../ide/solutions-and-projects-in-visual-studio.md)
