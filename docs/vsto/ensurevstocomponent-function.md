---
title: Função EnsureVSTOComponent
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f99ccb4cb76f942852716abf1fcb0c0f280decbd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797622"
---
# <a name="ensurevstocomponent-function"></a>Função EnsureVSTOComponent
  Essa API dá suporte à infraestrutura do Office e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```csharp
HRESULT EnsureVSTOComponent(
    IVSTProject *pProject
);
```

#### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*pProject*|Não use.|

## <a name="return-value"></a>Valor retornado
 Se a função obtiver êxito, retorna **S_OK**. Se a função falhar, ele retornará um código de erro.
