---
title: 'Método IJsDebugProcess:: CreateBreakpoint | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugProcess.CreateBreakPoint
apilocation:
- jscript9diag.dll
ms.assetid: a2cb4233-2846-4d11-aa13-21de43abda9f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b0a4d595a11dc54829c467a0aace9601042fa08
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575091"
---
# <a name="ijsdebugprocesscreatebreakpoint-method"></a>Método IJsDebugProcess::CreateBreakPoint
Define o ponto de interrupção na posição do documento especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT CreateBreakPoint(  
   UINT64 documentId,  
   DWORD characterOffset,  
   DWORD characterCount,  
   BOOL isEnabled,  
   IJsDebugBreakPoint **ppDebugBreakPoint  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `documentId`  
 no Ponteiro para IDebugDocumentText.  
  
 `characterOffset`  
 no Deslocamento de caractere do início do arquivo.  
  
 `characterCount`  
 no Comprimento do texto do documento no qual o ponto de interrupção deve ser inserido.  
  
 `isEnabled`  
 no Especifica se o ponto de interrupção está habilitado.  
  
 `ppDebugBreakPoint`  
 fora Objeto que representa o ponto de interrupção que foi criado.  
  
## <a name="return-value"></a>Valor retornado  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** jscript9diag. h  
  
## <a name="see-also"></a>Consulte também  
 [Interface IJsDebugProcess](../../winscript/reference/ijsdebugprocess-interface.md)