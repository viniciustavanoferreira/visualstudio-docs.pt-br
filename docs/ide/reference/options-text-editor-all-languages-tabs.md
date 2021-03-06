---
title: Opções, Editor de Texto, Todos os Idiomas, Guias
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.All_Languages.Tabs
- VS.ToolsOptionsPages.Text_Editor.Basic.Tabs
- VS.ToolsOptionsPages.Text_Editor.CSharp.Tabs
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Tabs
- VS.ToolsOptionsPages.Text_Editor.CoffeeScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.CSS.Tabs
- VS.ToolsOptionsPages.Text_Editor.Dockerfile.Tabs
- VS.ToolsOptionsPages.Text_Editor.F%2523.Tabs
- VS.ToolsOptionsPages.Text_Editor.HQL.Tabs
- VS.ToolsOptionsPages.Text_Editor.HTML.Tabs
- VS.ToolsOptionsPages.Text_Editor.HTMLX.Tabs
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.JSON.Tabs
- VS.ToolsOptionsPages.Text_Editor.LESS.Tabs
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.Tabs
- VS.ToolsOptionsPages.Text_Editor.ResJSON.Tabs
- VS.ToolsOptionsPages.Text_Editor.SCSS.Tabs
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Tabs
- VS.ToolsOptionsPages.Text_Editor.StreamAnalytics.Tabs
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.Tabs
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Tabs
- VS.ToolsOptionsPages.Text_Editor.XAML.Tabs
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
helpviewer_keywords:
- indents, Code Editor
- Code Editor, default behavior
- tabs, setting in Code Editor
- All Languages Text Editor Options dialog box
- editors, Code Editor
- Code Editor, indenting
- Code Editor, tabs
ms.assetid: 7e208e1d-5e3a-4bf7-a27b-4417e3e049c7
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0fc169960cf757e4e334d5f77b06ff70b0d6da7c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75594741"
---
# <a name="options-text-editor-all-languages-tabs"></a>Opções, Editor de Texto, Todos os Idiomas, Guias

Esta caixa de diálogo permite alterar o comportamento padrão do Editor de Código. Essas configurações também se aplicam a outros editores baseados no Editor de código, como o modo de exibição de Fonte do Designer de HTML. Para exibir essas opções, selecione **Opções** do menu **Ferramentas**. Na pasta **Editor de Texto**, expanda a subpasta **Todos os Idiomas** e, em seguida, escolha **Guias**.

> [!CAUTION]
> Esta página define opções padrão para todas as linguagens de desenvolvimento. Lembre-se de que redefinir uma opção nessa caixa de diálogo redefinirá as opções Guias em todas as linguagens para quaisquer opções selecionadas aqui. Para alterar as opções do Editor de Texto para apenas uma linguagem, expanda a subpasta para aquela linguagem e selecione suas páginas de opções.

Se forem selecionadas configurações diferentes nas páginas de opções Guias para linguagens de programação específicas, a mensagem “As configurações de recuo para formatos de texto individuais estão em conflito entre si” será exibida para diferentes opções de **Recuo**, e a mensagem “As configurações de guia para formatos de texto individuais estão em conflito entre si” será exibida para diferentes opções de **Guia**. Por exemplo, esse lembrete será exibido se a opção **Recuo inteligente** for selecionada para Visual Basic, mas **Bloquear recuo** estiver selecionado para Visual C++.

## <a name="indenting"></a>Recuo

Nenhum

Quando selecionada, novas linhas não serão recuadas. O ponto de inserção é colocado na primeira coluna de uma linha nova.

Bloco

Quando selecionada, novas linhas serão recuadas automaticamente. O ponto de inserção é colocado no mesmo ponto de partida que a linha anterior.

Inteligente

Quando selecionada, novas linhas serão posicionadas para caber no o contexto do código, conforme as configurações de formatação do outro código e as convenções do IntelliSense para sua linguagem de desenvolvimento. Essa opção não está disponível para todas as linguagens de desenvolvimento.

Por exemplo, as linhas incluídas entre uma chave de abertura ({) e uma chave de fechamento (}) podem ser recuadas automaticamente em uma parada de tabulação extra da posição das chaves alinhadas.

## <a name="tabs"></a>Tabulações

Tamanho da tabulação

Define a distância em espaços entre paradas de tabulação. O padrão é quatro espaços.

Tamanho do recuo

Define o tamanho em espaços de um recuo automático. O padrão é quatro espaços. Caracteres de tabulação, caracteres de espaço ou ambos serão inseridos para preencher o tamanho especificado.

Inserir espaços

Quando selecionadas, as operações de recuo inserirão apenas caracteres de espaço, não caracteres de TABULAÇÃO. Se o **Tamanho do recuo** estiver definido como 5, por exemplo, cinco caracteres de espaço serão inseridos sempre que você pressionar a tecla TAB ou o botão **Aumentar Recuo** na barra de ferramentas de **Formatação**.

Manter tabulações

Quando estiverem selecionadas, as operações de recuo inserirão tantos caracteres de TABULAÇÃO quantos forem possíveis. Cada caractere TAB preenche o número de espaços especificados no **tamanho da guia**. Se o **Tamanho do recuo** não for um múltiplo par do **Tamanho da tabulação**, os caracteres de espaço serão adicionados para preencher a diferença.

## <a name="see-also"></a>Confira também

- [Opções, Editor de Texto, Todas as Linguagens](../../ide/reference/options-text-editor-all-languages.md)
- [Caixa de diálogo Geral, Ambiente, Opções](../../ide/reference/general-environment-options-dialog-box.md)
