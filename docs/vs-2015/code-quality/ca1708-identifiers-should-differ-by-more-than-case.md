---
title: 'CA1708: os identificadores devem ser diferentes em mais de caso | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f611cb899a2386c47e1370214a74c2a5da52584f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669209"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: os identificadores devem ser diferentes além de maiúsculas de minúsculas
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Categoria|Microsoft. Naming|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Os nomes de dois tipos, membros, parâmetros ou namespaces totalmente qualificados são idênticos quando são convertidos em minúsculas.

## <a name="rule-description"></a>Descrição da Regra
 Os identificadores de namespaces, tipos, membros e parâmetros não podem se diferenciar apenas por maiúsculas porque linguagens com o Common Language Runtime como destino não precisam diferenciar maiúsculas e minúsculas. Por exemplo, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] é uma linguagem muito usada, que não diferencia maiúsculas de minúsculas.

 Esta regra é acionada somente em Membros publicamente visíveis.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Selecione um nome que seja exclusivo quando comparado a outros identificadores de uma maneira que não diferencia maiúsculas de minúsculas.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra. A biblioteca pode não ser utilizável em todos os idiomas disponíveis no [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].

## <a name="example-of-a-violation"></a>Exemplo de uma violação
 O exemplo a seguir demonstra uma violação dessa regra.

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase/cs/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase.cs#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA1709: os identificadores devem ter maiúsculas e minúsculas corretas](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
