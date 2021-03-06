---
title: 'Como: Mapear esquemas para planilhas dentro do Visual Studio'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Excel worksheets
- Excel [Office development in Visual Studio], XML schemas
- worksheets [Office development in Visual Studio], XML schemas
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 80a19924aaf4fa0afe8e809006ada7fada0288f3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428110"
---
# <a name="how-to-map-schemas-to-worksheets-inside-visual-studio"></a>Como: Mapear esquemas para planilhas dentro do Visual Studio
  Você pode mapear um esquema XML para uma planilha enquanto a planilha estiver aberta no Visual Studio. Você usa as mesmas ferramentas do Microsoft Office Excel que você usa quando a pasta de trabalho é aberta fora do Visual Studio. O projeto do Office cria os objetos de mesmos se você mapear o esquema para a planilha antes ou depois de criar sua solução do Excel.

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

> [!NOTE]
> É possível usar os esquemas XML com diversas partes em soluções do Excel.

## <a name="to-map-an-xml-schema-to-an-excel-worksheet-in-visual-studio"></a>Para mapear um esquema XML para uma planilha do Excel no Visual Studio

1. Abra o projeto de modelo ou a pasta de trabalho do Excel dentro do Visual Studio.

2. Clique na planilha para mover o foco para o designer.

3. Na faixa de opções, clique no **desenvolvedor** guia.

    > [!NOTE]
    > Se o **desenvolvedor** guia não estiver visível, você deve primeiro Mostrar. Para obter mais informações, confira [Como: Mostrar a guia Desenvolvedor na faixa de opções](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).

4. No **XML** , clique em **origem**.

     O **código-fonte XML** janela é aberta.

5. No **origem XML** janela, clique em **mapas XML**.

     O **mapas XML** caixa de diálogo é aberta.

6. No **mapas XML** caixa de diálogo, clique em **Add**.

7. Navegue até o arquivo de esquema, selecione-o e, em seguida, clique em **aberto**.

8. Clique em **OK**.

     O esquema é representado na **código-fonte XML** janela. Em seu projeto, com um tipo <xref:System.Data.DataSet> é gerado com base no esquema e um <xref:System.Windows.Forms.BindingSource> é criado.

9. Arrastar os elementos do **código-fonte XML** janela para os locais em sua planilha onde você deseja que os controles correspondentes a serem criados.

     Se você arrastar um elemento de esquema não repetitivo, o Office project gera uma <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> controle que é associada automaticamente a <xref:System.Windows.Forms.BindingSource>.

     Se você arrastar um elemento de esquema repetido, o Office project gera um <xref:Microsoft.Office.Tools.Excel.ListObject> controle que não é automaticamente associado a uma fonte de dados. Para obter mais informações, consulte [esquemas XML e dados no nível de documento personalizações](../vsto/xml-schemas-and-data-in-document-level-customizations.md).

## <a name="see-also"></a>Consulte também
- [Como: Mapear esquemas para documentos do Word dentro do Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)
- [Esquemas e dados em personalizações no nível de documento XML](../vsto/xml-schemas-and-data-in-document-level-customizations.md)
