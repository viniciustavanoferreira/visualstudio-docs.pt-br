---
title: Alternar &lt;T &gt; designer de atividade | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
caps.latest.revision: 3
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cb6d4eb189b75d6e401bca0cfe50a71081760478
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660097"
---
# <a name="switchlttgt-activity-designer"></a>Alternar &lt;T &gt; designer de atividade
A atividade de <xref:System.Activities.Statements.Switch%601> avalia uma expressão especificada e executa a atividade de uma coleção de atividades cuja chave associado corresponde ao valor obtido de avaliação.

 O **Switch \<T >** designer de atividade é usado para criar e configurar uma atividade de <xref:System.Activities.Statements.Switch%601> no [!INCLUDE[wfd1](../includes/wfd1-md.md)].

## <a name="the-switchtactivity"></a>O switch \<T atividade de >
 Uma atividade de <xref:System.Activities.Statements.Switch%601> contém <xref:System.Activities.Statements.Switch%601.Expression%2A> e um dicionário de <xref:System.Activities.Statements.Switch%601.Cases%2A>. Cada caso no dicionário consiste em um par que contém uma *chave* e uma atividade que serve como seu *valor*correspondente. A atividade de <xref:System.Activities.Statements.Switch%601> avalia <xref:System.Activities.Statements.Switch%601.Expression%2A> e o compara com cada uma das chaves. Se uma correspondência for encontrada, a atividade correspondente é executada. Somente uma correspondência é possível porque as chaves de dicionário devem ser exclusivos de acordo com o tipo de igualdade definido pelo comparer de igualdade de dicionário. Se nenhuma correspondência for encontrada, a atividade de <xref:System.Activities.Statements.Switch%601.Default%2A> é executada.

## <a name="how-to-use-the-switcht-activity-designer"></a>Como usar a opção \<T designer de atividade de >
 A **opção \<T** designer de atividade > pode ser encontrada na categoria **fluxo de controle** da **caixa de ferramentas**, que é acessada clicando na guia caixa de **ferramentas** na [!INCLUDE[wfd2](../includes/wfd2-md.md)] (como alternativa, selecione **barra de ferramentas** na **exibição** menu ou CTRL + ALT + X.) Depois de soltá-lo no [!INCLUDE[wfd2](../includes/wfd2-md.md)], ele exibe a caixa de diálogo **Selecionar tipos** para permitir que o usuário especifique o tipo genérico *t* usado na atividade 1. O valor padrão é **Int32**. Depois que o tipo genérico *T* tiver sido selecionado, uma **opção \<T** designer de > será adicionada ao designer de fluxo de trabalho.

 A seguir estão as propriedades de **Switch \<T >** designer. Todas essas propriedades podem ser editadas na grade de propriedade. Alguns deless também podem ser editados na superfície de designer.

 A tabela a seguir mostra as propriedades mais úteis de <xref:System.Activities.Statements.Switch%601> e descreve como elas são usadas no designer.

|Nome da Propriedade|Necessária|Uso|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável do designer de atividade de <xref:System.Activities.Statements.Switch%601> . O valor padrão é switch \<Int32 >. O valor pode ser editado na janela **Propriedades** ou diretamente no cabeçalho do designer.<br /><br /> Embora não seja necessário <xref:System.Activities.Activity.DisplayName%2A> restrita, é uma prática recomendada usar um.|
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|verdadeiro|Especifica a expressão usada para comparar as chaves na coleção dos casos para determinar que casos a executar.|
|<xref:System.Activities.Statements.Switch%601.Default%2A>||Especifica a atividade executada se nenhuma correspondência for encontrada. Clique no botão **Adicionar uma atividade** no designer para abrir a caixa **padrão** em que a atividade pode ser descartada.|
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||Especifica os casos a ser avaliado. Para adicionar um caso, clique no botão **Adicionar novo caso** na parte inferior da **opção \<T** designer de >. O botão será alterado para uma caixa de texto (a opção de combinação se o tipo genérico estiver selecionado ao adicionar o comutador \<T > for String ou enum). Depois de adicionar uma chave na caixa **valor do caso** , a área do caso é expandida e uma atividade pode ser descartada onde o texto de dica "soltar atividade aqui" para definir a lógica de execução para o caso.|

 Vários casos podem ser adicionados como as chaves dos casos não são duplicadas. Se não, uma caixa de diálogo de erro exibe relatar a chave especificada dos casos já existe e que você deve escolher uma chave diferente. Na **opção \<T** designer de >, apenas uma área de caso pode estar na exibição expandida de cada vez. Se uma área dos casos está na visualização recolhida, clique na área dos casos para expandi-la. Observe que para casos, recolhidos de designer mostra o nome para exibição de atividade dentro dos casos no lado direito se houver. Caso contrário, ele mostra o botão **Adicionar uma atividade** que expande o caso se você clicar nele e permitirá que você adicione uma atividade.

 Clique na chave de casos existentes altera a chave de um rótulo em uma caixa de texto para que você possa editar a chave dos casos.

 Existem 2 maneiras de excluir casos:

1. Selecione os casos e excluir-los.

2. Selecione o caso, clique com o botão direito do mouse para exibir o menu de contexto e selecione **excluir**.

   Observe que você deve selecionar os casos os próprios para excluir. Selecionando e excluindo a atividade dentro de um caso exclui somente a atividade não os casos.

## <a name="see-also"></a>Consulte também
 [Fluxo de Controle](../workflow-designer/control-flow-activity-designers.md)