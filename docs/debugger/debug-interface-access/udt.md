---
title: UDT | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SymTagUDT symbol
- user-defined type (UDT) symbol
- unions, as symbols
- UDT symbol
- structs [C++]
ms.assetid: f12459dd-c64d-4cc9-9ee3-a56e19e9e573
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab301f42891be063ccc6f6ae5476e060497efa21
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738457"
---
# <a name="udt"></a>UDT
Cada classe, estrutura e União é identificada por um símbolo de `SymTagUDT`. Cada membro, função, dados ou tipo aninhado, e cada classe base, aparece como um filho de classe do tipo definido pelo usuário (UDT).

## <a name="properties"></a>Propriedades
 A tabela a seguir mostra as propriedades válidas adicionais para esse tipo de símbolo.

|propriedade|Tipo de dados|Descrição|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Símbolo para a classe pai, se houver.|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID do símbolo pai da classe.|
|[IDiaSymbol::get_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE` se o UDT tiver um construtor.|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE` se o UDT estiver marcado como constante.|
|[IDiaSymbol::get_hasAssignmentOperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE` se o UDT tiver quaisquer operadores de atribuição definidos.|
|[IDiaSymbol::get_hasCastOperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE` se o UDT tiver qualquer operador de conversão definido.|
|[IDiaSymbol::get_hasNestedTypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE` se o UDT tiver definições de tipo aninhadas.|
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`LONGLONG`|O tamanho, em bytes, do UDT.|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Símbolo do [compiland](../../debugger/debug-interface-access/compiland.md)delimitador.|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID do símbolo pai léxico.|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|O nome do UDT.|
|[IDiaSymbol::get_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE` se o UDT estiver aninhado.|
|[IDiaSymbol::get_overloadedOperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE` se operadores sobrecarregados são definidos para o UDT.|
|[IDiaSymbol::get_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE` se o UDT estiver embalado.|
|[IDiaSymbol::get_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE` se o UDT aparece em um escopo léxico não global.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID do índice do símbolo.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Retorna `SymTagUDT` (um dos valores de [Enumeração SymTagEnum](../../debugger/debug-interface-access/symtagenum.md) ).|
|[IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|Indica se esta é uma estrutura, classe ou União; para obter detalhes, consulte [Enumeração UdtKind](../../debugger/debug-interface-access/udtkind.md).|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE` se o UDT não estiver alinhado.|
|[IDiaSymbol::get_virtualTableShape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|O tipo da tabela virtual.|
|[IDiaSymbol::get_virtualTableShapeId](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|ID do símbolo da forma da tabela virtual.|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE` se o UDT estiver marcado como volátil.|

## <a name="see-also"></a>Consulte também
- [Hierarquia de classes de tipos de símbolo](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)