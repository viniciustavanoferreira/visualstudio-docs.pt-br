---
title: Personalizando a transformação de texto T4 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
ms.assetid: 62cd9a3c-a6e1-4b29-93f5-f2a0cf47dc92
caps.latest.revision: 30
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 71cec79acfcc934f9ddd910006f32f5207b26c84
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654963"
---
# <a name="customizing-t4-text-transformation"></a>Personalizando transformação de texto T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Os modelos de texto são um recurso de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] que permitem gerar código de programa ou outros arquivos de texto por meio de um processo de transformação. Usando [!INCLUDE[vssdk_current_short](../includes/vssdk-current-short-md.md)], você pode estender o processo de transformação de modelo padrão Personalizando o processador de diretiva de modelo de texto ou o host de modelo de texto.

## <a name="in-this-section"></a>Nesta seção
 [O processo de transformação do modelo de texto](../modeling/the-text-template-transformation-process.md) Descreve como funciona a transformação de texto e explica a função do host de modelo e os processadores de diretiva.

 [Criando processadores de diretiva de modelo de texto T4 personalizados](../modeling/creating-custom-t4-text-template-directive-processors.md) O processador de diretiva lida com diretivas em seu modelo, como `<#@template#>.` ele é executado durante a compilação do modelo e pode carregar assemblies e outros recursos. Ele também pode inserir código que carregará recursos em tempo de execução. Ao definir seu próprio processador de diretiva, você pode reduzir a complexidade de seus modelos.

 [Invocando a transformação de texto em uma extensão do vs](../modeling/invoking-text-transformation-in-a-vs-extension.md) Se você estiver escrevendo uma extensão de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], como um comando de menu ou manipulador de eventos, sua extensão poderá usar o serviço de modelagem de texto para transformar qualquer modelo de texto. Você pode passar dados de parâmetro para o modelo usando o objeto de sessão e obter os valores de dentro do modelo usando a diretiva `<#@parameter#>`.

 [Processando modelos de texto usando um host personalizado](../modeling/processing-text-templates-by-using-a-custom-host.md) Quando o código do modelo de texto é executado, o host fornece acesso a arquivos externos e ao estado do aplicativo. Por exemplo, o host que executa as transformações de texto no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pode fornecer acesso ao Gerenciador de soluções. Ele também exibe erros na janela de mensagem de erro. Se você quiser executar transformações de texto em um contexto diferente, poderá definir seu próprio host que fornece acesso aos serviços disponíveis nesse contexto.

 Se você estiver escrevendo uma extensão de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], considere usar o serviço de transformação de texto existente em vez de escrever seu próprio host. Para obter mais informações, consulte [invocando a transformação de texto em uma extensão do vs](../modeling/invoking-text-transformation-in-a-vs-extension.md).

## <a name="reference"></a>Referência
 [Gravando um modelo de texto T4](../modeling/writing-a-t4-text-template.md)

 Fornece a sintaxe de diretivas de modelo de texto e blocos de controle.
