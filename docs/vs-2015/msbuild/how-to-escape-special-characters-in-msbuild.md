---
title: Como escapar caracteres especiais no MSBuild | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 94fc8d858e2db9bd1e00bb8770cf52672a900ab0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68178354"
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Como escapar caracteres especiais no MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Determinados caracteres têm significado especial em arquivos de projeto do [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]. O ponto e vírgula (;) e o asterisco (*) são exemplos de caracteres. Para obter uma lista completa desses caracteres especiais, consulte [Caracteres especiais do MSBuild](../msbuild/msbuild-special-characters.md).  
  
 Para usar esses caracteres especiais como literais em um arquivo de projeto, eles devem ser especificados usando a sintaxe %*xx*, em que *xx* representa o valor hexadecimal ASCII do caractere.  
  
## <a name="msbuild-special-characters"></a>Caracteres especiais no MSBuild  
 Um exemplo de quando os caracteres especiais são usados é no atributo `Include` de listas de itens. Por exemplo, a lista de itens a seguir declara dois itens: `MyFile.cs` e `MyClass.cs`.  
  
```  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Se você quiser declarar um item que contém um ponto e vírgula no nome, você deverá usar a sintaxe %*xx* para escapar o ponto e vírgula e evitar que o [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] declare dois itens separados. Por exemplo, o item a seguir escapa o ponto e vírgula e declara um item denominado `MyFile.cs;MyClass.cs`.  
  
```  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>Para usar um caractere especial do MSBuild como um caractere literal  
  
- Use a notação %*xx* no lugar do caractere especial, em que *xx* representa o valor hexadecimal do caractere ASCII. Por exemplo, para usar um asterisco (*) como um caractere literal, use o valor `%2A`.  
  
## <a name="see-also"></a>Veja também  
 [Conceitos do MSBuild](../msbuild/msbuild-concepts.md)   
 [MSBuild](msbuild.md) [Itens](../msbuild/msbuild-items.md)
