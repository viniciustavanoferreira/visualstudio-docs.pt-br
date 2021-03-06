---
title: Tutorial do Python no Visual Studio etapa 6, trabalhar com o Git
titleSuffix: ''
description: Etapa 6 de um passo a passo básico do Python no Visual Studio, abordando os recursos relacionados ao Git do Visual Studio.
ms.date: 01/28/2019
ms.topic: tutorial
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: cd8ebd706d9228d23eb5d5ce3b1429063bae55e5
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "72289709"
---
# <a name="step-6-work-with-git"></a>Etapa 6: Trabalhar com o Git

**Etapa anterior: [instalar pacotes e gerenciar o ambiente do Python](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

O Visual Studio fornece integração direta com repositórios locais do GIT e repositórios remotos em serviços como o GitHub e o Azure Repos. A integração inclui clonagem de um repositório, confirmação de alterações e gerenciamento de branches.

Este artigo fornece uma visão geral básica da criação de um repositório Git local para um projeto existente e visa familiarizar você com alguns dos recursos do Visual Studio relacionados ao Git.

1. Com um projeto aberto no Visual Studio, como o projeto da [etapa anterior](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md), clique com o botão direito do mouse na solução e selecione **Adicionar Solução ao Controle do Código-Fonte**. O Visual Studio cria um repositório local do Git que contém o código do projeto.

1. Quando o Visual Studio detecta que o projeto é gerenciado em um repositório do Git, controles relacionados com o Git também aparecem na parte inferior direita da janela do Visual Studio. Os controles mostram confirmações pendentes, alterações, o nome do repositório e o branch. Passe o mouse sobre os controles para ver informações adicionais.

    ![Informações adicionais são exibidas ao passar o mouse sobre um controle de Git na janela do Visual Studio](media/working-with-git-01.png)

1. Quando você cria um novo repositório ou seleciona qualquer um dos controles do Git, o Visual Studio abre a janela **Team Explorer**. (Você pode abrir a janela a qualquer momento com o comando Do menu > **Do'Soturação do Explorador** de exibição.) **View** A janela tem três painéis principais, que você alterna entre usar o drop-down no cabeçalho **do Team Explorer.** O painel **Sync,** que fornece operações de publicação, também aparece quando você seleciona o controle **Push** (o ícone da seta para cima):

    ![Team Explorer no Visual Studio depois de criar um repositório local](media/working-with-git-02.png)

1. Selecione **Alterações** (ou o controle do Git como ícone de lápis) para examinar as alterações não confirmadas e confirmá-las quando desejado.

    ![Team Explorer no Visual Studio mostrando as alterações não confirmadas](media/working-with-git-03.png)

    Clique duas vezes em um arquivo na lista **Alterações** para abrir um modo de exibição de comparação do arquivo:

    ![Modo de exibição de comparação para alterações em um arquivo](media/working-with-git-05.png)

1. Selecione **Branches** (ou o controle do Git com um nome de branch) para examinar os branches e executar operações de mesclagem e troca de base:

    ![Team Explorer no Visual Studio mostrando branches](media/working-with-git-04.png)

1. Selecionando o controle Git com o nome do repositório **(CosineWave** em uma imagem anterior), **o Team Explorer** mostra uma interface **Connect** com a qual você pode mudar rapidamente para outro repositório inteiramente.

1. Ao usar um repositório local, as alterações confirmadas vão diretamente para o repositório. Se você estiver conectado a um repositório remoto, selecione o cabeçalho de baixa no **Team Explorer,** escolha **Sincronizar** para alternar para a seção **Sincronização** e trabalhe com os comandos **Pull** and **Fetch** apresentados lá.

## <a name="go-deeper"></a>Aprofunde-se um pouco mais

Para um breve passo a passo da criação de um projeto a partir de um repositório remoto do Git, consulte [Quickstart: Clone um repositório de código Python no Visual Studio](quickstart-03-python-in-visual-studio-project-from-repository.md).

Para obter um tutorial muito mais abrangente, incluindo informações sobre como lidar com conflitos de mesclagem, revisar código com solicitações de pull, trocar a base e fazer cherry-picking de alterações entre branches, confira [Introdução ao GIT e ao Azure Repos](/azure/devops/repos/git/gitquickstart).

## <a name="tutorial-review"></a>Análise do tutorial

Parabéns por concluir este tutorial sobre Python no Visual Studio. Neste tutorial, você aprendeu como:

- Criar projetos e exibir o conteúdo do projeto.
- Use o editor de código e executar um projeto.
- Use a janela **Interativa** para desenvolver um novo código e copie facilmente esse código para o editor.
- Executar um programa concluído no depurador do Visual Studio.
- Instalar pacotes e gerenciar ambientes do Python.
- Trabalhar com o código em um repositório do Git.

Agora, explore os Conceitos e guias de Instruções, incluindo os seguintes artigos:

- [Criar uma extensão do C++ para o Python](working-with-c-cpp-python-in-visual-studio.md)
- [Publicar no Serviço de Aplicativo do Azure](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [Criação de perfil](profiling-python-code-in-visual-studio.md)
- [Teste de unidade](unit-testing-python-in-visual-studio.md)
