---
title: 'Como: Proteger partes de documentos usando controles de conteúdo'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- partial document protection [Office development in Visual Studio]
- content controls [Office development in Visual Studio], protecting documents
- Word [Office development in Visual Studio], partial document protection
- document protection [Office development in Visual Studio]
- Word [Office development in Visual Studio], restricted permissions
- GroupContentControl
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 129962209d8cfa541a34bc1575a73382cd63d7c4
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71254673"
---
# <a name="how-to-protect-parts-of-documents-by-using-content-controls"></a>Como: Proteger partes de documentos usando controles de conteúdo
  Ao proteger parte de um documento, você impede que os usuários alterem ou excluam o conteúdo dessa parte do documento. Há várias maneiras pelas quais você pode proteger partes de um Microsoft Office documento do Word usando controles de conteúdo:

- Você pode proteger um controle de conteúdo.

- Você pode proteger uma parte de um documento que não está em um controle de conteúdo.

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="EditDeleteControl"></a>Proteger um controle de conteúdo
 Você pode impedir que os usuários editem ou excluam um controle de conteúdo definindo as propriedades do controle em um projeto de nível de documento em tempo de design ou em tempo de execução.

 Você também pode proteger os controles de conteúdo que você adiciona a um documento em tempo de execução usando um projeto de suplemento do VSTO. Para obter mais informações, confira [Como: Adicione controles de conteúdo a documentos](../vsto/how-to-add-content-controls-to-word-documents.md)do Word.

### <a name="to-protect-a-content-control-at-design-time"></a>Para proteger um controle de conteúdo em tempo de design

1. No documento que está hospedado no [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, selecione o controle de conteúdo que você deseja proteger.

2. Na janela **Propriedades** , defina uma ou ambas as propriedades a seguir:

    - Para impedir que os usuários editem o controle, defina **LockContents** como **true**.

    - Para impedir que os usuários excluam o controle, defina **LockContentControl** como **true**.

3. Clique em **OK**.

### <a name="to-protect-a-content-control-at-run-time"></a>Para proteger um controle de conteúdo em tempo de execução

1. Defina a `LockContents` Propriedade do controle de conteúdo como **true** para impedir que os usuários editem o controle e defina `LockContentControl` a propriedade como **true** para impedir que os usuários excluam o controle.

     O exemplo de código a seguir demonstra <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> como <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> usar as propriedades e <xref:Microsoft.Office.Tools.Word.RichTextContentControl> de dois objetos diferentes em um projeto de nível de documento. Para executar esse código, adicione o código à `ThisDocument` classe em seu projeto e chame o `AddProtectedContentControls` método do `ThisDocument_Startup` manipulador de eventos.

     [!code-csharp[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#2)]

     O exemplo de código a seguir demonstra <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> como <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> usar as propriedades e <xref:Microsoft.Office.Tools.Word.RichTextContentControl> de dois objetos diferentes em um projeto de suplemento do VSTO. Para executar esse código, adicione o código à `ThisAddIn` classe em seu projeto e chame o `AddProtectedContentControls` método do `ThisAddIn_Startup` manipulador de eventos.

     [!code-vb[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#14)]
     [!code-csharp[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#14)]

## <a name="protect-a-part-of-a-document-that-is-not-in-a-content-control"></a>Proteger uma parte de um documento que não está em um controle de conteúdo
 Você pode impedir que os usuários alterem uma área de um documento colocando a área em <xref:Microsoft.Office.Tools.Word.GroupContentControl>um. Isso é útil nos seguintes cenários:

- Você deseja proteger uma área que não contém controles de conteúdo.

- Você deseja proteger uma área que já contém controles de conteúdo, mas o texto ou outros itens que você deseja proteger não estão nos controles de conteúdo.

> [!NOTE]
> Se você criar um <xref:Microsoft.Office.Tools.Word.GroupContentControl> que contenha controles de conteúdo inseridos, os controles de conteúdo inserido não serão protegidos automaticamente. Para impedir que os usuários editem um controle de conteúdo inserido, use a propriedade **LockContents** do controle.

### <a name="to-protect-an-area-of-a-document-at-design-time"></a>Para proteger uma área de um documento em tempo de design

1. No documento que está hospedado no [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, selecione a área que você deseja proteger.

2. Na faixa de faixas, clique na guia **desenvolvedor** .

    > [!NOTE]
    > Se a guia **desenvolvedor** não estiver visível, você deverá primeiro mostrá-la. Para obter mais informações, confira [Como: Mostre a guia Desenvolvedor na faixa de](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)faixas.

3. No grupo **controles** , clique no botão suspenso **grupo** e, em seguida, clique em **grupo**.

     Um <xref:Microsoft.Office.Tools.Word.GroupContentControl> que contém a região protegida é gerado automaticamente `ThisDocument` na classe em seu projeto. Uma borda que representa o controle de grupo é visível em tempo de design, mas não há nenhuma borda visível no tempo de execução.

### <a name="to-protect-an-area-of-a-document-at-run-time"></a>Para proteger uma área de um documento em tempo de execução

1. Selecione programaticamente a área que você deseja proteger e, em seguida <xref:Microsoft.Office.Tools.Word.ControlCollection.AddGroupContentControl%2A> , chame o método <xref:Microsoft.Office.Tools.Word.GroupContentControl>para criar um.

     O exemplo de código a seguir para um projeto de nível de documento adiciona texto ao primeiro parágrafo do documento, seleciona o primeiro parágrafo e, em seguida, <xref:Microsoft.Office.Tools.Word.GroupContentControl>cria uma instância de um. Para executar esse código, adicione o código à `ThisDocument` classe em seu projeto e chame o `ProtectFirstParagraph` método do `ThisDocument_Startup` manipulador de eventos.

     [!code-csharp[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#1)]

     O exemplo de código a seguir para um projeto de suplemento do VSTO adiciona texto ao primeiro parágrafo no documento ativo, seleciona o primeiro parágrafo e, em seguida, cria <xref:Microsoft.Office.Tools.Word.GroupContentControl>uma instância de um. Para executar esse código, adicione o código à `ThisAddIn` classe em seu projeto e chame o `ProtectFirstParagraph` método do `ThisAddIn_Startup` manipulador de eventos.

     [!code-vb[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#15)]
     [!code-csharp[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#15)]

## <a name="see-also"></a>Consulte também
- [Automatizar o Word usando objetos estendidos](../vsto/automating-word-by-using-extended-objects.md)
- [Controles de conteúdo](../vsto/content-controls.md)
- [Como: Adicionar controles de conteúdo a documentos do Word](../vsto/how-to-add-content-controls-to-word-documents.md)
- [Visão geral de itens de host e controles de host](../vsto/host-items-and-host-controls-overview.md)
- [Limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Adicionar controles a documentos do Office em tempo de execução](../vsto/adding-controls-to-office-documents-at-run-time.md)
