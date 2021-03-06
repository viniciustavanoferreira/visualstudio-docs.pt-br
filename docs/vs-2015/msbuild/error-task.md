---
title: Tarefa Erro | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Error
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Error task [MSBuild]
- MSBuild, Error task
ms.assetid: e96a90ee-a8ae-4e5b-8ef2-b5cf5fedd8b2
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b220d12b872a81cba5f46bd14fdebafaa58cf4a1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201807"
---
# <a name="error-task"></a>Tarefa Error
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Interrompe um build e registra um erro com base em uma instrução condicional avaliada.  
  
## <a name="parameters"></a>Parâmetros  
 A tabela a seguir descreve os parâmetros da tarefa `Error`.  
  
|Parâmetro|DESCRIÇÃO|  
|---------------|-----------------|  
|`Code`|Parâmetro `String` opcional.<br /><br /> O código de erro a associar ao erro.|  
|`File`|Parâmetro `String` opcional.<br /><br /> O nome do arquivo que contém o erro. Se nenhum nome de arquivo for fornecido, o arquivo que contém a tarefa de erro será usado.|  
|`HelpKeyword`|Parâmetro `String` opcional.<br /><br /> A palavra-chave Ajuda a ser associada ao erro.|  
|`Text`|Parâmetro `String` opcional.<br /><br /> O texto do erro que [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] registra se o parâmetro `Condition` resultar em `true`.|  
  
## <a name="remarks"></a>Comentários  
 A tarefa `Error` permite que projetos [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] emitam o texto de erro para agentes e interrompe a execução de build.  
  
 Se o parâmetro `Condition` avaliar `true`, o build será interrompido e um erro será registrado. Se um parâmetro `Condition` não existir, o erro será registrado e a execução de build será interrompida. Para obter mais informações sobre registro, consulte [Obter logs de build](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, consulte [Classe base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir verifica se todas as propriedades necessárias estão definidas. Se elas não estiverem definidas, o projeto gerará um evento de erro e registrará o valor do parâmetro `Text` da tarefa `Error`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Error  
            Text=" The 0 property must be set on the command line."  
            Condition="'$(0)' == ''" />  
        <Error  
            Text="The FREEBUILD property must be set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Veja também  
 [Referência de tarefas](../msbuild/msbuild-task-reference.md)   
 [Obtendo Logs de Build](../msbuild/obtaining-build-logs-with-msbuild.md)
