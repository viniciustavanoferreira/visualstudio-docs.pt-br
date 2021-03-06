---
title: Constantes SCRIPTTHREADID | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- SCRIPTTHREADID
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTTHREADID
ms.assetid: 1df9940c-ad0c-42d8-96b9-6a6abe2382e6
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf1b23b191bda29b00bf29f482332301897f9f37
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575665"
---
# <a name="scriptthreadid-constants"></a>Constantes SCRIPTTHREADID
Usado para especificar o tipo de thread.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
typedef DWORD SCRIPTTHREADID;  
```  
  
## <a name="constants"></a>{1&gt;Constantes&lt;1}  
  
|Constante|Valor|Significado|  
|--------------|-----------|-------------|  
|SCRIPTTHREADID_CURRENT|0xFFFFFFFD|O thread atualmente em execução.|  
|SCRIPTTHREADID_BASE|0xFFFFFFFE|O thread base; ou seja, o thread no qual o mecanismo de script foi instanciado.|  
|SCRIPTTHREADID_ALL|0xFFFFFFFF|Todos os threads.|  
  
## <a name="remarks"></a>Comentários  
 O tipo de `SCRIPTTHREADID` é usado por `IActiveScript::GetCurrentScriptThreadID`, `IActiveScript::GetScriptThreadID`, `IActiveScript::GetScriptThreadState`e `IActiveScript::InterruptScriptThread`, mas as constantes só podem ser usadas por `IActiveScript::GetScriptThreadState` e `IActiveScript::InterruptScriptThread`.  
  
## <a name="see-also"></a>Consulte também  
 [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)   
 [IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)   
 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)