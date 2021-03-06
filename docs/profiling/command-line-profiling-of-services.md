---
title: Criação de perfil dos serviços de linha de comando | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling toos,services
- profiling services
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: b20835eaf8b81bd64bd90aa75d2efb32975a7c53
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74772825"
---
# <a name="command-line-profiling-of-services"></a>Linha de comando de criação de perfil de serviços
Esta seção descreve os procedimentos e as opções para coletar dados de desempenho para serviços Windows usando as Ferramentas de Criação de Perfil do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] na linha de comando.

> [!NOTE]
> Os recursos de segurança aprimorados no Windows 8 e no Windows Server 2012 exigiram alterações significativas na maneira como o criador de perfil do Visual Studio coleta dados nessas plataformas. Os aplicativos UWP também requerem novas técnicas de coleta. Consulte [ferramentas de desempenho em aplicativos windows 8 e Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="common-tasks"></a>Tarefas comuns

| Tarefa | Conteúdo relacionado |
| - | - |
| **Coletar estatísticas do aplicativo:** use o método de amostragem para coletar estatísticas de desempenho. Os dados de amostragem são úteis para analisar problemas de utilização de CPU e para entender as características de desempenho geral de um aplicativo. | -   [Coletar estatísticas do aplicativo usando amostragem](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md) |
| **Coletar dados de tempo detalhados:** use o método de instrumentação para coletar informações de tempo detalhadas. Os dados de instrumentação são úteis para analisar problemas de E/S e para análise refinada de cenários de aplicativo. | -   [Coletar dados de tempo detalhados usando a instrumentação](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md) |
| **Coletar dados de memória do .NET:** use a amostragem ou a instrumentação para coletar dados de alocação de memória do .NET que mostra o tamanho e o número de objetos alocados. Também é possível coletar dados de tempo de vida do objeto que mostram o tamanho e o número de objetos recuperados em cada geração de coleta de lixo. | -   [Coletar dados de memória .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md) |
| **Coletar dados de simultaneidade:** use o método de simultaneidade para coletar dados de contenção de recursos e dados de atividade do thread que mostram a utilização da CPU, contenção e migração de threads, atrasos na sincronização, áreas de ES sobrepostas e outros eventos do sistema. | -   [Coletar dados de concorrência](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md) |
| **Adicionar dados de interação de camada:** é possível adicionar dados de desempenho sobre chamadas ADO.NET síncronas que o serviço efetuou para um banco de dados [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] da Microsoft. | -   [Coletar dados de interação entre camadas](../profiling/adding-tier-interaction-data-from-the-command-line.md) |

## <a name="related-tasks"></a>Tarefas relacionadas

|Tarefa|Conteúdo relacionado|
|----------|---------------------|
|**Criar o perfil de aplicativos autônomos (clientes)**|-   [Aplicativos autônomos de perfil](../profiling/command-line-profiling-of-stand-alone-applications.md)|
|**Aplicativos ASP.NET do perfil**|-   [Criar o perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|
