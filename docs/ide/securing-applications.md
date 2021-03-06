---
title: Segurança
ms.date: 06/01/2018
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio], applications
- application design, securability
ms.assetid: 7d32c4cf-8bec-4307-a2a8-42f0ceddf3eb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 87f06746901baaaf14f91032f8968a0d99fc20c2
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75595443"
---
# <a name="secure-applications"></a>Aplicativos seguros

Você deve considerar a segurança em todos os aspectos do desenvolvimento do aplicativo, do design à implantação. Comece executando o Visual Studio com a máxima segurança possível. Consulte [as permissões do usuário](../ide/user-permissions-and-visual-studio.md).

Para que você desenvolva aplicativos efetivamente seguros, é preciso ter um entendimento básico dos conceitos e dos recursos de segurança das plataformas para as quais você está desenvolvendo. Também é preciso entender as técnicas de codificação segura.

## <a name="code-for-security"></a>Codificar com segurança

A maioria dos erros de codificação que resultam em vulnerabilidades de segurança ocorrem porque os desenvolvedores fazem suposições incorretas ao trabalhar com a entrada do usuário ou porque eles não têm um entendimento completo da plataforma para a qual estão desenvolvendo.

- [Diretrizes de codificação segura](/dotnet/standard/security/secure-coding-guidelines) descreve as diferentes maneiras em que o código .NET pode ser projetado para trabalhar com o sistema de segurança.
- [Práticas recomendadas de segurança para C++](/cpp/top/security-best-practices-for-cpp) contém informações sobre as ferramentas de segurança e as práticas recomendadas para desenvolvedores de C++.

## <a name="build-for-security"></a>Compilar com segurança

A segurança também é uma consideração importante no processo de compilação. Algumas etapas adicionais podem melhorar a segurança de um aplicativo implantado e ajudar a evitar engenharia reversa não autorizada, falsificação ou outros ataques:

- [Dotfuscator](dotfuscator/index.md) é gratuito e ajuda a proteger assemblies .NET contra engenharia reversa e uso não autorizado, como depuração não autorizada.
- [Assinatura de nome forte](managing-assembly-and-manifest-signing.md) pode ser usada para identificar os componentes de software com exclusividade e evitar falsificação de nome.

## <a name="see-also"></a>Confira também

- [Segurança no .NET](/dotnet/standard/security/index)
- [Segurança do Azure](/azure/security/)
- [Guia de segurança do Windows 10 Mobile](/windows/security/threat-protection/windows-10-mobile-security-guide)
- [Recursos de segurança da plataforma Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/security/best-practices?view=toolsforcordova-2017)
- [Segurança do ASP.NET Core](/aspnet/core/security/?view=aspnetcore-2.1)
- [Segurança do Windows Forms](/dotnet/framework/winforms/windows-forms-security)
