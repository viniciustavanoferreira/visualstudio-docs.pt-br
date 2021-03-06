---
title: Designer de atividade paralela | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a46a340ccdeacacb8f04b962313db18975447a67
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672630"
---
# <a name="parallel-activity-designer"></a>Designer paralelo de atividades
A atividade de <xref:System.Activities.Statements.Parallel> executa uma coleção de filhos atividades simultaneamente.

## <a name="the-parallel-activity"></a>A atividade paralela
 A atividade de <xref:System.Activities.Statements.Parallel> armazena as atividades filho em uma coleção de <xref:System.Activities.Statements.Parallel.Branches%2A> . Use a atividade de <xref:System.Activities.Statements.Parallel> em vez de atividade de <xref:System.Activities.Statements.Sequence> se algumas das atividades filho podem ir ociosa.

 A atividade de <xref:System.Activities.Statements.Parallel> tem uma propriedade de <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> que contém uma expressão especificada usuário de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] . A atividade de <xref:System.Activities.Statements.Parallel> avalia essa propriedade após cada ramificação completa. Se for avaliada como **true**, a atividade de <xref:System.Activities.Statements.Parallel> será concluída sem executar as outras ramificações. Se a <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> não for avaliada como **true**, a atividade de <xref:System.Activities.Statements.Parallel> será concluída quando todas as suas atividades filhas forem concluídas.

### <a name="using-the-parallel-activity-designer"></a>Usando o designer paralelo de atividades
 O designer de atividade **paralela** pode ser encontrado na **categoria fluxo de controle** da **caixa de ferramentas**, que é acessada clicando na guia caixa de **ferramentas** no lado esquerdo da [!INCLUDE[wfd2](../includes/wfd2-md.md)] (como alternativa, selecione **barra** de **ferramentas no Menu Exibir** ou CTRL + ALT + X.)

 O designer de atividade **paralela** pode ser arrastado da **caixa de ferramentas** e descartado para a superfície de [!INCLUDE[wfd2](../includes/wfd2-md.md)] onde os designers de atividade normalmente são colocados, por exemplo, dentro de um designer de atividade de **sequência** . Depois de soltá-lo no [!INCLUDE[wfd2](../includes/wfd2-md.md)], ele cria uma atividade <xref:System.Activities.Statements.Parallel>, que, por padrão, contém uma <xref:System.Activities.Activity.DisplayName%2A> de **Parallel**

 Para adicionar uma atividade à coleção de <xref:System.Activities.Statements.Parallel.Branches%2A> da atividade paralela, arraste outro designer de atividade da caixa de **ferramentas** e solte-o no triângulo dentro do designer de atividade **paralela** . Os triângulos flanqueiam as atividades contidas em ramificações. As atividades adicionais podem ser adicionadas repetindo este procedimento. As atividades podem ser reordenadas arrastando-as e soltando-as no designer de atividade **paralela** .

### <a name="parallel-activity-properties-in-the-workflow-designer"></a>Propriedades paralelas de atividade em Designer de Fluxo de Trabalho
 A tabela a seguir mostra as propriedades paralelas de atividade e descreve como elas são usadas no designer.

|Nome da Propriedade|Necessária|Uso|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável para exibição do designer de atividade no cabeçalho. O valor padrão é **Parallel**. O valor pode ser editado opcionalmente na grade de **Propriedades** ou diretamente no cabeçalho do designer de atividade.|
|<xref:System.Activities.Statements.Parallel.Branches%2A>|True|Contém a coleção de atividades filhos sejam executadas.|
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|Avaliado após uma ramificação completa. Se for avaliado como **true**, os branches pendentes agendados serão cancelados. Se essa propriedade não for definida ou for avaliada como **false**, a atividade será concluída quando todas as suas atividades filhas forem concluídas. O valor padrão é **nulo**.|

## <a name="see-also"></a>Consulte também
 [ParallelForEach\<T >](../workflow-designer/parallelforeach-t-activity-designer.md) [Sequence](../workflow-designer/sequence-activity-designer.md) [fluxo de controle](../workflow-designer/control-flow-activity-designers.md)