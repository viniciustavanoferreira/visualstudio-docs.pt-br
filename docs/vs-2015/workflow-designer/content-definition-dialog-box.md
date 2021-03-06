---
title: Caixa de diálogo Definição de conteúdo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: 3
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d989f5a0c57e381041e8fe9c200aae1a76316ad8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656952"
---
# <a name="content-definition-dialog-box"></a>Caixa de diálogo de conteúdo da definição
A caixa de diálogo **definição de conteúdo** é usada em [!INCLUDE[wfd1](../includes/wfd1-md.md)] para configurar as propriedades de **conteúdo** das atividades <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>. [!INCLUDE[crabout](../includes/crabout-md.md)] os designers de atividade que usam essa caixa, consulte os tópicos [Enviar](../workflow-designer/send-activity-designer.md), [receber](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)e [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) .

 A tabela a seguir descreve os elementos da interface do usuário da caixa de diálogo **inicializar correlação** .

|Elemento da Interface do Usuário|Descrição|
|----------------|-----------------|
|**Message**|Especifica o conteúdo da mensagem com a caixa de texto expressão de **dados da mensagem** e o tipo usando a caixa de listagem suspensa **tipo de mensagem** . Por padrão, a **definição de conteúdo** usa o <xref:System.ServiceModel.Activities.ReceiveMessageContent>, que espera um <xref:System.ServiceModel.Channels.Message> ou um tipo de contrato de mensagem na definição do serviço de fluxo de trabalho.|
|**Parâmetros**|Clique no botão de opção **parâmetros** para usar <xref:System.ServiceModel.Activities.ReceiveParametersContent>, o que espera um contrato de dados. Use a grade de dados para definir uma coleção genérica de pares chave/valor de <xref:System.Activities.OutArgument> cujos valores são atribuídos aos parâmetros variáveis no fluxo de trabalho atual.|

 A caixa de diálogo **definição de conteúdo** é usada pelos designers **Enviar**, **receber**, **ReceiveAndSendReply**e **SendAndReceiveReply** . Acessá-lo é semelhante em cada caso e exemplos de receptor são usados aqui para ilustrar o procedimento.

 O designer de atividade **Receive** pode ser arrastado da **caixa de ferramentas** e descartado para a superfície de [!INCLUDE[wfd2](../includes/wfd2-md.md)] sempre que as atividades são geralmente colocadas. Isso cria uma atividade de <xref:System.ServiceModel.Activities.Receive> com <xref:System.Activities.Activity.DisplayName%2A> padrão Receive. Selecione o designer de atividade de **recebimento** e clique no botão de reticências ao lado do texto (conteúdo) da propriedade **conteúdo** na grade de propriedades da caixa de diálogo **definição de conteúdo** a ser exibida.

 O conteúdo pode ser especificado na seção de **mensagem** para uma atividade de <xref:System.ServiceModel.Activities.ReceiveMessageContent> ou dentro da seção de **parâmetro** para uma atividade de <xref:System.ServiceModel.Activities.ReceiveParametersContent>.

## <a name="see-also"></a>Consulte também
 [Ajuda da interface do usuário do Designer de Fluxo de Trabalho](../workflow-designer/workflow-designer-ui-help.md)