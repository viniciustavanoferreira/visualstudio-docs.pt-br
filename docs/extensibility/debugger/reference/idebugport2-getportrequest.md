---
title: IDebugPort2::GetPortRequest | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d48d39ea10e8425d5449444514489ac4b73c0a3f
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80725339"
---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
Obtém a descrição de uma porta que foi usada anteriormente para criar a porta (se disponível).

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetPortRequest( 
   IDebugPortRequest2** ppRequest
);
```

```csharp
int GetPortRequest( 
   out IDebugPortRequest2 ppRequest
);
```

## <a name="parameters"></a>parâmetros
`ppRequest`\
[fora] Retorna um objeto [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) representando a solicitação usada para criar a porta.

## <a name="return-value"></a>Valor retornado
 Se for `S_OK`bem sucedido, retorna; caso contrário, retorna um código de erro.  Retorna `E_PORT_NO_REQUEST` se uma porta não foi criada usando uma solicitação de porta [IDebugPortRequest2.](../../../extensibility/debugger/reference/idebugportrequest2.md)

## <a name="see-also"></a>Confira também
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)
- [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)
