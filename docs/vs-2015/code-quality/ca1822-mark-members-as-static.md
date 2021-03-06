---
title: 'CA1822: marcar Membros como estáticos | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 0ce4aa6aef9c70d0d628603afa7a256c309f280d
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75917939"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: marcar membros como estáticos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obter a documentação mais recente sobre o Visual Studio, consulte [CA1822: marcar Membros como estáticos](/visualstudio/code-quality/ca1822-mark-members-as-static).

|||
|-|-|
|NomeDoTipo|MarkMembersAsStatic|
|CheckId|CA1822|
|Categoria|Microsoft.Performance|
|Alteração Significativa|Não separável – se o membro não estiver visível fora do assembly, independentemente da alteração feita.<br /><br /> Não separável – se você simplesmente alterar o membro para um membro de instância com a palavra-chave `this`.<br /><br /> Quebrando – se você alterar o membro de um membro de instância para um membro estático e ele estiver visível fora do assembly.|

## <a name="cause"></a>Causa
 Um membro que não acessa dados de instância não está marcado como estático (compartilhado no [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).

## <a name="rule-description"></a>Descrição da Regra
 Os membros que não acessam dados da instância ou os métodos da instância de chamada podem ser marcados como estáticos (Shared no [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]). Depois que você marcar os métodos como estáticos, o compilador emitirá sites de chamada não virtuais para esses membros. A emissão de sites de chamada não virtuais impedirá uma verificação no tempo de execução para cada chamada, o que garante que o ponteiro do objeto atual seja não nulo. Isso pode obter um alto desempenho mensurável para o código sensível ao desempenho. Em alguns casos, a falha ao acessar a instância do objeto atual representa um problema de correção.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Marque o membro como estático (ou compartilhado em [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) ou use ' this '/' me ' no corpo do método, se apropriado.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É seguro suprimir um aviso dessa regra para o código fornecido anteriormente para o qual a correção seria uma alteração significativa.

## <a name="related-rules"></a>Regras relacionadas
 [CA1811: evitar código privado não chamado](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: evitar classes internas sem instâncias](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804: remover locais não usados](../code-quality/ca1804-remove-unused-locals.md)
