---
title: Criar minidespejos com todas as pilhas de chamadas
ms.date: 06/27/2019
ms.topic: conceptual
helpviewer_keywords:
- minidumps for Visual Studio issues"
author: corob-msft
ms.author: corob
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Collect minidumps to send to Microsoft for help with troubleshooting issues with Visual Studio
ms.openlocfilehash: 7b3be91e5d0d2e1f14724dd647670fc4885bcd4d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77271193"
---
# <a name="create-minidumps-for-a-visual-studio-process-with-all-call-stacks"></a>Criar minidespejos para um processo do Visual Studio com todas as pilhas de chamadas

Em alguns casos, a Microsoft pode solicitar o minidespejo de um processo em execução do Visual Studio com informações de todas as pilhas de chamadas. Para coletar essas informações, execute estas etapas:

## <a name="create-the-minidump-file"></a>Criar o arquivo de minidespejo

1. Inicie uma nova instância do Visual Studio.
1. No menu principal, escolha **Depurar** > **Anexar ao processo**.
1. Marque as caixas de seleção **Gerenciado** e **Nativo** relevantes e pressione **Anexar**.

   ![Anexar ao processo](../ide/media/attach-to-process.png)

1. Selecione a outra instância do Visual Studio a anexar na lista de processos em execução.
1. No menu principal, escolha **Debug** > **Break All**.
1. No menu principal, escolha **Depurar** > **Salvar dump as**.

## <a name="get-the-call-stacks-from-the-minidump"></a>Obter as pilhas de chamadas do minidespejo

1. Abra o arquivo de despejo no Visual Studio.
1. Vá para **Ferramentas** > **Opções** > **Depuração** > de**símbolos** e certifique-se de que os **servidores símbolos do Microsoft** estão verificados nos locais do arquivo Símbolo **(.pdb).**
1. Abra a janela **Comando** (**Exibição** > **Outras janelas** > **Janela de Comando**)
1. Digite '~*k'. A janela exibe as pilhas de chamadas de todos os threads.
1. Copie todo o texto da Janela de Comando e salve em um arquivo de texto.
1. Anexe o arquivo txt ao bug.
