---
title: 'IDebugDocumentHost:: OnCreateDocumentContext | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.OnCreateDocumentContext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::OnCreateDocumentContext
ms.assetid: 080c8604-cfd7-484e-a337-15040870e683
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3fdfa64f66288cba47dec7c498db15238e55f954
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72569117"
---
# <a name="idebugdocumenthostoncreatedocumentcontext"></a>IDebugDocumentHost::OnCreateDocumentContext
Notifica o host de que um novo contexto de documento está sendo criado e permite que o host retorne opcionalmente um controle desconhecido para o novo contexto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT OnCreateDocumentContext(  
   IUnknown**  ppunkOuter  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppunkOuter`  
 fora Um objeto que controla o novo contexto.  
  
## <a name="return-value"></a>Valor retornado  
 O método retorna um `HRESULT`. Os possíveis valores incluem, mas sem limitação, aqueles na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`S_OK`|O método foi bem-sucedido.|  
|`E_NOTIMPL`|O host não fornece um objeto de controle.|  
  
## <a name="remarks"></a>Comentários  
 Esse método permite que o host adicione uma nova funcionalidade aos contextos de documento fornecidos pelo auxiliar. Esse método pode retornar **E_NOTIMPL** ou um objeto externo nulo; nesse caso, o chamador é responsável por criar o contexto.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugDocumentHost Interface](../../winscript/reference/idebugdocumenthost-interface.md)