---
title: '&lt;signature&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <signature> JavaScript XML tag
- signature JavaScript XML tag
ms.assetid: 319138e7-cfbe-4b37-9643-2ddb7f9c63d4
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b4c640c28ada16a8a03943fcd1362d4fd521772c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671123"
---
# <a name="ltsignaturegt-javascript"></a>&lt;signature&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Agrupa um conjunto de elementos relacionados para uma função ou método para fornecer documentação para funções sobrecarregadas.

## <a name="syntax"></a>Sintaxe

```
<signature externalid="id" externalFile="filename"
    helpKeyword="keyword" locid="descriptionID">
</signature>
```

#### <a name="parameters"></a>Parâmetros
 `externalid` Opcional. Se o atributo `format` para o elemento [\<loc >](../ide/loc-javascript.md) for `vsdoc`, esse atributo especificará a ID de membro usada para localizar o código XML associado à assinatura. Ao contrário do atributo `locid`, esse atributo especifica que todos os elementos no membro com essa ID devem ser carregados. Todas as informações de descrição associadas presentes no código XML também serão mescladas com os elementos especificados na assinatura. Isso permite que você especifique elementos adicionais, como `<capability>`, no arquivo sidecar sem especificá-los no arquivo de origem. `externalid` é um atributo opcional.

 `externalFile` Opcional. Especifica o nome do arquivo no qual localizar o `externalid`. Esse atributo será ignorado se nenhum `externalid` estiver presente. Esse é um atributo opcional. O valor padrão é o nome do arquivo atual, mas com uma extensão de arquivo. xml em vez de. js. Por padrão, as regras de pesquisa de recursos gerenciados para localização são usadas para localizar o arquivo.

 `helpKeyword` Opcional. A palavra-chave para a ajuda F1.

 `locid` Opcional. O identificador para informações de localização sobre o campo. O identificador é uma ID de membro ou ele corresponde ao valor do atributo `name` em um pacote de mensagens definido pelos metadados OpenAjax. O tipo do identificador depende do formato especificado na marca [\<loc>](../ide/loc-javascript.md).

## <a name="remarks"></a>Comentários
 Use um elemento `<signature>` para cada descrição de função sobrecarregada no arquivo. js ou use um elemento `<signature>` para cada ID de membro externo especificado.

 O elemento `<signature>` deve ser colocado no corpo da função antes de qualquer instrução. Ao usar [\<summary >](../ide/summary-javascript.md), [\<param >](../ide/param-javascript.md)ou [\<returns](../ide/returns-javascript.md) elementos > com o elemento `<signature>`, coloque os outros elementos dentro do bloco `<signature>`.

## <a name="example"></a>Exemplo
 O exemplo de código a seguir mostra como usar o elemento `<signature>`.

```javascript
// Use of <signature> with externalid.
// Requires use of the <loc> tag to identify the external functions.
function illuminate(light) {
    /// <signature externalid='M:Windows.Devices.Light.Illuminate()' />
    /// <signature externalid='M:Windows.Devices.Light.Illuminate(System.Int32)'>
    ///   <param name='light' type='Number' />
    /// </signature>
}

// Use of <signature> for overloads implemented in JavaScript.
function add(a, b) {
    /// <signature>
    /// <summary>function summary 1</summary>
    /// <param name="a" type="Number">The first number</param>
    /// <param name="b" type="Number">The second number</param>
    /// <returns type="Number" />
    /// </signature>
    /// <signature>
    /// <summary>function summary 2 – differ by number of params</summary>
    /// <param name="a" type="Number">Only 1 parameter</param>
    /// <returns type="Number" />
    /// </signature>
    /// <signature>
    /// <summary>function summary 3 – differ by parameter type</summary>
    /// <param name="a" type="Number">Number parameter</param>
    /// <param name="b" type="String">String parameter</param>
    /// <returns type="Number" />
    /// </signature>
    /// <signature>
    /// <summary>function summary 4 – differ by return type</summary>
    /// <param name="a" type="Number">The first number</param>
    /// <param name="b" type="Number">The second number</param>
    /// <returns type="String" />
    /// </signature>

    return a + b;
}
```

## <a name="see-also"></a>Veja também
 [Comentários da documentação XML](../ide/xml-documentation-comments-javascript.md)
