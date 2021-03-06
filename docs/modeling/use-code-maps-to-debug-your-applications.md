---
title: Usar mapas de códigos para depurar aplicativos
ms.date: 09/28/2018
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, visualizing code
- Visual Studio Ultimate, navigating code visually
- Visual Studio Ultimate, understanding code
- Visual Studio Ultimate, mapping code relationships
- Visual Studio Ultimate, code maps
- mapping code relationships
- code maps
- mapping relationships in code
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e01857878f927c619529d3bbfc63728f84f0b81d
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75594104"
---
# <a name="use-code-maps-to-debug-your-applications"></a>Usar mapas de códigos para depurar aplicativos

Os mapas de código podem ajudá-lo a evitar a perda em grandes bases de código, código desconhecido ou código herdado. Por exemplo, quando você estiver Depurando, talvez seja necessário examinar o código em vários arquivos e projetos. Use mapas de código para navegar pelas partes do código e entender as relações entre eles. Dessa forma, você não precisa acompanhar esse código em seu cabeçalho ou desenhar um diagrama separado. Portanto, quando seu trabalho é interrompido, os mapas de código ajudam a atualizar sua memória sobre o código no qual você está trabalhando.

![&#45; Mapa de código mapeia relações no código](../modeling/media/codemapstoryboardpaint.png)

**Uma seta verde mostra onde o cursor aparece no editor**

Para obter detalhes dos comandos e ações que você pode usar ao trabalhar com mapas de código, consulte [procurar e reorganizar mapas de código](../modeling/browse-and-rearrange-code-maps.md).

> [!NOTE]
> Para criar e editar mapas de código, você precisa de Visual Studio Enterprise edição. Nas edições Visual Studio Community e Professional, você pode abrir diagramas gerados no Enterprise Edition, mas não pode editá-los.

## <a name="understand-the-problem"></a>Compreender o problema
 Suponhamos que haja um bug em um programa de desenho no qual você está trabalhando. Para reproduzir o bug, abra a solução no Visual Studio e pressione **F5** para iniciar a depuração.

 Quando você desenha uma linha e escolhe **desfazer meu último traço**, nada acontece até que você desenhe a próxima linha.

 ![Bug de &#45; reprodução do mapa de código](../modeling/media/codemapstoryboardpaint0.png)

 Assim, você começa a investigação procurando o método `Undo`. Você o encontra na classe `PaintCanvas`.

 ![Código de &#45; localização de mapa de código](../modeling/media/codemapstoryboardpaint1.png)

## <a name="start-mapping-the-code"></a>Começar a mapear o código
 Agora, comece a mapear o método `undo` e suas relações. No editor de códigos, você adiciona o método `undo` e os campos aos quais faz referência a um novo mapa de códigos. Quando você cria um novo mapa, ele pode demorar algum tempo para indexar o código. Isso ajuda a executar mais rapidamente as operações posteriores.

 ![Método de &#45; exibição de mapa de código e campos relacionados](../modeling/media/codemapstoryboardpaint3.png)

> [!TIP]
> O realce verde mostra os últimos itens que foram adicionados ao mapa. A seta verde mostra a posição do cursor no código. As setas entre os itens representam relações diferentes. Você pode obter mais informações sobre os itens no mapa movendo o mouse sobre eles e examinando suas dicas de ferramenta.

 ![Mapa &#45; de códigos Mostrar dicas de ferramenta](../modeling/media/codemapstoryboardpaint4.png)

## <a name="navigate-and-examine-code-from-the-map"></a>Navegar e examinar o código no mapa
 Para ver a definição de código de cada campo, clique duas vezes no campo no mapa ou selecione o campo e pressione **F12**. A seta verde alterna itens no mapa. O cursor no editor de códigos também se move automaticamente.

 ![Definição de &#45; campo de exame de mapa de código](../modeling/media/codemapstoryboardpaint5.png)

 ![Definição de &#45; campo de exame de mapa de código](../modeling/media/codemapstoryboardpaint5a.png)

> [!TIP]
> Também é possível mover a seta verde no mapa movendo-se o cursor no editor de códigos.

## <a name="understand-relationships-between-pieces-of-code"></a>Compreender as relações entre as partes do código
 Agora você deseja saber qual o outro código interage com os campos `history` e `paintObjects`. É possível adicionar todos os métodos que referenciam esses campos no mapa. Você pode fazer isso no mapa ou no editor de código.

 ![Mapa &#45; de códigos localizar todas as referências](../modeling/media/codemapstoryboardpaint6.png)

 ![Abrir um mapa de código no editor de códigos](../modeling/media/codemapstoryboardpaint6a.png)

> [!NOTE]
> Se você adicionar itens de um projeto que é compartilhado entre vários aplicativos, como Windows Phone ou a Windows Store, esses itens sempre aparecerão com o projeto de aplicativo ativo atualmente no mapa. Portanto, se você alterar o contexto para outro projeto de aplicativo, o contexto no mapa também será alterado para todos os itens adicionados recentemente do projeto compartilhado. Operações realizadas com um item no mapa se aplicam apenas aos itens que compartilham o mesmo contexto.

 Altere o layout para reorganizar o fluxo de relações e para facilitar a leitura do mapa. Também é possível mover itens pelo mapa arrastando-os.

 ![Layout de &#45; alteração do mapa de código](../modeling/media/codemapstoryboardpaint7a.png)

> [!TIP]
> Por padrão, **layout incremental** é ativado. Isso reorganiza o mapa o menos possível quando você adiciona novos itens. Para reorganizar todo o mapa toda vez que adicionar novos itens, desative o **layout incremental**.

 ![Layout de &#45; alteração do mapa de código](../modeling/media/codemapstoryboardpaint7.png)

 Vamos examinar esses métodos. No mapa, clique duas vezes no método **PaintCanvas** ou selecione esse método e pressione **F12**. Você aprende que esse método cria `history` e `paintObjects` como listas vazias.

 ![Definição do &#45; método de exame do mapa de códigos](../modeling/media/codemapstoryboardpaint8.png)

 Agora repita as mesmas etapas para examinar a definição do método `clear`. Você aprende que `clear` realiza algumas tarefas com `paintObjects` e `history`. Em seguida, ele chama o método `Repaint`.

 ![Definição do &#45; método de exame do mapa de códigos](../modeling/media/codemapstoryboardpaint9.png)

 Agora examine a definição do método `addPaintObject`. Ele também realiza algumas tarefas com `history` e `paintObjects`. Ele também chama `Repaint`.

 ![Definição do &#45; método de exame do mapa de códigos](../modeling/media/codemapstoryboardpaint10.png)

## <a name="find-the-problem-by-examining-the-map"></a>Encontre o problema examinando o mapa
 Aparentemente, todos os métodos que modificam `history` e `paintObjects` chamam `Repaint`. Ainda assim, o método `undo` não chama `Repaint`, mesmo que `undo` modifique os mesmos campos. Então você acha que é possível corrigir esse problema chamando `Repaint` em `undo`.

 ![Localizar chamada &#45; de método ausente no mapa de códigos](../modeling/media/codemapstoryboardpaint11.png)

 Se você não tivesse um mapa para mostrar essa chamada perdida, poderia ser bem mais difícil encontrar esse problema, especialmente com um código mais complexo.

## <a name="share-your-discovery-and-next-steps"></a>Compartilhar a descoberta e as próximas etapas
 Antes de você ou alguma outra pessoa corrigir esse bug, é possível fazer anotações no mapa sobre o problema e como corrigi-lo.

 ![Itens de &#45; comentário e sinalizador de mapa de código para acompanhamento](../modeling/media/codemapstoryboardpaint12.png)

 Por exemplo, é possível adicionar comentários ao mapa e sinalizar itens usando cores.

 ![Mapa &#45; de código comentado e itens sinalizados](../modeling/media/codemapstoryboardpaint12a.png)

 Se tiver o Microsoft Outlook instalado, você poderá enviar por email o mapa para outras pessoas. Também é possível exportar o mapa como uma imagem ou em outro formato.

 ![Mapa &#45; de código compartilhar, exportar, email](../modeling/media/codemapstoryboardpaint13.png)

## <a name="fix-the-problem-and-show-what-you-did"></a>Corrigir o problema e mostrar o que você fez
 Para corrigir esse bug, adicione a chamada de `Repaint` ao `undo`.

 ![Adicionar chamada &#45; de método ausente ao mapa de códigos](../modeling/media/codemapstoryboardpaint14.png)

 Para confirmar a correção, reinicie a sessão de depuração e tente reproduzir o erro. Agora, escolher **desfazer meu último traço** funciona conforme o esperado e confirma que você fez a correção correta.

 ![Correção de &#45; código de confirmação de mapa de código](../modeling/media/codemapstoryboardpaint15.png)

 É possível atualizar o mapa para mostrar a correção feita.

 ![Mapa de &#45; atualização do mapa de códigos com chamada de método ausente](../modeling/media/codemapstoryboardpaint16.png)

 O mapa agora mostra um link entre **desfazer** e **redesenhar**.

 ![Mapa &#45; de códigos atualizado no mapa com a chamada de método](../modeling/media/codemapstoryboardpaint17.png)

> [!NOTE]
> Ao atualizar o mapa, você talvez veja uma mensagem afirmando que o índice de código usado para criar o mapa foi atualizado. Isso significa que alguém alterou o código, o que faz o mapa não corresponder ao código atual. Isso não impede você de atualizar o mapa, mas talvez precise recriar o mapa para confirmar se ele corresponde ao código.

 Agora você concluiu sua investigação. Você encontrou e corrigiu o problema com êxito mapeando o código. Você também tem um mapa que ajuda a navegar no código, lembrar o que aprendeu e mostra as etapas que você seguiu para corrigir o problema.

## <a name="see-also"></a>Consulte também

- [Mapear métodos na pilha de chamadas ao depurar](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Visualizar código](../modeling/visualize-code.md)
