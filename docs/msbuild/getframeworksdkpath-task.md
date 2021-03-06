---
title: Tarefa GetFrameworkSdkPath | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d021bdb485846749ea2c7e9dfe483e09738fda46
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77633987"
---
# <a name="getframeworksdkpath-task"></a>Tarefa GetFrameworkSdkPath

Recupera o caminho para o Windows Software Development Kit (SDK).
## <a name="task-parameters"></a>Parâmetros de tarefa

A tabela a seguir descreve os parâmetros da tarefa `GetFrameworkSdkPath`.
A tabela a seguir descreve os parâmetros da tarefa `GetFrameworkSdkPath`.

|Parâmetro|Descrição|
|---------------|-----------------|
|`FrameworkSdkVersion20Path`|Parâmetro de saída opcional somente leitura `String`.<br /><br /> Retorna o caminho para o SDK do .NET versão 2.0, se presente. Caso contrário, retornará `String.Empty`.|
|`FrameworkSdkVersion35Path`|Parâmetro de saída opcional somente leitura `String`.<br /><br /> Retorna o caminho para o SDK do .NET versão 3.5, se presente. Caso contrário, retornará `String.Empty`.|
|`FrameworkSdkVersion40Path`|Parâmetro de saída opcional somente leitura `String`.<br /><br /> Retorna o caminho para o SDK do .NET versão 4.0, se presente. Caso contrário, retornará `String.Empty`.|
|`Path`|Parâmetro de saída `String` opcional.<br /><br /> Contém o caminho para o SDK mais recente do .NET, se houver qualquer versão. Caso contrário, retornará `String.Empty`.|

## <a name="remarks"></a>Comentários

Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Exemplo

O exemplo a `GetFrameworkSdkPath` seguir usa a tarefa de armazenar `SdkPath` o caminho para o SDK do Windows na propriedade.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="GetPath">
        <GetFrameworkSdkPath>
            <Output
                TaskParameter="Path"
                PropertyName="SdkPath" />
        </GetFrameworkSdkPath>
        <Message Text="$(SdkPath)"/>
    </Target>
</Project>
```

## <a name="see-also"></a>Confira também

- [Tarefas](../msbuild/msbuild-tasks.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)
