---
title: CaptureCurrentFrame | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9967d776845088e707035c7b1c56855ac80af82
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72736129"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
Captura o restante do quadro atual para o arquivo de log de gráficos.

## <a name="syntax"></a>Sintaxe

```C++
void CaptureCurrentFrame();
```

## <a name="remarks"></a>Comentários
 Se outra captura estiver em andamento, como uma captura que foi iniciada pela função `BeginCapture`, essa captura será concluída e registrada no log de gráficos como um quadro distinto. Imediatamente depois, o diagnóstico de gráficos começa a capturar o restante do quadro atual, que também é registrado como um quadro distinto. O fim do quadro atual é marcado por uma chamada para presente.

 Para capturar um quadro, você deve preparar seu aplicativo para capturar e gravar informações gráficas — ou seja, você deve ter chamado [init](init.md) por meio de uma instância da classe `VsgDbg` antes de chamar `CaptureCurrentFrame`.

## <a name="see-also"></a>Consulte também
- [Init](init.md)
- [BeginCapture](begincapture.md)