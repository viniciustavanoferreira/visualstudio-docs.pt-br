---
title: Aliases de comando
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- aliases, Visual Studio commands
- Visual Studio, commands
- predefined command aliases
- commands, aliases
- Visual Studio commands
- pre-defined command aliases
- command aliases
ms.assetid: de8bb378-8c1c-4087-a9a5-537fa8314c19
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b420644672309371ab61f1499e22d4745c69c569
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75596405"
---
# <a name="visual-studio-command-aliases"></a>Aliases de comando do Visual Studio

Os aliases de comando permitem que você digite menos caracteres quando deseja executar um comando. Insira os aliases na caixa **Localizar/Comando** ou na janela **Comando**. Por exemplo, em vez de inserir `>File.OpenFile` para exibir a caixa de diálogo **Abrir Arquivo**, você pode usar o alias predefinido `>of`.

Digite `alias` na janela **Comando** para exibir uma lista de aliases atuais e suas definições. Digite `>cls` para limpar o conteúdo da janela **Comando**. Se você quiser ver um alias para um comando específico, digite `alias <command name>`.

Você pode criar facilmente seu próprio alias para um dos comandos do Visual Studio (com ou sem argumentos). Por exemplo, a sintaxe para definir alias `File.NewFile MyFile.txt` é `alias MyAlias File.NewFile MyFile.txt`. Você pode excluir um de seus aliases com `alias <alias name> /delete`

A tabela a seguir contém uma lista de aliases de comando predefinidos do Visual Studio. Alguns nomes de comando têm mais de um alias predefinido. Clique nos links para os nomes de comando abaixo para exibir tópicos detalhados que explicam a sintaxe, os argumentos e as opções corretos para esses comandos.

|Nome do comando|Alias|Nome Completo|
|------------------|-----------|-------------------|
|[Comando Imprimir](../../ide/reference/print-command.md)|?|Debug.Print|
|[Comando Quick Watch](../../ide/reference/quick-watch-command.md)|??|Debug.Quickwatch|
|Adicionar novo projeto|AddProj|File.AddNewProject|
|[Comando Alias](../../ide/reference/alias-command.md)|Alias|Tools.Alias|
|Janela Autos|Autos|Debug.Autos|
|Janela Pontos de Interrupção|bl|Debug.Breakpoints|
|Alternar Ponto de Interrupção|bp|Debug.ToggleBreakPoint|
|janela de Pilha de Chamadas|CallStack|Debug.CallStack|
|Limpar Indicadores|ClearBook|Edit.ClearBookmarks|
|Feche|Feche|File.Close|
|Fechar Todos os Documentos|CloseAll|Window.CloseAllDocuments|
|Limpar Tudo|cls|Edit.ClearAll|
|Modo de comando|cmd|View.CommandWindow|
|Código de exibição|código|View.ViewCode|
|[Comando List Memory](../../ide/reference/list-memory-command.md)|d|Debug.ListMemory|
|[Comando Listar Memória](../../ide/reference/list-memory-command.md) como ANSI|da|Debug.ListMemory /Ansi|
|[Comando Listar Memória](../../ide/reference/list-memory-command.md) com formato de um byte|db|Debug.ListMemory /Format:OneByte|
|[Comando Listar Memória](../../ide/reference/list-memory-command.md) como ANSI com formato de quatro bytes|dc|Debug.ListMemory /Format:FourBytes /Ansi|
|[Comando Listar Memória](../../ide/reference/list-memory-command.md) no formato de quatro bytes|dd|Debug.ListMemory /Format:FourBytes|
|Excluir para BOL|DelBOL|Edit.DeleteToBOL|
|Excluir para EOL|DelEOL|Edit.DeleteToEOL|
|Excluir Espaço em Branco Horizontal|DelHSp|Edit.DeleteHorizontalWhitespace|
|Designer de Exibição|designer|View.ViewDesigner|
|[Comando Listar Memória](../../ide/reference/list-memory-command.md) em formato Float|df|Debug.ListMemory/Format:Float|
|janela de Desmontagem|disasm|Debug.Disassembly|
|[Comando listar memória](../../ide/reference/list-memory-command.md) no formato de oito bytes|dq|Debug.ListMemory /Format:EightBytes|
|[Comando Listar Memória](../../ide/reference/list-memory-command.md) como Unicode|du|Debug.ListMemory /Unicode|
|[Comando Evaluate Statement](../../ide/reference/evaluate-statement-command.md)|eval|Debug.EvaluateStatement|
|Sair|Sair|File.Exit|
|Formatar Seleção|format|Edit.FormatSelection|
|Tela inteira|Tela Inteira|View.FullScreen|
|[Iniciar comando](../../ide/reference/start-command.md)|g|Debug.Start|
|[comando Ir para](../../ide/reference/go-to-command.md)|GotoLn|Edit.GoTo|
|Ir para Chave|GotoBrace|Edit.GotoBrace|
|F1Help|Ajuda|Help.F1Help|
|Modo imediato|immed|Tools.ImmediateMode|
|Inserir Arquivo como Texto|InsertFile|Edit.InsertFileAsText|
|[Comando List Call Stack](../../ide/reference/list-call-stack-command.md)|kb|Debug.ListCallStack|
|Tornar Minúsculas|Lcase|Edit.MakeLowercase|
|Recortar Linha|LineCut|Edit.LineCut|
|Excluir linha|LineDel|Edit.LineDelete|
|Listar Membros|ListMembers|Edit.ListMembers|
|Janela Locais|Locais|Debug.Locals|
|[Comando de Saída de janela comando de log](../../ide/reference/log-command-window-output-command.md)|Log|Tools.LogCommandWindowOutput|
|Modo de marca da janela Comando|marca|Tools.CommandWindowMarkMode|
|Janela Memória|Memória Memory1|Debug.Memory1|
|Janela Memória 2|Memory2|Debug.Memory2|
|Janela Memória 3|Memory3|Debug.Memory3|
|Janela Memória 4|Memory4|Debug.Memory4|
|[Comando Definir Base](../../ide/reference/set-radix-command.md)|n|Debug.SetRadix|
|[Comando ShowWebBrowser](../../ide/reference/showwebbrowser-command.md)|nav navigate|View.ShowWebBrowser|
|Próximo Indicador|NextBook|Edit.NextBookmark|
|[Novo comando de arquivo](../../ide/reference/new-file-command.md)|nf|File.NewFile|
|Novo Projeto|np NewProj|File.NewProject|
|[Comando Open File](../../ide/reference/open-file-command.md)|of Open|File.OpenFile|
|[Comando Open Project](../../ide/reference/open-project-command.md)|op|File.OpenProject|
|Recolher para definições/Interromper estrutura de tópicos|OutlineDefs StopOutlining|Edit.CollapseToDefinitions|
|Depuração Parcial|p|Debug.StepOver|
|Informações de Parâmetro|ParamInfo|Edit.ParameterInfo|
|Depuração Circular|pr|Debug.StepOut|
|Indicador Anterior|PrevBook|Edit.PreviousBookmark|
|Imprimir arquivo|print|File.Print|
|Janela Propriedades|props|View.PropertiesWindow|
|Stop|q|Debug.StopDebugging|
|Refaz|refazer|Edit.Redo|
|Janela Registros|registros|Debug.Registers|
|Executar até o cursor|rtc|Debug.RunToCursor|
|Salvar Itens Selecionados|Salvar|File.SaveSelectedItems|
|Salvar Tudo|SaveAll|File.SaveAll|
|Salvar como|SaveAs|File.SaveSelectedItemsAs|
|[Comando Shell](../../ide/reference/shell-command.md)|shell|Tools.Shell|
|Parar Busca nos Arquivos|StopFind|Edit.FindInFiles /stop|
|Trocar âncora|SwapAnchor|Edit.SwapAnchor|
|Depuração Completa|t|Debug.StepInto|
|Tabular Seleção|tabular|Edit.TabifySelection|
|Janela Lista de Tarefas|TaskList|View.TaskList|
|Janela Threads|Threads|Debug.Threads|
|Lado a lado horizontalmente|TileH|Window.TileHorizontally|
|Organizar Lado a Lado Verticalmente|TileV|Window.TileVertically|
|Ativar/desativar Indicador|ToggleBook|Edit.ToggleBookmark|
|Janela caixa de ferramentas|caixa de ferramentas|View.Toolbox|
|[Comando Listar Desmontagem](../../ide/reference/list-disassembly-command.md)|u|Debug.ListDisassembly|
|Colocar em Maiúsculas|Ucase|Edit.MakeUppercase|
|Desfazer|desfazer|Edit.Undo|
|Cancelar Tabulação da Seleção|Cancelar Tabulação|Edit.UntabifySelection|
|Janela Inspecionar|Inspeção|Debug.WatchN|
|Ativar/Desativar Quebra Automática de Linha|WordWrap|Edit.ToggleWordWrap|
|Listar Processos|&#124;|Debug.ListProcesses|
|[Comando List Threads](../../ide/reference/list-threads-command.md)|~ ~*k ~\*kb|Debug.ListThreads Debug.ListTheads /AllThreads|

## <a name="see-also"></a>Confira também

- [Comandos do Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Janela Comando](../../ide/reference/command-window.md)
- [Caixa Localizar/Comando](../../ide/find-command-box.md)
