---
title: -Rebuild (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Devenv, /rebuild switch
- Rebuild Devenv switch (/Rebuild)
- projects [Visual Studio], rebuilding
- /Rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 76fe4bcf3441163604d93e9264ed6f78fcf0224b
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75565611"
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)

Limpa e, em seguida, compila a configuração de solução especificada.

## <a name="syntax"></a>Sintaxe

```shell
devenv SolutionName /Rebuild [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Argumentos

- *Solutionname*

  Obrigatórios. O caminho completo e o nome do arquivo de solução.

- *SolnConfigName*

  Opcional. O nome da configuração da solução (por exemplo, `Debug` ou `Release`) que será usado para recompilar a solução nomeada em *SolutionName*. Se mais de uma plataforma de solução estiver disponível, também será preciso especificar a plataforma (por exemplo, `Debug|Win32`). Se esse argumento não for especificado ou for uma cadeia de caracteres vazia (`""`), a ferramenta usará a configuração ativa da solução.

- `/Project`*ProjName*

  Opcional. O caminho e o nome de um arquivo de projeto na solução. Você pode inserir o nome de exibição do projeto ou um caminho relativo da pasta *SolutionName* para o arquivo do projeto. Também é possível inserir o caminho completo e o nome do arquivo do projeto.

- `/ProjectConfig` *ProjConfigName*

  Opcional. O nome da configuração de build do projeto (por exemplo, `Debug` ou `Release`) que será usado ao recompilar o `/Project` nomeado. Se mais de uma plataforma de solução estiver disponível, também será preciso especificar a plataforma (por exemplo, `Debug|Win32`). Se esta opção for especificada, ela substituirá o argumento *SolnConfigName*.

- `/Out`*Nome de saída*

  Opcional. O nome de um arquivo para o qual você deseja enviar a saída da ferramenta. Se o arquivo já existir, a ferramenta anexará a saída ao final do arquivo.

## <a name="remarks"></a>Comentários

- Esta opção faz a mesma coisa que o comando de menu **Recompilar Solução** dentro do IDE.

- Coloque as cadeias de caracteres que incluem espaços entre aspas duplas.

- As informações de resumo para limpeza ou compilação, incluindo erros, podem ser exibidas na janela **Comando** ou em qualquer arquivo de log especificado com a opção [/Out](out-devenv-exe.md).

## <a name="example"></a>Exemplo

Este exemplo limpa e recompila o projeto `CSharpWinApp`, usando a configuração de build do projeto `Debug` dentro de `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Confira também

- [Opções de linha de comando do Devenv](../../ide/reference/devenv-command-line-switches.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
