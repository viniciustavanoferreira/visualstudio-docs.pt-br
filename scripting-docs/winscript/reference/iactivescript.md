---
title: IActiveScript | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScript interface
ms.assetid: d8acee11-7f0d-4999-b97a-66774af16f71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a33db2bcbcb356a508fec2e6bc5449a899a1299
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577245"
---
# <a name="iactivescript"></a>IActiveScript
Fornece os métodos necessários para inicializar o mecanismo de script. O mecanismo de script deve implementar a interface `IActiveScript`.  
  
## <a name="methods-in-vtable-order"></a>Métodos em ordem vtable  
  
|Método|Descrição|  
|------------|-----------------|  
|[IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md)|Informa o mecanismo de script do site [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) fornecido pelo host.|  
|[IActiveScript::GetScriptSite](../../winscript/reference/iactivescript-getscriptsite.md)|Recupera o objeto do site associado ao mecanismo de script do Windows.|  
|[IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md)|Coloca o mecanismo de script no estado especificado.|  
|[IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md)|Recupera o estado atual do mecanismo de script.|  
|[IActiveScript::Close](../../winscript/reference/iactivescript-close.md)|Faz com que o mecanismo de script abandone qualquer script carregado atualmente, perca seu estado e libere qualquer ponteiro de interface que tenha para outros objetos, inserindo assim um estado fechado.|  
|[IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)|Adiciona o nome de um item de nível raiz ao namespace do mecanismo de script.|  
|[IActiveScript::AddTypeLib](../../winscript/reference/iactivescript-addtypelib.md)|Adiciona uma biblioteca de tipos ao namespace para o script.|  
|[IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)|Recupera a interface `IDispatch` para o script em execução.|  
|[IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)|Recupera um identificador definido pelo mecanismo de script para o thread em execução no momento.|  
|[IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)|Recupera um identificador definido por mecanismo de script para o thread associado ao thread do Microsoft Win32 fornecido.|  
|[IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)|Recupera o estado atual de um thread de script.|  
|[IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)|Interrompe a execução de um thread de script em execução.|  
|[IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)|Clona o mecanismo de script atual (menos qualquer estado de execução atual), retornando um mecanismo de script carregado que não tem nenhum site no thread atual.|  
  
## <a name="see-also"></a>Consulte também  
 [Referência de interfaces de script do Windows](../../winscript/reference/windows-script-interfaces-reference.md)