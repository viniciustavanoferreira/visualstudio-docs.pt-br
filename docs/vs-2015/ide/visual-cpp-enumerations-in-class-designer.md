---
title: Enumerações do Visual C++ no Designer de Classe | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7f967420e37d6337ce6d86cc56524f2751218f56
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651659"
---
# <a name="visual-c-enumerations-in-class-designer"></a>Enumerações do Visual C++ no Designer de Classe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O Designer de Classe oferece suporte ao `enum` do C++ e a tipos `enum class` de escopo. Veja um exemplo a seguir:

```
enum CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};

// or...
enum class CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};

```

 Uma forma de enumeração do C++ em um diagrama de classes parece e funciona como uma forma de estrutura, exceto pelo seguinte: o rótulo exibe **Enum** ou **Enum class**, ele é rosa em vez de azul e tem uma borda colorida nas margens esquerda e superior. As formas de enumeração e formas de estrutura tem cantos quadrados.

 Para obter mais informações sobre o uso do tipo `enum`, consulte [Enumerações](https://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3).

## <a name="see-also"></a>Veja também
 Trabalhando com [enumerações](https://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3) de [código Visual C++ (Designer de classe)](../ide/working-with-visual-cpp-code-class-designer.md)
