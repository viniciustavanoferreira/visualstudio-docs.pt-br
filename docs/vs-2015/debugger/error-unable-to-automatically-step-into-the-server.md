---
title: 'Erro: Não é possível intervir automaticamente no servidor | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- remote debugging, notification error
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8dcb8fa757f1cccf2f3aef6c2520e0c61da0b9f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682668"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Erro: Não é possível intervir no servidor automaticamente
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O erro é:  
  
 Não é possível realizar a depuração completa do servidor automaticamente. O depurador não foi notificado antes do procedimento remoto ter sido executado  
  
 Esse erro pode ocorrer quando você está tentando entrar em um serviço Web (confira [Entrar em um serviço Web XML](https://msdn.microsoft.com/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Pode ocorrer sempre que o [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] não estiver configurado corretamente.  
  
 Possíveis causas:  
  
- O arquivo web.config do aplicativo [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] não define a depuração como “true” em (confira [Modo de depuração em aplicativos ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
- Uma versão do [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] foi instalada depois que o Visual Studio foi instalado. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] deve ser instalado antes do Visual Studio. Para corrigir esse problema, use o Windows **painel de controle**, **programas e recursos** para reparar a instalação do Visual Studio.  
  
## <a name="see-also"></a>Consulte também  
 [Solução de problemas e erros de depuração remota](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Depuração remota](../debugger/remote-debugging.md)
