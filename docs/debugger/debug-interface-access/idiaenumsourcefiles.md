---
title: IDiaEnumSourceFiles | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles interface
ms.assetid: 5c0779a6-a2ea-408a-90da-ebdecf2b83c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 091d2f5996d53341e57c5c1b2125609642a156eb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744021"
---
# <a name="idiaenumsourcefiles"></a>IDiaEnumSourceFiles
Enumera os vários arquivos de origem contidos na fonte de dados.

## <a name="syntax"></a>Sintaxe

```
IDiaEnumSourceFiles : IUnknown
```

## <a name="methods-in-vtable-order"></a>Métodos em ordem vtable
A tabela a seguir mostra os métodos de `IDiaEnumSourceFiles`.

|Método|Descrição|
|------------|-----------------|
|[IDiaEnumSourceFiles::get__NewEnum](../../debugger/debug-interface-access/idiaenumsourcefiles-get-newenum.md)|Recupera a versão `IEnumVARIANT Interface` deste enumerador.|
|[IDiaEnumSourceFiles::get_Count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)|Recupera o número de arquivos de origem.|
|[IDiaEnumSourceFiles::Item](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md)|Recupera um arquivo de origem por meio de um índice.|
|[IDiaEnumSourceFiles::Next](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md)|Recupera um número especificado de arquivos de origem na sequência de enumeração.|
|[IDiaEnumSourceFiles::Skip](../../debugger/debug-interface-access/idiaenumsourcefiles-skip.md)|Ignora um número especificado de arquivos de origem em uma sequência de enumeração.|
|[IDiaEnumSourceFiles::Reset](../../debugger/debug-interface-access/idiaenumsourcefiles-reset.md)|Redefine uma sequência de enumeração para o início.|
|[IDiaEnumSourceFiles::Clone](../../debugger/debug-interface-access/idiaenumsourcefiles-clone.md)|Cria um enumerador que contém o mesmo estado de enumeração que o enumerador atual.|

## <a name="remarks"></a>Comentários

## <a name="notes-for-callers"></a>Observações para chamadores
Obtenha essa interface chamando o método `QueryInterface` em um objeto [IDiaTable](../../debugger/debug-interface-access/idiatable.md) . Consulte o exemplo para obter detalhes.

## <a name="example"></a>Exemplo
Este exemplo mostra como obter a interface `IDiaEnumSourceFiles` da lista de tabelas em um objeto de sessão de DIA. Para obter um exemplo de acesso às informações do arquivo de origem, consulte a interface [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) .

```C++

IDiaEnumSourceFiles* GetEnumSourceFiles(IDiaSession *pSession)
{
    IDiaEnumSourceFiles * pUnknown    = NULL;
    REFIID                iid         = __uuidof(IDiaEnumSourceFiles);
    IDiaEnumTables*       pEnumTables = NULL;
    IDiaTable*            pTable      = NULL;
    ULONG                 celt        = 0;

    if (pSession->getEnumTables(&pEnumTables) != S_OK)
    {
        wprintf(L"ERROR - GetTable() getEnumTables\n");
        return NULL;
    }
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)
    {
        // There is only one table that matches the given iid
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);
        pTable->Release();
        if (hr == S_OK)
        {
            break;
        }
    }
    pEnumTables->Release();
    return pUnknown;
}
```

## <a name="requirements"></a>Requisitos
Cabeçalho: dia2. h

Biblioteca: diaguids. lib

DLL: msdia80.dll

## <a name="see-also"></a>Consulte também
- [Interfaces (SDK de Acesso à Interface de Depuração)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
