---
title: 'Como: Mover planilhas em pastas de trabalho de forma programática'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, moving
- workbooks, moving worksheets in
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7e62e397bd9f8c2a0e8e8c8b7ed6581e289a9efc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812731"
---
# <a name="how-to-programmatically-move-worksheets-within-workbooks"></a>Como: Mover planilhas em pastas de trabalho de forma programática
  Programaticamente, você pode alterar a posição de planilhas em relação a outras planilhas em uma pasta de trabalho. Se você não especificar um local para a folha movida, o Excel cria uma nova pasta de trabalho para contê-lo.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-move-a-worksheet-in-a-document-level-customization"></a>Para mover uma planilha em uma personalização no nível de documento

1. Atribuir o número total de folhas na pasta de trabalho a uma variável e, em seguida, mova a primeira planilha para que ele se torne o último deles.

     [!code-csharp[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#24)]

## <a name="to-move-a-worksheet-in-a-vsto-add-in"></a>Para mover uma planilha em um suplemento do VSTO

1. Atribuir o número total de folhas na pasta de trabalho a uma variável e, em seguida, mova a primeira planilha para que ele se torne o último deles.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#16)]

## <a name="see-also"></a>Consulte também
- [Trabalhar com planilhas](../vsto/working-with-worksheets.md)
- [Como: Ocultar planilhas programaticamente](../vsto/how-to-programmatically-hide-worksheets.md)
- [Como: Excluir planilhas de pastas de trabalho de forma programática](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)
- [Como: Proteger planilhas programaticamente](../vsto/how-to-programmatically-protect-worksheets.md)
- [Acesso global a objetos em projetos do Office](../vsto/global-access-to-objects-in-office-projects.md)
