---
title: Como coletar dados do contador do Windows | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: c85187fd54d61fdf40956c8aee3c0a222d95a313
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74776313"
---
# <a name="how-to-collect-windows-counter-data"></a>Como coletar dados do contador do Windows

Os contadores do Windows são contadores de desempenho do sistema que podem ser coletados em intervalos definidos durante a criação de perfil. Na exibição de Marcas do relatório das Ferramentas de Criação de Perfil, uma linha é rotulada **AutoMark** para cada intervalo de coleta. A linha contém colunas que descrevem os valores do contador de desempenho nesse intervalo. Para restringir a análise a um período de tempo entre duas marcas específicas, selecione as marcas, clique com o botão direito do mouse e selecione **Filtrar por** > **marcas** no menu de atalho.

> [!NOTE]
> Os recursos de segurança aprimorados no Windows 8 e no Windows Server 2012 exigiram alterações significativas na maneira como o criador de perfil do Visual Studio coleta dados nessas plataformas. Os aplicativos UWP também requerem novas técnicas de coleta. Consulte [Ferramentas de desempenho em aplicativos do Windows 8 e do Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="to-collect-windows-counter-data"></a>Para coletar dados do contador do Windows

1. No Gerenciador de Desempenho, clique com botão direito do mouse na sessão para a qual você deseja configurar os contadores do Windows e selecione **Propriedades**.

2. Nas **Páginas de Propriedades**, clique em **Contadores do Windows**.

3. Selecione a caixa de seleção **Coletar Contadores do Windows**.

4. Na caixa de texto **Intervalo de coleta (ms)**, digite um intervalo de tempo.

5. Selecione uma categoria da lista suspensa **Categoria de Contador**.

6. Selecione uma instância da lista suspensa de **Instância**.

7. Selecione os contadores que você deseja usar ao analisar seu aplicativo.

8. Clique em **Aplicar.**

## <a name="see-also"></a>Confira também

[Configure as sessões](../profiling/configuring-performance-sessions.md)
de desempenho[Propriedades de sessão de](../profiling/performance-session-properties.md)
desempenho[CPU e contadores do Windows](../profiling/cpu-and-windows-counters.md)
