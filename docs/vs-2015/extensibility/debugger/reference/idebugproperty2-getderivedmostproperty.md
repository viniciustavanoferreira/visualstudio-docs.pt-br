---
title: IDebugProperty2::GetDerivedMostProperty | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fde68c090de11d6b479ea0587843a3d4a9d21f94
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164938"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
Obtém a propriedade mais derivado de uma propriedade.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT GetDerivedMostProperty ( 
   IDebugProperty2** ppDerivedMost
);
```

```csharp
int GetDerivedMostProperty ( 
   out IDebugProperty2 ppDerivedMost
);
```

#### <a name="parameters"></a>Parâmetros
 `ppDerivedMost`

 [out] Retorna um [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objeto que representa a propriedade mais derivado.

## <a name="return-value"></a>Valor de retorno
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retornará o código de erro. Retorna `S_GETDERIVEDMOST_NO_DERIVED_MOST` se não houver nenhuma propriedade mais derivado para recuperar.

## <a name="remarks"></a>Comentários
 Por exemplo, se esta propriedade descreve um objeto que implementa `ClassRoot` , mas o que é realmente uma instanciação de `ClassDerived` que é derivada de `ClassRoot`, em seguida, esse método retorna um [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objeto descrevendo o `ClassDerived` objeto.

## <a name="see-also"></a>Consulte também
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)