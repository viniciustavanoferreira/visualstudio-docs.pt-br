---
title: Refatoração Remover código inacessível
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
ms.openlocfilehash: cd827870f07fb3161674d287d20f266942e61afe
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79093978"
---
# <a name="remove-unreachable-code-refactoring"></a>Refatoração Remover código inacessível

Esta refatoração aplica-se a:

- C#

- Visual Basic

**O quê:** remove o código que nunca será executado.

**Quando:** seu programa não tem um caminho para um snippet de código, tornando esse snippet de código desnecessário.

**Por quê:** melhorar a legibilidade e a facilidade de manutenção removendo o código que é supérfluo e nunca será executado.

## <a name="how-to"></a>Como fazer

1. coloque o cursor em qualquer lugar no código esmaecido que está inacessível:

![Código inacessível esmaecido](media/unreachablecode-faded-cs.png)

1. Depois, siga um destes procedimentos:

   - **Teclado**
      - Pressione **Ctrl**+**.** para disparar o menu **Ações Rápidas e Refatorações** e selecionar **Remover código inacessível** no pop-up da janela Visualização.
   - **Mouse**
      - Clique com o botão direito do mouse no código, selecione o menu **Ações Rápidas e Refatorações** e selecione **Remover código inacessível** no pop-up da janela Visualização.

1. Quando estiver satisfeito com a alteração, pressione **Enter** ou clique na correção no menu e as alterações serão confirmadas.

Exemplo:

```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>Confira também

- [Refatoração](../refactoring-in-visual-studio.md)
- [Visualizar Alterações](../../ide/preview-changes.md)
