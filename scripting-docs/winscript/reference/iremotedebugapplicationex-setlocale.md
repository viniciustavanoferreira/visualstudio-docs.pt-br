---
title: 'IRemoteDebugApplicationEx: setlocale | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:SetLocale
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:SetLocale
ms.assetid: cd19f725-f4cd-453a-95e1-0bad676451da
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cc67e0ebd9ee2584985fa7d14073ba2694cbfa5
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575302"
---
# <a name="iremotedebugapplicationexsetlocale"></a>IRemoteDebugApplicationEx:SetLocale
Define o idioma para a localização do depurador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT SetLocale(  
   DWORD  dwLangID  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `dwLangID`  
 no A ID do idioma.  
  
## <a name="return-value"></a>Valor retornado  
 O método retorna um `HRESULT`. Os possíveis valores incluem, mas sem limitação, aqueles na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`S_OK`|O método foi bem-sucedido.|  
  
## <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Interface ISetNextStatement](../../winscript/reference/isetnextstatement-interface.md)