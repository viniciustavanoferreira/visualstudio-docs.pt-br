---
title: Registrando extensões do .NET Framework | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a5963faa5acb72ab0c94ca6b346456d83276e361
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445236"
---
# <a name="registering-extensions-of-the-net-framework"></a>Registrando extensões do .NET Framework
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode desenvolver um assembly que estende uma versão específica do .NET Framework. Para habilitar o assembly a ser exibido na caixa de diálogo **Adicionar Referências** do Visual Studio, você deve adicionar a pasta que contém o Registro do sistema.  
  
 Por exemplo, suponha que a empresa Trey Research desenvolveu uma biblioteca que estende o .NET Framework 4 e deseja que os assemblies de biblioteca apareçam na caixa de diálogo **Adicionar Referências** quando um projeto for voltado para o .NET Framework 4. Suponha também que os assemblies são de 32 bits em execução em um computador de 32 bits ou assemblies de 64 bits que são executados em um computador de 64 bits e que eles serão instalados na pasta C:\TreyResearch\Extensions4\.  
  
 Registre essa pasta usando esta chave: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Forneça esse valor padrão à chave: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
> O número de build da versão do .NET Framework pode ser diferente.  
  
 Para registrar um assembly de 32 bits em um computador de 64 bits, use o nó Wow6432, por exemplo: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Consulte também  
 [Integração com o Visual Studio](../msbuild/visual-studio-integration-msbuild.md)
