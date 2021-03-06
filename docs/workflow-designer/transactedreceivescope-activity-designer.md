---
title: Designer de atividade Designer de Fluxo de Trabalho-TransactedReceiveScope
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf5a52a6a806d72632bf31a7c73e41677e9ddaf9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654284"
---
# <a name="transactedreceivescope-activity-designer"></a>Designer de atividade de TransactedReceiveScope

O designer de **TransactedReceiveScope** é usado para criar e configurar uma atividade de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.

## <a name="the-transactedreceivescope-activity"></a>A atividade de TransactedReceiveScope

A atividade de <xref:System.ServiceModel.Activities.TransactedReceiveScope> permite que você fluxo uma transação nas transações de servidor criadas por um fluxo de trabalho ou por um distribuidor.

### <a name="using-the-transactedreceivescope-activity-designer"></a>Usando o designer de atividade de TransactedReceiveScope

Acesse o designer de atividade **TransactedReceiveScope** na categoria **mensagens** da **caixa de ferramentas**. O designer de atividade **TransactedReceiveScope** pode ser arrastado da **caixa de ferramentas** e descartado para a superfície de designer de fluxo de trabalho sempre que as atividades são geralmente colocadas. Isso cria uma atividade de <xref:System.ServiceModel.Activities.TransactedReceiveScope> com um **DisplayName** padrão de TransactedReceiveScope. O <xref:System.Activities.Activity.DisplayName%2A> pode ser editado no cabeçalho do designer de atividade **TransactedReceiveScope** ou na caixa **DisplayName** da grade de propriedades.

O designer de **TransactedReceiveScope** contém caixas de **solicitação** e **corpo** . Esses são usados para configurar a propriedade de <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> , que especifica uma atividade de <xref:System.ServiceModel.Activities.Receive> e uma propriedade de <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> , que especifica algum outro <xref:System.Activities.Activity>. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> cria uma transação. A transação é feita em ambientes para o escopo de <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> de modo que quaisquer atividades dentro desse escopo seja executado dentro desta transação.

### <a name="the-transactedreceivescope-properties"></a>As propriedades de TransactedReceiveScope

A tabela a seguir mostra as propriedades de <xref:System.ServiceModel.Activities.TransactedReceiveScope> e descreve como elas são usadas no designer. Essas <xref:System.Activities.Activity.DisplayName%2A> Propriedade podem ser editadas na grade de propriedades ou na superfície de Designer de Fluxo de Trabalho, mas as outras devem ser editadas na superfície de design.

|Nome da Propriedade|Necessária|Uso|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|O nome amigável opcional de atividade de <xref:System.ServiceModel.Activities.TransactedReceiveScope> . O padrão é TransactedReceiveScope.<br /><br /> Embora o nome de <xref:System.Activities.Activity.DisplayName%2A> não é necessário restrita, é uma prática recomendada usar um nome para exibição.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|verdadeiro|Descarta uma atividade de <xref:System.ServiceModel.Activities.Receive> no bloco de **solicitação** na superfície do designer de atividade.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|Remove uma <xref:System.Activities.Activity> no bloco **Body** na superfície do designer de atividade.|

## <a name="see-also"></a>Consulte também

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Receber](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Enviar](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)