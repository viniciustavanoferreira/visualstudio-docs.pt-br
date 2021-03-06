---
title: IDiaDataSource | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 453be1d77f1d2b1759e3de4433225cf97d026054
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744915"
---
# <a name="idiadatasource"></a>IDiaDataSource
Inicia o acesso a uma fonte de símbolos de depuração.

## <a name="syntax"></a>Sintaxe

```
IDiaDataSource : IUnknown
```

## <a name="methods-in-vtable-order"></a>Métodos em ordem vtable
A tabela a seguir mostra os métodos de `IDiaDataSource`.

|Método|Descrição|
|------------|-----------------|
|[IDiaDataSource::get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|Recupera o nome do arquivo para o último erro de carregamento.|
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|Abre e prepara um arquivo de banco de dados do programa (. pdb) como uma fonte de dado de depuração.|
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|Abre e verifica se o arquivo de banco de dados do programa (. pdb) corresponde às informações de assinatura fornecidas; Prepara o arquivo. pdb como uma fonte de dados de depuração.|
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|Abre e prepara os dados de depuração associados ao arquivo. exe/. dll.|
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|Prepara os dados de depuração armazenados em um arquivo de banco de dados do programa (. pdb) acessado por meio de um fluxo de dados na memória.|
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|Abre uma sessão para consultar símbolos.|

## <a name="remarks"></a>Comentários
Uma chamada para um dos métodos Load da interface `IDiaDataSource` abre a origem do símbolo. Uma chamada bem-sucedida para o método [IDiaDataSource:: openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) retorna uma interface [IDiaSession](../../debugger/debug-interface-access/idiasession.md) que dá suporte à consulta à fonte de dados. Se o método Load retornar um erro relacionado ao arquivo, o valor de retorno do método [IDiaDataSource:: get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md) conterá o nome do arquivo associado ao erro.

## <a name="notes-for-callers"></a>Observações para chamadores
Essa interface é obtida chamando a função `CoCreateInstance` com o identificador de classe `CLSID_DiaSource` e a ID de interface de `IID_IDiaDataSource`. O exemplo mostra como essa interface é obtida.

## <a name="example"></a>Exemplo

```C++

      IDiaDataSource* pSource;
HRESULT hr = CoCreateInstance(CLSID_DiaSource,
                              NULL,
                              CLSCTX_INPROC_SERVER,
                              IID_IDiaDataSource,
                              (void**) &pSource);
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
