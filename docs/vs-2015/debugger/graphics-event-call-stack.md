---
title: Pilha de chamadas do evento de gráficos | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8344050d26286263e0c33974b976e4ae25ff18de
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68192749"
---
# <a name="graphics-event-call-stack"></a>Pilha de chamadas de gráfico
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A pilha de chamadas do evento de gráficos no analisador de gráficos do Visual Studio o ajuda a mapear a relação entre eventos de gráficos problemático e código-fonte do seu aplicativo.  
  
 Esta é a janela de pilha de chamadas do evento:  
  
 ![A pilha de chamadas anteriores um evento DrawIndexed. ](../debugger/media/gfx-diag-demo-graphics-event-call-stack-orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")  
  
## <a name="understanding-the-graphics-event-call-stack"></a>Noções básicas sobre a pilha de chamadas do evento de gráficos  
 Você pode usar a pilha de chamadas do evento para entender o fluxo de execução que leva a um determinado evento do Direct3D. Ele é semelhante a janela de pilha de chamadas do Visual Studio, exceto que em vez de exibir a pilha de chamadas atual do thread ativo em um aplicativo em execução, ele exibe a pilha de chamadas que existia quando ocorreu o evento do Direct3D selecionado. Da pilha de chamada de evento, você pode ir para o site de chamada do evento Direct3D selecionado para inspecionar o código ao redor.  
  
 Usando a Pilha de Chamadas do Evento para identificar o caminho do código de origem de um evento de problema, você pode usar o seu conhecimento sobre o código na base para deduzir possíveis origens do problema ou você pode adicionar pontos de interrupção no código-fonte do aplicativo para usar técnicas de depuração tradicionais e examinar como o estado do aplicativo ou parâmetros do evento estão fazendo com que o evento se comporte incorretamente. Esse exame pode ajudá-lo a encontrar problemas no código-fonte que são manifestados somente como problemas de renderização.  
  
### <a name="graphics-event-call-stack-information"></a>Informações sobre a pilha de chamadas de gráfico  
 A pilha de chamadas do evento não dá suporte a eventos de pré-quadros ou definidos pelo usuário. A pilha de chamadas de eventos de gráficos é exibida em um formato de tabela.  
  
|Column|Descrição|  
|------------|-----------------|  
|**Nome**|Um símbolo que identifica a função que contém o site de chamada. O símbolo de depuração da função é exibido quando ela está disponível. Caso contrário, o deslocamento de função é exibido.|  
|**Arquivo**|O nome do arquivo do código-fonte ou arquivo de biblioteca que contém o site de chamada.|  
|**Local**|O número de linha do site de chamada.|  
  
### <a name="links-to-graphics-objects"></a>Links a objetos de gráficos  
 Para entender o evento de gráficos selecionado, você pode precisar obter informações sobre os objetos Direct3D que estão associados ele. O **pilha de chamadas do evento de gráficos** janela fornece links para essas informações.  
  
## <a name="see-also"></a>Consulte também  
 [Passo a passo: Objetos ausentes devido ao sombreamento de vértice](../debugger/walkthrough-missing-objects-due-to-vertex-shading.md)
