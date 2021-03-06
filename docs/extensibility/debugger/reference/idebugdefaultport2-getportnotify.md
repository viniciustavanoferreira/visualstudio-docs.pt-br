---
title: IDebugDefaultPort2:GetPortNotify | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 670dd128e6962c1e1d12f81eea03f9759fa56621
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80732408"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
Este método obtém uma interface [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) para esta porta.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetPortNotify(
   IDebugPortNotify2** ppPortNotify
);
```

```csharp
int GetPortNotify(
   out IDebugPortNotify2 ppPortNotify
);
```

## <a name="parameters"></a>parâmetros
`ppPortNotify`\
[fora] Um objeto [IDebugPortNotify2.](../../../extensibility/debugger/reference/idebugportnotify2.md)

## <a name="return-value"></a>Valor retornado
 Se for `S_OK`bem sucedido, retorna; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 Normalmente, `QueryInterface` o método é chamado sobre o objeto que implementa a interface [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) para obter uma interface [IDebugPortNotify2.](../../../extensibility/debugger/reference/idebugportnotify2.md) No entanto, existem circunstâncias em que a interface desejada é implementada em um objeto diferente. Este método oculta essas circunstâncias `IDebugPortNotify2` e retorna a interface do objeto mais apropriado.

## <a name="see-also"></a>Confira também
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)
