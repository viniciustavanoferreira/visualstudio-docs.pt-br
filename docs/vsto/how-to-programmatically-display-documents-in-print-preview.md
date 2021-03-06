---
title: 'Como: Exibir documentos em Visualizar impressão programaticamente'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], displaying documents in print preview
- documents [Office development in Visual Studio], displaying in print preview
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d8296d28e884c746e09b427914af02213bbbaa7e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62813030"
---
# <a name="how-to-programmatically-display-documents-in-print-preview"></a>Como: Exibir documentos em Visualizar impressão programaticamente
  Se sua solução gera um relatório, você talvez queira exibir o relatório para o usuário no modo de visualização de impressão.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="procedures-for-document-level-customizations"></a>Procedimentos para personalizações no nível do documento

### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>Para exibir um documento em Visualizar impressão chamando o método PrintPreview

1. Chame o <xref:Microsoft.Office.Tools.Word.Document.PrintPreview%2A> método da <xref:Microsoft.Office.Tools.Word.Document> classe. Para usar este exemplo de código, executá-la na `ThisDocument` classe em seu projeto.

     [!code-vb[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#13)]

### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>Para exibir um documento em Visualizar impressão, definindo a propriedade PrintPreview

1. Defina a <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> propriedade do <xref:Microsoft.Office.Interop.Word.Application> do objeto para **true**.

     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]

## <a name="procedures-for-vsto-add-ins"></a>Procedimentos para suplementos VSTO

### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>Para exibir um documento em Visualizar impressão chamando o método PrintPreview

1. Chame o <xref:Microsoft.Office.Interop.Word._Document.PrintPreview%2A> método da <xref:Microsoft.Office.Interop.Word.Document> que você deseja visualizar. Para usar este exemplo de código, executá-la na `ThisAddIn` classe em seu projeto.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#13)]

### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>Para exibir um documento em Visualizar impressão, definindo a propriedade PrintPreview

1. Defina a <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> propriedade do <xref:Microsoft.Office.Interop.Word.Application> do objeto para **true**.

     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]

## <a name="see-also"></a>Consulte também
- [Como: Imprimir documentos programaticamente](../vsto/how-to-programmatically-print-documents.md)
- [Como: Abrir documentos existentes programaticamente](../vsto/how-to-programmatically-open-existing-documents.md)
- [Como: Criar novos documentos programaticamente](../vsto/how-to-programmatically-create-new-documents.md)
