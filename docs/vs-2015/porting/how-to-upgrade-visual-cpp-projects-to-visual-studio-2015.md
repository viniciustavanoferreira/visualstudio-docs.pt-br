---
title: 'Como: atualizar projetos do Visual C++ para o Visual Studio 2015 | Microsoft Docs'
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- projects [C++], upgrading
ms.assetid: 9a283ebb-f6d8-49c0-a73e-323979ff56a2
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: 23461fb1927cfcbf738d2dbcb82e3977b3be265a
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "77278732"
---
# <a name="how-to-upgrade-visual-c-projects-to-visual-studio-2015"></a>Como: Atualizar projetos do Visual C++ para Visual Studio 2015
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para verificar a documentação mais recente do Visual Studio 2017, confira [Guia de portabilidade e atualização do Visual C++](/cpp/porting/visual-cpp-porting-and-upgrading-guide).

Quando você abre primeiro um projeto do Visual C++ que foi criado em uma versão anterior do Visual Studio, poderá ser solicitado que você atualize o projeto. A mensagem pergunta se você deseja atualizar para a versão mais recente do compilador e das bibliotecas do Visual C++. As opções de atualização dependem da versão do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] que foi usada para criar o projeto.

 Você pode usar o [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)] para abrir, editar, e compilar os projetos do [!INCLUDE[win8](../includes/win8-md.md)] que foram criados no [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], mas para criar um novo projeto do [!INCLUDE[win8](../includes/win8-md.md)], você deve usar o [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. (Para criar um projeto [!INCLUDE[win81](../includes/win81-md.md)], você deve usar [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)].)

 Para criar um projeto do Windows 10, você deve usar o [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)].

 Se a atualização do projeto não for solicitada, talvez não seja necessário que você faça algo para atualizá-lo.

- Se o projeto (.vcproj) foi criado em uma versão de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] mais antiga do que [!INCLUDE[vs2010](../includes/vs2010-md.md)], você deve atualizar o projeto.

- Se o projeto (.vcxproj) tiver sido criado no [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)], no [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] ou no [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)], haverá duas opções:

  - Você pode pular a atualização. [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)] carregará o projeto sem fazer nenhuma alteração se ele tiver acesso às ferramentas Visual C++ no [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] com SP1, no [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] ou no [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)]. Para fornecer este acesso, instale a versão do Visual Studio com a qual o projeto foi criado, no mesmo computador que tenha o [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)]. Para saber mais, veja [Como instalar as versões do Visual Studio lado a lado](../install/install-visual-studio-versions-side-by-side.md).

  - Você pode atualizar o projeto permitindo que o [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] faça as alterações que são descritas posteriormente neste tópico. Se você tiver mais de um projeto do Visual C++ em sua solução, deverá atualizar todos eles.

    > [!NOTE]
    > Se você recusar a atualização quando solicitado pela primeira vez, poderá atualizar o projeto mais tarde escolhendo **Atualizar projeto do VC++** no menu **Projeto**. Se o comando não aparecer, a atualização não será necessária.

## <a name="upgrading-a-visual-c-project"></a>Atualizando um projeto do Visual C++
 Se você permitir que [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)] atualize automaticamente o projeto, estas alterações serão feitas:

- Alteração do projeto para que ele use o compilador e as bibliotecas do [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)] (PlatformToolset = VisualStudio v140).

- Para projetos do [!INCLUDE[cppcli](../includes/cppcli-md.md)], alteração de TargetFrameworkVersion para .NET Framework 4.5.2.

## <a name="continuing-to-work-with-a-custom-platformtoolset"></a>Continuação do trabalho com um PlatformToolset personalizado
 Se você desejar continuar a trabalhar com um Conjunto de Ferramentas de Plataforma no [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)], o conjunto de ferramentas deverá ser colocado em %ProgramFiles%\MSBuild\Microsoft.Cpp\v4.0\Platforms\Win32\PlatformToolsets\ em uma máquina x86, ou em %ProgramFiles (x86)%\MSBuild\Microsoft.Cpp\v4.0\Platforms\Win32\PlatformToolsets\ em uma máquina x64. Para obter informações de como criar um PlatformToolset personalizado, confira [Multiplataforma nativa C++](https://blogs.msdn.com/b/vcblog/archive/2009/12/08/c-native-multi-targeting.aspx) no blog da equipe do Visual C++.

## <a name="see-also"></a>Consulte também
 [Guia de atualização e compatibilização do Visual C++](https://msdn.microsoft.com/library/f5fbcc3d-aa72-41a6-ad9a-a706af2166fb) [Compatibilização, migração e atualização de projetos do Visual Studio](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)
