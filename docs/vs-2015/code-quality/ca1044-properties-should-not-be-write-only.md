---
title: 'CA1044: as propriedades não devem ser somente gravação | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: aa2d07337ec48e41a9d8ad82602a387159192f92
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668271"
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044: as propriedades não devem ser somente leitura
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|Categoria|Microsoft. Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 A propriedade pública ou protegida tem um acessador set, mas não tem um acessador get.

## <a name="rule-description"></a>Descrição da Regra
 Obter acessadores fornecem acesso de leitura a uma propriedade e os acessadores de conjunto fornecem acesso de gravação. Embora seja aceitável e normalmente necessário ter uma propriedade somente leitura, as diretrizes de design proíbem o uso de propriedades somente gravação. Isso ocorre porque permitir que um usuário defina um valor e, em seguida, impedir que o usuário exiba o valor não fornece nenhuma segurança. Além disso, sem acesso de leitura, o estado de objetos compartilhados não pode ser exibido, o que limita sua utilidade.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, adicione um acessador get à propriedade. Como alternativa, se o comportamento de uma propriedade somente gravação for necessário, considere converter essa propriedade em um método.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É altamente recomendável que você não omita um aviso dessa regra.

## <a name="example"></a>Exemplo
 No exemplo a seguir, `BadClassWithWriteOnlyProperty` é um tipo com uma propriedade somente gravação. `GoodClassWithReadWriteProperty` contém o código corrigido.

 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/cs/FxCop.Design.PropertiesNotWriteOnly.cs#1)]
 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/vb/PropertiesNotWriteOnly.vb#1)]
