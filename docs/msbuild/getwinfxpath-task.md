---
title: Tarefa GetWinFXPath | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- getting the directory of the current .NET Framework runtime [WPF MSBuild]
- GetWinFXPath task [WPF MSBuild], parameters
- GetWinFXPath task [WPF MSBuild]
- obtaining the path to the current .NET Framework runtime [WPF MSBuild]
ms.assetid: b1dfb467-f3d3-47f3-83ef-af7b0e33a772
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab8e15cef722e935dde322072f6834ba00be8bc5
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77633961"
---
# <a name="getwinfxpath-task"></a>Tarefa GetWinFXPath

A <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> tarefa retorna o diretório do tempo de execução atual .NET.

## <a name="task-parameters"></a>Parâmetros de tarefa

| Parâmetro | Descrição |
|-------------------| - |
| `WinFXPath` | Parâmetro de saída opcional **String**.<br /><br /> Especifica o caminho real para o tempo de execução .NET. |
| `WinFXNativePath` | Parâmetro obrigatório **String**.<br /><br /> Especifica o caminho para o tempo de execução nativo .NET. |
| `WinFXWowPath` | Parâmetro obrigatório **String**.<br /><br /> Especifica o caminho para os conjuntos .NET no módulo Windows de 32 bits **no Windows** em sistemas de 64 bits. |

## <a name="remarks"></a>Comentários

 Se a tarefa <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> está em execução em um processador de 64 bits, o parâmetro **WinFXPath** está definido como o caminho armazenado no parâmetro **WinFXWowPath**, caso contrário, o parâmetro **WinFXPath** é definido como o caminho armazenado no parâmetro **WinFXNativePath**.

## <a name="example"></a>Exemplo

 O exemplo a seguir mostra como usar a tarefa **GetWinFXPath** para detectar o caminho nativo até o tempo de execução .NET.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.GetWinFXPath"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="GetWinFXPathTask">
    <GetWinFXPath
      WinFXNativePath="c:\WinFXNative"
      WinFXWowPath="c:\WinFXWowNative" />
  </Target>
  <Import Project="$(MSBuildBinPath)\Microsoft.WinFX.targets" />
</Project>
```

## <a name="see-also"></a>Confira também

- [Referência WPF MSBuild](../msbuild/wpf-msbuild-reference.md)
- [Referência de tarefas](../msbuild/wpf-msbuild-task-reference.md)
- [Referência do MSBuild](../msbuild/msbuild-reference.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)
- [Compilar um aplicativo WPF](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
