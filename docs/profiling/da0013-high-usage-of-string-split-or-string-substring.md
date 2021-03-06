---
title: 'DA0013: alto uso de String.Split ou String.Substring | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: d42469ac5236a41eda96af5d1fe896a5ed84a321
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779396"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: uso alto de String.Split ou String.Substring

|||
|-|-|
|ID de regra|DA0013|
|Categoria|Diretrizes de uso do .NET Framework|
|Métodos de criação de perfil|amostragem|
|Mensagem|Considere a possibilidade de reduzir o uso das funções String.Split e String.Substring.|
|Tipo de regra|Aviso|

## <a name="cause"></a>Causa
 Chamadas aos métodos System.String.Split ou System.String.Substring são uma proporção significativa dos dados de criação de perfil. Considere o uso de System.String.IndexOf ou System.String.IndexOfAny se estiver testando a existência de uma subcadeia de caracteres em uma cadeia de caracteres.

## <a name="rule-description"></a>Descrição da regra
 O método Split opera em um objeto String e retorna uma nova matriz de Strings que contém as subcadeias da original. A função aloca memória ao objeto de matriz retornado e aloca um novo objeto String a cada elemento de matriz encontrado. Da mesma forma, o método Substr funciona em um objeto String e retorna uma nova String equivalente à subcadeia de caracteres solicitada.

 Se o gerenciamento de alocações de memória for crítico para seu aplicativo, considere o uso de alternativas aos métodos String.Split e String.Substr. Por exemplo, é possível usar o método IndexOf ou IndexOfAny para localizar uma subcadeia de caracteres específica em uma String de caracteres sem criar uma nova instância da classe String.

## <a name="how-to-investigate-a-warning"></a>Como investigar um aviso
 Clique duas vezes na mensagem na janela **Lista de erros** para navegar até a exibição de [detalhes](../profiling/function-details-view.md) da função dos dados do perfil de amostragem. Examine as funções de chamada para encontrar as seções do programa que fazem o uso mais frequente dos métodos System.String.Split ou System.String.Substr. Se possível, use o método IndexOf ou IndexOfAny para localizar uma subcadeia de caracteres específica em uma String de caracteres sem criar uma nova instância da classe String.
