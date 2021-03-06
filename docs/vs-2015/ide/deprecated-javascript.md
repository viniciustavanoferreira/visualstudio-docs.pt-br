---
title: '&lt;deprecated&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 343f3ebe4bea7ee999f60741c189f35defb0ac7b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665812"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;deprecated&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Especifica uma função ou um método preterido.

## <a name="syntax"></a>Sintaxe

```
<deprecated
    type="deprecate|remove"
    locid="descriptionID">description
</deprecated>
```

#### <a name="parameters"></a>Parâmetros
 `type` Opcional. Especifica se a função ou o método será removido em uma versão futura ou se a função ou o método já foi removido e se o seu uso pode resultar em um erro. Defina como `deprecate` para especificar que a função ou o método será removido em uma versão futura. Defina como `remove` para especificar que a função ou o método já foi removido.

 `locid` Opcional. O identificador de informações de localização sobre o método ou função. O identificador é uma ID de membro ou ele corresponde ao valor do atributo `name` em um pacote de mensagens definido pelos metadados OpenAjax. O tipo do identificador depende do formato especificado no elemento [\<loc>](../ide/loc-javascript.md).

 `description` Opcional. Uma descrição da função ou método que está sendo preterido.

## <a name="remarks"></a>Comentários
 Os elementos usados para anotar funções, que incluem `<deprecated>`, devem ser colocados no corpo da função antes de qualquer instrução. Ao marcar uma função como preterida, recomendamos que você substitua seu elemento [\<summary >](../ide/summary-javascript.md) pelo elemento `<deprecated>`.

## <a name="example"></a>Exemplo
 O código a seguir mostra como usar o elemento `<deprecated>`.

```javascript
function areaFunction(radiusParam) {
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>
    /// <returns type="Number">The area.</returns>
    var areaVal;
    areaVal = Math.PI * radiusParam * radiusParam;
    return areaVal;
}

```

## <a name="see-also"></a>Veja também
 [Comentários da documentação XML](../ide/xml-documentation-comments-javascript.md)
