---
title: Designer de atividade do TerminateWorkflow | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
caps.latest.revision: 4
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c204c14818a9c6e6fb0a46e6234b550838f3b1a4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72607088"
---
# <a name="terminateworkflow-activity-designer"></a>Designer de atividade de TerminateWorkflow
O designer de atividade **TerminateWorkflow** é usado para criar e configurar uma atividade de <xref:System.Activities.Statements.TerminateWorkflow>.

## <a name="the-terminateworkflow-activity"></a>A atividade de TerminateWorkflow
 A atividade de <xref:System.Activities.Statements.TerminateWorkflow> finaliza a execução de um fluxo de trabalho.

### <a name="using-the-terminateworkflow-activity-designer"></a>Usando o designer de atividade de TerminateWorkflow
 O designer de atividade do **TerminateWorkflow** pode ser encontrado na categoria **tempo de execução** da **caixa de ferramentas**, que é acessada clicando na guia caixa de **ferramentas** (como alternativa, selecione **caixa de ferramentas** no menu **Exibir** ou CTRL + ALT + X.)

 O designer de atividade do **TerminateWorkflow** pode ser arrastado da **caixa de ferramentas** e descartado para a superfície de [!INCLUDE[wfd2](../includes/wfd2-md.md)] sempre que as atividades são geralmente colocadas, como dentro de um <xref:System.Activities.Statements.Sequence>. Isso cria uma atividade de <xref:System.Activities.Statements.TerminateWorkflow> com um **DisplayName** padrão de TerminateWorkflow. O <xref:System.Activities.Activity.DisplayName%2A> pode ser editado no cabeçalho do designer de atividade **TerminateWorkflow** ou na caixa **DisplayName** da grade de propriedades.

### <a name="the-terminateworkflow-properties"></a>As propriedades de TerminateWorkflow
 A tabela a seguir mostra as propriedades de <xref:System.Activities.Statements.TerminateWorkflow> e descreve como elas são usadas no designer. Essas propriedades podem ser editadas na grade de propriedade e algumas delass podem ser editadas na superfície de [!INCLUDE[wfd2](../includes/wfd2-md.md)] .

|Nome da Propriedade|Necessária|Uso|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|O nome amigável de atividade de <xref:System.Activities.Statements.TerminateWorkflow> . O padrão é TerminateWorkflow. Embora o nome para exibição não é necessário restrita, é uma prática recomendada usar um nome para exibição.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|A exceção para indicar quando o fluxo de trabalho é encerrado. Defina essa propriedade na grade de propriedade.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|A razão que explica como o fluxo de trabalho foi encerrado. Defina essa propriedade na grade de propriedade.|

## <a name="see-also"></a>Consulte também
 [Persistir](../workflow-designer/persist-activity-designer.md) o [tempo de execução](../workflow-designer/runtime-activity-designers.md)