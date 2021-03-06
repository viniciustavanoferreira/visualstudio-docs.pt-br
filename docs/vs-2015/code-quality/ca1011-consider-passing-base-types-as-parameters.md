---
title: 'CA1011: considerar a passagem de tipos base como parâmetros | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 3968d81e8ee18b4b0a56bed50f7aa1f121e1c074
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663252"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: considere a passagem dos tipos base como parâmetros
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Categoria|Microsoft. Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Uma declaração de método inclui um parâmetro formal que é um tipo derivado, e o método chama somente os membros do tipo base do parâmetro.

## <a name="rule-description"></a>Descrição da Regra
 Quando um tipo de base é especificado como um parâmetro em uma declaração de método, qualquer tipo derivado do tipo de base pode ser passado como o argumento correspondente ao método. Quando o argumento é usado dentro do corpo do método, o método específico que é executado depende do tipo do argumento. Se a funcionalidade adicional fornecida pelo tipo derivado não for necessária, o uso do tipo base permitirá um uso mais amplo do método.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, altere o tipo do parâmetro para seu tipo base.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É seguro suprimir um aviso dessa regra

- Se o método exigir a funcionalidade específica que é fornecida pelo tipo derivado

   \- ou -

- para impor que apenas o tipo derivado, ou um tipo mais derivado, é passado para o método.

  Nesses casos, o código será mais robusto devido à verificação de tipo forte que é fornecida pelo compilador e tempo de execução.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra um método, `ManipulateFileStream`, que pode ser usado somente com um objeto <xref:System.IO.FileStream>, que viola essa regra. Um segundo método, `ManipulateAnyStream`, satisfaz a regra substituindo o parâmetro <xref:System.IO.FileStream> usando um <xref:System.IO.Stream>.

 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cpp/FxCop.Design.ConsiderPassingBaseTypes.cpp#1)]
 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cs/FxCop.Design.ConsiderPassingBaseTypes.cs#1)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/vb/FxCop.Design.ConsiderPassingBaseTypes.vb#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA1059: os membros não devem expor determinados tipos concretos](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)
