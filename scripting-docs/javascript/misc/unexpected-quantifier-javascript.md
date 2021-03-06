---
title: Quantificador inesperado (JavaScript) | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2070ec6ad01eb62c6be9b6b9acfc91cba7bc863d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572530"
---
# <a name="unexpected-quantifier-javascript"></a>Quantificador inesperado (JavaScript)
Ao compor seu padrão de pesquisa de expressão regular, você criou um elemento pattern com um fator de repetição ilegal. Por exemplo, o padrão  
  
```js
/^+/  
```  
  
 é inválido porque o elemento ^ (início da entrada) não pode ter um fator de repetição. A tabela a seguir lista os elementos que não podem ter fatores de repetição.  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|^|Início da entrada|  
|$|Fim da entrada|  
|\b|Limite de palavra|  
|\B|Limite de não palavra|  
|*|Zero ou mais repetições|  
|+|Uma ou mais repetições|  
|?|Zero ou uma repetição|  
|p|n repetições|  
|{n,}|n ou mais repetições|  
|{n, m}|De n a m repetições, inclusivo|  
  
### <a name="to-correct-this-error"></a>Para corrigir este erro  
  
- Verifique se o seu elemento de padrão de pesquisa contém apenas fatores de repetição legal.  
  
## <a name="see-also"></a>Consulte também  
 @No__t_1 de [objeto de expressão regular](../../javascript/reference/regular-expression-object-javascript.md)  
 [Sintaxe de expressão regular (JavaScript)](https://msdn.microsoft.com/library/1400241x)