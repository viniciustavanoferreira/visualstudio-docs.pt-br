---
title: Função CvCreateMarkerSeriesWithCodePageA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b7e540e56ce0e97ac2c6aa2e42012569f9e4f272
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62553065"
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>Função CvCreateMarkerSeriesWithCodePageA
Cria a série de marcador para determinado provedor e uma página de código especificada. Essa função pode ser usada para especificar a página de código explicitamente para o texto gravado por funções ANSI da API do marcador. Configurar a página de código pode ser útil caso o rastreamento seja capturado e então analisado em diferentes computadores com diferentes localidades/idiomas. Por padrão, a página de código retornada pela função GetACP() é usada.

## <a name="syntax"></a>Sintaxe

```C
HRESULT CvCreateMarkerSeriesWithCodePageA(
   _In_ PCV_PROVIDER pProvider,
   _In_ LPCSTR pSeriesName,
   _In_ UINT nTextCodePage,
   _Out_ PCV_MARKERSERIES* ppMarkerSeries
);
```

#### <a name="parameters"></a>parâmetros
 `pProvider` Objeto do provedor inicializado anteriormente por CvInitProvider. Não pode ser NULL.

 `pSeriesName` Nome da série de marcador. Não pode ser NULL, mas uma cadeia de caracteres vazia é permitida.

 `nTextCodePage` Página de código válida.

 `ppMarkerSeries` Endereço de uma variável de saída que armazenará o contexto de série de marcador. Não pode ser NULL.

## <a name="return-value"></a>Valor retornado
 S_OK quando a série de marcador é criada com êxito ou código de erro no caso de erros. Use as macros SUCCEEDED/FAILED para verificar a condição de erro.

## <a name="requirements"></a>Requisitos
 **Cabeçalho:** *cvmarkers.h*

## <a name="see-also"></a>Confira também
- [Referência da biblioteca C++](../profiling/cpp-library-reference.md)