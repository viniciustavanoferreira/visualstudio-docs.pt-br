---
title: -Command (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9083d14c82eb2d283431e28d03bbbf96c14258cc
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660849"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Executa o comando especificado depois de iniciar o IDE (ambiente de desenvolvimento integrado) do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].

## <a name="syntax"></a>Sintaxe

```
devenv /command CommandName
```

## <a name="arguments"></a>Arguments
 `CommandName` Necessário. O nome completo de um comando [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ou seu alias, colocado entre aspas duplas. Para obter mais informações sobre comandos e a sintaxe de aliases, consulte [Comandos do Visual Studio](../../ide/reference/visual-studio-commands.md).

## <a name="remarks"></a>Comentários
 Após a conclusão da inicialização, o IDE executa o comando nomeado. Se você usar essa opção, o IDE não mostrará a Página Inicial do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] na inicialização.

 Se um suplemento expor um comando, será possível usar essa opção para iniciar o suplemento por meio da linha de comando. Para obter mais informações, consulte [Como controlar suplementos usando o Gerenciador de Suplementos](https://msdn.microsoft.com/library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).

## <a name="example"></a>Exemplo
 Esse exemplo inicia [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] e executa a macro Abrir Arquivos Favoritos automaticamente.

```
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"
```

## <a name="see-also"></a>Veja também
 [Linha de comando do devenv alterna](../../ide/reference/devenv-command-line-switches.md) os [aliases de comando do Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
