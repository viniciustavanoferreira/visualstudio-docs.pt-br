---
title: Tempo de preempção | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de7a02f7247e09876bc4598d44fc1c395161ebc2
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62935887"
---
# <a name="preemption-time"></a>Tempo de preempção
Esses segmentos na linha do tempo estão associados aos tempos de bloqueio categorizados como Preempção. Esta categoria implica que um thread é alternado devido a um destes motivos:

- O agendador substituiu usando um thread de prioridade mais alta.

- O quantum de execução do thread expirou e outros threads estavam prontos para execução.

  Durante esse tempo, um thread foi bloqueado pelo motivo de espera do kernel, que a Visualização Simultânea está contando como preempção. Os segmentos de preempção são iniciados quando um thread é enviado de um núcleo lógico e terminam quando esse thread continua a execução.

  A dica de ferramenta para um segmento de preempção exibe o nome do processo ou do thread que causou a preempção. No entanto, isso não significa que o processo ou thread que assumiu o controle foi realmente executado durante o período de admitiu preempção.

## <a name="see-also"></a>Confira também
- [Exibição de linhas](../profiling/threads-view-parallel-performance.md)