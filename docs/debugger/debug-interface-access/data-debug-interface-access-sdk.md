---
title: Dados (debug interface Access SDK) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- global variables [C++], as symbols
- local variables [C++], as symbols
- class members [C++], as symbols
- Data symbol
ms.assetid: 0f17e96a-2e06-42c9-a877-3e5e670ee0ef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94e1be7a1809c52683be045f71fcc681a6b270a8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745295"
---
# <a name="data-debug-interface-access-sdk"></a>Data (SDK de Acesso à Interface de Depuração)
Todas as variáveis, como parâmetros, variáveis locais, variáveis globais e membros de classe, são identificadas por `SymTagData` símbolos. Os valores constantes (`LocIsConstant`) também são identificados com esse tipo.

## <a name="properties"></a>Propriedades
 A tabela a seguir mostra as propriedades que são válidas para esse tipo de símbolo.

|propriedade|Tipo de dados|Descrição|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Se for um campo, um dos valores da [Enumeração CV_access_e](../../debugger/debug-interface-access/cv-access-e.md).|
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Parte de deslocamento do local; para obter detalhes, consulte a [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Parte da seção do local; para obter detalhes, consulte a [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSymbol::get_addressTaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|`BOOL`|`TRUE` se o endereço de dados for referenciado por outro símbolo.|
|[IDiaSymbol::get_bitPosition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|`DWORD`|Posição do bit do local; para obter detalhes, consulte a [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md) (sem suporte no dia SDK v 8.0).|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Símbolo da classe, se for um campo de estrutura, União ou classe.|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID do símbolo pai da classe.|
|[IDiaSymbol::get_compilerGenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|`BOOL`|`TRUE` se os dados foram gerados pelo compilador.|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE` se os dados estiverem marcados como sendo constantes.|
|[IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|Um dos valores de [enumeração do datakind](../../debugger/debug-interface-access/datakind.md) .|
|[IDiaSymbol::get_isAggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|`BOOL`|`TRUE` se os dados fizerem parte de um tipo de dados agregado (somente no DIA SDK v 8.0 e posterior).|
|[IDiaSymbol::get_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|`BOOL`|`TRUE` se os dados foram divididos em uma agregação de vários símbolos (somente no DIA SDK v 8.0 e posterior).|
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Comprimento do campo de bits; para obter detalhes, consulte a [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Símbolo para o compiland, função ou bloco delimitador.|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID do símbolo pai léxico.|
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Qualquer um dos tipos de local permitidos; para obter detalhes, consulte [locais de símbolo](../../debugger/debug-interface-access/symbol-locations.md)|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|O nome da variável.|
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Deslocamento do conteúdo do registro; para obter detalhes, consulte a [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSymbol::get_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|`DWORD`|Registrar designador de local; para obter detalhes, consulte a [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md).|
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Posição relativa dos dados dentro de seu bloco.|
|[IDiaSymbol::get_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|`DWORD`|Obtém o número de slot dos dados.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID do índice do símbolo.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Retorna `SymTagData` (um dos valores de [Enumeração SymTagEnum](../../debugger/debug-interface-access/symtagenum.md) ).|
|[IDiaSymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|O token de metadados que representa os dados.|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Símbolo para o tipo de variável.|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID do símbolo de tipo de variável.|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE` se os dados estiverem desalinhados.|
|[IDiaSymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|O valor dos dados constantes.|
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Posição dos dados no executável.|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE` se os dados são marcados como voláteis.|

## <a name="see-also"></a>Consulte também
- [Enumeração CV_access_e](../../debugger/debug-interface-access/cv-access-e.md)
- [Enumeração DataKind](../../debugger/debug-interface-access/datakind.md)
- [Hierarquia lexical de tipos de símbolo](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
- [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md)
- [Locais de símbolos](../../debugger/debug-interface-access/symbol-locations.md)