---
title: Introdução (debug interface Access SDK) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2dd6a98f377ba295d6a866c9db95671de4ff16ea
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745099"
---
# <a name="getting-started-debug-interface-access-sdk"></a>Guia de Introdução (SDK de Acesso à Interface de Depuração)
O SDK de acesso à interface de depuração (DIA) fornece documentação de instruções e um exemplo que ilustra como usar a API de DIA. Use as interfaces e métodos no DIA SDK para desenvolver aplicativos personalizados que abrem os arquivos. PDB e. dbg e pesquisem o conteúdo de símbolos, valores, atributos, endereços e outras informações de depuração. Esse SDK também fornece tabelas de referência para as propriedades associadas a símbolos encontrados C++ em aplicativos.

 Para usar melhor o DIA SDK, você deve estar familiarizado com o seguinte:

- C++linguagem de programação

- Programação COM

- IDE (ambiente de desenvolvimento integrado) do Visual Studio para compilar os exemplos

  O DIA SDK normalmente é instalado com o Visual Studio e seu local padrão é *[unidade]* \Program Files\Microsoft Visual Studio 9.0 \ dia SDK. Como parte da instalação, o msdia90. dll, que implementa o DIA SDK, é registrado automaticamente, de modo que tudo o que você precisa fazer para usá-lo é incluir `dia2.h` em seu programa e vincular a `diaguids.lib`.

  Cabeçalho: include\dia2.h

  Library: lib\diaguids.lib

  DLL: bin\msdia80.dll

  IDL: idl\dia2.idl

## <a name="in-this-section"></a>Nesta seção

[Visão Geral](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)

Revisa a arquitetura básica do DIA.

[Consultando o arquivo .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)

Fornece instruções passo a passo sobre como usar a API do DIA para consultar um arquivo. pdb.

## <a name="see-also"></a>Consulte também

- [SDK de Acesso à Interface de Depuração](../../debugger/debug-interface-access/debug-interface-access-sdk.md)