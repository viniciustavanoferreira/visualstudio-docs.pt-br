---
title: Designer de Fluxo de Trabalho-alternar<T> designer de atividade
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a39e8c1e789c1c448e30962789d1a9ab7f3e65c5
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75593116"
---
# <a name="switcht-activity-designer"></a>Alternar\<T > designer de atividade

A atividade de <xref:System.Activities.Statements.Switch%601> avalia uma expressão especificada e executa a atividade de uma coleção de atividades cuja chave associado corresponde ao valor obtido de avaliação.

O **Switch < T\>** Activity Designer é usado para criar e configurar uma atividade de <xref:System.Activities.Statements.Switch%601> no designer de fluxo de trabalho.

## <a name="the-switchtactivity"></a>A atividade alternar\<T >

Uma atividade de <xref:System.Activities.Statements.Switch%601> contém <xref:System.Activities.Statements.Switch%601.Expression%2A> e um dicionário de <xref:System.Activities.Statements.Switch%601.Cases%2A>. Cada caso no dicionário consiste em um par que contém uma *chave* e uma atividade que serve como seu *valor*correspondente. A atividade de <xref:System.Activities.Statements.Switch%601> avalia <xref:System.Activities.Statements.Switch%601.Expression%2A> e o compara com cada uma das chaves. Se uma correspondência for encontrada, a atividade correspondente é executada. Somente uma correspondência é possível porque as chaves de dicionário devem ser exclusivos de acordo com o tipo de igualdade definido pelo comparer de igualdade de dicionário. Se nenhuma correspondência for encontrada, a atividade de <xref:System.Activities.Statements.Switch%601.Default%2A> é executada.

## <a name="how-to-use-the-switcht-activity-designer"></a>Como usar a opção\<> designer de atividades

Acesse a **opção\<t >** designer de atividade na categoria **fluxo de controle** da caixa de **ferramentas**. Depois de soltá-lo no Designer de Fluxo de Trabalho, ele exibe a caixa de diálogo **Selecionar tipos** para permitir que o usuário especifique o tipo genérico *T* usado na atividade <xref:System.Activities.Statements.Switch%601>. O valor padrão é **Int32**. Depois que o tipo genérico *T* tiver sido selecionado, uma **opção <** designer de\>será adicionada ao designer de fluxo de trabalho.

A seguir estão as propriedades de **Switch < T\>** designer. Todas essas propriedades podem ser editadas na grade de propriedade. Alguns deless também podem ser editados na superfície de designer.

A tabela a seguir mostra as propriedades mais úteis de <xref:System.Activities.Statements.Switch%601> e descreve como elas são usadas no designer.

|Nome da Propriedade|Necessário|Medição de|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica o nome amigável do designer de atividade de <xref:System.Activities.Statements.Switch%601> . O valor padrão é switch < Int32\>. O valor pode ser editado na janela **Propriedades** ou diretamente no cabeçalho do designer.<br /><br /> Embora não seja necessário <xref:System.Activities.Activity.DisplayName%2A> restrita, é uma prática recomendada usar um.|
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|verdadeiro|Especifica a expressão usada para comparar as chaves na coleção dos casos para determinar que casos a executar.|
|<xref:System.Activities.Statements.Switch%601.Default%2A>||Especifica a atividade executada se nenhuma correspondência for encontrada. Clique no botão **Adicionar uma atividade** no designer para abrir a caixa **padrão** em que a atividade pode ser descartada.|
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||Especifica os casos a ser avaliado. Para adicionar um caso, clique no botão **Adicionar novo caso** na parte inferior do **Switch\<t >** designer. O botão é alterado para uma caixa de texto (a box de combinação, se o tipo genérico estiver selecionado ao adicionar a opção\<T > é cadeia de caracteres ou enum). Depois de adicionar uma chave na caixa **valor do caso** , a área do caso é expandida e uma atividade pode ser descartada onde o texto de dica "soltar atividade aqui" para definir a lógica de execução para o caso.|

Vários casos podem ser adicionados como as chaves dos casos não são duplicadas. Se não, uma caixa de diálogo de erro exibe relatar a chave especificada dos casos já existe e que você deve escolher uma chave diferente. No **\<t >** designer, apenas uma área de caso pode estar na exibição expandida de cada vez. Se uma área dos casos está na visualização recolhida, clique na área dos casos para expandi-la. Observe que para casos, recolhidos de designer mostra o nome para exibição de atividade dentro dos casos no lado direito se houver. Caso contrário, ele mostra o botão **Adicionar uma atividade** que expande o caso se você clicar nele e permitirá que você adicione uma atividade.

Clique na chave de casos existentes altera a chave de um rótulo em uma caixa de texto para que você possa editar a chave dos casos.

Existem 2 maneiras de excluir casos:

- Selecione os casos e excluir-los.

- Selecione o caso, clique com o botão direito do mouse para exibir o menu de contexto e selecione **excluir**.

Observe que você deve selecionar os casos os próprios para excluir. Selecionando e excluindo a atividade dentro de um caso exclui somente a atividade não os casos.

## <a name="see-also"></a>Veja também

- [Fluxo de Controle](../workflow-designer/control-flow-activity-designers.md)
