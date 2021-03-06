---
title: Ações rápidas, lâmpadas e chaves de fenda
ms.date: 03/28/2018
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2ce8ce85e027a7ed7f78d0da1f68f328c1ca103d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75596951"
---
# <a name="quick-actions"></a>Ações Rápidas

As Ações Rápidas permitem refatorar, gerar ou, de outro modo, modificar o código de maneira fácil com uma única ação. As Ações Rápidas estão disponíveis para C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp) e os arquivos de código do Visual Basic. Algumas ações são específicas para uma linguagem e outras se aplicam a todas as linguagens.

É possível usar as Ações rápidas para:

- Aplique uma correção de código para uma violação de regra [do analisador de código](../code-quality/roslyn-analyzers-overview.md)

::: moniker range=">=vs-2019"

- [Suprimir](../code-quality/use-roslyn-analyzers.md#suppress-violations) uma violação de regra do analisador de código ou [configurar](../code-quality/use-roslyn-analyzers.md#automatically-configure-rule-severity) sua gravidade

::: moniker-end

::: moniker range="vs-2017"

- [Suprimir](../code-quality/use-roslyn-analyzers.md#suppress-violations) uma violação de regra do analisador de código

::: moniker-end

- Aplique uma refatoração (por exemplo, [inline uma variável temporária](../ide/reference/inline-temporary-variable.md))

- Gerar código (por exemplo, [introduzir uma variável local)](../ide/reference/introduce-local-variable.md)

> [!NOTE]
> Este tópico aplica-se ao Visual Studio no Windows. Para o Visual Studio para Mac, confira [Refatoração (Visual Studio para Mac)](/visualstudio/mac/refactoring).

Ações rápidas podem ser aplicadas ![usando o](media/light-bulb-icon.png) ícone ![da lâmpada](media/screwdriver-icon.png) da lâmpada ou ícones da chave de fenda, ou pressionando **Ctrl**+**.** quando o cursor estiver em uma linha de código para a qual uma ação está disponível. Você verá uma lâmpada de erro ![ícone de lâmpada de erro](media/error-light-bulb-icon.png) se houver um rabisco vermelho, indicando um erro e o Visual Studio terá uma solução disponível para esse erro.

Para qualquer linguagem, terceiros podem oferecer sugestões e diagnósticos personalizados, por exemplo, como parte de um SDK, e as lâmpadas do Visual Studio aparecerão de acordo com essas regras.

## <a name="icons"></a>Ícones

O ícone exibido quando uma Ação Rápida fica disponível oferece uma indicação do tipo de correção ou que a refatoração está disponível. O ícone de *chave de fenda* ![ícone de chave de fenda](media/screwdriver-icon.png) indica apenas que há ações disponíveis para alterar o código, mas você não deve necessariamente usá-las. O ícone de *lâmpada amarela* ![ícone de lâmpada](media/light-bulb-icon.png) indica que há ações disponíveis que você *deve* executar para melhorar o seu código. O ícone de *lâmpada de erro* ![ícone de lâmpada de erro](media/error-light-bulb-icon.png) indica que há uma ação disponível que corrige um erro no seu código.

## <a name="to-see-a-light-bulb-or-screwdriver"></a>Para ver uma lâmpada ou chave de fenda

Se uma correção estiver disponível, lâmpadas aparecerão:

- Quando você passa o mouse no local de um erro

   ![Lâmpada com o mouse focalizando](../ide/media/vs2015_lightbulb_hover.png)

- Na margem esquerda do editor quando você move o cursor para a linha aplicável do código

Você também pode pressionar **Ctrl**+**.** em qualquer lugar em uma linha para ver uma lista de Ações Rápidas e refatorações disponíveis.

Para ver possíveis correções, selecione a seta para baixo ao lado da lâmpada ou do link **Mostrar possíveis correções**. Uma lista de Ações Rápidas disponíveis é exibida.

![Lâmpada expandida](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>Confira também

- [Geração de código no Visual Studio](../ide/code-generation-in-visual-studio.md)
- [Ações Rápidas Comuns](../ide/common-quick-actions.md)
- [Estilos de código e Ações Rápidas](../ide/code-styles-and-code-cleanup.md)
- [Escrever e refatorar o código (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
- [Refatoração (Visual Studio para Mac)](/visualstudio/mac/refactoring)
