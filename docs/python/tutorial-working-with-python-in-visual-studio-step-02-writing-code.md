---
title: Etapa 2 do Tutorial do Python no Visual Studio, escrever e executar o código
titleSuffix: ''
description: Etapa 2 de um passo a passo básico das funcionalidades do Python no Visual Studio, incluindo como editar código e executar um projeto.
ms.date: 01/28/2019
ms.topic: tutorial
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: fda68b9e5bffbd1afab3389a0d8d624312a8de3f
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "62429984"
---
# <a name="step-2-write-and-run-code"></a>Etapa 2: Escrever e executar código

**Etapa anterior: [Criar um novo projeto do Python](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)**

Embora **o Solution Explorer** seja onde você gerencia arquivos de projeto, a janela do *editor* é tipicamente onde você trabalha com o *conteúdo* de arquivos, como código-fonte. O editor tem reconhecimento contextual do tipo de arquivo que você está editando, incluindo a linguagem de programação (com base na extensão do arquivo) e oferece recursos apropriados para essa linguagem, como a coloração de sintaxe e o preenchimento automático usando o IntelliSense.

1. Depois de criar um novo projeto do "Aplicativo Python", um arquivo vazio padrão chamado *PythonApplication1.py* é aberto no editor do Visual Studio.

1. No editor, comece digitando `print("Hello, Visual Studio")` e observe como o Visual Studio IntelliSense exibe opções de preenchimento automático durante a digitação. A opção delineada na lista de desímpara das audações é a conclusão padrão usada quando você pressiona a **tecla Tab.** As conclusões são mais úteis quando instruções ou identificadores mais longos estão envolvidos.

    ![Pop-up de preenchimento automático do IntelliSense](media/vs-getting-started-python-04-IntelliSense1b.png)

1. O IntelliSense mostra diferentes informações, dependendo da instrução que está sendo usada, da função que está sendo chamada e assim por diante. Com a função `print`, ao digitar `(` depois de `print` para indicar uma chamada função, as informações de uso completas dessa função são exibidas. O pop-up do IntelliSense também mostra o argumento atual em negrito (**valor** conforme mostrado aqui):

    ![Pop-up de preenchimento automático do IntelliSense em uma função](media/vs-getting-started-python-05-IntelliSense2b.png)

1. Preencha a instrução para que ela corresponda ao seguinte:

    ```python
    print("Hello, Visual Studio")
    ```

1. Observe a coloração de sintaxe que diferencia a instrução `print` do argumento `"Hello Visual Studio"`. Além disso, exclua temporariamente a última `"` na cadeia de caracteres e observe como o Visual Studio mostra um sublinhado vermelho para o código que contém erros de sintaxe. Então, substitua o `"` para corrigir o código.

    ![Coloração de sintaxe e realce de erros do IntelliSense](media/vs-getting-started-python-06-IntelliSense3b.png)

    > [!Tip]
    > Como o ambiente de desenvolvimento é uma questão muito pessoal, o Visual Studio oferece controle total sobre a aparência e o comportamento do Visual Studio. Selecione o comando de menu**Opções** **de ferramentas** > e explore as configurações nas guias **Ambiente** e Editor **de Texto.** Por padrão, você vê somente um número limitado de opções; para ver todas as opções de todas as linguagens de programação, selecione **Mostrar todas as configurações** na parte inferior da caixa de diálogo.

1. Execute o código que você escreveu até agora pressionando **Ctrl**+**F5** ou selecionando **Debug** > **Start sem depuração** do item do menu. O Visual Studio avisará se ainda houver erros em seu código.

1. Quando você executa o programa, uma janela de console aparece exibindo os resultados, assim como seria se você executasse um interpretador do Python com *PythonApplication1.py*, usando a linha de comando. Pressione uma tecla para fechar a janela e retornar ao editor do Visual Studio.

    ![Saída da primeira execução do programa](media/vs-getting-started-python-07-output.png)

1. Além das conclusões para instruções e funções, o IntelliSense fornece preenchimentos para instruções `import` e `from` do Python. Esses preenchimentos ajudam você a descobrir com facilidade quais módulos estão disponíveis no ambiente e os membros desses módulos. No editor, exclua a linha `print` e comece a digitar `import`. Uma lista de módulos é exibida quando você digita o espaço:

    ![IntellSense mostrando os módulos disponíveis para uma instrução de importação](media/vs-getting-started-python-08-import1.png)

1. Preencha a linha digitando ou selecionando `sys`.

1. Na próxima linha, digite `from` para ver uma lista de módulos novamente:

    ![IntellSense mostrando os módulos disponíveis para uma instrução From](media/vs-getting-started-python-09-import2.png)

1. Selecione ou digite `math` e continue digitando com um espaço e `import`, o que exibe os membros do módulo:

    ![IntellSense mostrando membros do módulo](media/vs-getting-started-python-10-import3.png)

1. Conclua com a importação dos membros `sin`, `cos` e `radians`, observando os preenchimentos automáticos disponíveis para cada um. Quando terminar, o código deverá ser exibido da seguinte maneira:

    ```python
    import sys
    from math import cos, radians
    ```

    > [!Tip]
    > Os preenchimentos trabalham com subcadeias de caracteres durante a digitação, encontrando a correspondência de partes de palavras, letras no início de palavras e até mesmo caracteres ignorados. Confira [Editar o código – Preenchimentos](editing-python-code-in-visual-studio.md#completions) para obter detalhes.

1. Adicione um pouco mais de código para imprimir os valores de cosseno para 360 graus:

    ```python
    for i in range(360):
        print(cos(radians(i)))
    ```

1. Execute o programa novamente com **Ctrl**+**F5** ou **Debug** > **Start sem depuração**. Quando terminar, feche a janela de saída.

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Use a janela REPL interativa](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md)

## <a name="go-deeper"></a>Aprofunde-se um pouco mais

- [Editar código](editing-python-code-in-visual-studio.md)
- [Código de formatação](formatting-python-code.md)
- [Código de refatoração](refactoring-python-code.md)
- [Usar PyLint](linting-python-code.md)
