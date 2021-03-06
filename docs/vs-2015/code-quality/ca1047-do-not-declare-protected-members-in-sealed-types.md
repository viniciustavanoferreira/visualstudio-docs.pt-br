---
title: 'CA1047: não declarar membros protegidos em tipos lacrados | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ebc6732e559b70e753a44b14cf45b7de9fc150d4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668178"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: não declarar membros protegidos em tipos lacrados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|Categoria|Microsoft. Design|
|Alteração Significativa|Sem interrupção|

## <a name="cause"></a>Causa
 Um tipo público é `sealed` (`NotInheritable` no Visual Basic) e declara um membro protegido ou um tipo aninhado protegido. Essa regra não relata violações para métodos de <xref:System.Object.Finalize%2A>, que devem seguir esse padrão.

## <a name="rule-description"></a>Descrição da Regra
 Os tipos declaram membros protegidos de forma que a herança de tipos possa acessar ou substituir o membro. Por definição, você não pode herdar de um tipo lacrado, o que significa que métodos protegidos em tipos lacrados não podem ser chamados.

 O C# compilador emite um aviso para esse erro.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, altere o nível de acesso do membro para privado ou torne o tipo herdável.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra. Deixar o tipo em seu estado atual pode causar problemas de manutenção e não fornece nenhum benefício.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra um tipo que viola essa regra.

 [!code-csharp[FxCop.Design.SealedNoProtected#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.SealedNoProtected/cs/FxCop.Design.SealedNoProtected.cs#1)]
 [!code-vb[FxCop.Design.SealedNoProtected#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.SealedNoProtected/vb/FxCop.Design.SealedNoProtected.vb#1)]
