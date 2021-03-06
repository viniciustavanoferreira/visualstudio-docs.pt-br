---
title: 'Como: Por meio de programação listar arquivos usados recentemente pasta de trabalho'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 954a106b87d0ee941aa9c3a6c9c35579d1cb3d54
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812528"
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>Como: Por meio de programação listar arquivos usados recentemente pasta de trabalho
  O <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> propriedade retorna uma coleção que contém os nomes de todos os arquivos que aparecem na lista de arquivos usados recentemente o Microsoft Office Excel. O comprimento da lista varia dependendo do número de arquivos que o usuário tiver selecionado para manter. Você pode exibir os resultados em um intervalo.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-list-recently-used-workbooks-in-a-range-object"></a>Para pastas de trabalho de lista usada recentemente em um objeto de intervalo

1. Percorra a lista de arquivos recentes e exibir os nomes nas células relativo a um <xref:Microsoft.Office.Interop.Excel.Range> objeto.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]

## <a name="see-also"></a>Consulte também
- [Trabalhar com pastas de trabalho](../vsto/working-with-workbooks.md)
- [Controle NamedRange](../vsto/namedrange-control.md)
- [Parâmetros opcionais em soluções do Office](../vsto/optional-parameters-in-office-solutions.md)
