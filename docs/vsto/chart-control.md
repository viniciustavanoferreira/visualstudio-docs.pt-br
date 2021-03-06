---
title: Controle de gráfico
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.ExcelChart
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], events
- Chart control [Office development in Visual Studio]
- Chart control [Office development in Visual Studio], data binding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 864422aac695fbf474e6ed6b8cf6d765247eabf9
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255298"
---
# <a name="chart-control"></a>Controle de gráfico
  O <xref:Microsoft.Office.Tools.Excel.Chart> controle é um objeto de gráfico que expõe eventos. Quando você adiciona um gráfico a uma planilha, o Visual Studio cria <xref:Microsoft.Office.Tools.Excel.Chart> um objeto que você pode programar diretamente sem precisar atravessar o Microsoft Office modelo de objeto do Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="create-the-control"></a>Criar o controle
 Você pode adicionar <xref:Microsoft.Office.Tools.Excel.Chart> controles a uma Microsoft Office planilha do Excel em tempo de design ou em tempo de execução em um projeto de nível de documento.

 Você pode adicionar <xref:Microsoft.Office.Tools.Excel.Chart> controles a uma planilha em tempo de execução em um suplemento do VSTO. Para obter mais informações, confira [Como: Adicione controles de gráfico a planilhas](../vsto/how-to-add-chart-controls-to-worksheets.md).

> [!NOTE]
> Objetos de gráfico criados dinamicamente não são persistidos na planilha como controles de host quando a planilha é fechada. Para obter mais informações, consulte [Adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md).

## <a name="formatting"></a>Formatação
 Toda a formatação que pode ser aplicada a <xref:Microsoft.Office.Interop.Excel.Chart> um também pode ser aplicada a <xref:Microsoft.Office.Tools.Excel.Chart> um controle. Isso inclui bordas, fontes, tipo de gráfico, linhas de grade, legenda e rótulos de dados.

## <a name="events"></a>Eventos
 Os eventos a seguir estão disponíveis para <xref:Microsoft.Office.Tools.Excel.Chart> o controle:

- <xref:Microsoft.Office.Tools.Excel.Chart.ActivateEvent>

- <xref:Microsoft.Office.Tools.Excel.Chart.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.Chart.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.Chart.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.Chart.Calculate>

- <xref:Microsoft.Office.Tools.Excel.Chart.Deactivate>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.Chart.DragOver>

- <xref:Microsoft.Office.Tools.Excel.Chart.DragPlot>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseDown>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseMove>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseUp>

- <xref:Microsoft.Office.Tools.Excel.Chart.Resize>

- <xref:Microsoft.Office.Tools.Excel.Chart.SelectEvent>

- <xref:Microsoft.Office.Tools.Excel.Chart.SeriesChange>

## <a name="see-also"></a>Consulte também
- [Exemplos e orientações de desenvolvimento do Office](../vsto/office-development-samples-and-walkthroughs.md)
- [Estenda documentos do Word e pastas de trabalho do Excel em suplementos do VSTO em tempo de execução](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Controles em documentos do Office](../vsto/controls-on-office-documents.md)
- [Adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Automatizar o Excel usando objetos estendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Como: Adicionar controles de gráfico a planilhas](../vsto/how-to-add-chart-controls-to-worksheets.md)
- [Associar dados a controles em soluções do Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
