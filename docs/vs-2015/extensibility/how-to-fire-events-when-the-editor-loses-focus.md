---
title: 'Como: Disparar eventos quando o Editor perde o foco | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2ebca733798636ca32787b88b8874c31a2ffffdb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204202"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>Como: Disparar eventos quando o Editor perder o foco
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Às vezes, é necessário saber quando um editor perde o foco no quadro de janela. Por exemplo, talvez seja necessário extrair o código de uma janela de código depois que o editor não está mais focalizado nele. O procedimento a seguir fornece as etapas a seguir para receber notificações do editor de perder o foco.  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>Para disparar um evento em resposta a um editor de perder o foco  
  
1. Monitorar eventos de seleção, obtendo uma <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> do objeto de <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>.  
  
2. Chame <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> e forneça-o seu <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> objeto.  
  
3. Em sua chamada para <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>, procure `elementid==SEID_WindowFrame`.  
  
4. Teste o `varValueNew` parâmetro por duas coisas:  
  
    1. O quadro de janela que você está procurando.  
  
    2. O ponto em que seu programa perde a seleção para esse quadro de janela.
