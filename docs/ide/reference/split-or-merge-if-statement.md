---
title: Dividir ou mesclar instruções if
ms.date: 03/10/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: a3b42f83faacda6be34b282150cf4fb4c0f379f1
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79093694"
---
# <a name="split-or-merge-if-statements"></a>Dividir ou mesclar instruções if

Esta refatoração aplica-se a:

- C#

- Visual Basic

**O quê:** **Dividir** ou fundir [se](/dotnet/csharp/language-reference/keywords/if-else) as declarações.

**Quando:** Você deseja dividir `if` uma declaração `&&` que use os `if` operadores em `if` `||` uma declaração aninhada ou mesclar uma declaração com uma declaração externa. `if`

**Por que:** É uma questão de preferência de estilo.  

## <a name="how-to"></a>Como fazer

Se você quiser dividir a instrução `if`:

1. Coloque o cursor na instrução `if` pelo operador `&&` ou `||`.

2. Pressione **Ctrl**+**.** para acionar o menu **Ações e Refatorações Rápidas**.

    ![Dividir instrução if](../media/split-if-statement.png)

3. Selecione **Dividir em instruções if aninhadas**.

    ![Dividir instrução if concluída](../media/split-if-statement-complete.png)

Se você deseja mesclar a instrução `if` interna com a instrução `if` externa: 

1. Coloque o cursor na palavra-chave `if` interna.

2. Pressione **Ctrl**+**.** para acionar o menu **Ações e Refatorações Rápidas**.

    ![Mesclar instrução If](../media/merge-if-statement.png)

3. Selecione **Mesclar com instrução if externa**.

    ![Mesclar instrução if concluída](../media/merge-if-statement-complete.png)

## <a name="see-also"></a>Confira também

- [Refatoração](../refactoring-in-visual-studio.md)