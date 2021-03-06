---
title: Modificar o Visual Studio
titleSuffix: ''
description: Saiba como modificar o Visual Studio, passo a passo.
ms.date: 02/10/2019
ms.topic: conceptual
helpviewer_keywords:
- modify Visual Studio
- change visual studio
- changing Visual Studio
- customize Visual Studio
ms.assetid: 3399ea7b-a291-4a9e-80a1-b861a21afa1d
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 57aa5531eb6d6517b520991ababefc38b25a9a2d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77125345"
---
# <a name="modify-visual-studio-by-adding-or-removing-workloads-and-components"></a>Modificar o Visual Studio adicionando ou removendo cargas de trabalho e componentes

::: moniker range="vs-2019"

É fácil modificar o Visual Studio para que ele inclua apenas o que você deseja, quando você deseja. Para fazer isso, abra o Instalador do Visual Studio para adicionar ou remover componentes e cargas de trabalho.

::: moniker-end

::: moniker range="vs-2017"

Não apenas tornamos mais fácil para você personalizar o Visual Studio para corresponder às etapas que deseja realizar, mas também facilitamos a customização do Visual Studio. Para isso, abra o novo Visual Studio Installer e faça as alterações desejadas.

::: moniker-end

Veja como.

>[!IMPORTANT]
>Para instalar, atualizar ou modificar o Visual Studio, faça logon com uma conta que tenha permissões administrativas. Para obter mais informações, consulte [permissões de usuário e Visual Studio](../ide/user-permissions-and-visual-studio.md).

>[!NOTE]
> Os procedimentos a seguir supõem que você tem uma conexão com a internet.
>
> Para obter mais informações sobre como modificar uma [instalação offline](create-an-offline-installation-of-visual-studio.md) do Visual Studio criada anteriormente, confira as páginas [Atualizar uma instalação baseada em rede do Visual Studio](update-a-network-installation-of-visual-studio.md) e [Controlar as atualizações em implantações baseadas em rede do Visual Studio](controlling-updates-to-visual-studio-deployments.md).

## <a name="open-the-visual-studio-installer"></a>Abra o Visual Studio Installer

::: moniker range="vs-2017"

1. Localize o Instalador do Visual Studio no computador.

     Por exemplo, em um computador que executa o Windows 10, selecione **Iniciar** e, em seguida, role até a letra **I**, onde ele está listado como **Instalador do Visual Studio**.

     ![Instalador visual studio](media/locate-the-visual-studio-installer.png "Localize o Microsoft Visual Studio Installer")

     >[!TIP]
     >Em alguns computadores, o Instalador do Visual Studio poderá estar listado sob a letra **“M”** como **Instalador do Microsoft Visual Studio**.<br/><br/> Como alternativa, encontre o Instalador do Visual Studio no seguinte local: `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

1. Abra o instalador e, em seguida, escolha **Modificar**.

     ![Lançar ou modificar o Visual Studio](media/modify-visual-studio.png "Modificar o Visual Studio 2017")

     > [!IMPORTANT]
     > Se houver uma atualização pendente, o botão Modificar estará em um local diferente. Dessa forma, você pode modificar o Visual Studio sem atualizá-lo, caso queria. Clique em **Mais** e, em seguida, escolha **Modificar**.
     >
     > ![Atualizar ou modificar o Visual Studio](media/modify-or-update-visual-studio.png "Atualizar ou modificar o Visual Studio 2017")

::: moniker-end

::: moniker range="vs-2019"

1. Localize o Instalador do Visual Studio no computador.

     Por exemplo, em um computador que executa o Windows 10, selecione **Iniciar** e, em seguida, role até a letra **I**, onde ele está listado como **Instalador do Visual Studio**.

     ![Abra o Instalador do Visual Studio no Windows](media/vs-2019/vs-installer-windows-start.png "Abra o Visual Studio Installer")

     > [!NOTE]
     > Também é possível encontrar o Instalador do Visual Studio no seguinte local:
     >
     > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

    Talvez você precise atualizar o instalador antes de continuar. Nesse caso, siga os prompts.

1. No instalador, procure a edição do Visual Studio instalada por você e escolha **Modificar**.

     ![Atualizar ou modificar o Visual Studio](media/vs-2019/vs-installer-modify.png "Atualizar ou modificar o Visual Studio 2019")

     > [!IMPORTANT]
     > Se houver uma atualização pendente, o botão Modificar estará em um local diferente. Desta forma, você pode modificar o Visual Studio sem atualizá-lo, se quiser. Escolha **Mais**e, em seguida, escolha **Modificar**.
     >
     > ![Atualizar ou modificar o Visual Studio](media/vs-2019/modify-update-visual-studio.png "Atualizar ou modificar o Visual Studio 2019")

::: moniker-end

## <a name="modify-workloads"></a>Modificar cargas de trabalho

::: moniker range="vs-2017"

 As [cargas de trabalho](https://visualstudio.microsoft.com/vs/support/selecting-workloads-visual-studio-2017/) contêm os recursos necessários para a linguagem de programação ou a plataforma que está sendo usada. Use cargas de trabalho para modificar o Visual Studio para que ele dê suporte ao trabalho que você deseja fazer, quando desejar fazê-lo.

1. No Visual Studio Installer, escolha a guia Cargas de trabalho e selecione ou **desmarque** as cargas de trabalho desejadas.

    ![Caixa de diálogo de instalação do Visual Studio 2017](media/modify-workloads.png "Escolha uma carga de trabalho no Visual Studio 2019")

1. Escolha se deseja aceitar a opção padrão **Instalar durante o download** ou a opção **Baixar tudo, depois instalar**.

    ![Opções de configuração do Visual Studio 2017](media/vs-2019/vs-installer-choose-install-or-download.png "Escolha instalar durante o download ou para baixar primeiro e instalar depois")

    A opção "Baixar tudo, depois instalar" é útil se você deseja baixar primeiro e instalar mais tarde.

1. Escolha **Modificar**.

1. Depois que as novas cargas de trabalho forem instaladas, escolha **Iniciar** no Visual Studio Installer para abrir o Visual Studio.

::: moniker-end

::: moniker range="vs-2019"

 As cargas de trabalho contêm os recursos necessários para a linguagem de programação ou plataforma que você está usando. Use cargas de trabalho para modificar o Visual Studio para que ele dê suporte ao trabalho que você deseja fazer, quando desejar fazê-lo.

 > [!TIP]
>Para obter mais informações sobre quais pacotes de ferramentas e componentes você precisa para o desenvolvimento, consulte [as cargas de trabalho do Visual Studio](https://visualstudio.microsoft.com/vs/#workloads).

1. No Visual Studio Installer, escolha a guia Cargas de trabalho e selecione ou **desmarque** as cargas de trabalho desejadas.

    ![Diálogo de configuração do Visual Studio 2019](media/vs-2019/vs-installer-modify-workloads.png "Escolha uma carga de trabalho no Visual Studio 2019")

1. Escolha se deseja aceitar a opção padrão **Instalar durante o download** ou a opção **Baixar tudo, depois instalar**.

    ![Opções de configuração do Visual Studio 2019](media/vs-2019/vs-installer-choose-install-or-download.png "Escolha instalar durante o download ou para baixar primeiro e instalar depois")

    A opção "Baixar tudo, depois instalar" é útil se você deseja baixar primeiro e instalar mais tarde.

1. Escolha **Modificar**.

1. Depois que as novas cargas de trabalho forem instaladas, escolha **Iniciar** no Visual Studio Installer para abrir o Visual Studio.

::: moniker-end

## <a name="modify-individual-components"></a>Modificar componentes individuais

Se você não quiser usar cargas de trabalho para personalizar sua instalação do Visual Studio, escolha a guia **Componentes Individuais** no Instalador do Estúdio Visual, selecione os componentes desejados e siga as instruções.

>[!TIP]
> Para obter informações sobre o componente SSDT (SSDT), consulte [Baixar e instalar o SSDT para o Visual Studio](/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-ver15).

## <a name="modify-language-packs"></a>Modificar pacotes de idiomas

Por padrão, o instalador corresponde à linguagem do sistema operacional quando ele é executado pela primeira vez. No entanto, você pode mudar o idioma sempre que quiser. Para isso, escolha a guia **Pacotes de idiomas** no Visual Studio Installer, selecione o idioma que preferir e siga as instruções.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Confira também

* [Lista de IDs de componente e carga de trabalho do Visual Studio](workload-and-component-ids.md)
* [Atualizar o Visual Studio](update-visual-studio.md)
* [Atualizar uma instalação em rede do Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Atualizar o Visual Studio enquanto estiver em uma linha de base de manutenção](update-servicing-baseline.md)
* [Atualizações de controle para implantações do Visual Studio com base em rede](controlling-updates-to-visual-studio-deployments.md)
* [Desinstalar o Visual Studio](uninstall-visual-studio.md)
