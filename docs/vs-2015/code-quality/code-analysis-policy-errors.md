---
title: Erros de política de análise de código | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.policyfailures
helpviewer_keywords:
- policy errors, code analysis
ms.assetid: d1f221cd-68c0-4277-9397-b76ad0dbae77
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 8cb50fffc1411e77f771b0f74fbb947144eb6017
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672919"
---
# <a name="code-analysis-policy-errors"></a>Erros da política de análise do código
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Os seguintes erros ocorrerão se a política de análise de código não for satisfeita no check-in:

 **As configurações de análise de código para um ou mais projetos não são compatíveis com a política de análise de código.**

 Os requisitos de análise de código que estão fazendo check-in no controle do código-fonte do projeto de equipe não foram atendidos para um ou mais projetos de código. Esse erro pode ser causado por uma ou mais das seguintes condições:

1. A análise de código não está habilitada na compilação para todos os projetos na solução.

2. O conjunto de regras locais para o projeto no Visual Studio tem uma configuração de **ação** menos restritiva do que o conjunto de regras do projeto de equipe, por exemplo, uma regra que é definida como **ação** =**erro** no servidor tem sua **ação** definida como **aviso** ou **nenhum** no conjunto de regras que está sendo executado no Visual Studio).

3. O conjunto de regras especificado no Visual Studio não contém todas as regras especificadas no conjunto de regras especificado na política de check-in de análise de código para o projeto de equipe.

   **Falha na política de análise de código. Há erros no projeto {0} ou a compilação não está atualizada.**

   A compilação contém erros ou os erros foram corrigidos, mas a análise de código não foi executada após a correção.

   **Falha no check-in. A política de análise de código requer que você faça o check-in por meio do Visual Studio com uma solução aberta.**

   A política de análise de código requer que todos os arquivos que estão sendo verificados devem estar na solução aberta no momento. Para corrigir esse erro, abra a solução que contém o arquivo no qual será feito o check-in.

   **Nem todos os arquivos no check-in pendente estão dentro da solução aberta no momento.**

   A política de análise de código requer que todos os arquivos que estão sendo verificados devem estar na solução aberta no momento. Esse erro é gerado quando há uma solução aberta, mas alguns arquivos na exibição "verificação pendente" não fazem parte da solução atualmente aberta. Para corrigir esse erro, abra a solução que contém o arquivo no qual será feito o check-in.

   **A versão de ' {0} ' não está correta. O nome forte especificado na política é ' {1} '.**

   Este erro se aplica a projetos .NET. Uma Rule. dll exigida pela política de análise de código existe no computador local, mas a versão/chave pública não corresponde. Para corrigir esse erro, o criador da política deve atualizar o. DLLs em *C:\Program Files\Microsoft Visual Studio 8 \ Team Tools\Static Analysis Tools\FxCop\Rules \\* Directory em seu computador.

   **o assembly ' {0} ' especificado na política não existe.**

   Este erro se aplica a projetos .NET. Uma regra exigida pela política de análise de código não tem a dll correspondente instalada no computador cliente. Para corrigir esse erro, o criador de política deve atualizar a dll em *C:\Program Files\Microsoft Visual Studio 8 \ Team Tools\Static Analysis Tools\FxCop\Rules \\* Directory em seu computador.

   **As configurações de regra do Project {0} não estão em conformidade com a política de análise de código.**

   Este erro se aplica a projetos .NET. As configurações de regras de código gerenciado não são tão rigorosas quanto a política requer. Para corrigir esse erro, a configuração do cliente deve ser a mesma ou mais estrita do que o requisito de política no servidor.

   **A análise de código não está habilitada na configuração ativa. Alterne para a configuração {0} e compile o projeto {1} antes de fazer check-in.**

   No [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], a configuração ativa não tem a análise de código habilitada, mas há pelo menos uma análise de código habilitada.

   **Você deve habilitar a análise de código para binários gerenciados nas propriedades do projeto {0} e compilar antes de fazer check-in.**

   Esse erro se aplica a aplicativos [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] .NET. A política requer que a análise de código gerenciado seja executada, mas não está habilitada no projeto atual no cliente.

   **Você deve habilitar a análise de código nas propriedades do projeto {0} e compilar antes de fazer check-in.**

   Esse erro é aplicado a projetos de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] e projetos Web. A política requer que a análise de código gerenciado seja executada, mas não está habilitada no projeto atual no cliente.

   **Você deve habilitar a análiseC++ de C/Code nas propriedades do projeto {0} e compilar antes de fazer check-in.**

   Esse erro se aplica a projetos não gerenciados. A política de análise de código requer análise de códigoC++para C/, mas não está habilitada no projeto atual no cliente.

## <a name="see-also"></a>Consulte também
 [Erros de aplicativo de análise de código](../code-quality/code-analysis-application-errors.md)
