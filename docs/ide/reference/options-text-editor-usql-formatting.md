---
title: Opções de formatação do editor de U-SQL
ms.date: 01/17/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.NewLines
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.Indentation
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.General
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 200ec41a1295178f1127d10053985384a7813158
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75568263"
---
# <a name="options-text-editor-u-sql-formatting"></a>Opções, Editor de Texto, U-SQL, Formatação

Use a página de opções **de formatação** para definir opções para formatação de código no editor de código. Para acessar esta página de opções, escolha **Opções de** > **ferramentas**. Na caixa de diálogo **Opções**, escolha **Editor de Texto** > **U-SQL** > **Formatação**.

## <a name="general-page"></a>Página Geral

### <a name="general-settings"></a>Configurações gerais

Essas configurações afetam *quando* o editor de códigos aplica opções de formatação ao código.

- **Formatar automaticamente a instrução concluída ao inserir ponto-e-vírgula**

   Quando essa opção estiver selecionada, as instruções serão formadas quando você escolher a tecla de ponto-e-vírgula, de acordo com as opções de formatação selecionadas para o editor.

- **Formatar automaticamente ao colar**

   Quando selecionada, formata o texto que é colado no editor de acordo com as opções de formatação selecionadas para o editor.

## <a name="preview-windows"></a>Janelas de visualização

As subpáginas **Recuo**, **Novas Linhas** e **Espaçamento** exibem uma janela de visualização na parte inferior. A janela de visualização mostra o efeito de cada opção. Para usar a janela de visualização, selecione uma opção de formatação. A janela de visualização mostra um exemplo da opção selecionada. Quando você altera uma configuração marcando uma caixa de seleção, a janela de visualização é atualizada para mostrar o efeito da nova configuração.

### <a name="indentation-remarks"></a>Comentários de recuo

Opções de recuo nas páginas **de guias** para cada idioma só determinam onde o editor de código coloca o cursor quando você **pressiona Enter** no final de uma linha. As opções de recuo em **Formatação** se aplicam quando o código é formatado automaticamente, por exemplo:

- Quando você cola o código no arquivo enquanto **Formatar automaticamente ao colar** está selecionada
- Quando o bloco que está sendo formatado é digitado manualmente

## <a name="see-also"></a>Confira também

- [Caixa de diálogo Geral, Meio Ambiente, Opções](../../ide/reference/general-environment-options-dialog-box.md)
