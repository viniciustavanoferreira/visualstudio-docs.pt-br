---
title: Depurar versões de funções de alocação de heap | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.crt
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- debugging [CRT], heap allocation functions
- debugging memory leaks, CRT debug library functions
- malloc function
- memory leaks, CRT debug library functions
- heap allocation, debug
- _malloc_dbg function
ms.assetid: 91748bdc-f4cd-4d8b-ab98-0493dab7ed0d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0fde776e9f2bd48aca92c7ba6d7f1fe1e23f01a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738366"
---
# <a name="debug-versions-of-heap-allocation-functions"></a>Versões de depuração das funções de alocação da pilha
A biblioteca em tempo de execução C contém versões especiais de depuração das funções de alocação do heap. Essas funções têm os mesmos nomes que as versões com o _dbg anexado a elas. Este tópico descreve as diferenças entre a versão de lançamento de uma função CRT e a versão de _dbg, usando `malloc` e `_malloc_dbg` como exemplos.

 Quando [_DEBUG](/cpp/c-runtime-library/debug) é definido, o CRT mapeia todas as chamadas de [malloc](/cpp/c-runtime-library/reference/malloc) para [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg). Consequentemente, você não precisa reescrever seu código usando `_malloc_dbg` em vez de `malloc` para receber os benefícios durante a depuração.

 No entanto, talvez você queira chamar explicitamente `_malloc_dbg`. Chamar `_malloc_dbg` explicitamente tem alguns benefícios adicionais:

- Acompanhar alocações de tipo `_CLIENT_BLOCK`.

- Armazenar o arquivo de origem e o número da linha em que a solicitação de alocação ocorreu.

  Se você não quiser converter suas chamadas de `malloc` para `_malloc_dbg`, poderá obter as informações do arquivo de origem definindo [_CRTDBG_MAP_ALLOC](/cpp/c-runtime-library/crtdbg-map-alloc), o que faz com que o pré-processador mapeie diretamente todas as chamadas para `malloc` para `_malloc_dbg` em vez de depender de um wrapper ao contrário `malloc`.

  Para controlar os tipos separados de alocações em blocos do cliente, você deverá chamar `_malloc_dbg` diretamente e definir o parâmetro `blockType` como `_CLIENT_BLOCK`.

  Quando _DEBUG não está definido, as chamadas para `malloc` não são incomodadas, chamadas para `_malloc_dbg` são resolvidas para `malloc`, a definição de [_CRTDBG_MAP_ALLOC](/cpp/c-runtime-library/crtdbg-map-alloc) é ignorada e as informações do arquivo de origem pertencentes à solicitação de alocação não são fornecidas. Como `malloc` não tem um parâmetro de tipo de bloco, as solicitações para tipos de `_CLIENT_BLOCK` são tratadas como alocações padrão.

## <a name="see-also"></a>Consulte também

- [Técnicas de depuração CRT](../debugger/crt-debugging-techniques.md)