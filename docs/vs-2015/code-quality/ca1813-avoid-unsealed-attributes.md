---
title: 'CA1813: evitar atributos não lacrados | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: fe5967ef099794b6c71029e9d03d959dd83b01dc
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72647064"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: evitar atributos não lacrados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Categoria|Microsoft. performance|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um tipo público herda de <xref:System.Attribute?displayProperty=fullName>, não é abstrato e não é lacrado (`NotInheritable` em Visual Basic).

## <a name="rule-description"></a>Descrição da Regra
 A biblioteca de classes do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] fornece métodos para recuperar atributos personalizados. Por padrão, esses métodos pesquisam a hierarquia de herança de atributo; por exemplo <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> pesquisa o tipo de atributo especificado ou qualquer tipo de atributo que estenda o tipo de atributo especificado. Lacrar o atributo elimina a pesquisa por meio da hierarquia de herança e pode melhorar o desempenho.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, lacre o tipo de atributo ou torne-o abstrato.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É seguro suprimir um aviso dessa regra. Você deve fazer isso somente se estiver definindo uma hierarquia de atributo e não puder lacrar o atributo ou torná-lo abstrato.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra um atributo personalizado que satisfaz essa regra.

 [!code-csharp[FxCop.Performance.AttributesSealed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.AttributesSealed/cs/FxCop.Performance.AttributesSealed.cs#1)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.AttributesSealed/vb/FxCop.Performance.AttributesSealed.vb#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA1019: definir acessadores para argumentos de atributo](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1018: marcar atributos com AttributeUsageAttribute](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>Consulte também
 [Atributos](https://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)
