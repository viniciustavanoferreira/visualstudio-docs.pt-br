---
title: IDiaDataSource::openSession | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4bec5507d15374e6e88afd4567d4b0fec9ca6cb7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198597"
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Abre uma sessão para consultar os símbolos.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 ppSession  
 [out] Retorna um [IDiaSession](../../debugger/debug-interface-access/idiasession.md) objeto que representa a sessão aberta.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro. A tabela a seguir mostra os possíveis valores retornados para esse método.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|E_UNEXPECTED|O [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) objeto anteriormente não foi inicializado com uma origem de símbolos.|  
|E_INVALIDARG|Parâmetro `ppSession` inválido.|  
|E_OUTOFMEMORY|Memória insuficiente para abrir a sessão.|  
  
## <a name="remarks"></a>Comentários  
 Este método abre uma [IDiaSession](../../debugger/debug-interface-access/idiasession.md) objeto para uma fonte de dados.  
  
 `IDiaSession` objetos de implementação de consultas na fonte de dados. Uma sessão gerencia um espaço de endereço para cada conjunto de símbolos de depuração. Se o arquivo. dll ou. .exe descrito pelos símbolos de fonte de dados estiver ativo no endereço vários intervalos (por exemplo, porque vários processos tem carregado) e uma sessão para cada intervalo de endereços deve ser usada.  
  
## <a name="example"></a>Exemplo  
  
```cpp#  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Visão geral](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Consultando o arquivo .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)
