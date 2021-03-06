---
title: 'CA2141: métodos Transparent não devem satisfazer LinkDemands | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 5e8e88401a6fbe3ab7dc635dadee9215b049b2d5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602842"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141:Transparent métodos não devem atender a LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um método transparente de segurança chama um método em um assembly que não está marcado com o atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) ou um método transparente de segurança satisfaz um `.LinkDemand` <xref:System.Security.Permissions.SecurityAction> para um tipo ou um método.

## <a name="rule-description"></a>Descrição da Regra
 Satisfazer um LinkDemand é uma operação sensível à segurança que pode causar a elevação não intencional de privilégio. O código Transparent de segurança não deve satisfazer LinkDemands, pois não está sujeito aos mesmos requisitos de auditoria de segurança que o código crítico de segurança. Os métodos Transparent nos assemblies de nível 1 do conjunto de regras de segurança farão com que todas as LinkDemands que eles satisfazem sejam convertidas para solicitações completas em tempo de execução, o que pode causar problemas de desempenho Nos assemblies de nível 2 do conjunto de regras de segurança, os métodos transparentes não serão compilados no compilador JIT (just-in-time) se tentarem atender a um LinkDemand.

 Em assemblies que usee segurança de nível 2, tentativas por um método transparente de segurança para satisfazer um LinkDemand ou chamar um método em um assembly não APTCA gera um <xref:System.MethodAccessException>; em assemblies de nível 1, LinkDemand torna-se uma demanda completa.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, marque o método de acesso com o atributo <xref:System.Security.SecurityCriticalAttribute> ou <xref:System.Security.SecuritySafeCriticalAttribute> ou remova LinkDemand do método acessado.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra.

## <a name="example"></a>Exemplo
 Neste exemplo, um método transparente tenta chamar um método que tem um LinkDemand. Esta regra será acionada neste código.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2141.transparentmethodsmustnotsatisfylinkdemands/cs/ca2141 - transparentmethodsmustnotsatisfylinkdemands.cs#1)]
