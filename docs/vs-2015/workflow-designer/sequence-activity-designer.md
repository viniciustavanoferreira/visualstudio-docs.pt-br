---
title: Designer de atividade de sequência | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3acf02ab478eee244557e04f19f78ba2d5f0b950
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663253"
---
# <a name="sequence-activity-designer"></a>Arranje seqüencialmente o designer de atividades
A atividade de <xref:System.Activities.Statements.Sequence> contém uma coleção ordenada de atividades filhos que executa em ordem.

 Outra maneira de executar um conjunto de atividades em ordem é usar uma atividade de <xref:System.Activities.Statements.Flowchart> . Considere usar o [fluxograma](../workflow-designer/flowchart-activity-designer.md) quando você tiver um fluxo de programa de ramificação simples ou de looping que você deseja modelar diagramaticamente.

## <a name="using-the-sequence-activity-designer"></a>Usando o designer de atividade de sequência
 Para adicionar uma atividade de <xref:System.Activities.Statements.Sequence>, arraste o designer de atividade de **sequência** da **caixa de ferramentas** e solte-o na superfície de [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Para adicionar uma atividade filho a essa atividade de <xref:System.Activities.Statements.Sequence>, arraste alguma outra atividade da caixa de **ferramentas** e solte-a no triângulo, no quadro, com o texto de dica "soltar atividade aqui".

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>Propriedades de atividade da sequência em Designer de Fluxo de Trabalho
 A tabela a seguir mostra as propriedades de <xref:System.Activities.Statements.Sequence> e descreve como elas são usadas no designer. Essas propriedades podem ser editadas na grade de propriedade ou na superfície de designer.

|Nome da Propriedade|Necessária|Uso|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável do designer de atividade de <xref:System.Activities.Statements.Sequence> no cabeçalho. O valor padrão é sequência. O valor pode ser editado na grade de propriedade ou diretamente no cabeçalho do designer de atividade.<br /><br /> Embora não seja necessário <xref:System.Activities.Activity.DisplayName%2A> restrita, é uma prática recomendada usar um.|

## <a name="see-also"></a>Consulte também
 [Fluxo de controle](../workflow-designer/control-flow-activity-designers.md) [de fluxograma](../workflow-designer/flowchart-activity-designer.md)