---
title: Exibições de atividade (herdadas) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7546f752ef7ee1053d1b0b785334a8da814720c6
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75851475"
---
# <a name="activity-views-legacy"></a>Visualizações de atividade (legados)
Muitas das atividades fornecidas por [!INCLUDE[wf](../includes/wf-md.md)], que fluxos de trabalho são compostos, têm várias exibições de design disponíveis em [!INCLUDE[wfd1](../includes/wfd1-md.md)]herdado. Quando você arrasta um designer de atividade da **caixa de ferramentas** para a superfície de design e, depois, sempre que seleciona a atividade, você pode alternar entre os diferentes modos de exibição de design usando o menu de **fluxo de trabalho** ou clicando com o botão direito do mouse na atividade selecionada. Além disso, quando você move o ponteiro sobre o nome de uma atividade selecionada, um conjunto lista suspensa de guias que aparece você pode usar para alternar entre modos de exibição diferentes.

 Cada atividade tem pelo menos uma exibição; Essa é a exibição padrão mostrada quando você arrasta um designer de atividade da **caixa de ferramentas** para a superfície de design. Essa exibição padrão de atividade está disponível como a opção de **exibição [tipo de atividade]** nos menus e na guia, por exemplo, **Exibir paralelo**. A maioria das atividades têm modos de exibição adicionais e as atividades diferentes podem ter diferentes modos de exibição. Por exemplo, a atividade [TransactionScopeActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.transactionscopeactivity.aspx) tem a exibição de compensação e a atividade [EventHandlingScopeActivity](https://msdn2.microsoft.com/library/system.workflow.activities.eventhandlingscopeactivity.aspx) tem uma exibição de eventos. Muitas das atividades fornecidas com Windows Workflow Foundation têm o **manipulador de exibição cancelar** e exibem exibições de design de **falhas** para exibir o [CancellationHandlerActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.cancellationhandleractivity.aspx) e um [FaultHandlersActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.faulthandlersactivity.aspx) associado a eles.

 A tabela a seguir lista o nome e a descrição de cada uma.

|Opção de menu/guia|Descrição|
|----------------------|-----------------|
|**View [tipo de atividade]**|Selecione este menu catalogue ou a opção para exibir a representação gráfica padrão de atividade selecionada.|
|**Exibir manipulador de cancelamento**|Selecione esta exibição de opção de menu ou guia para exibir o [CancellationHandlerActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.cancellationhandleractivity.aspx) associado à atividade selecionada.|
|**Exibir manipulador de falhas**|Selecione esta exibição de opção de menu ou guia para exibir o [FaultHandlersActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.faulthandlersactivity.aspx) associado à atividade selecionada.|
|**Exibir manipulador de compensação**|Selecione esta exibição de opção de menu ou guia para exibir o [CompensationHandlerActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.compensationhandleractivity.aspx) associado à [TransactionScopeActivity](https://msdn2.microsoft.com/library/system.workflow.componentmodel.transactionscopeactivity.aspx)selecionada.|
|**Exibir manipulador de eventos**|Selecione esta exibição de opção de menu ou guia para exibir o [EventHandlersActivity](https://msdn2.microsoft.com/library/system.workflow.activities.eventhandlersactivity.aspx) associado ao [EventHandlingScopeActivity](https://msdn2.microsoft.com/library/system.workflow.activities.eventhandlingscopeactivity.aspx)selecionado.|

 Para obter informações sobre modos de exibição semelhantes, consulte [exibições de fluxo de trabalho Sequencial (Herdado)](../workflow-designer/sequential-workflow-views-legacy.md).

## <a name="see-also"></a>Veja também
 [Exibições de fluxo de trabalho sequenciais de atividades de fluxo de](../workflow-designer/sequential-workflow-views-legacy.md) [trabalho herdadas](../workflow-designer/legacy-workflow-activities.md)
