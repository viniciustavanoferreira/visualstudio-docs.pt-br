---
title: Como posso depurar violações de acesso ao executar meu programa fora do depurador? | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ce5b21f92eecf2e8929c142bc1ee32e20d386335
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74299249"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Como posso depurar violações de acesso ao executar meu programa fora do depurador?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Descrição do problema  
 Meu programa é executado corretamente no ambiente do Visual Studio, mas quando eu o executo em modo autônomo no sistema operacional Windows, ele gera uma violação de acesso. Como posso depurar esse problema?  
  
## <a name="solution"></a>Solução  
 Defina a opção [depuração Just-In-Time](../debugger/just-in-time-debugging-in-visual-studio.md) e execute o programa autônomo, até que ocorra a violação de acesso. Em seguida, na caixa de diálogo **Violação de Acesso**, clique em **Cancelar** para iniciar o depurador.  
  
 Além disso, consulte o artigo da Base de Dados de Conhecimento Q133174, “Como localizar onde ocorre uma falha geral de proteção (GP)”. Você pode encontrar artigos da base de dados de conhecimento no CD da biblioteca MSDN ou pesquisando [http://support.microsoft.com/](https://support.microsoft.com/).  
  
## <a name="see-also"></a>Consulte também  
 [Perguntas frequentes sobre depuração de código nativo](../debugger/debugging-native-code-faqs.md)   
 [Depurando código nativo](../debugger/debugging-native-code.md)
