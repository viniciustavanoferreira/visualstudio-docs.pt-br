---
title: 'Como: Use Pesquisa em Designer de Fluxo de Trabalho'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: 12bda4af085b8ab41d3e11841f24cd5dfd389738
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650304"
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>Como: Use Pesquisa em Designer de Fluxo de Trabalho

Para facilitar a criação de fluxos de trabalho maiores e mais complexos, você pode pesquisar dentro do Designer de Fluxo de Trabalho para localizar itens por palavra-chave. Observe que o designer não suporta substitui.

## <a name="quick-find"></a>Localização Rápida

A localização rápida localiza o seguinte no designer:

- Propriedades de objetos de <xref:System.Activities.Activity> , de objetos, <xref:System.Activities.Statements.FlowNode> de objetos <xref:System.Activities.Statements.State> , das transições, e outros itens personalizados de controle de fluxo.

- Variáveis

- Arguments

- Expressões

### <a name="use-quick-find"></a>Usar localização rápida

1. Com o designer de fluxo de trabalho aberto, pressione **Ctrl + F**ou selecione **Editar**  > **Localizar e substituir**  > **localização rápida**.

2. Insira o termo de pesquisa na caixa de texto **Localizar** e clique em **Localizar próximo**.

3. O termo de pesquisa está localizado no fluxo de trabalho atual. A imagem a seguir mostra um nome de exibição da atividade que está sendo localizado no designer:

   ![Resultado de pesquisa no designer de fluxo de trabalho](../workflow-designer/media/designersearch.png)

## <a name="find-in-files"></a>Localizar nos arquivos

Localizar em arquivos localiza cadeias de caracteres em arquivos de fluxo de trabalho, incluindo arquivos XAML.

### <a name="use-find-in-files"></a>Usar Localizar em arquivos

1. No Visual Studio, pressione **Ctrl** +**Shift** +**F**ou selecione **editar**  > **Localizar e substituir**  > **localizar nos arquivos**.

2. Insira o item de pesquisa na caixa de texto **Localizar** e clique em **Localizar tudo**.

3. O resultado de Find é mostrado na exibição de **resultado de localização** . Clicar duas vezes em um item de resultado navega até a atividade que contém a correspondência no designer de fluxo de trabalho.