---
title: IEnumDebugReferenceInfo2::Próximo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2::Next
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Next
ms.assetid: 70b31a57-1701-4757-9e7e-63ec60a71b3c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4bb10504b2dbe02856364baa0670a7c825ef80cd
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80715321"
---
# <a name="ienumdebugreferenceinfo2next"></a>IEnumDebugReferenceInfo2::Next
Retorna o próximo conjunto de elementos da enumeração.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT Next(
   ULONG                   celt,
   DEBUG_REFERENCE_INFO ** rgelt,
   ULONG*                  pceltFetched
);
```

```csharp
int Next(
   uint                   celt,
   DEBUG_REFERENCE_INFO[] rgelt,
   ref uint               pceltFetched
);
```

## <a name="parameters"></a>parâmetros
`celt`\
[em] O número de elementos para recuperar. Também especifica o tamanho `rgelt` máximo da matriz.

`rgelt`\
[dentro, fora] Matriz de elementos [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) a serem preenchidos.

`pceltFetched`\
[fora] Retorna o número de elementos realmente retornados em `rgelt`.

## <a name="return-value"></a>Valor retornado
 Se for bem-sucedido, retornará `S_OK`. Retornos `S_FALSE` se menos do que o número solicitado de elementos pode ser devolvido; caso contrário, retorna um código de erro.

## <a name="see-also"></a>Confira também
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)
