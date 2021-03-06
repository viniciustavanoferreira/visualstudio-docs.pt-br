---
title: Publicar em uma pasta
ms.date: 04/02/2019
helpviewer_keywords:
- deployment, website, console, publish
ms.assetid: e963fb4b-6d32-4d45-86bb-ef7e4d3028b0
author: sayedihashimi
ms.author: sayedha
manager: unniravindranathan
ms.prod: visual-studio-mac
ms.openlocfilehash: 0ea70fb1a5898e2415b7f74e93233ca03ea52c45
ms.sourcegitcommit: b4e0cc76d94fe8cf6d238c4cc09512d17131a195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81224492"
---
# <a name="publish-to-a-folder-using-visual-studio-for-mac"></a>Publique para uma pasta usando o Visual Studio para Mac

Você pode usar a ferramenta Publicar para publicar aplicativos .NET Core Console ou ASP.NET Core para uma pasta.

## <a name="prerequisites"></a>Pré-requisitos

- [Visual Studio 2019 para Mac](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs4mac2019) instalado com .NET Core ativado.
- Um projeto de console .NET Core ou ASP.NET Core. Se você ainda não tiver um projeto, [crie um](/visualstudio/mac/create-new-projects?view=vsmac-2019).

## <a name="publish-to-folder"></a>Publicar na Pasta

Usando o Visual Studio para Mac, você pode publicar seus projetos .NET Core para uma pasta usando a ferramenta Publicar. Depois de publicar em uma pasta, você pode transferir os arquivos para um ambiente diferente. Para publicar uma pasta, siga estas etapas.

 1. No Painel de Soluções, clique com o botão direito do mouse no projeto e escolha **Publicar**.

    ![Menu de contexto Publicar](media/publish-context-menu.png)

 2. Se você já tiver publicado este projeto, o perfil de publicação será exibido no menu. Selecione o perfil de publicação para iniciar o processo de publicação.

 3. Para publicar este projeto em uma pasta pela primeira vez, selecione **Publicar na Pasta**

    ![Menu de contexto Publicar na pasta](media/publish-to-folder-context-menu.png)

 4. A caixa de diálogo **Publicar na pasta** é exibida. Nessa caixa de diálogo, você pode personalizar a pasta em que o projeto será publicado. Você pode usar o botão **Procurar** para fazer isso ou colar em um caminho.

 5. Depois que você clicar em **Publicar**, acontecerão algumas coisas. Primeiro, um perfil de publicação será criado. Um perfil de publicação é um arquivo do MSBuild que é importado para o projeto durante o processo de publicação. Ele contém as propriedades que são usadas durante o processo de publicação. Esses arquivos são armazenados no `Properties/PublishProfiles` e têm a extensão `.pubxml`. Em seguida, o processo de publicação será iniciado. Você pode monitorar o progresso observando a barra de status no Visual Studio para Mac.

    ![Barra de status do IDE com o status Publicar](media/publish-to-folder-status-bar.png)

 6. Depois que a publicação for concluída com êxito, uma janela do Finder abrirá a pasta de publicação. Agora que um perfil de publicação foi criado, ele será exibido no menu de contexto de publicação.

    ![Menu de contexto de publicação com o perfil da pasta](media/publish-context-menu-with-folder-profile.png)

 7. Para publicar o projeto novamente com as mesmas configurações, clique no perfil no menu de contexto de publicação.

## <a name="customize-publish-options"></a>Personalizar as opções de publicação

Para alterar o nome do perfil de publicação (que é exibido no menu de contexto de publicação), renomeie o arquivo de perfil de publicação. Não altere a extensão do arquivo (`.pubxml`).

Para alterar o caminho da pasta de publicação, abra o perfil de publicação e edite o valor de `publishUrl`.

Para alterar a configuração de build que é usada, altere a propriedade `LastUsedBuildConfiguration` no perfil de publicação.
