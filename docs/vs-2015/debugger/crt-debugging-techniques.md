---
title: Técnicas de depuração de CRT | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- c.runtime.debugging
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [CRT]
- CRT, debugging
- debugging [C++], CRT debug support
ms.assetid: 9be561f6-14a8-44ff-925d-d911d5b8e6ff
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a69defe75b80ef1f395931017dfc942398ca2710
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68161486"
---
# <a name="crt-debugging-techniques"></a>Técnicas de depuração CRT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Se você estiver depurando um programa que usa a biblioteca em tempo de execução C, essas técnicas de depuração poderão ser úteis.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Uso da biblioteca de depuração CRT](../debugger/crt-debug-library-use.md)  
 Descreve o suporte à depuração fornecido pela biblioteca em tempo de execução C e fornece instruções para acessar as ferramentas.  
  
 [Macros para relatórios](../debugger/macros-for-reporting.md)  
 Fornece informações sobre as macros **_RPTn** e **_RPTFn** (definidas em CRTDBG.H), que substituem o uso de instruções `printf` para depuração.  
  
 [Versões de depuração de funções de alocação de heap](../debugger/debug-versions-of-heap-allocation-functions.md)  
 Discute as versões especiais de depuração das funções de alocação de heap, incluindo: como o CRT mapeia as chamadas, os benefícios de chamá-las explicitamente, como evitar a conversão, rastrear os tipos separados de alocações em blocos do cliente e os resultados de não definir _DEBUG.  
  
 [Detalhes do heap de depuração CRT](../debugger/crt-debug-heap-details.md)  
 Fornece links para o gerenciamento de memória e o heap de depuração, tipos de blocos no heap de depuração, como usar o heap de depuração, o estado de heap que informa funções e como controlar solicitações de alocação do heap.  
  
 [Gravação da função de gancho de depuração](../debugger/debug-hook-function-writing.md)  
 Lista links para funções de gancho de bloco de cliente, funções de gancho de alocação, ganchos de alocação e alocações de memória CRT, e funções de gancho de relatório.  
  
 [Localizando perdas de memória usando a biblioteca CRT](../debugger/finding-memory-leaks-using-the-crt-library.md)  
 Aborda técnicas para detectar e isolar vazamentos de memória usando o depurador e a biblioteca em tempo de execução C.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Depurando código nativo](../debugger/debugging-native-code.md)  
 Discute alguns problemas comuns e técnicas de depuração para aplicativos C e C++.  
  
 [Segurança do depurador](../debugger/debugger-security.md)  
 Fornece recomendações para depuração mais segura.
