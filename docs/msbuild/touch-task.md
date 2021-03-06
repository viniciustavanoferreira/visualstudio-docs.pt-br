---
title: Tarefa Touch | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 873783196a3eebdaca9cc4278b091e084c1488b0
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631647"
---
# <a name="touch-task"></a>tarefa Touch

Define os horários de modificação e acesso aos arquivos.

## <a name="parameters"></a>parâmetros

 A tabela a seguir descreve os parâmetros da tarefa `Touch`.

|Parâmetro|Descrição|
|---------------|-----------------|
|`AlwaysCreate`|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, cria todos os arquivos que ainda não existem.|
|`Files`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem>`[]` obrigatório.<br /><br /> Especifica a coleção de arquivos a serem tocados.|
|`ForceTouch`|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, força um toque de arquivo, mesmo que os arquivos sejam somente leitura.|
|`Time`|Parâmetro `String` opcional.<br /><br /> Especifica uma hora diferente da atual. O formato deve ser um formato aceitável para o método <xref:System.DateTime.Parse%2A>.|
|`TouchedFiles`|Parâmetro de saída <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Contém a coleção de itens que foram tocados com êxito.|

## <a name="remarks"></a>Comentários

 Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Exemplo

 O exemplo a seguir usa a tarefa `Touch` para alterar os horários de acesso e modificação dos arquivos especificados na coleção de itens `Files` e coloca a lista de arquivos tocados com êxito na coleção de itens `FilesTouched`.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

<ItemGroup>
    <Files Include="File1.cs;File2.cs;File3.cs" />
</ItemGroup>

    <Target Name="TouchFiles">
        <Touch
            Files="@(Files)">
            <Output
                TaskParameter="TouchedFiles"
                ItemName="FilesTouched"/>
    </Touch>
</Target>
</Project>
```

## <a name="see-also"></a>Confira também

- [Tarefas](../msbuild/msbuild-tasks.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)
