---
title: Função CvWriteFlag | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvWriteFlagExVA
- cvmarkers/CvWriteFlagExW
- cvmarkers/CvWriteFlagExVW
- cvmarkers/CvWriteFlagExA
helpviewer_keywords:
- CvWriteFlagExW method
- CvWriteFlagExVA method
- CvWriteFlagExA method
- CvWriteFlagExVW method
ms.assetid: ee9da1e2-7b34-4cba-81e2-215d25d32e4d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3a5a388c8f838f182d2f1f3d3f56f84b8fbf10e6
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62936674"
---
# <a name="cvwriteflag-function"></a>Função CvWriteFlag
Grava um sinalizador para o arquivo de rastreamento da Visualização Simultânea.

## <a name="syntax"></a>Sintaxe

```C
HRESULT CvWriteFlagExW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCWSTR pMessage,
    ...
    );

HRESULT CvWriteFlagExA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCSTR pMessage,
    ...
    );

HRESULT CvWriteFlagExVW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCWSTR pMessage,
    _In_ va_list argList);

HRESULT CvWriteFlagExVA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCSTR pMessage,
    _In_ va_list argList);
```

#### <a name="parameters"></a>parâmetros
 `argList` Lista de argumentos.

 `category` Categoria.

 `level` Nível de prioridade.

 `pMarkerSeries` Contexto de série de marcador válido. Não pode ser NULL.

 `pMessage` Cadeia de formato da mensagem. Não pode ser NULL.

## <a name="return-value"></a>Valor retornado
 S_OK quando a mensagem é gravada com êxito. Código de erro em caso de erros. Use as macros SUCCEEDED/FAILED para verificar a condição de erro.

## <a name="requirements"></a>Requisitos
 **Cabeçalho:** *cvmarkers.h*

 **Unicode:** CvWriteFlagExW, CvWriteFlagExVW

 <strong>ANSI:</strong>CvWriteFlagExA, CvWriteFlagExVA

## <a name="see-also"></a>Confira também
- [Referência da biblioteca C++](../profiling/cpp-library-reference.md)