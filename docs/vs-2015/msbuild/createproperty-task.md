---
title: Tarefa CreateProperty | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ea16950e47760e89204503413fd98811e781d059
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184053"
---
# <a name="createproperty-task"></a>Tarefa CreateProperty
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popula as propriedades com os valores passados. Isso permite que os valores sejam copiados de uma propriedade ou cadeia de caracteres para outra.  
  
## <a name="attributes"></a>Atributos  
 A tabela a seguir descreve os parâmetros da tarefa `CreateProperty`.  
  
|Parâmetro|DESCRIÇÃO|  
|---------------|-----------------|  
|`Value`|Parâmetro de saída `String` opcional.<br /><br /> Especifica o valor a ser copiado para a nova propriedade.|  
|`ValueSetByTask`|Parâmetro de saída `String` opcional.<br /><br /> Contém o mesmo valor que o parâmetro `Value`. Use esse parâmetro somente para evitar que a propriedade de saída seja definida por [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] quando ela ignora o destino delimitador porque as saídas estão atualizadas.|  
  
## <a name="remarks"></a>Comentários  
 Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, consulte [Classe base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa a tarefa `CreateProperty` para criar a propriedade `NewFile` usando a combinação dos valores das propriedades `SourceFilename` e `SourceFileExtension`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 Depois de executar o projeto, o valor da propriedade `NewFile` será `Module1.vb`.  
  
## <a name="see-also"></a>Veja também  
 [Referência de tarefas](../msbuild/msbuild-task-reference.md)   
 [Tarefas](../msbuild/msbuild-tasks.md)
