---
title: Função CvReleaseMarkerSeries | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6bfa9952a834110ef0fea36568ea210b637547aa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68177748"
---
# <a name="cvreleasemarkerseries-function"></a>Função CvReleaseMarkerSeries
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Libera a série de marcador. Não use um objeto de série de marcador após a liberação; caso contrário, o aplicativo poderá falhar. A falha ao liberar a série de marcador causa uma perda de memória.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pMarkerSeries`  
 Endereço da variável de objeto do provedor. O endereço não pode ser NULL; a variável pode ter qualquer valor.  
  
## <a name="return-value"></a>Valor de retorno  
 S_OK quando a série de marcador é liberada com êxito ou código de erro no caso de erros. Use as macros SUCCEEDED/FAILED para verificar a condição de erro.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** cvmarkers.h  
  
## <a name="see-also"></a>Veja também  
 [Referência de biblioteca C++](../profiling/cpp-library-reference.md)
