---
title: 'Erro: não é possível entrar automaticamente no servidor | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 34b298b299bb4911bfe64b362d94c3e90ecfa585
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72736871"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Erro: não é possível intervir automaticamente no servidor
O erro é:

 Não é possível realizar a depuração completa do servidor automaticamente. O depurador não foi notificado antes do procedimento remoto ter sido executado

 Esse erro pode ocorrer quando você está tentando entrar em um serviço Web (confira [Entrar em um serviço Web XML](https://msdn.microsoft.com/library/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Pode ocorrer sempre que o [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] não estiver configurado corretamente.

 Possíveis causas:

- O arquivo web.config do aplicativo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] não define a depuração como “true” em (confira [Modo de depuração em aplicativos ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).

- Uma versão do [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] foi instalada depois que o Visual Studio foi instalado. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] deve ser instalado antes do Visual Studio. Para corrigir esse problema, use o **Painel de Controle, Programas e Recursos do Windows** para reparar a instalação do Visual Studio.

## <a name="see-also"></a>Consulte também
- [Erros e solução de problemas de depuração remota](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Depuração remota](../debugger/remote-debugging.md)