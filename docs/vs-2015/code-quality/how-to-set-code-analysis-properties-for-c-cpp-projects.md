---
title: Como definir propriedades de análise de código para C-C++ Projects | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.native
- VC.Project.VCCLCompilerTool.EnablePrefast
- VC.Project.VCFxCopTool.EnablePREfast
- VC.Project.VCFxCopTool.IgnoreGeneratedCode
helpviewer_keywords:
- properties, C/C++ Code Analysis
- properties, Code Analysis
- code analysis properties
- C/C++ code analysis properties
ms.assetid: 7af52097-6d44-4785-9b9f-43b7a7d447d7
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: b2fb3cb81b49fd4b8cc83e0548110d2025c7488d
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "77277991"
---
# <a name="how-to-set-code-analysis-properties-for-cc-projects"></a>Como definir propriedades de análise de código para projetos do C/C++
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode configurar quais regras a ferramenta de análise de código usa para analisar o código em cada configuração do seu projeto. Além disso, você pode direcionar a análise de código para suprimir avisos do código que foi gerado e adicionado ao seu projeto por uma ferramenta de terceiros.  
  
## <a name="code-analysis-property-page"></a>Página de propriedades de análise de código  
 A página de propriedades de **análise de código** contém todas as definições de configuração de análise de código para um projeto. Para abrir a página de propriedades de análise de código de um projeto no **Gerenciador de soluções**, clique com o botão direito do mouse no projeto e clique em **Propriedades**. Em seguida, expanda **Propriedades de configuração** e selecione a guia **análise de código** .  
  
## <a name="project-configuration-and-platform"></a>Configuração e plataforma de projeto  
 A lista de **configurações** e a lista de **plataformas** permite que você aplique diferentes configurações de análise de código a diferentes combinações de plataforma e configuração de projeto. Por exemplo, você pode direcionar a análise de código para aplicar um conjunto de regras ao seu projeto para compilações de depuração e um conjunto diferente para compilações de versão.  
  
## <a name="enabling-code-analysis"></a>Habilitando análise de código  
 Você pode decidir se deseja habilitar a análise de código para seu projeto selecionando **Habilitar análise de códigoC++ para C/no Build**. Em combinação com a lista de **configuração** , você pode, por exemplo, decidir desabilitar a análise de código para compilações de depuração e habilitá-la para compilações de versão.  
  
 Se o seu projeto contiver código gerenciado, você poderá decidir se deseja habilitar ou desabilitar a análise de código selecionando **Habilitar análise de código na compilação**.  
  
 A análise de código foi projetada para ajudá-lo a melhorar a qualidade do seu código e evitar armadilhas comuns. Portanto, considere atentamente se a análise de código deve ser desabilitada. Geralmente, é melhor desabilitar conjuntos de regras ou regras individuais que você não deseja aplicar ao seu projeto.  
  
## <a name="generated-code"></a>Código gerado  
 Os desenvolvedores frequentemente usam ferramentas para ajudar a desenvolver aplicativos rapidamente. Essas ferramentas podem gerar código que é adicionado ao projeto. Talvez você queira ver as violações de regra que a análise de código descobre no código gerado. No entanto, talvez você não queira vê-los se não quiser manter o código.  
  
 A caixa de seleção **suprimir resultados do código gerado** na página Propriedades **gerais** permite que você selecione se deseja ver avisos de análise de código do código gerenciado gerado por uma ferramenta de terceiros.  
  
## <a name="rule-sets"></a>Conjuntos de regras  
 Se o seu projeto contiver código gerenciado, você poderá selecionar as regras a serem aplicadas em uma análise de código selecionando um conjunto de regras na lista **executar este conjunto de regras** .  
  
## <a name="see-also"></a>Consulte Também  
 [Analisando a Qualidade do Código Gerenciado](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [Análise de código para avisos do C/C++](../code-quality/code-analysis-for-c-cpp-warnings.md)
