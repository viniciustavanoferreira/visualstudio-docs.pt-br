---
title: Tarefa de aviso | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Warning
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Warning task [MSBuild]
- MSBuild, Warning task
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e95b59b4ccc0bd2df89e45512a5bdd05c027556
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631088"
---
# <a name="warning-task"></a>tarefa Warning

Registra um aviso durante um build com base em uma instrução condicional avaliada.

## <a name="parameters"></a>parâmetros

 A tabela a seguir descreve os parâmetros da tarefa `Warning`.

| Parâmetro | Descrição |
|---------------| - |
| `Code` | Parâmetro `String` opcional.<br /><br /> O código de erro que será associado ao aviso. |
| `File` | Parâmetro `String` opcional.<br /><br /> Especifica o arquivo relevante, se houver. Se nenhum arquivo for fornecido, o arquivo que contém a tarefa de aviso será usado. |
| `HelpKeyword` | Parâmetro `String` opcional.<br /><br /> A palavra-chave Ajuda que será associada ao aviso. |
| `Text` | Parâmetro `String` opcional.<br /><br /> O texto de aviso que o `Condition` MSBuild `true`registra se o parâmetro for avaliado em . |

## <a name="remarks"></a>Comentários

 A `Warning` tarefa permite que os projetos do MSBuild verifiquem a presença de uma configuração ou propriedade necessária antes de prosseguir com a próxima etapa de compilação.

 Se o parâmetro `Condition` da tarefa `Warning` for avaliada como `true`, o valor do parâmetro `Text` será registrado e o build continuará a ser executada. Se não existir um parâmetro `Condition`, o texto de aviso será registrado. Para saber mais sobre o log, confira [Obter logs de build](../msbuild/obtaining-build-logs-with-msbuild.md).

 Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Exemplo

 O exemplo de código a seguir verifica as propriedades que são definidas na linha de comando. Se nenhuma propriedade estiver definida, o projeto gerará um evento de aviso e registrará o valor do parâmetro `Text` da tarefa `Warning`.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="ValidateCommandLine">
        <Warning
            Text=" The 0 property was not set on the command line."
            Condition="'$(0)' == ''" />
        <Warning
            Text=" The FREEBUILD property was not set on the command line."
            Condition="'$(FREEBUILD)' == ''" />
    </Target>
    ...
</Project>
```

## <a name="see-also"></a>Confira também

- [Obter logs de build](../msbuild/obtaining-build-logs-with-msbuild.md)
- [Referência de esquema de arquivo de projeto](../msbuild/msbuild-project-file-schema-reference.md)
