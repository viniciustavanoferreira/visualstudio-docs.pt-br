---
title: Executar como administrador
ms.date: 01/06/2020
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 927031b4755644aeac553367a4f8a08faa0c0992
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75718630"
---
# <a name="user-permissions-and-visual-studio"></a>Permissões de usuário e o Visual Studio

Por razões de segurança, você deve executar o Visual Studio como um usuário típico sempre que possível.

> [!WARNING]
> Você deve se certificar de não compilar, iniciar ou depurar qualquer solução do Visual Studio que não venha de uma pessoa de confiança ou de uma localidade confiável.

Você pode fazer quase tudo no Visual Studio IDE como um usuário típico. Você precisa de permissões de administrador para concluir as seguintes tarefas:

|Área|Tarefa|Para obter mais informações|
|----------|----------| - |
|Instalação|Instale ou modifique o Visual Studio.|[Instale o Visual Studio,](../install/install-visual-studio.md) [modifique o visual studio](../install/modify-visual-studio.md)|
||Instalar, atualizar ou remover conteúdo da Ajuda local.|[Instalar e gerenciar o conteúdo da Ajuda local](../help-viewer/install-manage-local-content.md)|
|Caixa de Ferramentas|Adicionar controles COM clássicos à **Caixa de ferramentas**.|[Ferramentas](../ide/reference/toolbox.md)|
|Construção|Usar eventos de pós-build que registram um componente.|[Noções básicas sobre etapas e eventos de build personalizados](/cpp/build/understanding-custom-build-steps-and-build-events)|
||Incluir uma etapa de registro ao criar projetos C++.||
|Depuração|Depurar aplicativos executados com permissões elevadas.|[Configurações e preparação do depurador](../debugger/debugger-settings-and-preparation.md)|
||Depurar aplicativos que são executados em uma conta de usuário diferente, como sites do ASP.NET.|[Depurar aplicativos ASP.NET e AJAX](../debugger/how-to-enable-debugging-for-aspnet-applications.md)|
||Depurar na zona para XBAP (aplicativos de navegador XAML).|[Host do WPF (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Usar o emulador para depurar projetos de serviço de nuvem do Microsoft Azure.|[Depurar um serviço de nuvem no Visual Studio](/azure/vs-azure-tools-debug-cloud-services-virtual-machines)|
||Configurar um firewall para depuração remota.|[Depuração remota](../debugger/remote-debugging.md)|
|Ferramentas de desempenho|Anexação a um aplicativo com privilégios elevados.|[Guia de iniciantes para o perfil de desempenho](../profiling/beginners-guide-to-performance-profiling.md)|
||Use o Criador de Perfil de GPU.|[Criação de perfil de GPU](../profiling/gpu-usage.md)|
|Implantação|Implantar um aplicativo Web para o IIS (Serviços de Informações da Internet) em um computador local.|[Implantar um aplicativo Web ASP.NET usando o Visual Studio](/aspnet/web-forms/overview/older-versions-getting-started/deployment-to-a-hosting-provider/)|

## <a name="run-visual-studio-as-an-administrator"></a>Executar o Visual Studio como administrador

Se você precisar executar o Visual Studio como administrador, siga estas etapas para abrir o IDE:

> [!NOTE]
> Estas instruções referem-se ao Windows 10. Elas são semelhantes para outras versões do Windows.

::: moniker range="vs-2017"

1. Abra o menu **Iniciar** e role até o Visual Studio 2017.

1. No menu de contexto ou de atalho do **Visual Studio 2017**, selecione **Mais** > **Executar como administrador**.

   Quando o Visual Studio for iniciado, **(Administrador)** será exibido após o nome do produto na barra de título.

::: moniker-end

::: moniker range=">=vs-2019"

1. Abra o menu **Iniciar** e role a página até o Visual Studio 2019.

1. No menu de contexto ou de atalho do **Visual Studio 2019**, selecione **Mais** > **Executar como administrador**.

   Quando o Visual Studio for iniciado, **(Administrador)** será exibido após o nome do produto na barra de título.

::: moniker-end

Você também pode modificar o atalho do aplicativo para sempre ser executado com permissões administrativas.

## <a name="see-also"></a>Confira também

- [Porta, migrar e atualizar projetos do Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Instale o Visual Studio](../install/install-visual-studio.md)
