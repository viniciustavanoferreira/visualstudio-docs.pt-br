---
title: Enumeração JS_PROPERTY_MEMBERS | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JS_PROPERTY_MEMBERS
apilocation:
- jscript9diag.dll
ms.assetid: 3b870e5c-5518-4073-8384-f0c9c1777d9e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3645e95859e2c2b785e01c7ee9a3cbee8155138d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571721"
---
# <a name="js_property_members-enumeration"></a>Enumeração JS_PROPERTY_MEMBERS
Sinaliza para especificar o tipo de informação a ser retornada em uma solicitação para membros de um objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
enum JS_PROPERTY_MEMBERS{   JS_PROPERTY_MEMBERS_ALL = 0,   JS_PROPERTY_MEMBERS_ARGUMENTS = 1} JS_PROPERTY_MEMBERS;  
```  
  
## <a name="members"></a>Membros  
  
### <a name="values"></a>Valores  
  
|Name|Descrição|  
|----------|-----------------|  
|`JS_PROPERTY_MEMBERS_ALL`|Representa uma solicitação para enumerar todos os membros.|  
|`JS_PROPERTY_MEMBERS_ARGUMENTS`|Representa uma solicitação para enumerar somente argumentos.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** jscript9diag. h  
  
## <a name="see-also"></a>Consulte também  
 [Referência de interfaces de script do Windows](../../winscript/reference/windows-script-interfaces-reference.md)