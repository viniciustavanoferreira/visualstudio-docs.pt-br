---
title: IDiaStackWalker | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2366c933bf072c295b29d06ff5610bd3735c0077
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741517"
---
# <a name="idiastackwalker"></a>IDiaStackWalker
Fornece métodos para fazer uma movimentação de pilha usando informações no arquivo. pdb.

## <a name="syntax"></a>Sintaxe

```
IDiaStackWalker: IUnknown
```

## <a name="methods-in-vtable-order"></a>Métodos em ordem vtable
A tabela a seguir mostra os métodos de `IDiaStackWalker`.

|Método|Descrição|
|------------|-----------------|
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|Recupera um enumerador de quadros de pilha para plataformas x86.|
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|Recupera um enumerador de quadro de pilha para um tipo de plataforma específico.|

## <a name="remarks"></a>Comentários
Essa interface é usada para obter uma lista de quadros de pilha para um módulo carregado. Cada um dos métodos é passado como um objeto [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) (implementado pelo aplicativo cliente) que fornece as informações necessárias para criar a lista de quadros de pilha.

## <a name="notes-for-callers"></a>Observações para chamadores
Essa interface é obtida chamando o método `CoCreateInstance` com o identificador de classe `CLSID_DiaStackWalker` e a ID de interface de `IID_IDiaStackWalker`. O exemplo mostra como essa interface é obtida.

## <a name="example"></a>Exemplo
Este exemplo mostra como obter a interface `IDiaStackWalker`.

```C++

IDiaStackWalker* pStackWalker;
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,
                              NULL,
                              CLSCTX_INPROC_SERVER,
                              IID_IDiaStackWalker,
                              (void**) &pStackWalker);
if (FAILED(hr))
{
    // Report error and exit
}
```

## <a name="requirements"></a>Requisitos
Cabeçalho: dia2. h

Biblioteca: diaguids. lib

DLL: msdia80.dll

## <a name="see-also"></a>Consulte também
- [Interfaces (SDK de Acesso à Interface de Depuração)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
