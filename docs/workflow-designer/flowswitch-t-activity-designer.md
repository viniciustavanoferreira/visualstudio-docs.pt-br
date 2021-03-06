---
title: Designer de Fluxo de Trabalho-FlowSwitch<T> designer de atividade
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8271100936b9cf70e17c0e6279297d583714f018
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75597146"
---
# <a name="flowswitcht-activity-designer"></a>Designer de atividade do FlowSwitch\<T >

A atividade de <xref:System.Activities.Statements.FlowSwitch%601> é um nó condicional que fornece a ramificação para o fluxo de controle baseado no critério de correspondência quando mais de duas ramificações alternativas são necessários. Se a ramificação de fluxo requer apenas dois caminhos, use a atividade de <xref:System.Activities.Statements.FlowDecision> em vez disso.

## <a name="the-flowswitcht-activity"></a>A atividade FlowSwitch\<T >

A atividade <xref:System.Activities.Statements.FlowSwitch%601> contém um <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> que retorna um valor do tipo *t* (especificado pelo parâmetro Generic) quando avaliado. A atividade também contém um conjunto de <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>, que especifica um mapeamento exclusivo de resultados possíveis da avaliação a um conjunto de objetos de <xref:System.Activities.Statements.FlowNode> . O <xref:System.Activities.Statements.FlowNode> executado é aquele cujo objeto do tipo *t* corresponde ao valor do <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>avaliado. Os exemplos de <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> podem opcionalmente () são fornecidos para casos em que nenhuma correspondência for obtida.

### <a name="using-the-flowswitcht-activity-designer"></a>Usando o designer de atividades FlowSwitch\<T >

O designer de atividades **FlowSwitch\<t >** pode ser encontrado na categoria **fluxograma** da **caixa de ferramentas**, que é acessada clicando na guia caixa de **ferramentas** no lado esquerdo da designer de fluxo de trabalho. Como alternativa, selecione **caixa de ferramentas** no menu **Exibir** ou pressione **Ctrl**+**ALT**+**X**.

O designer de atividades **FlowSwitch\<t >** pode ser arrastado da **caixa de ferramentas** e retirado para a superfície de designer de fluxo de trabalho dentro de um designer de atividade de **fluxograma** . Use a janela **Selecionar tipos** que é exibida para especificar o tipo (associado ao código com o <xref:System.Activities.Statements.FlowSwitch%601> por seu parâmetro genérico) obtido da avaliação da <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. Este procedimento cria uma atividade de <xref:System.Activities.Statements.FlowSwitch%601> rotulada como **switch** dentro da atividade de <xref:System.Activities.Statements.Flowchart>. O <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> pode ser digitado na caixa **expressão** da janela **Propriedades** clicando em onde o texto de dica diz "inserir uma expressão vb".

Passe o mouse sobre o **FlowSwitch\<t >** designer de atividades para fazer com que os identificadores quadrados usados para vincular <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> apareçam ao longo de suas bordas. Depois de arrastar o **FlowSwitch < T\>** designer de atividades e outros designers de atividades para o **fluxograma**, os objetos de <xref:System.Activities.Activity> que eles representam estão prontos para serem vinculados para especificar a ordem de execução. Para criar um dos <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> associados ao <xref:System.Activities.Statements.FlowSwitch%601>, clique em um dos identificadores de caso quadrado no perímetro do **FlowSwitch < t\>** e arraste-o (segurando o botão do mouse) para um dos identificadores que aparece de maneira semelhante em volta da atividade de destino quando o mouse passa sobre seu designer. Solte o botão do mouse e uma seta do **FlowSwitch < T\>** ao designer de destino aparecerá representando esse caso. O valor padrão para esse caso é exibido na seta e pode ser editado na caixa de **caso** da janela **Propriedades** .

### <a name="the-flowswitcht-properties"></a>As propriedades FlowSwitch\<T >

A tabela a seguir mostra as propriedades de <xref:System.Activities.Statements.FlowSwitch%601> e descreve como elas são usadas no designer. Essas propriedades podem ser editadas na grade de propriedade ou na superfície de designer.

|Nome da Propriedade|Necessário|Medição de|
|-|--------------|-|
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|verdadeiro|Especifica a expressão que é avaliada para determinar qual de <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> para alternar o caminho execução.|
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|Especifica um mapeamento exclusivo de resultados possíveis obtidos de avaliar <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> a um conjunto de objetos de <xref:System.Activities.Statements.FlowNode> .|
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|verdadeiro|Especificar o mapeamento quando a avaliação de <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> não coincide com um dos valores contidos no objeto de <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> .|

## <a name="see-also"></a>Veja também

- [Fluxograma](../workflow-designer/flowchart-activity-designers.md)
- [Fluxograma](../workflow-designer/flowchart-activity-designer.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)
