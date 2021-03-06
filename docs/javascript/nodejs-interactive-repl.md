---
title: Usar o REPL do Node.js
description: O Visual Studio fornece suporte para interação com o runtime do Node.js
ms.date: 12/04/2018
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: faed930c60869010f740cf0a1e118a40299ce782
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62840648"
---
# <a name="work-with-the-nodejs-interactive-window"></a>Trabalhar com a janela interativa do Node.js

As Ferramentas Node.js para Visual Studio incluem uma janela interativa para o runtime do Node.js instalado. Essa janela permite que você insira o código JavaScript e veja os resultados imediatamente, bem como executar comandos npm para interagir com o projeto atual. A janela interativa também é conhecida como um REPL (**R**ead/**E**valuate/**P**rint **L**oop).

## <a name="open-the-interactive-window"></a>Abrir a janela interativa

Abra a janela interativa clicando com o botão direito do mouse no nó do projeto Node.js no Gerenciador de Soluções e selecionando **Abrir Janela Interativa do Node.js**.

![Janela interativa do Node.js no menu de contexto do projeto](../javascript/media/interactivewindow-open-from-project.png)

As teclas de atalho padrão para abrir a janela interativa Node.js são **[CTRL] + K, N**. Ou, você pode abrir a janela da barra de ferramentas escolhendo **Exibir** > Janela Interativa do**Windows** > **Node.js**.

## <a name="use-the-repl"></a>Usar o REPL

Depois de abrir a janela, você poderá inserir comandos.

![Janela interativa do Node.js](../javascript/media/interactivewindow.png)

A janela interativa tem vários comandos internos, que começam com um prefixo de ponto para diferenciá-los das funções JavaScript declaradas. Há suporte para os seguintes comandos:

**.cls, .clear** Limpa o conteúdo da janela do editor, deixando intactos o histórico e o contexto de execução.

**.help** Exibe a ajuda do comando especificado ou de todos os comandos disponíveis e as associações de teclas, caso nenhum seja especificado.

**.info** Mostra informações sobre o executável do Node.js atual usado.

**.npm** Executa um comando npm. Se a solução contiver mais de um projeto, especifique o projeto de destino usando `.npm [projectname] <npm arguments>`.

**.reset** Redefine o ambiente de execução para o estado inicial, mantendo o histórico.

**.save** Salva a sessão atual do REPL em um arquivo.