---
title: Se o designer de atividade | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: 4
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6b35fe7f1b55dde25ec896f230f66cef00d24eed
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72659064"
---
# <a name="if-activity-designer"></a>Se designer de atividades
A atividade de <xref:System.Activities.Statements.If> avalia uma condição e executa uma atividade dependendo dos resultados da avaliação. Esta atividade é mais útil ao usar um estilo modelando procedural de programação. Uma atividade de <xref:System.Activities.Statements.If> pode ser aninhadas dentro de uma atividade de <xref:System.Activities.Statements.Sequence> ou uma atividade de <xref:System.Activities.Statements.Parallel> , por exemplo. Se você estiver usando uma atividade de <xref:System.Activities.Statements.Flowchart> , considere usar uma atividade de <xref:System.Activities.Statements.FlowDecision> em vez disso.

## <a name="if-properties-in-the-workflow-designer"></a>Se as propriedades em Designer de Fluxo de Trabalho
 A tabela a seguir mostra as propriedades mais úteis de atividade de <xref:System.Activities.Statements.If> e descreve como usá-los no designer.

|Nome da Propriedade|Necessária|Uso|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.If.Condition%2A>|verdadeiro|A condição que determina que atividade filho para executar. Para definir o <xref:System.Activities.Statements.If.Condition%2A>, digite uma expressão de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] na caixa **condição** no designer de atividade **If** ou na grade de propriedades.|
|<xref:System.Activities.Statements.If.Else%2A>|False|A atividade a ser executada se a <xref:System.Activities.Statements.If.Condition%2A> for **falsa**. Para adicionar uma atividade que é executada pela ramificação de <xref:System.Activities.Statements.If.Else%2A>, descarte uma atividade da caixa de **ferramentas** no **else** , no **If** Activity Designer, com texto de dica "soltar atividade aqui".|
|<xref:System.Activities.Statements.If.Then%2A>|False|A atividade a ser executada se a <xref:System.Activities.Statements.If.Condition%2A> for **verdadeira**. Para adicionar uma atividade que é executada pela ramificação <xref:System.Activities.Statements.If.Then%2A>, descarte uma atividade da caixa de **ferramentas** em **seguida** no designer de atividade **If** com texto de dica "soltar atividade aqui".|

## <a name="see-also"></a>Consulte também
 [Fluxo de controle](../workflow-designer/control-flow-activity-designers.md) [paralelo](../workflow-designer/parallel-activity-designer.md) de [sequência](../workflow-designer/sequence-activity-designer.md)