---
title: Adicionar uma regra de limite para teste de carga
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d1389df0c307ad6ec65575fc7934e622928a0ca1
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75591626"
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Como adicionar uma regra de limite usando o Editor de Teste de Carga

As regras de limite nos testes de carga comparam um valor de contador de desempenho ou com um valor constante, ou outro valor de contador de desempenho.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-add-a-threshold-rule"></a>Para adicionar uma regra de limite

1. Abra um teste de carga.

2. No Editor de Teste de Carga, expanda o nó **Conjuntos de contadores**.

3. Expanda uma das **Categorias de contadores** em um dos Conjuntos de contadores. Por exemplo, você pode selecionar **LoadTest:Scenario**. Expanda o nó.

4. Clique com o botão direito do mouse em um dos contadores, por exemplo, **Carga de usuários**, em **LoadTest:Scenario**. Selecione **Adicionar regra de limite**.

     A caixa de diálogo **Adicionar regra de limite** é exibida.

5. Você pode escolher entre dois tipos de regra: **Comparar Constante** e **Comparar Contador**. Selecione o tipo apropriado e defina os valores.

    > [!NOTE]
    > Defina a propriedade **Alertar caso seja superado** como **Verdadeiro** para indicar que ultrapassar um limite é um problema ou como **Falso** para indicar que ficar abaixo do limite é um problema.

## <a name="see-also"></a>Confira também

- [Analisar violações de regra de limite](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Especificar os conjuntos de contadores e as regras de limite para computadores em um teste de carga](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analisar os resultados do teste de carga](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
