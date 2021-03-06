---
title: '&lt;loc&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <loc> JavaScript XML tag
- loc JavaScript XML tag
ms.assetid: 0d3349b6-4bdd-418f-bc11-73665305baae
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cf6016b2c12fd5ebe7cfb76c14c776508d99d2db
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651474"
---
# <a name="ltlocgt-javascript"></a>&lt;loc&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Especifica o local e o tipo do arquivo sidecar que fornece informações do IntelliSense localizadas.

## <a name="syntax"></a>Sintaxe

```
<loc filename="filename"
    format="vsdoc|messagebundle" />
```

#### <a name="parameters"></a>Parâmetros
 `filename` Opcional. O nome raiz do arquivo sidecar que contém informações de localização para a cultura neutra. Quando o Visual Studio pesquisa informações de localização, ele tenta encontrar uma versão específica da cultura desse arquivo. Por exemplo, se `filename` for jQuery. xml, o Visual Studio pesquisará a pasta específica da cultura correta (como JA) no mesmo local que o arquivo. js que contém o elemento `<loc>`. Se ele localizar a pasta específica da cultura, ele verificará se existe um arquivo jQuery. xml nela. Se não for possível localizar o arquivo correto, ele usará regras de local de recurso gerenciado. O valor padrão para `filename` é o nome do arquivo atual, mas com uma extensão. xml em vez de. js.

 `format` Opcional. O tipo de arquivo sidecar usado para localização. Use `messagebundle` para especificar o uso de grupos de mensagens definidos por metadados abertos do Ajax. `messagebundle` é o formato recomendado. No entanto, esse formato não tem suporte no Microsoft Ajax ou em arquivos. winmd. Use `vsdoc` para especificar o formato de localização de .NET Framework padrão usado pelo Microsoft Ajax e Windows Runtime. Esse atributo é opcional. `vsdoc` é o formato padrão.

## <a name="remarks"></a>Comentários
 O elemento `<loc>` deve aparecer na parte superior do arquivo na mesma seção que o elemento `<reference>`. As regras de uso para o elemento `<loc>` são as mesmas que o elemento `<reference>`. Para obter mais informações, consulte a seção "referências de diretivas" no [JavaScript IntelliSense](../ide/javascript-intellisense.md).

 O Visual Studio processa um único elemento `<loc>` para cada arquivo. js. Se vários elementos de `<loc>` estiverem presentes, apenas um único elemento de `<loc>` será usado. Comportamento para determinar qual elemento de `<loc>` a ser usado não está definido.

 Ao usar o formato de pacote de mensagens, use o atributo `locid` em comentários de documentação XML para especificar o valor do atributo `name`.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra como usar o elemento `<loc>` com o formato messagebundle. Adicione o XML a seguir a um arquivo chamado messageFilename. xml e coloque o arquivo na pasta específica da cultura correta, conforme especificado na descrição do parâmetro `filename`.

```
<?xml version="1.0" encoding="utf-8" ?>
<messagebundle>
  <msg name="1">A class that represents a rectangle</msg>
  <msg name="2">The height of a rectangle</msg>
  <msg name="3">The width of a rectangle</msg>
</messagebundle>

```

 Para o exemplo de messagebundle, adicione o código a seguir a um arquivo JavaScript em seu projeto. O elemento `<loc>` deve aparecer como a primeira linha no arquivo JavaScript. As descrições nesse código serão substituídas por descrições localizadas, se disponíveis.

```javascript
/// <loc filename="messageFilename.xml" format="messagebundle"/>

function doSomething(a,b)
{
    /// <summary locid='1'>description</summary>
    /// <param name='a' locid='2'>parameter a description</param>
    /// <param name='b' locid='3'>parameter b description</param>
}

```

 O exemplo a seguir usa o formato VSDoc. Adicione o XML a seguir a um arquivo chamado scriptFilename. xml e coloque o arquivo na pasta específica da cultura correta.

```
<?xml version="1.0" encoding="utf-8" ?>
<doc>
  <assembly>
    <name>Lights</name>
  </assembly>
  <members>
    <member name="M:illuminate">
      <summary>Activates a light. </summary>
      <param name='a'>The light to activate. </param>
    </member>
  </members>
</doc>

```

 Para o exemplo de VSDoc, adicione o código a seguir a um arquivo JavaScript em seu projeto. As descrições nesse código serão substituídas por descrições localizadas, se disponíveis.

```javascript
/// <loc filename="scriptFilename.xml" format="vsdoc" />

function illuminate(a)
{
    /// <summary locid='M:illuminate'>description</summary>
    /// <param name='a' type='Number'>parameter a description</param>
}

```

## <a name="see-also"></a>Veja também
 [Comentários da documentação XML](../ide/xml-documentation-comments-javascript.md)
