---
title: Função CvInitProvider | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a97be63cd782397e984fd8dbce7da844efa07540
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62552661"
---
# <a name="cvinitprovider-function"></a>Função CvInitProvider
Inicializa o provedor de marcador. Deve ser chamada antes das outras funções do SDK da Visualização Simultânea.

## <a name="syntax"></a>Sintaxe

```C
HRESULT CvInitProvider(
   _In_ const GUID* pGuid,
   _Out_ PCV_PROVIDER* ppProvider
);
```

#### <a name="parameters"></a>parâmetros
 `pGuid` GUID do provedor. Não pode ser NULL.

 `ppProvider` Endereço de uma variável de saída que armazenará o contexto de provedor. Não pode ser NULL.

## <a name="return-value"></a>Valor retornado
 S_OK quando o provedor é inicializado com êxito ou código de erro no caso de erros. Use as macros SUCCEEDED/FAILED para verificar a condição de erro.

## <a name="requirements"></a>Requisitos
 **Cabeçalho:** *cvmarkers.h*

## <a name="see-also"></a>Confira também
- [Referência da biblioteca C++](../profiling/cpp-library-reference.md)