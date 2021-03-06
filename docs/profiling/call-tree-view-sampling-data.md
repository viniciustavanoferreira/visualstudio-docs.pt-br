---
title: Modo de exibição de árvore de chamadas – Dados de amostragem | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method,Call Tree view
- Call Tree view
ms.assetid: 5c4e8ec3-d0d3-485a-93bd-9060df4eb739
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 558cef408ceca48a55563ae31f2399da0e951b8e
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779747"
---
# <a name="call-tree-view---sampling-data"></a>Modo de exibição de árvore de chamadas – dados de amostragem
O modo de exibição de Árvore de Chamadas exibe os caminhos de execução de função que foram percorridos no aplicativo analisado.

> [!NOTE]
> Os recursos de segurança aprimorados no Windows 8 e no Windows Server 2012 exigiram alterações significativas na maneira como o criador de perfil do Visual Studio coleta dados nessas plataformas. Os aplicativos UWP também requerem novas técnicas de coleta. Consulte [Ferramentas de desempenho em aplicativos do Windows 8 e do Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

 A raiz da árvore é o ponto de entrada do aplicativo ou do componente. Cada nó da função lista todas as funções que ela chamou e os dados de desempenho sobre essas chamadas de função.

 Os valores no modo de exibição de Árvore de Chamadas são para as instâncias de função que foram chamadas pela função pai na árvore de chamadas. Valores de percentual são calculados comparando o valor de instância de função para o número total de amostras na execução de criação de perfil.

## <a name="highlight-the-execution-hot-path"></a>Realçar o afunilamento de execução
 O modo de exibição de Árvore de Chamada pode expandir e realçar o caminho de execução do processo ou da função que foram amostrados com mais frequência. Para exibir o caminho mais ativo, clique com o botão direito do mouse no processo ou função e clique em **Expandir caminho quente**.

## <a name="set-the-call-tree-root-node"></a>Configurar do nó raiz da árvore de chamadas
 Cada processo na execução de criação de perfil é exibido como um nó raiz. Para definir o nó inicial do modo de exibição de Árvore de Chamadas, clique com o botão direito do mouse no nó que você deseja definir como o nó inicial e selecione **Definir Raiz**.

 Ao definir o nó raiz, você elimina todas as outras entradas da visualização exceto a subárvore do nó selecionado. Para redefinir o nó raiz de volta para o nó original, clique com botão direito do mouse na janela Modo de Exibição de Árvore de Chamadas e selecione **Redefinir Raiz**.

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
|**Nível**|A profundidade dessa função na árvore de chamadas. Somente em relatórios de linha de comando [VSPerfReport](../profiling/vsperfreport.md).|
|**Amostras Exclusivas**|O número de amostras coletadas nessa função quando ela foi chamada pela função pai na árvore de chamadas. Esse número não inclui amostras coletadas em funções que foram chamadas pela função.|
|**% de Amostras Exclusivas**|O percentual de todas as amostras na execução de criação de perfil que eram amostras exclusivas dessa função quando ela foi chamada pela função pai na árvore de chamadas.|
|**Amostras Inclusivas**|O número de amostras coletadas nessa função quando ela foi chamada pela função pai na árvore de chamadas. Esse número inclui amostras coletadas em funções chamadas pela função.|
|**% de Amostras Inclusivas**|O percentual de todas as amostras na execução de criação de perfil que eram amostras inclusivas dessa função quando ela foi chamada pela função pai na árvore de chamadas.|

## <a name="see-also"></a>Confira também
- [Como personalizar as colunas de visualização de relatório](../profiling/how-to-customize-report-view-columns.md)
- [Modo de exibição de árvore de chamadas – dados de amostragem do criador de perfil](../profiling/call-Tree-view-sampling-data.md)
- [Modo de exibição de árvore de chamadas – amostragem](../profiling/call-tree-view-dotnet-memory-sampling-data.md)
- [Modo de exibição de árvore de chamadas – instrumentação](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)
- [Modo de exibição de árvore de chamadas](../profiling/call-tree-view-instrumentation-data.md)
