---
title: IDebugEvent2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f663be5910b342a6adba5da0b84d7e0d80cacc10
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65695410"
---
# <a name="idebugevent2"></a>IDebugEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Essa interface é usada para comunicar informações de depuração essenciais, como interromper um ponto de interrupção e informações não-críticas, como uma mensagem de depuração.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Observações para implementadores  
 O mecanismo de depuração (DES) e o fornecedor de porta personalizada implementam essa interface no mesmo objeto, como todas as outras interfaces de evento.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 Usando a interface do argumento IID (ID) fornecido ao [evento](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) ou [evento](../../../extensibility/debugger/reference/idebugportevents2-event.md), o Gerenciador de sessão de depuração (SDM) chama [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) no `IDebugEvent2` interface para obter a interface de eventos apropriado.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
 A tabela a seguir mostra os métodos de `IDebugEvent2`.  
  
|Método|Descrição|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Obtém os atributos para este evento de depuração.|  
  
## <a name="remarks"></a>Comentários  
 Interfaces de evento mais específico, como [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), não derivam da interface IDebugEvent2, mas em vez disso, são implementados como uma interface separada no mesmo objeto como `IDebugEvent2`.  
  
## <a name="requirements"></a>Requisitos  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Principais Interfaces](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
