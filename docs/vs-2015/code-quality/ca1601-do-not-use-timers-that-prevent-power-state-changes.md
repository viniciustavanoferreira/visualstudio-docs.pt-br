---
title: 'CA1601: não use temporizadores que impeçam alterações de estado de energia | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 95f13604908ad45c5f33a011fec886bba90d0bd8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669287"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: não usar temporizadores que impeçam alterações no estado de energia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|Categoria|Microsoft. Mobility|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um temporizador tem um intervalo definido para ocorrer mais de uma vez por segundo.

## <a name="rule-description"></a>Descrição da Regra
 Não sondar com mais frequência do que uma vez por segundo ou usar temporizadores que ocorrem com mais frequência do que uma vez por segundo. A atividade periódica de alta frequência manterá a CPU ocupada e interferirá nos temporizadores ociosos que economizam energia e desligam monitores e discos rígidos.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Defina intervalos de timer para ocorrer menos de uma vez por segundo.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Essa regra deve ser suprimida somente se o acionamento do temporizador mais de uma vez por segundo for necessário e as considerações de mobilidade puderem ser ignoradas com segurança.
