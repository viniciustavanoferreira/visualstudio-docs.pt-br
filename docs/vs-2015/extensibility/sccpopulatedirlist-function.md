---
title: Função SccPopulateDirList | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6078f0fd90855c432b333fd5967367460d0a364e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200030"
---
# <a name="sccpopulatedirlist-function"></a>Função SccPopulateDirList
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Esta função determina quais diretórios e (opcionalmente) arquivos são armazenados no controle do código-fonte, dada uma lista de diretórios para examinar.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
SCCRTN SccPopulateDirList(  
   LPVOID        pContext,  
   LONG          nDirs,  
   LPCSTR*       lpDirPaths,  
   POPDIRLISTFUNCpfnPopulate,  
   LPVOID        pvCallerData,  
   LONG          fOptions  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 pContext  
 [in] O ponteiro de contexto de plug-in de controle do código-fonte.  
  
 nDirs  
 [in] Número de caminhos de diretório no `lpDirPaths` matriz.  
  
 lpDirPaths  
 [in] Matriz de caminhos de diretório para examinar.  
  
 pfnPopulate  
 [in] Função de retorno de chamada a ser chamada para cada caminho de diretório e (opcionalmente) no nome do arquivo `lpDirPaths` (consulte [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) para obter detalhes).  
  
 pvCallerData  
 [in] Valor a ser passados inalterados para a função de retorno de chamada.  
  
 fOptions  
 [in] Uma combinação de valores que controlam como os diretórios são processados (consulte a seção "PopulateDirList sinalizadores" [sinalizadores de bit usados por comandos específicos](../extensibility/bitflags-used-by-specific-commands.md) para possíveis valores).  
  
## <a name="return-value"></a>Valor de retorno  
 A implementação de plug-in de controle do código-fonte desta função deve retornar um dos seguintes valores:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|SCC_OK|A operação foi concluída com êxito.|  
|SCC_E_UNKNOWNERROR|Ocorreu um erro.|  
  
## <a name="remarks"></a>Comentários  
 Somente os diretórios e (opcionalmente) os nomes de arquivo que realmente estão no repositório de controle de origem são passados para a função de retorno de chamada.  
  
## <a name="see-also"></a>Consulte também  
 [Funções de API de plug-in de controle do código-fonte](../extensibility/source-control-plug-in-api-functions.md)   
 [Sinalizadores de bit usados por comandos específicos](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [Códigos de erro](../extensibility/error-codes.md)
