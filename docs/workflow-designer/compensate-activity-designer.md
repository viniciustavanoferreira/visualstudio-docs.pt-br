---
title: Designer de atividade Designer de Fluxo de Trabalho-Compensate
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 65203663214e6bc82a4a7b20af9caa25bfd98ee4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650650"
---
# <a name="compensate-activity-designer"></a>Compense o designer de atividades

O designer de atividade **Compensate** é usado para criar e configurar uma atividade de <xref:System.Activities.Statements.Compensate>.

## <a name="the-compensate-activity"></a>A atividade de compesação

A atividade de <xref:System.Activities.Statements.Compensate> chama explicitamente <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> para uma atividade contida em <xref:System.Activities.Statements.CompensableActivity>. Se a atividade de <xref:System.Activities.Statements.Compensate> não é usada dentro de <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, ou <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> de <xref:System.Activities.Statements.CompensableActivity>, então você deve especificar a propriedade de <xref:System.Activities.Statements.Compensate.Target%2A> .

<xref:System.Activities.Statements.CompensationToken> especificado por <xref:System.Activities.Statements.Compensate.Target%2A> fornece um meio para confirmar ou compensar explicitamente <xref:System.Activities.Statements.CompensableActivity> uma vez que <xref:System.Activities.Statements.CompensableActivity.Body%2A> de <xref:System.Activities.Statements.CompensableActivity> terminou com êxito.

### <a name="using-the-compensate-activity-designer"></a>Usando o designer de atividade de compesação

O designer de atividade **Compensate** pode ser encontrado na categoria **transação** da **caixa de ferramentas**. Para abrir a **caixa de ferramentas**, selecione a guia caixa de **ferramentas** no lado esquerdo da designer de fluxo de trabalho. Como alternativa, selecione **caixa de ferramentas** no menu **Exibir** ou pressione **Ctrl** +**ALT** +**X**.

O designer de atividade **Compensate** pode ser arrastado da **caixa de ferramentas** e descartado para a superfície de designer de fluxo de trabalho onde as atividades são colocadas, como dentro de um <xref:System.Activities.Statements.Sequence>. O descarte do designer de atividade cria uma atividade de <xref:System.Activities.Statements.Compensate> com um <xref:System.Activities.Activity.DisplayName%2A> padrão de Compensate. O valor <xref:System.Activities.Activity.DisplayName%2A> pode ser editado no cabeçalho do designer de atividade **Compensate** ou na caixa **DisplayName** da grade de propriedades.

### <a name="the-compensate-properties"></a>As propriedades de compesação

A tabela a seguir mostra as propriedades de <xref:System.Activities.Statements.CancellationScope> e descreve como elas são usadas no designer. A propriedade <xref:System.Activities.Activity.DisplayName%2A> pode ser editada na grade de propriedades ou na superfície Designer de Fluxo de Trabalho. Edite a propriedade <xref:System.Activities.Statements.Compensate.Target%2A> na grade de propriedades.

|Nome da Propriedade|Necessária|Uso|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável opcional de atividade de <xref:System.Activities.Statements.Compensate> . O padrão é compensa.|
|<xref:System.Activities.Statements.Compensate.Target%2A>|verdadeiro|Especifica <xref:System.Activities.InArgument%601> que contém <xref:System.Activities.Statements.CompensationToken> para esta atividade de <xref:System.Activities.Statements.Compensate> .|

## <a name="see-also"></a>Consulte também

- [Transação](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Designer de atividade Compensate](../workflow-designer/compensate-activity-designer.md)
- [Confirmar](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)