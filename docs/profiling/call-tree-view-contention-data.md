---
title: Modo de exibição de árvore de chamadas - Dados de contenção | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Call Tree view
ms.assetid: 9bd4bde2-2ca3-446c-9ccc-7421522e03ae
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: e91e231f72b006d2020c8b4d5d96c7e24fa1dd9c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779773"
---
# <a name="call-tree-view---contention-data"></a>Modo de exibição de árvore de chamadas - Dados de contenção
O modo de exibição de Árvore de Chamadas exibe os caminhos de execução de função que foram percorridos no aplicativo analisado. A raiz da árvore é o ponto de entrada do aplicativo ou do componente. Cada nó de função lista todas as funções que chamou, o número de vezes que a função foi bloqueada e por quanto tempo a função esteve bloqueada porque estava competindo por um recurso com outros threads ou processos.

 Os valores no modo de exibição de Árvore de Chamadas são para as instâncias de função que foram chamadas pela função pai na árvore de chamadas. Os percentuais são calculados ao comparar o valor da instância de função ao número total de contenções na execução da criação de perfil.

## <a name="highlight-the-execution-hot-path"></a>Realçar o afunilamento de execução
 O modo de exibição de árvore de chamadas pode expandir e realçar o caminho de execução do processo ou da função que criou a maior parte das contenções.

- Para exibir o caminho mais ativo, clique com o botão direito do mouse no processo ou na função e, em seguida, clique em **Expandir Afunilamento**.

## <a name="set-the-call-tree-root-node"></a>Configurar do nó raiz da árvore de chamadas
 Cada processo na execução de criação de perfil aparece como um nó raiz. Para definir o nó inicial do modo de exibição de Árvore de Chamadas, clique com o botão direito do mouse no nó que você deseja definir como o nó inicial e, em seguida, clique em **Definir Raiz**.

 Ao definir o nó raiz, você elimina todas as outras entradas da visualização, com exceção da subárvore do nó selecionado. Para redefinir o nó raiz de volta para o nó original, clique com botão direito do mouse na janela modo de exibição de Árvore de Chamadas e, em seguida, clique em **Redefinir Raiz**.

|Coluna|Descrição|
|------------|-----------------|
|**Tempo Bloqueado Exclusivo**|O tempo em que as instâncias dessa função nesse caminho de execução estiveram bloqueadas durante a execução da criação de perfil. O tempo não inclui o período de bloqueio de funções filho que foram chamadas pela função.|
|**% de Tempo Bloqueado Exclusivo**|O percentual de todo o tempo bloqueado na execução da criação de perfil que representou o tempo bloqueado exclusivo para essa função nesse contexto.|
|**Contenções Exclusivas**|O número de contenções que ocorreram em instâncias dessa função nesse caminho de execução. O número não inclui contenções de funções filho chamadas pela função.|
|**% de Contenções Exclusivas**|A porcentagem de todas as contenções na execução da criação de perfil que eram exclusivas das instâncias dessa função e foram chamadas pela função pai na árvore de chamada.|
|**Endereço de função**|O endereço da função.|
|**Nome da função**|O nome totalmente qualificado da função.|
|**Tempo Bloqueado Inclusivo**|O tempo total em que as instâncias dessa função nesse caminho de execução estiveram bloqueadas durante a execução da criação de perfil. O tempo inclui o período de bloqueio de funções filho chamadas pela função.|
|**% de Tempo Bloqueado Inclusivo**|O percentual de todo o tempo bloqueado na execução da criação de perfil que representou o tempo bloqueado inclusivo das instâncias dessa função nesse caminho de execução.|
|**Contenções Inclusivas**|O número total de contenções que bloquearam instâncias dessa função nesse caminho de execução. O número inclui as contenções de funções filho chamadas pela função.|
|**% de Contenções Inclusivas**|O percentual de todas as contenções na execução da criação de perfil que eram inclusivas das instâncias dessa função nesse caminho de execução.|
|**Nível**|O nível da função na árvore de chamadas. Somente em relatórios de linha de comando VSReport. Para obter mais informações, consulte [VSPerfReport](../profiling/vsperfreport.md).|
|**Número de linha da função**|O número de linha do início dessa função no arquivo de origem.|
|**Nome do módulo**|O nome do módulo que contém a função.|
|**Caminho do Módulo**|O demarcador do módulo que contém a função.|
|**ID do Processo**|A ID de processo (PID) da criação de perfil.|
|**Nome do processo**|O nome do processo.|
|**Arquivo de origem**|O arquivo de origem que contém a definição dessa função.|

## <a name="see-also"></a>Confira também
- [Como personalizar as colunas de visualização de relatório](../profiling/how-to-customize-report-view-columns.md)
- [Modo de exibição de árvore de chamadas](../profiling/call-tree-view.md)
- [Modo de exibição de árvore de chamadas – instrumentação](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)
- [Modo de exibição de árvore de chamadas – amostragem](../profiling/call-tree-view-dotnet-memory-sampling-data.md)
- [Modo de exibição de árvore de chamadas](../profiling/call-tree-view-instrumentation-data.md)
- [Modo de exibição de árvore de chamadas](../profiling/call-tree-view-sampling-data.md)
