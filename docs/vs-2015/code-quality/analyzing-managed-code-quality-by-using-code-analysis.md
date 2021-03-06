---
title: Analisando a qualidade de código gerenciado usando a análise de código | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis,managed code
- managed code analyis
ms.assetid: 68510a55-da51-4381-81a5-0feba76b8b4f
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 0d5f0646f26226e9895414db512681e0a7a71faa
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671110"
---
# <a name="analyzing-managed-code-quality-by-using-code-analysis"></a>Analisando a qualidade do código gerenciado usando a análise de código
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode usar as ferramentas de análise de código no Visual Studio para descobrir possíveis problemas em seu código, como acesso a dados não seguro, violações de uso e problemas de design. A análise de código funciona em aplicativos .NET Framework, nativos C++(C e) e de banco de dados. A análise de código para código gerenciado organiza regras em *conjuntos de regras* que visam problemas de codificação específicos.

## <a name="common-tasks"></a>Tarefas comuns

|Tarefas comuns|Conteúdo de suporte|
|------------------|------------------------|
|**Introdução prática:** Aprenda os conceitos básicos da análise de código corrigindo defeitos em um aplicativo simples de .NET Framework.|[instruções passo a -   : analisando código gerenciado para defeitos de código](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)|
|**Configurar análise de código para um projeto:** As regras para código gerenciado são organizadas em conjuntos de regras direcionados a áreas específicas, como segurança e design. Você pode usar um dos conjuntos de regras padrão da Microsoft ou criar seus próprios.|[visão geral da análise de código de -    para código gerenciado](../code-quality/code-analysis-for-managed-code-overview.md)<br />-   [usando conjuntos de regras para regras de análise de código de grupo](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)<br />-   [suprimir avisos usando o atributo SuppressMessage](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)|
|**Executar análise de código:** Você pode especificar que a análise de código seja executada automaticamente toda vez que uma configuração de projeto for criada e você possa executar a análise de código manualmente em um projeto.|-   [como habilitar e desabilitar a análise automática de código](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)<br />-   [como executar a análise de código manualmente](../code-quality/how-to-run-code-analysis-manually-for-managed-code.md)|
|**Analisar resultados da análise de código:** Avisos e erros de análise de código são listados na janela de análise de código. Você pode escolher um aviso ou um título de erro para exibir informações adicionais sobre o aviso e exibir e realçar a linha de código-fonte que disparou a regra. Você pode escolher a ID de aviso para exibir informações detalhadas na biblioteca MSDN que inclui informações e exemplos de como resolver o problema.|-   [como: Exibir defeitos de código gerenciado](../code-quality/how-to-view-managed-code-defects.md)<br />[análise de código de -    para avisos de código gerenciado](../code-quality/code-analysis-for-managed-code-warnings.md)<br />-   [avisos por CheckId](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)<br />-   [métodos anônimos e a análise de código](../code-quality/anonymous-methods-and-code-analysis.md)|
|**Integre a análise de código com o ciclo de vida de desenvolvimento:** As políticas de check-in no [!INCLUDE[esprscc](../includes/esprscc-md.md)] permitem que as equipes de desenvolvimento verifiquem se todos os check-ins de código atendem a um conjunto comum de padrões de análise de código. A criação de um item de trabalho para uma violação de regra de análise de código é um procedimento simples que pode ser executado na janela de Lista de Erros.|-   [aprimorando a qualidade do código com as políticas de check-in do projeto de equipe](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)<br />-   [como: sincronizar conjuntos de regras de projeto de código com a política de check-in do projeto de equipe](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)<br />-   [como: criar um item de trabalho para um defeito de código gerenciado](../code-quality/how-to-create-a-work-item-for-a-managed-code-defect.md)|
