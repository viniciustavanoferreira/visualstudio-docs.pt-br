---
title: 'Passo a passo: Criando um Glifo de Margem | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - margin glyph
ms.assetid: 814185db-24f9-417f-b3b1-7c5aabb42b45
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9588b150dd795fc2bc5e6c55d8f6e2359f609939
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80697695"
---
# <a name="walkthrough-create-a-margin-glyph"></a>Passo a passo: Crie um glifo de margem
Você pode personalizar a aparência das margens do editor usando extensões personalizadas do editor. Este passo a passo coloca um glifo personalizado na margem do indicador sempre que a palavra "todo" aparece em um comentário de código.

## <a name="prerequisites"></a>Pré-requisitos
 A partir do Visual Studio 2015, você não instala o Visual Studio SDK a partir do centro de downloads. Está incluído como um recurso opcional na configuração do Visual Studio. Você também pode instalar o VS SDK mais tarde. Para obter mais informações, consulte [Instalar o Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-mef-project"></a>Crie um projeto MEF

1. Crie um projeto C# VSIX. (Na caixa de diálogo **Novo Projeto,** selecione **Visual C# / Extensibility**, em seguida, **Projeto VSIX**.) Diga a `TodoGlyphTest`solução.

2. Adicione um item de projeto do Editor Classifier. Para obter mais informações, consulte [Criar uma extensão com um modelo de item do editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).

3. Exclua os arquivos de classe existentes.

## <a name="define-the-glyph"></a>Defina o glifo
 Defina um glifo <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory> executando a interface.

### <a name="to-define-the-glyph"></a>Para definir o glifo

1. Adicione um arquivo de `TodoGlyphFactory`classe e nomeie-o .

2. Adicione o seguinte código usando declarações.

     [!code-csharp[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_1.cs)]
     [!code-vb[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_1.vb)]

3. Adicione uma `TodoGlyphFactory` classe nomeada <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory>que implementa .

     [!code-csharp[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_2.cs)]
     [!code-vb[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_2.vb)]

4. Adicione um campo privado que defina as dimensões do glifo.

     [!code-csharp[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_3.cs)]
     [!code-vb[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_3.vb)]

5. Implementar `GenerateGlyph` definindo o elemento interface do usuário glifos (UI). `TodoTag`é definido mais tarde neste passo a passo.

     [!code-csharp[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_4.cs)]
     [!code-vb[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_4.vb)]

6. Adicione uma `TodoGlyphFactoryProvider` classe nomeada <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider>que implementa . Exporte esta <xref:Microsoft.VisualStudio.Utilities.NameAttribute> classe com um de <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> "TodoGlyph", <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> um de After <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> VsTextMarker, um de "code", e um de TodoTag.

     [!code-csharp[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_5.cs)]
     [!code-vb[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_5.vb)]

7. Implementar <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider.GetGlyphFactory%2A> o método instanciando o `TodoGlyphFactory`.

     [!code-csharp[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_6.cs)]
     [!code-vb[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_6.vb)]

## <a name="define-a-todo-tag-and-tagger"></a>Defina uma tag e tagger Todo
 Defina a relação entre o elemento ui que você definiu nas etapas anteriores e a margem indicadora. Crie um tipo de tag e tagger e exporte-o usando um provedor de tagger.

### <a name="to-define-a-todo-tag-and-tagger"></a>Para definir uma tag e tagger todo

1. Adicione um novo arquivo de classe `TodoTagger`ao projeto e nomeie-o .

2. Adicione as seguintes importações.

     [!code-csharp[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_7.cs)]
     [!code-vb[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_7.vb)]

3. Adicione uma classe chamada `TodoTag`.

     [!code-csharp[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_8.cs)]
     [!code-vb[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_8.vb)]

4. Modificar a `TodoTagger` classe nomeada <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> que `TodoTag`implementa o tipo .

     [!code-csharp[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_9.cs)]
     [!code-vb[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_9.vb)]

5. À `TodoTagger` classe, adicione campos <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> privados para um e para que o texto encontre nos intervalos de classificação.

     [!code-csharp[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_10.cs)]
     [!code-vb[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_10.vb)]

6. Adicione um construtor que define o classificador.

     [!code-csharp[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_11.cs)]
     [!code-vb[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_11.vb)]

7. Implemente <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> o método encontrando todas as faixas de classificação cujos nomes incluem a palavra "comentário" e cujo texto inclui o texto de pesquisa. Sempre que o texto de pesquisa <xref:Microsoft.VisualStudio.Text.Tagging.TagSpan%601> for `TodoTag`encontrado, recupere um novo tipo .

     [!code-csharp[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_12.cs)]
     [!code-vb[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_12.vb)]

8. Declare `TagsChanged` um evento.

     [!code-csharp[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_13.cs)]
     [!code-vb[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_13.vb)]

9. Adicione uma `TodoTaggerProvider` classe nomeada <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>que implementa <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> e exporte-a <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> com um de "código" e um de TodoTag.

     [!code-csharp[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_14.cs)]
     [!code-vb[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_14.vb)]

10. Importar <xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService>o .

     [!code-csharp[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_15.cs)]
     [!code-vb[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_15.vb)]

11. Implementar <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> o método instanciando o `TodoTagger`.

     [!code-csharp[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_16.cs)]
     [!code-vb[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_16.vb)]

## <a name="build-and-test-the-code"></a>Construa e teste o código
 Para testar este código, construa a solução TodoGlyphTest e execute-o na instância experimental.

### <a name="to-build-and-test-the-todoglyphtest-solution"></a>Para construir e testar a solução TodoGlyphTest

1. Compile a solução.

2. Execute o projeto pressionando **F5**. Uma segunda instância do Visual Studio começa.

3. Certifique-se de que a margem indicadora está aparecendo. (No menu **Ferramentas,** clique em **Opções**. Na página **do Editor de texto,** certifique-se de que **a margem indicadora** está selecionada.)

4. Abra um arquivo de código que tenha comentários. Adicione a palavra "todo" a uma das seções de comentários.

5. Um círculo azul claro com um contorno azul escuro aparece na margem indicadora à esquerda da janela de código.
