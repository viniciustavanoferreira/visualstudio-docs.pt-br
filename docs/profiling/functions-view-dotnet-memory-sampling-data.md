---
title: Exibição de Funções – Dados de Amostragem de Memória do .NET | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- dotnet
ms.openlocfilehash: cce13da0c2dfee61d70da8bc288d1f0ff4690deb
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74780033"
---
# <a name="functions-view---net-memory-sampling-data"></a>Exibição Funções – dados de amostragem de memória do .NET
A exibição Funções dos dados de criação de perfil de alocação de memória do .NET que foram coletados usando o método de amostragem lista as funções que alocaram a memória durante a execução da criação de perfil e reporta o tamanho e quantidade de alocações.

|Coluna|Descrição|
|------------|-----------------|
|**ID do Processo**|A ID de processo (PID) da criação de perfil.|
|**Nome do processo**|O nome do processo.|
|**Nome do módulo**|O nome do módulo que contém a função.|
|**Caminho do Módulo**|O demarcador do módulo que contém a função.|
|**Arquivo de origem**|O arquivo de origem que contém a definição dessa função.|
|**Nome da função**|O nome totalmente qualificado da função.|
|**Número de linha da função**|O número de linha do início dessa função no arquivo de origem.|
|**Endereço de função**|O endereço da função.|
|**Alocações Inclusivas**|O número total de objetos que foram alocados nessa função e suas funções filho.|
|**% de Alocações Inclusivas**|O percentual de todos os objetos que foram alocados na execução da criação de perfil que eram alocações inclusivas dessa função.|
|**Alocações Exclusivas**|O número de objetos criados quando a função estava executando diretamente na parte superior da pilha de chamadas. Esse número não inclui objetos criados em funções filho.|
|**% de Alocações Exclusivas**|O percentual de todos os objetos alocados na execução de criação de perfil que eram alocações exclusivas dessa função.|
|**Bytes Inclusivos**|O número de bytes da memória que foram alocados por esta função e suas funções filho.|
|**% de Bytes Inclusivos**|O percentual de todos os bytes de memória que foram alocados na execução de criação de perfil que eram bytes inclusivos dessa função.|
|**Bytes Exclusivos**|O número de bytes da memória que foram alocados por esta função, mas não por suas funções filho.|
|**% de Bytes Exclusivos**|O percentual de todos os bytes de memória que foram alocados na execução de criação de perfil que eram bytes exclusivos dessa função.|

## <a name="see-also"></a>Confira também
- [Exibição de funções - instrumentação](../profiling/functions-view-dotnet-memory-instrumentation-data.md)
- [Exibição de funções](../profiling/functions-view-sampling-data.md)
- [Exibição de funções](../profiling/functions-view-instrumentation-data.md)
