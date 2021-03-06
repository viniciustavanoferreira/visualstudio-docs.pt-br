---
title: 'Como: Redimensionar controles de indicador'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- Bookmark control, resizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 99e5c789f65a1dff460bc22dd4a0c097e11c7e98
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252212"
---
# <a name="how-to-resize-bookmark-controls"></a>Como: Redimensionar controles de indicador
  Você define o tamanho de um <xref:Microsoft.Office.Tools.Word.Bookmark> controle ao adicioná-lo a um Microsoft Office documento do Word. Você também pode redimensioná-lo em um momento posterior.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Há três maneiras de redimensionar um indicador:

- Adicionar ou remover texto do <xref:Microsoft.Office.Tools.Word.Bookmark> controle.

   Sempre que você adicionar texto em um indicador, o tamanho do indicador aumentará automaticamente para conter o novo texto. Quando você exclui texto, o tamanho do indicador diminui automaticamente.

- Altere as <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> propriedades <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> e do <xref:Microsoft.Office.Tools.Word.Bookmark> controle.

   Isso será útil se você estiver alterando o tamanho apenas alguns caracteres.

- Recrie o <xref:Microsoft.Office.Tools.Word.Bookmark> controle.

   Isso será útil se houver uma alteração significativa no tamanho ou no local de um indicador.

  Em projetos de nível de documento, você pode <xref:Microsoft.Office.Tools.Word.Bookmark> adicionar controles ao documento em seu projeto em tempo de design ou em tempo de execução. Em projetos de suplemento do VSTO, você pode adicionar <xref:Microsoft.Office.Tools.Word.Bookmark> controles a qualquer documento aberto em tempo de execução. Para obter mais informações, confira [Como: Adicione controles de indicadores a documentos](../vsto/how-to-add-bookmark-controls-to-word-documents.md)do Word.

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="change-the-start-and-end-properties"></a>Alterar as propriedades de início e término

### <a name="to-resize-a-bookmark-in-a-document-level-project-at-design-time"></a>Para redimensionar um indicador em um projeto de nível de documento no tempo de design

1. Selecione o indicador na janela **Propriedades** .

2. Aumente ou diminua o valor da <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> propriedade.

3. Aumente ou diminua o valor da <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> propriedade.

### <a name="to-resize-a-bookmark-in-a-document-level-project-at-run-time"></a>Para redimensionar um indicador em um projeto de nível de documento em tempo de execução

1. Modifique as <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> propriedades <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> e de um <xref:Microsoft.Office.Tools.Word.Bookmark> que você criou em tempo de execução ou em tempo de design.

     O exemplo de código a seguir adiciona cinco caracteres ao início de um indicador `SampleBookmark`chamado. Esse código pressupõe que haja pelo menos cinco caracteres de texto antes do indicador.

     [!code-csharp[Trin_VstcoreHostControlsWord#2](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreHostControlsWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#2)]

     O exemplo de código a seguir adiciona cinco caracteres ao final do mesmo indicador. Esse código pressupõe que haja pelo menos cinco caracteres de texto após o indicador.

     [!code-csharp[Trin_VstcoreHostControlsWord#3](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#3)]

### <a name="to-resize-a-bookmark-in-a-vsto-add-in-project-at-run-time"></a>Para redimensionar um indicador em um projeto de suplemento do VSTO em tempo de execução

1. Modifique as <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> propriedades <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> e de um <xref:Microsoft.Office.Tools.Word.Bookmark> que você criou em tempo de execução.

     O exemplo de código a seguir <xref:Microsoft.Office.Tools.Word.Bookmark> cria um que contém o texto no primeiro parágrafo do documento ativo e, em seguida, remove cinco caracteres do início e do fim <xref:Microsoft.Office.Tools.Word.Bookmark>do.

     [!code-vb[Trin_WordAddInDynamicControls#16](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#16)]
     [!code-csharp[Trin_WordAddInDynamicControls#16](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#16)]

## <a name="recreate-the-bookmark"></a>Recriar o indicador
 Você pode redimensionar um indicador em um projeto de nível de documento adicionando um novo indicador com o mesmo nome que o indicador existente, mas que tem um tamanho diferente.

### <a name="to-recreate-a-bookmark-in-a-document-level-project-at-design-time"></a>Para recriar um indicador em um projeto de nível de documento no tempo de design

1. Selecione o texto a ser incluído no novo <xref:Microsoft.Office.Tools.Word.Bookmark> controle.

2. No menu **Inserir** , clique em **indicador**.

3. Na caixa de diálogo **indicador** , selecione o nome do indicador que você deseja redimensionar e clique em **Adicionar**.

## <a name="see-also"></a>Consulte também
- [Como: Adicionar controles de indicador a documentos do Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)
- [Automatizar o Word usando objetos estendidos](../vsto/automating-word-by-using-extended-objects.md)
- [Visão geral de itens de host e controles de host](../vsto/host-items-and-host-controls-overview.md)
- [Como: Redimensionar controles NamedRange](../vsto/how-to-resize-namedrange-controls.md)
- [Como: Redimensionar controles ListObject](../vsto/how-to-resize-listobject-controls.md)
- [Limitações programáticas de itens de host e controles de host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
