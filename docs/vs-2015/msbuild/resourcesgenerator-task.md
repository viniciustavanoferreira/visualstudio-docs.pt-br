---
title: Tarefa ResourcesGenerator | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fa8b438727160bb5a752643f7ef9791ca5e09245
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682133"
---
# <a name="resourcesgenerator-task"></a>Tarefa ResourcesGenerator
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A tarefa <xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> insere um ou mais recursos (jpg, .ico, .bmp, [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] em formato binário e outros tipos de extensão) em um arquivo .resources.  
  
## <a name="task-parameters"></a>Parâmetros da tarefa  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`OutputPath`|Parâmetro da **cadeia de caracteres** obrigatório.<br /><br /> Especifica o caminho do diretório de saída. Se o caminho não for um caminho absoluto, ele será tratado como um caminho relativo ao diretório do projeto raiz.|  
|`OutputResourcesFile`|Parâmetro de saída **ITaskItem[]** obrigatório.<br /><br /> Especifica o caminho e o nome dos arquivos .resource gerados. Se o caminho não for um caminho absoluto, o arquivo .resources será gerado em relação ao diretório raiz do projeto.|  
|`ResourcesFiles`|Parâmetro obrigatório **ITaskItem[]**.<br /><br /> Especifica um ou mais recursos para ser inserido no arquivo .resources gerado.|  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir gera um arquivo .resources com um único recurso .bmp. O recurso .bmp é gerado para um diretório relativo ao diretório raiz do projeto.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência MSBuild do WPF](../msbuild/wpf-msbuild-reference.md)   
 [Referência de tarefas](../msbuild/wpf-msbuild-task-reference.md)   
 [Referência do MSBuild](../msbuild/msbuild-reference.md)   
 [Referência de tarefas](../msbuild/msbuild-task-reference.md)   
 [Como compilar um aplicativo WPF (WPF)](https://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)
