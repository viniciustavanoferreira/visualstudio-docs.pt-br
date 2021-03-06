---
title: COMPUTER_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COMPUTER_INFO structure
ms.assetid: 943085b2-f165-462d-9a4e-2086f0cdfff4
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 27794dff51646b72dbbfda81ead02e5206ade78b
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737659"
---
# <a name="computer_info"></a>COMPUTER_INFO
Descreve o computador no qual o depurador está sendo executado.

## <a name="syntax"></a>Sintaxe

```cpp
typedef struct tagCOMPUTER_INFO
{
    WORD wProcessorArchitecture;
    WORD wSuiteMask;
    DWORD dwOperatingSystemVersion;
} COMPUTER_INFO;
```

```csharp
public struct COMPUTER_INFO
{
    public ushort wProcessorArchitecture;
    public ushort wSuiteMask;
    public uint dwOperatingSystemVersion;
}
```

## <a name="members"></a>Membros
`wProcessorArchitecture`\
Identifica a arquitetura do microprocessador.

`wSuiteMask`\
Identifica a máscara da suíte.

`dwOperatingSystemVersion`\
Número da versão do sistema operacional.

## <a name="remarks"></a>Comentários
Essa estrutura é devolvida pelo método [GetComputerInfo.](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)

## <a name="requirements"></a>Requisitos
Cabeçalho: Msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Montagem: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Confira também
- [Estruturas e uniões](../../../extensibility/debugger/reference/structures-and-unions.md)
- [ObterInformações do Computador](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)
