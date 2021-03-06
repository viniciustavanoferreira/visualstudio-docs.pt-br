---
title: Introdução à edição para desenvolvedores do C#
description: Esta introdução de 10 minutos ao editor de códigos do Visual Studio mostra algumas das formas pelas quais o Visual Studio facilita a escrita, a navegação e o entendimento do código C#.
ms.custom: seodec18, get-started
ms.date: 11/20/2018
ms.technology: vs-ide-general
ms.topic: tutorial
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 0cacd56ff6b3b3510505ca2752404b55a2771429
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "75590430"
---
# <a name="learn-to-use-the-code-editor"></a>Saiba como usar o editor de códigos

Nesta introdução de 10 minutos ao editor de código do Visual Studio, adicionaremos o código a um arquivo para ver algumas das formas pelas quais o Visual Studio facilita a escrita, a navegação e o entendimento do código.

::: moniker range="vs-2017"

> [!TIP]
> Se você ainda não instalou o Visual Studio, vá para a página [de downloads](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) do Visual Studio para instalá-lo gratuitamente.

::: moniker-end

::: moniker range="vs-2019"

> [!TIP]
> Se você ainda não instalou o Visual Studio, vá para a página [de downloads](https://visualstudio.microsoft.com/downloads) do Visual Studio para instalá-lo gratuitamente.

::: moniker-end

Este artigo pressupõe que você já esteja familiarizado com o C#. Caso contrário, sugerimos que você primeiro examine um tutorial, como [Introdução ao C# e ao ASP.NET Core no Visual Studio](tutorial-aspnet-core.md).

> [!TIP]
> Para acompanhar este artigo, verifique se você tem as configurações do C# selecionadas para o Visual Studio. Para obter informações sobre como selecionar configurações para o IDE (ambiente de desenvolvimento integrado), confira [Selecionar configurações de ambiente](visual-studio-ide.md#select-environment-settings).

## <a name="create-a-new-code-file"></a>Criar um novo arquivo de código

Comece criando um novo arquivo e adicionando códigos nele.

::: moniker range="vs-2017"

1. Abra o Visual Studio.

::: moniker-end

::: moniker range=">=vs-2019"

1. Abra o Visual Studio. Pressione **Esc** ou clique em **Continuar sem código** na janela de início para abrir o ambiente de desenvolvimento.

::: moniker-end

2. No menu **Arquivo** na barra de menu, escolha **Arquivo Novo** > **ou** **pressione Ctrl**+**N**.

3. Na caixa de diálogo **Novo Arquivo**, na categoria **Geral**, escolha **Classe do Visual C#** e, então, selecione **Abrir**.

   Um novo arquivo é aberto no editor com o esqueleto de uma classe de C#. (Observe que não precisamos criar um projeto completo do Visual Studio para obter alguns dos benefícios que o editor de códigos oferece; basta ter um arquivo de código!)

   ![Arquivo de código C# no Visual Studio](../media/tutorial-editor.png)

## <a name="use-code-snippets"></a>Usar snippets de código

O Visual Studio fornece *snippets de código* úteis que você pode usar para gerar os blocos de código usados com frequência de forma rápida e fácil. Os [snippets de código](../../ide/code-snippets.md) estão disponíveis para linguagens de programação diferentes, incluindo C#, Visual Basic e C++. Vamos adicionar o snippet `void Main` de C# em nosso arquivo.

1. Coloque o cursor logo acima **}** da cinta de fechamento `svm` final } `static void Main` &mdash;no arquivo e digite os caracteres (o que significa não se preocupe muito se você não sabe o que isso significa).

   Uma caixa de diálogo pop-up é exibida com informações sobre o snippet de código `svm`.

   ![IntelliSense para o snippet de código no Visual Studio](../media/tutorial-intellisense-snippet.png)

1. Pressione a **Guia** duas vezes para inserir o snippet de código.

   Você verá que a assinatura do método `static void Main()` será adicionada ao arquivo. O método [Main()](/dotnet/csharp/programming-guide/main-and-command-args/) é o ponto de entrada para aplicativos C#.

Os snippets de código disponíveis variam em linguagens de programação diferentes. Você pode olhar os trechos de código disponíveis para o seu idioma escolhendo **Editar** > **intesteja** > **o Snippet** ou pressionando **Ctrl**+**K**, **Ctrl**+**X**e, em seguida, escolhendo a pasta do seu idioma. Para o C#, a lista tem este aspecto:

![Lista de snippet de código de C#](../media/tutorial-code-snippet-list.png)

A lista inclui snippets para a criação de uma [classe](/dotnet/csharp/programming-guide/classes-and-structs/classes), um [construtor](/dotnet/csharp/programming-guide/classes-and-structs/constructors), um loop [for](/dotnet/csharp/language-reference/keywords/for), uma instrução [if](/dotnet/csharp/language-reference/keywords/if-else) ou [switch](/dotnet/csharp/language-reference/keywords/switch) e muito mais.

## <a name="comment-out-code"></a>Comentar o código

A barra de ferramentas, que é a linha de botões sob a barra de menus no Visual Studio, pode ajudar a aumentar sua produtividade durante a codificação. Por exemplo, você pode alternar o modo de preenchimento do IntelliSense (o [IntelliSense](../../ide/using-intellisense.md) é um recurso de codificação que exibe uma lista de correspondência de métodos, entre outras coisas), aumentar ou diminuir um recuo de linha ou comentar um código que você não deseja compilar. Nesta seção, comentaremos alguns códigos.

![Barra de ferramentas do editor](../media/tutorial-editor-toolbar.png)

1. Cole o código a seguir no corpo do método `Main()`.

    ```csharp
    // _words is a string array that we'll sort alphabetically
    string[] _words = {
        "the",
        "quick",
        "brown",
        "fox",
        "jumps"
    };

    string[] morewords = {
        "over",
        "the",
        "lazy",
        "dog"
    };

    IEnumerable<string> query = from word in _words
                                orderby word.Length
                                select word;
    ```

1. Não estamos usando a variável `morewords`, mas podemos usá-la mais tarde. Portanto, não queremos excluí-la por completo. Em vez disso, vamos comentar as linhas. Selecione a definição inteira de `morewords` até o ponto e vírgula de fechamento e, em seguida, escolha o botão **Comentar as linhas selecionadas** na barra de ferramentas. Se preferir usar o teclado, **pressione Ctrl**+**K,** **Ctrl**+**C**.

   ![Botão de comentários](../media/tutorial-comment-out.png)

   Os caracteres de comentários `//` de C# são adicionados ao início de cada linha selecionada para comentar o código.

## <a name="collapse-code-blocks"></a>Recolher blocos de código

Não queremos ver o [construtor](/dotnet/csharp/programming-guide/classes-and-structs/constructors) vazio para `Class1` que foi gerado. Portanto, para desobstruir nossa exibição do código, vamos recolhê-la. Escolha a pequena caixa cinza com o sinal de subtração dentro da margem da primeira linha do construtor. Ou, se você é um usuário de teclado, coloque o cursor em qualquer lugar no código do construtor e **pressione Ctrl**+**M**, **Ctrl**+**M**.

![Botão Recolher estrutura de tópicos](../media/tutorial-collapse.png)

O bloco de código é recolhido apenas na primeira linha, seguido por um sinal de reticências (`...`). Para expandir o bloco de código novamente, clique na mesma caixa cinza que agora tem um sinal de mais nele, ou pressione **Ctrl**+**M**, **Ctrl**+**M** novamente. Este recurso é chamado [de Delineamento](../../ide/outlining.md) e é especialmente útil quando você está colapsando métodos longos ou classes inteiras.

## <a name="view-symbol-definitions"></a>Exibir definições de símbolo

O editor do Visual Studio facilita a inspeção da definição de um tipo, método, etc. Uma maneira é navegar até o arquivo que contém a definição, por exemplo, escolhendo **Ir para Definição** ou pressionando **F12** em qualquer lugar que o símbolo seja referenciado. Uma maneira ainda mais rápida que não move o foco para fora do arquivo em que você está trabalhando é usar a opção [Inspecionar Definição](../../ide/go-to-and-peek-definition.md#peek-definition). Vamos espiar a definição do tipo `string`.

1. Clique com o botão direito do mouse em qualquer ocorrência de `string` e escolha **Espiar Definição** no menu de conteúdo. Ou, pressione **Alt**+**F12**.

   Uma janela pop-up será exibida com a definição da classe `String`. Você pode rolar na janela pop-up ou até mesmo inspecionar a definição de outro tipo do código inspecionado.

   ![Inspecionar janela de definição](../media/tutorial-peek-definition.png)

1. Feche a janela de definição inspecionada ao selecionar a caixa pequena com um “x” no canto superior direito da janela pop-up.

## <a name="use-intellisense-to-complete-words"></a>Usar o IntelliSense para completar palavras

[O IntelliSense](../../ide/using-intellisense.md) é um recurso inestimável quando você está codificando. Ele pode mostrar informações sobre membros disponíveis de um tipo ou detalhes de parâmetros para sobrecargas diferentes de um método. Você também pode usar o IntelliSense para completar uma palavra depois que você digitar caracteres suficientes para desambiguá-la. Vamos adicionar uma linha de código para imprimir as cadeias de caracteres ordenadas na janela de console, que é o local padrão para envio da saída do programa.

1. Abaixo da variável `query`, comece a digitar o código a seguir:

   ```csharp
   foreach (string str in qu
   ```

   Você verá o IntelliSense mostrar as **Informações Rápidas** sobre o símbolo `query`.

   ![Preenchimento de palavras do IntelliSense no Visual Studio](../media/tutorial-intellisense-completion-list.png)

1. Para inserir o restante da palavra `query` usando a funcionalidade de preenchimento de palavras do IntelliSense, pressione **Tab**.

1. Finalize o bloco de código para que ele se pareça com o seguinte código. Você mesmo pode praticar usando os snippets de código novamente ao inserir `cw` e, então, pressionar a **Guia** duas vezes para gerar o código `Console.WriteLine`.

   ```csharp
   foreach (string str in query)
   {
      Console.WriteLine(str);
   }
   ```

## <a name="refactor-a-name"></a>Refatorar um nome

Ninguém obtém o código correto na primeira vez e uma das coisas que talvez você precise alterar é o nome de uma variável ou de um método. Vamos experimentar a funcionalidade de [refatorar](../../ide/refactoring-in-visual-studio.md) do Visual Studio para renomear a variável `_words` como `words`.

1. Coloque o cursor sobre `_words` a definição da variável e escolha **Renomear** no menu de clique siou ou contexto, ou **pressione Ctrl**+**R,** **Ctrl**+**R**.

   Uma caixa de diálogo pop-up chamada **Renomear** aparecerá no canto superior direito do editor.

1. Insira o nome desejado **words**. Observe que a referência ao `words` na consulta também será renomeada automaticamente. Antes de pressionar **Enter**, marque a caixa de seleção **Incluir Comentários** na caixa pop-up **Renomear**.

   ![Caixa de diálogo Renomear](../media/tutorial-rename.png)

1. Pressione **Enter**.

   As duas ocorrências de `words` foram renomeadas, bem como a referência ao `words` do comentário de código.

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Saiba mais sobre projetos e soluções](../tutorial-projects-solutions.md)

## <a name="see-also"></a>Confira também

- [Snippets de código](../../ide/code-snippets.md)
- [Navegue pelos códigos](../../ide/navigating-code.md)
- [Estrutura de tópicos](../../ide/outlining.md)
- [Ir para Definição e Definição de Pico](../../ide/go-to-and-peek-definition.md)
- [Refatoração](../../ide/refactoring-in-visual-studio.md)
- [Usar o IntelliSense](../../ide/using-intellisense.md)
