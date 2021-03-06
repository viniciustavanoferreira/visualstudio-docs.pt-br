---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 835e2cec19e36418091e094abd2ec76bd6403398
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72734837"
---
# <a name="vsg_default_run_filename"></a>VSG_DEFAULT_RUN_FILENAME
Define o nome de arquivo padrão do arquivo de log de gráficos.

## <a name="syntax"></a>Sintaxe

```C++
#define VSG_DEFAULT_FILENAME filename
```

#### <a name="parameters"></a>Parâmetros
 `filename` o nome de arquivo fornecido por padrão ao arquivo de log de gráficos quando as informações gráficas são capturadas programaticamente.

## <a name="value"></a>Valor
 Um literal de cadeia de caracteres que representa o nome de arquivo do arquivo de log de gráficos. Por padrão, L "default. vsglog".

```C++
#define VSG_DEFAULT_FILENAME L"default.vsglog"
```

## <a name="remarks"></a>Comentários
 Se o símbolo de pré-processador `DONT_SAVE_VSGLOG_TO_TEMP` for definido, o nome do arquivo será relativo ao diretório atual do aplicativo capturado, ou será um caminho absoluto; caso contrário, ele é relativo ao diretório de arquivos temporários do usuário e não pode ser um caminho absoluto.

 Para alterar o nome de arquivo definido, você deve redefini-lo antes de incluir `vsgcapture.h` em seu programa.

## <a name="example"></a>Exemplo
 Este exemplo mostra como alterar o nome de arquivo padrão do arquivo de captura:

```C++
// Redefine the default capture filename before including vsgcapture.h
#define VSG_DEFAULT_FILENAME L"capture.vsglog"

#include <vsgcapture.h>
```

## <a name="see-also"></a>Consulte também
- [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)