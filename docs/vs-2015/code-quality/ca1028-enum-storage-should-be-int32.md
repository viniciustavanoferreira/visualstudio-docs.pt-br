---
title: 'CA1028: o armazenamento de enumeração deve ser Int32 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: fc1039cb547a48c4f2dd3ea869b46d4706e9c3a2
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661911"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: o armazenamento de enum deve ser Int32
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Categoria|Microsoft. Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 O tipo subjacente de uma enumeração pública não é <xref:System.Int32?displayProperty=fullName>.

## <a name="rule-description"></a>Descrição da Regra
 Uma enumeração é um tipo de valor que define um conjunto de constantes nomeadas relacionadas. Por padrão, o tipo de dados <xref:System.Int32?displayProperty=fullName> é usado para armazenar o valor constante. Embora você possa alterar esse tipo subjacente, ele não é necessário ou recomendado para a maioria dos cenários. Observe que nenhum benefício de desempenho significativo é obtido usando um tipo de dados menor do que <xref:System.Int32>. Se você não puder usar o tipo de dados padrão, deverá usar um dos tipos integrais compatíveis com o sistema de linguagem comum (CLS), <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> ou <xref:System.Int64> para garantir que todos os valores da enumeração possam ser representados na programação em conformidade com CLS Idiomas.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, a menos que existam problemas de tamanho ou compatibilidade, use <xref:System.Int32>. Para situações em que <xref:System.Int32> não é grande o suficiente para manter os valores, use <xref:System.Int64>. Se a compatibilidade com versões anteriores exigir um tipo de dados menor, use <xref:System.Byte> ou <xref:System.Int16>.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Suprimir um aviso desta regra somente se os problemas de compatibilidade com versões anteriores exigirem. Em aplicativos, a falha em obedecer a essa regra geralmente não causa problemas. Em bibliotecas, em que a interoperabilidade de linguagem é necessária, a falha na conformidade com essa regra pode afetar negativamente os usuários.

## <a name="example-of-a-violation"></a>Exemplo de uma violação

### <a name="description"></a>Descrição
 O exemplo a seguir mostra duas enumerações que não usam o tipo de dados subjacente recomendado.

### <a name="code"></a>Código
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/cs/FxCop.Design.EnumIntegralType.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralType#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/vb/FxCop.Design.EnumIntegralType.vb#1)]

## <a name="example-of-how-to-fix"></a>Exemplo de como corrigir

### <a name="description"></a>Descrição
 O exemplo a seguir corrige a violação anterior alterando o tipo de dados subjacente para <xref:System.Int32>.

### <a name="code"></a>Código
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/cs/FxCop.Design.EnumIntegralTypeFixed.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/vb/FxCop.Design.EnumIntegralTypeFixed.vb#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA1008: as enums devem ter valor zero](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: marcar enums com FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: não marcar enums com FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: não nomear valores de enum como 'Reservados'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: não usar valores de enum como prefixo com o nome do tipo](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>Consulte também
 <xref:System.Byte?displayProperty=fullName> <xref:System.Int16?displayProperty=fullName>
 <xref:System.Int32?displayProperty=fullName>
 <xref:System.Int64?displayProperty=fullName>
