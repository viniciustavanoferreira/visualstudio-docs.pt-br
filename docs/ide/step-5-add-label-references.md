---
title: 'Etapa 5: Adicionar referências de rótulo'
ms.date: 11/04/2016
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
dev_langs:
- CSharp
- VB
ms.assetid: d418350c-0396-494e-8149-71fa61b395c5
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de89d7194425e1a8cba9e11f2734372d80b256b3
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "77579333"
---
# <a name="step-5-add-label-references"></a>Etapa 5: Adicionar referências de rótulo
O programa precisa rastrear quais controles de rótulo o jogador escolhe. Atualmente, o programa mostra todos os rótulos escolhidos pelo jogador. Mas isso será alterado. Depois que o primeiro rótulo é escolhido, o programa deve mostrar o ícone do rótulo. Depois que o segundo rótulo é escolhido, o programa deve exibir ambos os ícones por um breve momento e depois ocultá-los novamente. Agora seu programa rastreará qual controle de rótulo será escolhido primeiro e qual será escolhido em segundo usando *variáveis de referência*.

## <a name="to-add-label-references"></a>Para adicionar referências de rótulo

1. Adicione referências de rótulo ao seu formulário usando o código a seguir.

     [!code-vb[VbExpressTutorial4Step5#5](../ide/codesnippet/VisualBasic/step-5-add-label-references_1.vb)]
     [!code-csharp[VbExpressTutorial4Step5#5](../ide/codesnippet/CSharp/step-5-add-label-references_1.cs)]

     > [!IMPORTANT]
     > Use o controle de linguagem de programação no canto superior direito desta página para exibir o trecho de código C# ou o trecho de código Visual Basic.<br><br>![Controle de linguagem de programação para Docs.Microsoft.com](../ide/media/docs-programming-language-control.png)

     Essas variáveis de referência parecem semelhantes às instruções que você usou anteriormente para adicionar objetos (como os objetos <xref:System.Windows.Forms.Timer>, <xref:System.Collections.Generic.List%601> e <xref:System.Random>) ao formulário. No entanto, essas instruções não fazem com que os dois controles de rótulo extras apareçam no formulário, pois a palavra-chave `new` não foi usada em nenhuma das duas instruções. Sem a palavra-chave `new`, nenhum objeto é criado. Por esse motivo `firstClicked` e `secondClicked` são chamadas de variáveis de referência: elas rastreiam (ou fazem referência a) os objetos Label.

     Quando uma variável não está acompanhando um objeto, ela é `null` definida como `Nothing` um valor reservado especial: em C# e no Visual Basic. Desse modo, quando o programa for iniciado, `firstClicked` e `secondClicked` serão definidas como `null` ou `Nothing`, o que significa que as variáveis não estão rastreando nada.

2. Modifique o manipulador de eventos <xref:System.Windows.Forms.Control.Click> para usar a nova variável de referência `firstClicked`. Remova a última instrução no método do manipulador de eventos `label_Click()` (`clickedLabel.ForeColor = Color.Black;`) e substitua-a pela instrução `if` que se segue. (Não se esqueça de incluir o comentário e a instrução `if` inteira.)

     [!code-vb[VbExpressTutorial4Step5#6](../ide/codesnippet/VisualBasic/step-5-add-label-references_2.vb)]
     [!code-csharp[VbExpressTutorial4Step5#6](../ide/codesnippet/CSharp/step-5-add-label-references_2.cs)]

3. Salve e execute seu programa. Escolha um dos controles de rótulo e seu ícone é exibido.

4. Escolha o próximo controle de rótulo e observe que nada acontece. O programa já está acompanhando o primeiro rótulo `firstClicked` que o jogador `null` escolheu, `Nothing` então não é igual a C# ou no Visual Basic. Quando sua instrução `if` verifica `firstClicked` para determinar se ele é igual a `null` ou `Nothing`, ela descobre que não é e não executa as instruções na instrução `if`. Assim, apenas o primeiro ícone escolhido fica preto, e os outros ícones são invisíveis, como mostrado na imagem a seguir.

     ![Jogo da memória mostrando um ícone](../ide/media/express_tut4step5.png)<br/>
***Jogo correspondente*** *mostrando um ícone*

     Essa situação será corrigida na primeira etapa do tutorial adicionando um controle **Temporizador**.

## <a name="to-continue-or-review"></a>Para continuar ou revisar

- Para ir para a próxima etapa do tutorial, consulte **[Passo 6: Adicione um temporizador](../ide/step-6-add-a-timer.md)**.

- Para retornar à etapa anterior do tutorial, veja [Etapa 4: Adicionar um manipulador de eventos Click a cada rótulo](../ide/step-4-add-a-click-event-handler-to-each-label.md).
