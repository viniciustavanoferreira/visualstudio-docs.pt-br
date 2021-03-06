---
title: IDiaPropertyStorage::ReadMultiple | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 40cd84e00f2e6abea285368a6206c7400abf8877
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62538077"
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Leituras especificada de propriedades do conjunto de propriedade atual.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT ReadMultiple(   
   ULONG          cpspec,  
   PROPSPEC const rgpspec,  
   PROPVARIANT    rgvar  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `cpspec`  
 [in] Contagem de propriedades especificadas no `rgpspec` matriz. Se for zero, o método não retorna nenhuma propriedade, mas retornar `S_OK` como um código de êxito.  
  
 `rgpspec`  
 [in] Uma matriz de propriedades a serem lidos. Propriedades podem ser especificadas por uma ID de propriedade ou por um nome de cadeia de caracteres opcional. Não é necessário especificar as propriedades em uma ordem específica na matriz. A matriz pode conter propriedades duplicadas, resultando em valores de propriedade duplicados no retorno para propriedades simples. Propriedades simples não devem retornar o acesso negado em uma tentativa para abri-los em uma segunda vez. A matriz pode conter uma mistura de IDs de propriedade e IDs de cadeia de caracteres. Essa matriz deve ter pelo menos `cpspec` número de valores de propriedade.  
  
 `rgvar`  
 [no, out] Uma matriz de `PROPVARIANT` estruturas (no namespace Microsoft.VisualStudio.OLE.Interop) a ser preenchida com valores para cada propriedade. A matriz deve ser pelo menos `cpspec` elementos de tamanho. O chamador não precisar inicializar os valores na matriz.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`. Retorna `S_FALSE` se um ou mais das propriedades não foi encontrado. Caso contrário, retornará um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Se uma propriedade não foi encontrado, a entrada correspondente na `rgvar` matriz contém uma `VARIANT` com o tipo de `VT_EMPTY`.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
