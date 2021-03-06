---
title: 'IDebugExpressionCallBack:: OnComplete | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionCallBack.onComplete
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugExpressionCallBack::onComplete
ms.assetid: d0b89db3-38e7-44e0-93fe-60205f9149dd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1fd142cc7ecbcd984be1943da05fa782260b10f8
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576417"
---
# <a name="idebugexpressioncallbackoncomplete"></a>IDebugExpressionCallBack::onComplete
Indica que a avaliação da expressão foi concluída.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT onComplete();  
```  
  
#### <a name="parameters"></a>Parâmetros  
 Esse método não usa parâmetros.  
  
## <a name="return-value"></a>Valor retornado  
 O método retorna um `HRESULT`. Os possíveis valores incluem, mas sem limitação, aqueles na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`S_OK`|O método foi bem-sucedido.|  
  
## <a name="remarks"></a>Comentários  
 Esse método é chamado quando a avaliação da expressão é concluída. O método `IDebugExpression::GetResultAsString` pode ser chamado de dentro deste manipulador de eventos.  
  
## <a name="see-also"></a>Consulte também  
 @No__t_1 de [interface IDebugExpressionCallBack](../../winscript/reference/idebugexpressioncallback-interface.md)  
 [IDebugExpression::GetResultAsString](../../winscript/reference/idebugexpression-getresultasstring.md)