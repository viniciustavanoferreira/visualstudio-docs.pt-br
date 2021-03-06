---
title: Interface IDebugSessionProvider | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe73901d92cb42675ff9ec981bd9b90dcca5d546
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979042"
---
# <a name="idebugsessionprovider-interface"></a>Interface IDebugSessionProvider
A principal interface fornecida por um depurador IDE para habilitar o host e o idioma iniciou a depuração. Ele estabelece uma sessão de depuração para um aplicativo em execução. Essa interface é implementada pelo Gerenciador de depuração de máquina.  
  
 Além dos métodos herdados de `IUnknown`, o `IDebugSessionProvider` interface expõe os métodos a seguir.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
  
|Método|Descrição|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|Inicia uma sessão de depuração com o aplicativo especificado.|