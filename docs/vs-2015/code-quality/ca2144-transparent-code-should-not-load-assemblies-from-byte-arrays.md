---
title: 'CA2144: o código transparent não deve carregar assemblies de matrizes de bytes | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 36b27880b5574e9e47067c240bc162cc15e8d3b6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72610312"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: o código transparente não deve carregar assemblies a partir de matrizes de bytes
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um método transparente carrega um assembly de uma matriz de bytes usando um dos seguintes métodos:

- <xref:System.Reflection.Assembly.Load%2A>

- <xref:System.Reflection.Assembly.Load%2A>

- <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>Descrição da Regra
 A revisão de segurança para o código transparente não é tão completo quanto a revisão de segurança para o código crítico porque o código transparente não pode realizar ações confidenciais de segurança. Os assemblies carregados a partir de uma matriz de bytes podem não ser observados no código transparente e essa matriz de bytes pode conter código crítico ou código crítico de segurança mais importante, que precisa ser auditado. Portanto, o código transparent não deve carregar assemblies de uma matriz de bytes.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, marque o método que está carregando o assembly com o <xref:System.Security.SecurityCriticalAttribute> ou o atributo <xref:System.Security.SecuritySafeCriticalAttribute>.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra.

## <a name="example"></a>Exemplo
 A regra é acionada no código a seguir porque um método transparente carrega um assembly de uma matriz de bytes.

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2144.transparentmethodsshouldnotloadassembliesfrombytearrays/cs/ca2144 - transparentmethodsshouldnotloadassembliesfrombytearrays.cs#1)]
