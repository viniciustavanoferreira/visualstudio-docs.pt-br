---
title: IEnumDebugModules2::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2::Skip
helpviewer_keywords:
- IEnumDebugModules2::Skip
ms.assetid: 61dc42f4-8544-45bb-8da0-fb22cccec7da
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 02111475e7757eb91b1d55963e6175208747806f
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80716471"
---
# <a name="ienumdebugmodules2skip"></a>IEnumDebugModules2::Skip
Pula o número especificado de elementos.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT Skip(
   ULONG celt
);
```

```csharp
int Skip(
   uint celt
);
```

## <a name="parameters"></a>parâmetros
`celt`\
[em] Número de elementos para pular.

## <a name="return-value"></a>Valor retornado
 Se for bem-sucedido, retornará `S_OK`. `S_FALSE` Retornos `celt` se for maior do que o número de elementos restantes; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários
 Se `celt` especificar um valor maior do que o número de elementos `S_FALSE` restantes, a enumeração é definida até o final e é devolvida.

## <a name="see-also"></a>Confira também
- [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)
