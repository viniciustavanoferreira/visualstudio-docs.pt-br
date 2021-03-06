---
title: Interface IRemoteDebugApplicationEx | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplicationEx Interface
ms.assetid: 8e16164d-dbb2-4488-9507-25ae34f343dc
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab9e25a28ade1ac73b9e4837dae61e2d91f24c45
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788372"
---
# <a name="iremotedebugapplicationex-interface"></a>Interface IRemoteDebugApplicationEx
Representa um aplicativo em execução. Ele não precisa corresponder a um processo do sistema operacional. Normalmente, um depurador destina-se um aplicativo para depuração. O Gerenciador de depuração do processo normalmente implementa o objeto de aplicativo.  
  
 Além dos métodos herdados de `IUnknown`, o `IRemoteDebugApplicationEx` interface expõe os métodos a seguir.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
  
|Método|Descrição|  
|------------|-----------------|  
|[IRemoteDebugApplicationEx:GetHostPid](../../winscript/reference/iremotedebugapplicationex-gethostpid.md)|Retorna a ID de processo para o aplicativo host.|  
|GetHostMachineName|Retorna o nome do computador que o aplicativo host está sendo executado.|  
|[IRemoteDebugApplicationEx:SetLocale](../../winscript/reference/iremotedebugapplicationex-setlocale.md)|Define o idioma para a localização do depurador.|  
|[IRemoteDebugApplicationEx:ForceStepMode](../../winscript/reference/iremotedebugapplicationex-forcestepmode.md)|Força o depurador em modo de etapa única.|  
|[IRemoteDebugApplicationEx:RevokeBreak](../../winscript/reference/iremotedebugapplicationex-revokebreak.md)|Revoga um comando de interrupção.|  
|SetProxyBlanketAndAddRef|Atualiza as informações de segurança COM um proxy para um objeto de depurador a fim de garantir a compatibilidade com a depuração remota de sistemas operacionais baseados no Windows 95.|  
|ReleaseFromSetProxyBlanket|AddRef versões de SetProxyBlanketAndAddRef.|