---
title: 'Como: Coletar dados de ETW (Rastreamento de Eventos para Windows) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
ms.assetid: aa2261fe-d5f5-49fc-a171-d18842e1dc7d
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9d113a32622c40c68a030fdbc670ec19c6038de2
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432813"
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>Como: Coletar o rastreamento de eventos para Windows (ETW) de dados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O ETW (Rastreamento de Eventos para Windows) é um recurso de rastreamento eficiente em nível de kernel que permite que o criador de perfil registre log de eventos de kernel ou de eventos definidos pelo aplicativo. Os dados coletados pelo provedor de eventos podem ser exibidos somente usando a opção /**Summary:ETW** da ferramenta de linha de comando [VSPerfReport](../profiling/vsperfreport.md). Você pode usar esse relatório para determinar o local em que ocorrem problemas de desempenho no aplicativo.  
  
 **Requisitos**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!NOTE]
> Os recursos de segurança aprimorados no Windows 8 e no Windows Server 2012 exigiram alterações significativas na maneira como o criador de perfil do Visual Studio coleta dados nessas plataformas. Os aplicativos da Windows Store também requerem novas técnicas de coleta. Consulte [Ferramentas de desempenho em aplicativos do Windows 8 e do Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-enable-event-trace-providers"></a>Para habilitar provedores de rastreamento de eventos  
  
1. No **Gerenciador de Desempenho**, clique com o botão direito do mouse na sessão de desempenho e, em seguida, clique em **Propriedades**.  
  
2. Nas **Páginas de Propriedades**, clique nas propriedades de **Eventos do Windows**.  
  
3. Na lista **Selecionar provedor de rastreamento de eventos do qual coletar dados**, selecione os provedores de eventos que você deseja usar para analisar seu aplicativo.  
  
## <a name="see-also"></a>Consulte também  
 [Configurando sessões de desempenho](../profiling/configuring-performance-sessions.md)
