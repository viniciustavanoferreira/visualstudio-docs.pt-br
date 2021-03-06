---
title: 'IDebugExpressionContext:: GetLanguageInfo | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionContext.GetLanguageInfo
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext::GetLanguageInfo
ms.assetid: 35e25662-0b2a-4c3f-bce4-f01726bc04a8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e6dd3d3bb254cd91f411da3b6b587bc37c3a777
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576404"
---
# <a name="idebugexpressioncontextgetlanguageinfo"></a>IDebugExpressionContext::GetLanguageInfo
Retorna um nome e um GUID para o idioma que possui este contexto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT GetLanguageInfo(  
   BSTR*  pbstrLanguageName,  
   GUID*  pLanguageID  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pbstrLanguageName`  
 fora O nome do idioma.  
  
 `pLanguageID`  
 fora A ID exclusiva para o idioma.  
  
## <a name="return-value"></a>Valor retornado  
 O método retorna um `HRESULT`. Os possíveis valores incluem, mas sem limitação, aqueles na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`S_OK`|O método foi bem-sucedido.|  
  
## <a name="remarks"></a>Comentários  
 Esse método retorna um nome e um GUID para o idioma que possui esse contexto.  
  
## <a name="see-also"></a>Consulte também  
 [Interface IDebugExpressionContext](../../winscript/reference/idebugexpressioncontext-interface.md)