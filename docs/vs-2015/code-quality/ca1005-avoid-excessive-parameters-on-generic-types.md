---
title: 'CA1005: evitar parâmetros excessivos em tipos genéricos | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7e75b2e295a561e026b437b3c62724536a3ac64e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671985"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: evitar parâmetros excessivos em tipos genéricos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|Categoria|Microsoft. Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um tipo genérico visível externamente tem mais de dois parâmetros de tipo.

## <a name="rule-description"></a>Descrição da Regra
 Quanto mais parâmetros de tipo um tipo genérico contiver, mais difícil será saber e lembrar-se do que cada parâmetro de tipo representa. Normalmente, é óbvio com um parâmetro de tipo, como em `List<T>` e, em certos casos, com dois parâmetros de tipo, como em `Dictionary<TKey, TValue>`. Se houver mais de dois parâmetros de tipo, a dificuldade se tornará muito grande para a maioria dos usuários ( C# por exemplo, `TooManyTypeParameters<T, K, V>` no ou `TooManyTypeParameters(Of T, K, V)` no [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, altere o design para não usar mais do que dois parâmetros de tipo.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprimir um aviso dessa regra, a menos que o design absolutamente exija mais do que dois parâmetros de tipo. Fornecer genéricos em uma sintaxe que seja fácil de entender e usar reduz o tempo necessário para aprender e aumentar a taxa de adoção de novas bibliotecas.

## <a name="related-rules"></a>Regras relacionadas
 [CA1010: as coleções devem implementar a interface genérica](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: não declarar membros estáticos em tipos genéricos](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: não expor listas genéricas](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: não aninhar tipos genéricos em assinaturas de membro](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: os métodos genéricos devem fornecer o parâmetro de tipo](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: usar instâncias do manipulador de eventos genéricos](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: usar genéricos quando apropriado](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Consulte também
 [Genéricos](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
