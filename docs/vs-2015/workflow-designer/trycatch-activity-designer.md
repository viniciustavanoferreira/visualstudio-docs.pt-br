---
title: O designer de atividade TryCatch | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TryCatch.UI
- System.Activities.Statements.Catch`1.UI
ms.assetid: 02a326c2-4009-442f-b7cb-e42121fd2992
caps.latest.revision: 8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b26bb37d1ddeabb77b1399c6cbce5ae55b59702c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654672"
---
# <a name="trycatch-activity-designer"></a>Designer de atividade de TryCatch
O designer de atividade **TryCatch** é usado para criar e configurar uma atividade de <xref:System.Activities.Statements.TryCatch>.

## <a name="the-trycatch-activity"></a>A atividade de TryCatch
 A atividade de <xref:System.Activities.Statements.TryCatch> contém uma atividade de <xref:System.Activities.Statements.TryCatch.Try%2A>, uma coleção de **\<TException Catch >** e uma atividade de <xref:System.Activities.Statements.TryCatch.Finally%2A>. Um <xref:System.Activities.Statements.Catch%601> do tipo **TException** contém um <xref:System.Activities.Statements.Catch%601.ExceptionType%2A> e um <xref:System.Activities.Statements.Catch%601.Action%2A>. São usados juntos para implementar um mecanismo exceção baseado típico de manipulação de erro. Uma atividade de <xref:System.Activities.Statements.TryCatch> tentar executar a atividade de <xref:System.Activities.Statements.TryCatch.Try%2A> . Se a atividade de <xref:System.Activities.Statements.TryCatch.Try%2A> lançar qualquer exceção, a atividade de <xref:System.Activities.Statements.TryCatch> usará sua **captura < TException \>** coleção para corresponder à exceção. Se houver uma correspondência, a <xref:System.Activities.Statements.Catch%601.Action%2A> do **Catch correspondente \<TException >** será executada, servindo como a lógica de tratamento de erros para a exceção. Se as atividades na seção de <xref:System.Activities.Statements.TryCatch.Try%2A> completa com êxito ou as atividades em <xref:System.Activities.Statements.TryCatch.Catches%2A> completa com êxito, a atividade de <xref:System.Activities.Statements.TryCatch> executa sua atividade de <xref:System.Activities.Statements.TryCatch.Finally%2A> . [!INCLUDE[crdefault](../includes/crdefault-md.md)][exceções](https://msdn.microsoft.com/library/065205cc-52dd-4f30-9578-b17d8d113136).

### <a name="using-the-trycatch-activity-designer"></a>Usando o designer de atividade de TryCatch
 O designer de atividade **TryCatch** pode ser encontrado na **categoria tratamento de erros** da **caixa de ferramentas**, que é acessada clicando na guia caixa de **ferramentas** no lado esquerdo da [!INCLUDE[wfd2](../includes/wfd2-md.md)] (como alternativa, selecione **barra de ferramentas** no  **Menu Exibir** ou Ctlr + Alt + X.)

 O designer de atividade **TryCatch** pode ser arrastado da **caixa de ferramentas** e descartado para a superfície de [!INCLUDE[wfd2](../includes/wfd2-md.md)] sempre que as atividades são geralmente colocadas, como dentro de um <xref:System.Activities.Statements.Sequence>. Isso cria uma atividade de <xref:System.Activities.Statements.TryCatch> com <xref:System.Activities.Activity.DisplayName%2A> padrão de TryCatch. O valor <xref:System.Activities.Activity.DisplayName%2A> pode ser editado no cabeçalho do designer de atividade **TryCatch** ou na caixa **DisplayName** da grade de propriedades. As outras propriedades devem ser editadas na superfície do designer de atividade **TryCatch** .

 Clique no botão expandir no canto superior direito do **TryCatch** designer para ver as caixas **try**, **Catch**e **finally** na exibição expandida. Para adicionar um catch, clique no botão **Adicionar nova captura** no **TryCatch** designer. O botão muda para uma caixa de combinação de tipo. Selecione um tipo de exceção e pressione ENTER para adicionar a captura. Depois de adicionar um **Catch**, a área de captura se expande e uma atividade pode ser removida para o catch para definir a lógica de execução para o catch. Observe que há uma caixa de texto no lado direito da área expandida catch. Você pode nomear a variável de exceções usando esta caixa de texto. A variável de exceção só pode ser usada para atividades dentro do mesmo **Catch**.

 O designer **TryCatch** não oferece suporte à edição **Catch**. Se você quiser alterar o tipo de exceção, será necessário excluir o **Catch** e adicionar um novo. Um **Catch** pode ser excluído selecionando-o e excluindo-o ou usando o menu **excluir** no menu de contexto acessado clicando com o botão direito do mouse.

### <a name="the-trycatch-properties"></a>As propriedades de TryCatch
 A tabela a seguir mostra o <xref:System.Activities.Statements.TryCatch>properties e descreve como eles são usados no designer.

|Nome da Propriedade|Necessária|Uso|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável opcional de atividade de <xref:System.Activities.Statements.TryCatch> . O padrão é TryCatch.|
|<xref:System.Activities.Statements.TryCatch.Try%2A>|False|A atividade executada primeiro quando <xref:System.Activities.Statements.TryCatch> executar.|
|<xref:System.Activities.Statements.TryCatch.Catches%2A>|False|A coleção de elementos **Catch** a ser verificada quando a atividade de <xref:System.Activities.Statements.TryCatch.Try%2A> gera uma exceção.<br /><br /> Você precisa pelo menos de adicionar uma atividade em <xref:System.Activities.Statements.TryCatch.Catches%2A> ou uma atividade no bloco de <xref:System.Activities.Statements.TryCatch.Finally%2A> .|
|<xref:System.Activities.Statements.TryCatch.Finally%2A>|False|A atividade a ser executada quando <xref:System.Activities.Statements.TryCatch.Try%2A> e todas as atividades necessárias na coleção de <xref:System.Activities.Statements.TryCatch.Catches%2A> tiver terminado a execução.<br /><br /> Você precisa pelo menos de adicionar uma atividade em <xref:System.Activities.Statements.TryCatch.Catches%2A> ou uma atividade no bloco de <xref:System.Activities.Statements.TryCatch.Finally%2A> .|

## <a name="see-also"></a>Consulte também
 [Throw](../workflow-designer/throw-activity-designer.md) de [regeração](../workflow-designer/rethrow-activity-designer.md) de [coleção](../workflow-designer/collection-activity-designers.md)