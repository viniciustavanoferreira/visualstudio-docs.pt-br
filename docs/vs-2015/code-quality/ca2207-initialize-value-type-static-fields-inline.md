---
title: 'CA2207: inicializar campos estáticos de tipo de valor embutido | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: a2b3c1faf4ecf3ecf79a3c78d0ded106b88345ee
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72609362"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: inicializar campos estáticos de tipo de valor embutido
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|Categoria|Microsoft. Usage|
|Alteração Significativa|Sem interrupção|

## <a name="cause"></a>Causa
 Um tipo de valor declara um construtor estático explícito.

## <a name="rule-description"></a>Descrição da Regra
 Quando um valor tipo é declarado, ele passa por uma inicialização padrão onde todos os campos de tipo de valor são definidos como zero e todos os campos de tipo de referência são definidos como `null` (`Nothing` em Visual Basic). Um construtor estático explícito só é garantido para execução antes de um construtor de instância ou membro estático do tipo ser chamado. Portanto, se o tipo for criado sem chamar um construtor de instância, não haverá garantia de que o construtor estático seja executado.

 Se todos os dados estáticos forem inicializados em linha e nenhum construtor estático explícito C# for declarado, os compiladores e Visual Basic adicionarão o sinalizador `beforefieldinit` à definição da classe MSIL. Os compiladores também adicionam um construtor estático privado que contém o código de inicialização estático. Esse construtor estático privado tem a garantia de ser executado antes que qualquer campo estático do tipo seja acessado.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, inicialize todos os dados estáticos quando ele estiver declarado e remova o construtor estático.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Não suprima um aviso nessa regra.

## <a name="related-rules"></a>Regras relacionadas
 [CA1810: inicializar campos estáticos de tipo de referência embutido](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)
