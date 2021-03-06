---
title: Armazenar em cache a fonte de dados no documento do Office programaticamente
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 241ce42c2d411fdaf611f3a7f2b52eb40c8c32a2
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189587"
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>Como: armazenar em cache uma fonte de dados programaticamente em um documento do Office
  Você pode adicionar programaticamente um objeto de dados ao cache de dados em um documento chamando o método `StartCaching` de um item de host, como um <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>ou <xref:Microsoft.Office.Tools.Excel.Worksheet>. Remova um objeto de dados do cache de dados chamando o método `StopCaching` de um item de host.

 O método `StartCaching` e o método `StopCaching` são privados, mas aparecem no IntelliSense.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Quando você usa o método `StartCaching` para adicionar um objeto de dados ao cache de dados, o objeto de dados não precisa ser declarado com o atributo <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>. No entanto, o objeto de dados deve atender a certos requisitos a serem adicionados ao cache de dados. Para obter mais informações, consulte [armazenar dados em cache](../vsto/caching-data.md).

## <a name="to-programmatically-cache-a-data-object"></a>Para armazenar em cache um objeto de dados de forma programática

1. Declare o objeto de dados no nível de classe, não dentro de um método. Este exemplo pressupõe que você está declarando um <xref:System.Data.DataSet> chamado `dataSet1` que você deseja armazenar em cache programaticamente.

     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]

2. Crie uma instância do objeto de dados e, em seguida, chame o método `StartCaching` da instância do documento ou da planilha e passe o nome do objeto de dados.

     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]

## <a name="to-stop-caching-a-data-object"></a>Para parar de armazenar em cache um objeto de dados

1. Chame o método `StopCaching` da instância do documento ou da planilha e passe o nome do objeto de dados. Este exemplo pressupõe que você tenha um <xref:System.Data.DataSet> nomeado `dataSet1` que você deseja interromper o cache.

     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]

    > [!NOTE]
    > Não chame `StopCaching` do manipulador de eventos para o evento `Shutdown` de um documento ou planilha. No momento em que o evento de `Shutdown` é gerado, é muito tarde para modificar o cache de dados. Para obter mais informações sobre o evento `Shutdown`, consulte [eventos em projetos do Office](../vsto/events-in-office-projects.md).

## <a name="see-also"></a>Consulte também

- [Dados de cache](../vsto/caching-data.md)
- [Como armazenar em cache dados para uso offline ou em um servidor](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)
- [Como armazenar dados em cache em um documento protegido por senha](../vsto/how-to-cache-data-in-a-password-protected-document.md)
- [Acessar dados em documentos no servidor](../vsto/accessing-data-in-documents-on-the-server.md)
- [Salvar dados](../data-tools/save-data-back-to-the-database.md)
