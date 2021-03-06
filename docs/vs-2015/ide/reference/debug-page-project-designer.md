---
title: Página de Depuração, Designer de Projeto | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
caps.latest.revision: 37
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 006662d7c07ba0498fff4617eca3fdc7c631d37b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660792"
---
# <a name="debug-page-project-designer"></a>Página de Depuração, Designer de Projeto
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!WARNING]
> Este tópico não se aplica a aplicativos da Windows Store. Consulte [Iniciar uma sessão de depuração (VB, C#, C++ e XAML)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) no Centro de Desenvolvimento do Windows.

 Use a página **Depurar** do **Designer de Projeto** para definir as propriedades do comportamento de depuração em um projeto do Visual Basic ou C#.

 Para acessar a página **Depurar**, selecione um nó do projeto no **Gerenciador de Soluções**. No menu **Projeto**, escolha _ProjectName_**Propriedades**. Quando o **Designer de Projeto** for exibido, clique na guia **Depurar**.

## <a name="configuration-and-platform"></a>Configuração e plataforma
 As opções a seguir permitem selecionar a configuração e a plataforma a ser exibida ou modificada.

 **Configuração** Especifica quais definições de configuração devem ser exibidas ou modificadas. As configurações podem ser **Depurar** (padrão), **Versão** ou **Todas as Configurações**. Para obter mais informações, consulte [Configurações de projeto de depuração e versão](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e).

 **Plataforma** Especifica quais configurações de plataforma devem ser exibidas ou modificadas. As opções podem incluir **Qualquer CPU** (padrão), **x64** e **x86**. Para obter mais informações, consulte [Configurações de projeto de depuração e versão](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e).

## <a name="start-action"></a>Iniciar ação
 **Iniciar ação** indica o item a ser iniciado quando o aplicativo for depurado: o projeto, um programa personalizado, uma URL ou nada. Por padrão, essa opção é definida como **Iniciar projeto**. A configuração **Iniciar ação** na página **Depurar** determina o valor da propriedade `StartAction`.

 **Iniciar projeto** Escolha esta opção para especificar que o executável (para projetos de aplicativo de console e aplicativo do Windows) deve ser iniciado quando o aplicativo é depurado. Essa opção é habilitada por padrão.

 **Iniciar programa externo** Escolha esta opção para especificar que um programa específico deve ser iniciado quando o aplicativo for depurado.

 **Iniciar o navegador com a URL** Escolha esta opção para especificar que uma URL específica deve ser acessada quando o aplicativo for depurado.

## <a name="start-options"></a>Opções de Inicialização
 **Argumentos de linha de comando** Nessa caixa de texto, insira os argumentos de linha de comando a serem usados para depuração.

 **Diretório de trabalho** Nessa caixa de texto, insira o diretório do qual o projeto será iniciado. Ou clique no botão Procurar ( **...** ) para escolher um diretório.

 **Usar computador remoto** Para depurar o aplicativo de um computador remoto, marque essa caixa de seleção e insira o caminho para o computador remoto na caixa de texto.

## <a name="enable-debuggers"></a>Habilitar Depuradores
 **Habilitar depuração de código não gerenciado** Esta opção especifica se há suporte para a depuração de código nativo. Marque esta caixa de seleção se você estiver fazendo chamadas para objetos COM ou se iniciar um programa personalizado escrito em código nativo que chama o seu projeto e você precisar depurar o código nativo. Desmarque esta caixa de seleção para desabilitar a depuração de código não gerenciado. Por padrão, a caixa de seleção fica desmarcada.

 **Habilitar depuração de SQL Server** Marque ou desmarque essa caixa de seleção para habilitar ou desabilitar a depuração de procedimentos SQL do seu aplicativo Visual Basic. Por padrão, a caixa de seleção fica desmarcada.

 **Habilitar o processo de hospedagem do Visual Studio** Marque essa caixa de seleção para habilitar o processo de hospedagem do Visual Studio. Por padrão, a caixa de seleção fica marcada. Para obter mais informações, consulte [Processo de hospedagem (vshost.exe)](../../ide/hosting-process-vshost-exe.md).

 Para depurar em uma zona de segurança, você precisa habilitar essa opção e **Depurar este aplicativo com o conjunto de permissões selecionado** na [Caixa de diálogo Configurações de Segurança Avançadas](../../ide/reference/advanced-security-settings-dialog-box.md).

## <a name="see-also"></a>Consulte também
 [Depurando nas](../../debugger/debugging-in-visual-studio.md) [configurações do projeto C# do](../../debugger/project-settings-for-csharp-debug-configurations.md) Visual Studio para configurações do projeto de configurações [de depuração para uma Visual Basic configuração de depuração](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md) [Gerenciando Propriedades de depuração](https://msdn.microsoft.com/92474d16-e7fe-4fac-9287-6bd6b3a7eb68) [como: Depurar um aplicativo ClickOnce com Permissões restritas](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md) [como: criar e editar configurações](../../ide/how-to-create-and-edit-configurations.md)
