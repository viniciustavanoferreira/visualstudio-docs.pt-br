---
title: Preenchimento automático incrementalmente alterando os intervalos de dados programaticamente
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a514f83d12cd00c4a7792ae0bf2483fdd916897a
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177690"
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>Como: Por meio de programação automaticamente preencher intervalos com dados alterados em incrementos
  O <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> método da <xref:Microsoft.Office.Interop.Excel.Range> objeto permite que você preencha um intervalo em uma planilha com valores automaticamente. Geralmente, o <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> método é usado para armazenar aumentando ou diminuindo valores em um intervalo de forma incremental. Você pode especificar o comportamento, fornecendo uma constante opcional do <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> enumeração.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Você deve especificar dois intervalos ao usar <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:

- O intervalo que chama o <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> método, que especifica o ponto de partida do preenchimento e contém um valor inicial.

- O intervalo que você deseja preencher, passado como um parâmetro para o <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> método. Esse intervalo de destino deve incluir o intervalo que contém o valor inicial.

    > [!NOTE]
    > Não é possível passar uma <xref:Microsoft.Office.Tools.Excel.NamedRange> controlar em vez do <xref:Microsoft.Office.Interop.Excel.Range>. Para obter mais informações, consulte [limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

## <a name="example"></a>Exemplo
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]

## <a name="compile-the-code"></a>Compilar o código
 A primeira célula do intervalo que você deseja preencher deve conter um valor inicial.

 O exemplo requer que você preenche três regiões:

- Coluna B é incluir cinco dias da semana. Para o valor inicial, digite **segunda-feira** na célula B1.

- Coluna C é incluir cinco meses. Para o valor inicial, digite **janeiro** na célula C1.

- A coluna D é incluir uma série de números, incrementar por dois para cada linha. Para os valores iniciais, digite **4** da célula D1 e **6** na célula D2.

## <a name="see-also"></a>Consulte também
- [Trabalhar com intervalos](../vsto/working-with-ranges.md)
- [Como: Por meio de programação se referir a intervalos de planilhas em código](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)
- [Como: Aplicar estilos a intervalos em pastas de trabalho programaticamente](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)
- [Como: Executar cálculos do Excel](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)
- [Visão geral dos controles de host e de itens de host](../vsto/host-items-and-host-controls-overview.md)
- [Parâmetros opcionais em soluções do Office](../vsto/optional-parameters-in-office-solutions.md)
