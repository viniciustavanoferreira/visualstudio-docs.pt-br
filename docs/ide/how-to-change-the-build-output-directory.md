---
title: Como alterar o diretório de saída do build
ms.date: 05/15/2019
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 37342796f2dd94138136bb837cf6007d19d350c4
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "76114260"
---
# <a name="how-to-change-the-build-output-directory"></a>Como alterar o diretório de saída do build

Você pode especificar o local de saída gerado pelo seu projeto por configuração (para depuração, versão ou ambas).

## <a name="change-the-build-output-directory"></a>Alterar o diretório de saída do build

1. Para abrir as páginas de propriedades do projeto, clique com o botão direito do mouse no nó do projeto no **Gerenciador de Soluções** e selecione **Propriedades**.

2. Selecione a guia apropriada com base no tipo de projeto:

   - Para C#, selecione a guia **Compilar**.
   - Para o Visual Basic, selecione a guia **Compilar**.
   - Para C++ ou JavaScript, selecione a guia **Geral**.

3. Na lista suspensa de configuração na parte superior, escolha a configuração cujo local do arquivo de saída você deseja alterar (**Depuração**, **Versão** ou **Todas as Configurações**).

4. Localize a entrada de caminho de saída na página&mdash;ele é diferente, dependendo de seu tipo de projeto:

   - **Caminho de saída** para projetos C# e JavaScript
   - **Caminho de saída de build** para projetos Visual Basic
   - **Diretório de saída** para projetos Visual C++

   Digite o caminho para o qual gerar a saída (absoluto ou relativo para o diretório raiz do projeto), ou escolha **Procurar** para, em vez disso, navegar até essa pasta.

   ![Propriedade de caminho de saída para um projeto C# do Visual Studio](media/output-path.png)
   
   > [!NOTE]
   > Alguns projetos incluirão, por padrão, framework e tempo de execução no caminho de compilação. Para alterar isso, clique com o botão direito do mouse no nó do projeto no **Solution Explorer,** selecione **Editar arquivo de**projeto e adicione o seguinte:
   > ```xml
   > <PropertyGroup>
   >   <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
   >   <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
   > </PropertyGroup>
   > ```

> [!TIP]
> Se a saída não está sendo gerada para o local que especificou, verifique se você está compilando a configuração correspondente (por exemplo, **Depuração** ou **Versão**), selecionando-a na barra de menus do Visual Studio.
>
> ![Seletor de configuração de build do Visual Studio de 2019](media/build-configuration-chooser.png)

## <a name="see-also"></a>Confira também

- [Página de compilação, Project Designer (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Página de Propriedade Geral (projeto)](/cpp/build/reference/general-property-page-project)
- [Compilação e construção](../ide/compiling-and-building-in-visual-studio.md)
