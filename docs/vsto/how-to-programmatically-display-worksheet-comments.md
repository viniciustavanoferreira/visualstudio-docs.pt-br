---
title: 'Como: Exibir comentários em planilhas de forma programática'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, comments
- comments, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: cc030fed25409f5c034abfd07f1f9358bfea593b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812690"
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Como: Exibir comentários em planilhas de forma programática
  Programaticamente, você pode mostrar e ocultar comentários em planilhas do Microsoft Office Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Para exibir todos os comentários em uma planilha em uma personalização no nível de documento

1. Definir a <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> propriedade para **verdadeiro** se você desejar mostrar comentários; caso contrário **false**. Esse código deve ser colocado em uma classe de folha, não no `ThisWorkbook` classe.

     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]

## <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Para exibir todos os comentários em uma planilha em um suplemento do VSTO do nível de aplicativo

1. Definir a <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> propriedade para **verdadeiro** se você desejar mostrar comentários; caso contrário **false**.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]

## <a name="see-also"></a>Consulte também
- [Trabalhar com planilhas](../vsto/working-with-worksheets.md)
- [Como: Programaticamente, adicionar e excluir comentários em planilhas](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)
- [Visão geral dos controles de host e de itens de host](../vsto/host-items-and-host-controls-overview.md)
