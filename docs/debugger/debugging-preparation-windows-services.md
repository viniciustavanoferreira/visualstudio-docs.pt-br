---
title: Preparar para depurar serviços do Windows | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Windows services
- Windows Service applications, debugging
ms.assetid: ac0a99f7-ec3d-4a20-b17f-698a817fdcc2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3161f6d2c328e8e33dd82ed206aa8aa20e654cc9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738083"
---
# <a name="debugging-preparation-windows-services"></a>Preparação de depuração: Serviços Windows
Um serviço do Windows é um programa executado em segundo plano no Microsoft Windows. Os exemplos incluem o serviço de Telnet e o serviço de tempo do Windows, que atualiza o relógio visível do computador. Um serviço do Windows não pode ser executados no [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]; ele deve ser executado no contexto do Gerenciador de Controle de Serviços. Para obter mais informações, confira [Criando serviços do Windows](/dotnet/framework/windows-services/how-to-create-windows-services), [Depurando aplicativos de serviço Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications) e [Aplicativos de serviço Windows](/dotnet/framework/windows-services/index).

## <a name="see-also"></a>Consulte também
- [Depurando código gerenciado](../debugger/debugging-managed-code.md)
- [Tipos de projeto C#, F# e Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
- [Configurações do projeto para configurações de depuração de C#](../debugger/project-settings-for-csharp-debug-configurations.md)
- [Definições do projeto para uma configuração de depuração do Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)
- [Como depurar o método OnStart](../debugger/how-to-debug-the-onstart-method.md)