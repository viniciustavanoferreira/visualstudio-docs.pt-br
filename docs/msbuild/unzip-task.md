---
title: Tarefa de descompactação | Microsoft Docs
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Unzip
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Unzip task [MSBuild]
- MSBuild, Unzip task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d331fda05e8655be0536a1e83d8309ae8c060b1f
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631504"
---
# <a name="unzip-task"></a>Tarefa de descompactação

Descompacta um arquivo *.zip* no local especificado.

>[!NOTE]
>A tarefa `Unzip` está disponível apenas no MSBuild 15.8 e superiores.

## <a name="parameters"></a>parâmetros

 A tabela a seguir descreve os parâmetros da tarefa `Unzip`.

|Parâmetro|Descrição|
|---------------|-----------------|
|`DestinationFolder`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem> necessário<br /><br /> Especifica a pasta de destino para descompactar o arquivo.|
|`OverwriteReadOnlyFiles`|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, substitui os arquivos somente leitura. Usa `false` como padrão.|
|`SkipUnchangedFiles`|Parâmetro `Boolean` opcional.<br /><br /> Se ele for `true`, ignorará a descompactação de arquivos inalterados. Usa `true` como padrão. A tarefa `Unzip` considera os arquivos como inalterados se eles têm o mesmo tamanho e a mesma hora da última modificação.|
|`SourceFiles`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem>`[]` obrigatório.<br /><br /> Especifica um ou mais arquivos a serem descompactados. Quando vários arquivos são especificados, eles são descompactados em ordem na mesma pasta.|

## <a name="remarks"></a>Comentários

 Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Exemplo

 O exemplo a seguir descompacta um arquivo morto e substitui os arquivos somente leitura.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="UnzipArchive" BeforeTargets="Build">
        <Unzip
            SourceFiles="MyArchive.zip"
            DestinationFolder="$(OutputPath)\unzipped"
            OverwriteReadOnlyFiles="true"
        />
    </Target>

</Project>
```

## <a name="see-also"></a>Confira também

- [Tarefas](../msbuild/msbuild-tasks.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)
