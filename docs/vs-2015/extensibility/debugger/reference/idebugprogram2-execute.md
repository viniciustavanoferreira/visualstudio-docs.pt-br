---
title: IDebugProgram2::Execute | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgram2::Execute
helpviewer_keywords:
- IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f6134c10f30d66011dca5e40c28b6cbe6a7c94ed
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430560"
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Continua a execução deste programa de um estado parado. Qualquer estado de execução anterior (por exemplo, uma etapa) estiver desmarcado, e o programa inicia a execução novamente.  
  
> [!NOTE]
> Este método foi preterido. Use o [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md) método em vez disso.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Quando o usuário inicia a execução de um estado parado no thread do algum outro programa, este método é chamado neste programa. Esse método também é chamado quando o usuário seleciona o **inicie** comando da **depurar** menu no IDE. A implementação desse método pode ser tão simple quanto chamar o [retomar](../../../extensibility/debugger/reference/idebugthread2-resume.md) método no thread atual no programa.  
  
> [!WARNING]
> Não enviar um evento de interrupção ou um evento (síncrono) imediato [evento](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) ao manipular essa chamada; caso contrário, o depurador poderá parar de responder.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)
