---
title: METADATA_ADDRESS_PARAM | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- METADATA_ADDRESS_PARAM
helpviewer_keywords:
- METADATA_ADDRESS_PARAM structure
ms.assetid: 90904f19-0e71-4cb3-a56e-6a2e92f66dfc
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a0319cfc6f2be817a25126e67cdc470bc727a4ca
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80714435"
---
# <a name="metadata_address_param"></a>METADATA_ADDRESS_PARAM
Esta estrutura representa um parâmetro de um método ou função.

## <a name="syntax"></a>Sintaxe

```cpp
typedef struct _tagMETADATA_ADDRESS_PARAM {
   _mdToken tokMethod;
   _mdToken tokParam;
   DWORD    dwIndex;
} METADATA_ADDRESS_PARAM;
```

```csharp
public struct METADATA_ADDRESS_PARAM {
   public int  tokMethod;
   public int  tokParam;
   public uint dwIndex;
}
```

## <a name="members"></a>Membros
 `tokMethod`\
 O ID do método do método do que o parâmetro faz parte.

 `tokParam`\
 A ID do parâmetro.

 `dwIndex`\
 O índice do parâmetro em uma lista de parâmetros.

## <a name="remarks"></a>Comentários
 Essa estrutura faz parte da união na [estrutura DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) quando o `dwKind` campo da `DEBUG_ADDRESS_UNION` estrutura é definido para `ADDRESS_KIND_PARAM` (um valor da enumeração [ADDRESS_KIND).](../../../extensibility/debugger/reference/address-kind.md)

## <a name="requirements"></a>Requisitos
 Cabeçalho: sh.h

 Namespace: Microsoft.VisualStudio.Debugger.Interop

 Montagem: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Confira também
- [Estruturas e uniões](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
- [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
