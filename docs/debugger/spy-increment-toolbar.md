---
title: Barra de ferramentas do Spy + + | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Spy++ toolbar
ms.assetid: 949c18fb-bb25-42ed-9130-c4a47869f24d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fa1dfe0917fece3c814678295c5abd6013b426b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72729732"
---
# <a name="spy-toolbar"></a>Barra de ferramentas do Spy++
A barra de ferramentas aparece na barra de menus no Spy + +. Para exibir ou ocultar a barra de ferramentas, no menu **Exibir** , clique em **barra de ferramentas**.

 Os controles a seguir estão disponíveis na barra de ferramentas.

## <a name="uielement-list"></a>Lista UIElement

|Botão|Efeito|
|------------|------------|
|![Botão&#43; &#43; do Windows do Spy](../debugger/media/icon_spy--_windows.gif "Icon_Spy + + _Windows")|Exibe um modo de exibição de árvore das janelas e dos controles no sistema. Para obter mais informações, consulte [exibição do Windows](../debugger/windows-view.md).|
|![Botão&#43; &#43; processos do Spy](../debugger/media/icon_spy--_processes.gif "Icon_Spy + + _Processes")|Exibe um modo de exibição de árvore dos processos no sistema. Para obter mais informações, consulte [exibição de processos](../debugger/processes-view.md).|
|![Botão&#43; &#43; de threads do Spy](../debugger/media/icon_spy--_threads.gif "Icon_Spy + + _Threads")|Exibe um modo de exibição de árvore dos threads no sistema. Para obter mais informações, consulte [exibição de threads](../debugger/threads-view.md).|
|![Botão&#43; &#43; mensagens do Spy](../debugger/media/icon_spy--_messages.gif "Icon_Spy + + embutidas")|Cria uma janela para exibir mensagens de janela e abre a caixa de diálogo **Opções de mensagem** para que você possa selecionar a janela cujas mensagens serão exibidas e também selecionar outras opções. Para obter mais informações, consulte [exibição de mensagens](../debugger/messages-view.md).|
|![Botão&#43; &#43; do Spy Start log](../debugger/media/icon_spy--_startlog.gif "Icon_Spy + + _StartLog")|Inicia o log de mensagens e exibe o fluxo de mensagens. Esse controle está disponível somente quando uma janela de **mensagens** é a janela ativa. Para obter mais informações, consulte [como: Iniciar e parar a exibição do log de mensagens](../debugger/how-to-start-and-stop-the-message-log-display.md).|
|![Botão&#43; &#43; de log do Spy Stop](../debugger/media/icon_spy--_stoplog.gif "Icon_Spy + + _StopLog")|Interrompe o log de mensagens e a exibição do fluxo de mensagens. Esse controle está disponível somente quando uma janela de **mensagens** é a janela ativa. Para obter mais informações, consulte [como: Iniciar e parar a exibição do log de mensagens](../debugger/how-to-start-and-stop-the-message-log-display.md).|
|![Botão&#43; &#43; opções de log do Spy](../debugger/media/icon_spy--_logoptions.gif "Icon_Spy + + _LogOptions")|Exibe a caixa de diálogo [Opções de mensagem](../debugger/message-options-dialog-box.md) . Use essa caixa de diálogo para selecionar os tipos de mensagem e do Windows para exibição. Esse controle está disponível somente quando uma janela de **mensagens** é a janela ativa.|
|![Botão&#43; &#43; limpar log do Spy](../debugger/media/spy--_clearlog.gif "Spy + + _ClearLog")|Limpa o conteúdo da janela de **mensagens** ativas. Esse controle está disponível somente quando uma janela de **mensagens** é a janela ativa.|
|![Botão&#43; &#43; de janela de localização do Spy](../debugger/media/icon_spy--_findwindow.gif "Icon_Spy + + _FindWindow")|Abre a caixa de diálogo [localizar janela](../debugger/find-window-dialog-box.md) , que permite definir critérios de pesquisa de janela e exibir propriedades ou mensagens. Para obter mais informações, consulte [como: usar a ferramenta Finder](../debugger/how-to-use-the-finder-tool.md).|
|![Botão&#43; &#43; localizar primeira janela do Spy](../debugger/media/icon_spy--_window.gif "Icon_Spy + + _Window")|Pesquisa a exibição atual de uma janela, processo, thread ou mensagem correspondente.|
|![Botão&#43; &#43; Localizar próxima janela do Spy](../debugger/media/icon_spy--_nextwindow.gif "Icon_Spy + + _NextWindow")|Pesquisa o modo de exibição atual para a próxima janela, processo, thread ou mensagem correspondente. Esse controle (e o comando de menu relacionado) está disponível somente quando há um resultado de pesquisa válido que não é exclusivo. Por exemplo, quando você usa um identificador de janela como o critério de pesquisa na árvore de janela, ele produz resultados exclusivos porque há apenas uma janela na árvore de janela que tem esse identificador; nesta instância, **Localizar próximo** não está disponível.|
|![Botão&#43; &#43; da janela Localizar anterior do Spy](../debugger/media/icon_spy--_prevwindow.gif "Icon_Spy + + _PrevWindow")|Pesquisa o modo de exibição atual da janela, processo, thread ou mensagem correspondente anterior. Esse controle (e o comando de menu relacionado) está disponível somente quando há um resultado de pesquisa válido que não é exclusivo. Por exemplo, quando você usa um identificador de janela como o critério de pesquisa na árvore de janela, ele produz resultados exclusivos porque há apenas uma janela na árvore de janela que tem esse identificador; nesta instância, **Localizar anterior** não está disponível.|
|![Botão&#43; &#43; do Gerenciador de propriedades do Spy](../debugger/media/icon_spy--_propexp.gif "Icon_Spy + + _PropExp")|Exibe as propriedades da janela selecionada no modo de exibição do Windows.|
|![Botão&#43; &#43; de atualização do Spy](../debugger/media/icon_spy--_refresh.gif "Icon_Spy + + _Refresh")|Atualiza as exibições do sistema.|

## <a name="see-also"></a>Consulte também
- [Usando Spy++](../debugger/using-spy-increment.md)
- [Exibições do Spy++](../debugger/spy-increment-views.md)
- [Referência a Spy++](../debugger/spy-increment-reference.md)