---
title: IEnumDebugPorts2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPorts2::Reset
helpviewer_keywords:
- IEnumDebugPorts2::Reset
ms.assetid: 67da406c-eadb-421e-ae12-e26e9866f262
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6247e48af98f5c21a0afc40577e18d38bba06506
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80716188"
---
# <a name="ienumdebugports2reset"></a>IEnumDebugPorts2::Reset
Redefine a enumeração para o primeiro elemento.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>Valor retornado
 Se for `S_OK`bem sucedido, retorna; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 Depois que este método é chamado, a próxima chamada para o método [Next](../../../extensibility/debugger/reference/ienumdebugports2-next.md) retorna o primeiro elemento da enumeração.

## <a name="see-also"></a>Confira também
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)
