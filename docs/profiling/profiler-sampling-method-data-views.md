---
title: Exibições de dados do método de amostragem do criador de perfil | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,sampling data views
- sampling data views
ms.assetid: 798de693-e43a-4056-aff5-48310c2172c5
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 8d845d84d421ca44f5b936df0a7138fefa848d8d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74772144"
---
# <a name="profiler-sampling-method-data-views"></a>Exibições de dados do método de amostragem do criador de perfil
Esta seção contém informações de referência sobre as exibições e os relatórios dos arquivos de dados do criador de perfil que foram gerados por método de amostragem.

> [!NOTE]
> Os recursos de segurança aprimorados no Windows 8 e no Windows Server 2012 exigiram alterações significativas na maneira como o criador de perfil do Visual Studio coleta dados nessas plataformas. Os aplicativos UWP também requerem novas técnicas de coleta. Consulte [Ferramentas de desempenho em aplicativos do Windows 8 e do Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="in-this-section"></a>Nesta seção
- [Exibição resumida](../profiling/summary-view-sampling-data.md)

 Lista as funções que foram executadas com mais frequência quando os exemplos foram coletados e as funções que estavam executando o trabalho mais individual.

- [Modo de exibição de árvore de chamadas](../profiling/call-tree-view-sampling-data.md)

 Exibe os caminhos de execução das funções em uma árvore hierárquica.

- [Visualização de módulos](../profiling/modules-view-sampling-data.md)

 Organiza os dados de criação de perfil por módulo e lista as funções, as linhas de código-fonte e as instruções que estavam em execução quando os exemplos foram coletados.

- [Visualização de chamada / Callee - Dados de amostragem](../profiling/caller-callee-view-sampling-data.md)

 Exibe os dados de criação de perfil para uma função selecionada e as funções que chamaram e foram chamadas pela função selecionada.

- [Visualização de funções](../profiling/functions-view-sampling-data.md)

 Organiza a criação de perfil por função e lista as funções que estavam em execução quando os exemplos foram coletados.

- [Visualização de linhas](../profiling/lines-view-sampling-data.md)

 Lista as linhas de código-fonte que estavam em execução quando os exemplos foram coletados.

- [Exibição ponteiros de instrução (IPs)](../profiling/instruction-pointers-ips-view-sampling-data.md)

 Lista as linhas de código-fonte que estavam em execução quando os exemplos foram coletados.

## <a name="reference"></a>Referência
- [Exibição de processos](../profiling/process-view.md)

 Lista o processo e as horas final e inicial do thread.

- [Exibição de marcas](../profiling/marks-view.md)

 Lista ETW e eventos de amostragem inseridos em um arquivo de dados de criação de perfil.

- [Exibição de detalhes da função](../profiling/function-details-view.md)

 Exibe um gráfico da relação entre uma função selecionada e as funções que chamaram e foram chamadas pela função selecionada.

## <a name="related-sections"></a>Seções relacionadas
- [Visualizações de dados do método de instrumentação](../profiling/instrumentation-method-data-views.md)

 As informações de referência sobre as exibições e os relatórios dos arquivos de dados do criador de perfil que foram gerados usando o método de instrumentação.

- [Exibições de dados de memória .NET](../profiling/dotnet-memory-data-views.md)

 Informações de referência sobre as exibições e relatórios de arquivos de dados do criador de perfil que incluem dados de memória do .NET.

## <a name="see-also"></a>Confira também
- [Noções básicas sobre valores de dados de amostragem](../profiling/understanding-sampling-data-values.md)
