---
title: 'Como: Redimensionar controles NamedRange'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- NamedRange control, resizing
- ranges, resizing in Excel
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 80a7fd251d525541b6894c757d7acd148900047c
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252045"
---
# <a name="how-to-resize-namedrange-controls"></a>Como: Redimensionar controles NamedRange
  Você pode definir o tamanho de um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle ao adicioná-lo a um Microsoft Office documento do Excel; no entanto, talvez você queira redimensioná-lo posteriormente.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Você pode redimensionar um intervalo nomeado em tempo de design ou em tempo de execução em projetos de nível de documento. Você também pode redimensionar intervalos nomeados em tempo de execução em suplementos do VSTO no nível de aplicativo.

 Este tópico descreve as seguintes tarefas:

- [Redimensionar controles NamedRange em tempo de design](#designtime)

- [Redimensionar controles NamedRange em tempo de execução em um projeto de nível de documento](#runtimedoclevel)

- [Redimensionar controles NamedRange em tempo de execução em um projeto de suplemento do VSTO](#runtimeaddin)

## <a name="designtime"></a>Redimensionar controles NamedRange em tempo de design
 Você pode redimensionar um intervalo nomeado redefinindo seu tamanho na caixa de diálogo **definir nome** .

### <a name="to-resize-a-named-range-by-using-the-define-name-dialog-box"></a>Para redimensionar um intervalo nomeado usando a caixa de diálogo Definir nome

1. Clique com o botão <xref:Microsoft.Office.Tools.Excel.NamedRange> direito do mouse em um controle.

2. Clique em **gerenciar intervalos nomeados** no menu de atalho.

     A caixa de diálogo **definir nome** é exibida.

3. Selecione o intervalo nomeado que você deseja redimensionar.

4. Desmarque a caixa **refere-se a** .

5. Selecione as células que você deseja usar para definir o tamanho do intervalo nomeado.

6. Clique em **OK**.

## <a name="runtimedoclevel"></a>Redimensionar controles NamedRange em tempo de execução em um projeto de nível de documento
 Você pode redimensionar um intervalo nomeado programaticamente <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> usando a propriedade.

> [!NOTE]
> Na janela **Propriedades** , a <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> propriedade é marcada como somente leitura.

### <a name="to-resize-a-named-range-programmatically"></a>Para redimensionar um intervalo nomeado programaticamente

1. Crie um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle na célula **a1** de `Sheet1`.

     [!code-csharp[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#4)]

2. Redimensione o intervalo nomeado para incluir a célula **B1**.

     [!code-csharp[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#5)]

## <a name="runtimeaddin"></a>Redimensionar controles NamedRange em tempo de execução em um projeto de suplemento do VSTO
 Você pode redimensionar <xref:Microsoft.Office.Tools.Excel.NamedRange> um controle em qualquer planilha aberta em tempo de execução. Para obter mais informações sobre como adicionar um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle a uma planilha usando um suplemento do VSTO, consulte [como: Adicione controles NamedRange a planilhas](../vsto/how-to-add-namedrange-controls-to-worksheets.md).

### <a name="to-resize-a-named-range-programmatically"></a>Para redimensionar um intervalo nomeado programaticamente

1. Crie um <xref:Microsoft.Office.Tools.Excel.NamedRange> controle na célula **a1** de `Sheet1`.

     [!code-csharp[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#10)]
     [!code-vb[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#10)]

2. Redimensione o intervalo nomeado para incluir a célula **B1**.

     [!code-csharp[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#11)]
     [!code-vb[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#11)]

## <a name="see-also"></a>Consulte também
- [Estenda documentos do Word e pastas de trabalho do Excel em suplementos do VSTO em tempo de execução](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Controles em documentos do Office](../vsto/controls-on-office-documents.md)
- [Visão geral de itens de host e controles de host](../vsto/host-items-and-host-controls-overview.md)
- [Automatizar o Excel usando objetos estendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Controle NamedRange](../vsto/namedrange-control.md)
- [Como: Adicionar controles NamedRange a planilhas](../vsto/how-to-add-namedrange-controls-to-worksheets.md)
- [Como: Redimensionar controles de indicador](../vsto/how-to-resize-bookmark-controls.md)
- [Como: Redimensionar controles ListObject](../vsto/how-to-resize-listobject-controls.md)
