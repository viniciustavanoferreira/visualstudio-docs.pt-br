---
title: Modo tela inteira e espaço virtual
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 77f224a6e3a1b12ed17799ddf6a2fc5c23f5d4cc
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75591028"
---
# <a name="how-to-manage-editor-modes"></a>Como gerenciar modos do editor

Você pode exibir o editor de código do Visual Studio em vários modos de exibição.

> [!NOTE]
> As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos neste artigo, dependendo da sua edição ou das configurações ativas. Para alterar as configurações, por exemplo, para configurações **Gerais** ou do **Visual C++**, escolha **Ferramentas** > **Importar e Exportar Configurações** e, em seguida, escolha **Redefinir todas as configurações**.

## <a name="enable-full-screen-mode"></a>Habilitar o modo de tela inteira

Você pode optar por ocultar todas as janelas de ferramentas e visualizar apenas janelas de documentos ativando o modo **tela cheia.**

- Pressione **Alt**+**Shift**+**Enter** para entrar ou sair do modo **full screen.**

     -- ou --

- Emita o comando `View.Fullscreen` na janela **Comando**.

## <a name="enable-virtual-space-mode"></a>Habilitar o modo de espaço virtual

No modo **Espaço virtual**, os espaços são inseridos no final de cada linha de código. Selecione essa opção para posicionar comentários em um ponto consistente ao lado do seu código.

1. Selecione **Opções** no menu **Ferramentas**.

2. Expanda a pasta **Editor de Texto** e escolha **Todas as Linguagens** para definir essa opção globalmente ou escolha uma pasta de idioma específico. Por exemplo, para ativar números de linha apenas no Visual Basic, escolha o nó **Editor de** > **texto** básico.

3. Selecione as opções **Gerais** e, em **Configurações**, selecione **Habilitar Espaço virtual**.

    > [!NOTE]
    > O **Espaço virtual** está habilitado no modo **Seleção de Coluna**. Quando o modo **Espaço virtual** não está habilitado, o ponto de inserção é movido do final de uma linha diretamente para o primeiro caractere da próxima.

## <a name="see-also"></a>Confira também

- [Personalizar layouts de janela no Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md)
- [Fontes e cores, ambiente, caixa de diálogo Opções](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)
