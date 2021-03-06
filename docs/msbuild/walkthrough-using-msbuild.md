---
title: 'Instruções passo a passo: usando o MSBuild | Microsoft Docs'
ms.date: 03/20/2019
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tutorial
ms.assetid: b8a8b866-bb07-4abf-b9ec-0b40d281c310
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 310fa3b6795a5e340dcd9c7fa40cb27807c132ba
ms.sourcegitcommit: 0b8497b720eb06bed8ce2194731177161b65eb84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82072535"
---
# <a name="walkthrough-use-msbuild"></a>Passo a passo: usar o MSBuild

O MSBuild é a plataforma de build da Microsoft e do Visual Studio. Estas instruções passo a passo apresentam os componentes essenciais do MSBuild e mostram como gravar, manipular e depurar projetos do MSBuild. Você aprenderá a:

- Criar e manipular um arquivo de projeto.

- Usar as propriedades de build

- Usar itens de build.

Você pode executar o MSBuild no Visual Studio ou na **Janela de Comando**. Nestas instruções passo a passo, você criará um arquivo de projeto do MSBuild usando o Visual Studio. Você editará o arquivo de projeto no Visual Studio e usará a **janela Comando** para compilar o projeto e examinar os resultados.

## <a name="create-an-msbuild-project"></a>Criar um projeto do MSBuild

 O sistema de projetos do Visual Studio é baseado no MSBuild. Isso facilita a criação de um novo arquivo de projeto usando o Visual Studio. Nesta seção, você criará um arquivo de projeto do Visual C#. Você também poderá escolher criar um arquivo de projeto do Visual Basic. No contexto destas instruções passo a passo, a diferença entre os dois arquivos de projeto é secundária.

**Para criar um arquivo de projeto**

1. Abra o Visual Studio e crie um projeto.

    ::: moniker range=">=vs-2019"
    Pressione **Esc** para fechar a janela de início. Digite **Ctrl + Q** para abrir a caixa de pesquisa, digite **winforms**, depois escolha **Criar um novo aplicativo do Windows Forms (.NET Framework)**. Na caixa de diálogo que aparece, escolha **Criar**.

    Na caixa **Nome**, digite `BuildApp`. Insira um **Local** para a solução, por exemplo, *D:\\*. Aceite os padrões para **Solução**, **Nome da solução** (**BuildApp**) e **Estrutura**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Na barra de menu superior, escolha **Arquivo** > **Novo** > **Projeto**. No painel esquerdo da caixa de diálogo **Novo Projeto**, expanda **Visual C#** > **Windows Desktop** e, em seguida, escolha **Aplicativo do Windows Forms (.NET Framework)**. Em seguida, escolha **OK**.

    Na caixa **Nome**, digite `BuildApp`. Insira um **Local** para a solução, por exemplo, *D:\\*. Aceite os padrões para **Criar diretório para a solução** (marcado), **Adicionar ao Controle do Código-Fonte** (não marcado) e **Nome da Solução** (**BuildApp**).
    ::: moniker-end

1. Clique em **OK** ou **Criar** para criar o arquivo de projeto.

## <a name="examine-the-project-file"></a>Examinar o arquivo de projeto

 Na seção anterior, você usou o Visual Studio para criar um arquivo de projeto do Visual C#. O arquivo de projeto é representado no **Gerenciador de Soluções** pelo nó de projeto chamado BuildApp. Você pode usar o editor de códigos do Visual Studio para examinar o arquivo de projeto.

**Para examinar o arquivo de projeto**

1. No **Solution Explorer,** clique no nó de projeto **BuildApp**.

1. No navegador **Propriedades,** observe que a propriedade **Project File** é *BuildApp.csproj*. Todos os arquivos do projeto são nomeados com o sufixo *proj*. Se você tivesse criado um projeto do Visual Basic, o nome do arquivo de projeto seria *BuildApp.vbproj*.

1. Clique com o botão direito do mouse no nó de projeto novamente e clique em **Editar BuildApp.csproj**. 

     O arquivo de projeto aparecerá no editor de códigos.

>[!NOTE]
> Para alguns tipos de projeto, como C++, você precisa descarregar o projeto (clique com o botão direito do mouse no arquivo do projeto e escolha **descarregar o projeto**) antes de poder abrir e editar o arquivo do projeto.

## <a name="targets-and-tasks"></a>Destinos e tarefas

Os arquivos de projeto são arquivos formatados em XML com o nó raiz [Project](../msbuild/project-element-msbuild.md).

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0"  xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
```

Projetos mais novos do .NET Core (estilo `Sdk` SDK) têm um atributo.

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

Se o projeto não for um projeto no estilo SDK, você deve especificar o namespace xmlns no elemento Projeto. Se o `ToolsVersion` estiver presente em um novo projeto, ele deverá ser o "15.0".

O trabalho de compilar um aplicativo é feito com os elementos [Target](../msbuild/target-element-msbuild.md) e [Task](../msbuild/task-element-msbuild.md).

- Uma tarefa é a menor unidade de trabalho ou, em outras palavras, é o "átomo" de um build. As tarefas são componentes executáveis independentes que podem ter entradas e saídas. Não existem tarefas referenciadas ou definidas no arquivo de projeto no momento. Você adicionará tarefas ao arquivo de projeto nas seções a seguir. Para obter mais informações, consulte o tópico [Tarefas](../msbuild/msbuild-tasks.md).

- Um destino é uma sequência nomeada de tarefas. Para obter mais informações, consulte o tópico [Destinos](../msbuild/msbuild-targets.md).
- [pode ser uma seqüência nomeada de tarefas, mas criticamente, representa algo a ser construído ou feito, por isso deve ser definido de uma forma orientada a objetivos]

O destino padrão não está definido no arquivo de projeto. Em vez disso, ele será especificado nos projetos importados. O elemento [Import](../msbuild/import-element-msbuild.md) especifica projetos importados. Por exemplo, em um projeto C#, o destino padrão é importado do arquivo *Microsoft.CSharp.targets*.

```xml
<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
```

Os arquivos importados são efetivamente inseridos no arquivo de projeto sempre que são referenciados.

Em projcts no estilo SDK, você não vê esse elemento de importação, uma vez que o atributo SDK faz com que este arquivo seja importado implicitamente.

O MSBuild controla os destinos de um build e garante que cada destino seja compilado não mais de uma vez.

## <a name="add-a-target-and-a-task"></a>Adicionar um destino e uma tarefa

 Adicione um destino ao arquivo de projeto. Adicione uma tarefa ao destino que exibe uma mensagem.

**Para adicionar um destino e uma tarefa**

1. Adicione estas linhas ao arquivo de projeto logo após a instrução Import:

    ```xml
    <Target Name="HelloWorld">
    </Target>
    ```

    Com isso, um destino chamado HelloWorld será criado. Observe que você tem suporte ao IntelliSense ao editar o arquivo de projeto.

2. Adicione linhas ao destino HelloWorld de modo que a seção resultante tenha esta aparência:

    ```xml
    <Target Name="HelloWorld">
      <Message Text="Hello"></Message>  <Message Text="World"></Message>
    </Target>
    ```

3. Salve o arquivo de projeto.

A tarefa Message é uma das muitas tarefas fornecidas com o MSBuild. Para obter uma lista completa de tarefas e informações de uso disponíveis, consulte [Referência tarefa](../msbuild/msbuild-task-reference.md).

A tarefa Mensagem pega o valor da seqüência do atributo Texto como entrada e o exibe no dispositivo de saída (ou grava-o em um ou mais logs, se aplicável). O destino HelloWorld executa a tarefa Message duas vezes: primeiro para exibir "Hello" e, em seguida, para exibir "World".

## <a name="build-the-target"></a>Compilar o destino

Se você tentar construir este projeto a partir do Visual Studio, ele não construirá o alvo definido. Isso porque o Visual Studio escolhe o destino padrão, que ainda é o do arquivo *importado .targets.*

Execute o MSBuild no **Prompt de Comando do Desenvolvedor** para o Visual Studio para compilar o destino HelloWorld definido acima. Use o interruptor de linha de comando -target ou -t para selecionar o alvo.

> [!NOTE]
> Nós nos referiremos ao **Prompt de Comando do Desenvolvedor** como a **janela Comando** nas seções abaixo.

**Para construir o alvo:**

1. Abra a **janela de comando**.

   (Windows 10) Na caixa de pesquisa na barra de tarefas, comece a digitar o nome da ferramenta, como `dev` ou `developer command prompt`. Isso abre uma lista de aplicativos instalados que correspondem ao seu padrão de pesquisa.

   Caso você precise encontrá-lo manualmente, o arquivo será *LaunchDevCmd.bat* na pasta *<pasta de instalação do visual studio\>\<versão>\Common7\Tools*.

2. A partir da janela de comando, navegue até a pasta que contém o arquivo do projeto, neste caso, *D:\BuildApp\BuildApp*.

3. Executar msbuild com `-t:HelloWorld`o interruptor de comando . Com isso, o destino HelloWorld é selecionado e compilado:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

4. Examine a saída na **janela Comando**. Você deverá ver as duas linhas "Hello" e "World":

    ```output
    Hello
    World
    ```

> [!NOTE]
> Se em vez disso aparecer `The target "HelloWorld" does not exist in the project`, será porque você provavelmente se esqueceu de salvar o arquivo de projeto no editor de códigos. Salve o arquivo e tente novamente.

 Ao alternar entre o editor de códigos e a janela Comando, você poderá alterar o arquivo de projeto e ver os resultados rapidamente.

## <a name="build-properties"></a>Compilar propriedades

 As propriedades de build são pares nome-valor que guiam o build. Várias propriedades de build já estão definidas na parte superior do arquivo de projeto:

```xml
<PropertyGroup>
...
  <ProductVersion>10.0.11107</ProductVersion>
  <SchemaVersion>2.0</SchemaVersion>
  <ProjectGuid>{30E3C9D5-FD86-4691-A331-80EA5BA7E571}</ProjectGuid>
  <OutputType>WinExe</OutputType>
...
</PropertyGroup>
```

 Todas as propriedades são elementos filho dos elementos PropertyGroup. O nome da propriedade é o nome do elemento filho e o valor da propriedade é o elemento de texto do elemento filho. Por exemplo,

```xml
<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>
```

 define a propriedade chamada TargetFrameworkVersion, dando-lhe o valor de string "v4.5".

 As propriedades de build podem ser redefinidas a qualquer momento. Se

```xml
<TargetFrameworkVersion>v3.5</TargetFrameworkVersion>
```

 aparecer mais adiante no arquivo de projeto ou em um arquivo importado posteriormente no arquivo de projeto, a TargetFrameworkVersion usará o novo valor "v3.5".

## <a name="examine-a-property-value"></a>Examinar um valor da propriedade

 Para obter o valor de um imóvel, use `PropertyName` a seguinte sintaxe, onde está o nome do imóvel:

```xml
$(PropertyName)
```

Use essa sintaxe para examinar algumas das propriedades no arquivo de projeto.

**Para examinar um valor da propriedade**

1. No editor de códigos, substitua o destino HelloWorld por este código:

    ```xml
    <Target Name="HelloWorld">
      <Message Text="Configuration is $(Configuration)" />
      <Message Text="MSBuildToolsPath is $(MSBuildToolsPath)" />
    </Target>
    ```

1. Salve o arquivo de projeto.

1. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

1. Examine a saída. Você deverá ver estas duas linhas (a sua versão do .NET Framework poderá ser diferente):

    ::: moniker range=">=vs-2019"

    ```output
    Configuration is Debug
    MSBuildToolsPath is C:\Program Files (x86)\Microsoft Visual Studio\2019\<Visual Studio SKU>\MSBuild\15.0\Bin
    ```

    ::: moniker-end
    ::: moniker range="vs-2017"

    ```output
    Configuration is Debug
    MSBuildToolsPath is C:\Program Files (x86)\Microsoft Visual Studio\2017\<Visual Studio SKU>\MSBuild\15.0\Bin
    ```

    ::: moniker-end

### <a name="conditional-properties"></a>Propriedades condicionais

Muitas propriedades `Configuration` como são definidas condicionalmente, ou seja, o atributo `Condition` aparece no elemento de propriedade. As propriedades condicionais serão definidas ou redefinidas somente se a condição for avaliada como "true". Observe que as propriedades indefinidas recebem o valor padrão de uma cadeia de caracteres vazia. Por exemplo,

```xml
<Configuration   Condition=" '$(Configuration)' == '' ">Debug</Configuration>
```

significa "Se a propriedade Configuration ainda não foi definida, é preciso defini-la e atribuir a ela o valor 'Debug'".

Quase todos os elementos do MSBuild podem ter um atributo Condition. Para mais discussões sobre como usar o atributo Condition, consulte [Condições](../msbuild/msbuild-conditions.md).

### <a name="reserved-properties"></a>Propriedades reservadas

O MSBuild reserva alguns nomes de propriedade para armazenar informações sobre o arquivo de projeto e os binários do MSBuild. MSBuildToolsPath é um exemplo de uma propriedade reservada. As propriedades reservadas são referenciadas com a notação $ como qualquer outra propriedade. Para saber mais, confira [Como referenciar o nome ou o local do arquivo de projeto](../msbuild/how-to-reference-the-name-or-location-of-the-project-file.md) e [Propriedades reservadas e conhecidas do MSBuild](../msbuild/msbuild-reserved-and-well-known-properties.md).

### <a name="environment-variables"></a>Variáveis de ambiente

Você pode referenciar variáveis de ambiente em arquivos de projeto da mesma maneira que as propriedades de build. Por exemplo, para usar a variável de ambiente PATH em seu arquivo de projeto, use $(Path). Se o projeto contiver uma definição de propriedade que tem o mesmo nome que uma variável de ambiente, a propriedade no projeto substituirá o valor da variável de ambiente. Para saber mais, confira [Como usar variáveis de ambiente em um build](../msbuild/how-to-use-environment-variables-in-a-build.md).

## <a name="set-properties-from-the-command-line"></a>Definir propriedades na linha de comando

As propriedades podem ser definidas na linha de comando usando a opção de linha de comando -property ou -p. Os valores das propriedades recebidos da linha de comando substituem os valores das propriedades definidos no arquivo de projeto e nas variáveis de ambiente.

**Para definir um valor de propriedade a partir da linha de comando:**

1. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld -p:Configuration=Release
    ```

1. Examine a saída. Você deverá ver esta linha:

    ```output
    Configuration is Release.
    ```

O MSBuild cria a propriedade Configuration e atribui a ela o valor "Release".

## <a name="special-characters"></a>Caracteres especiais

Determinados caracteres têm significado especial em arquivos de projeto do MSBuild. O ponto e vírgula (;) e o asterisco (*) são exemplos desses caracteres. Para usar esses caracteres especiais como literais em um arquivo de projeto, eles precisam ser especificados com a sintaxe %\<xx>, em que \<xx> representa o valor hexadecimal ASCII do caractere.

Altere a tarefa Message para mostrar o valor da propriedade Configuration com caracteres especiais para torná-la mais legível.

**Para usar caracteres especiais na tarefa Mensagem:**

1. No editor de códigos, substitua ambas as tarefas Message por esta linha:

    ```xml
    <Message Text="%24(Configuration) is %22$(Configuration)%22" />
    ```

1. Salve o arquivo de projeto.

1. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

1. Examine a saída. Você deverá ver esta linha:

    ```output
    $(Configuration) is "Debug"
    ```

Para saber mais, confira [Caracteres especiais no MSBuild](../msbuild/msbuild-special-characters.md).

## <a name="build-items"></a>Compilar itens

Um item é uma informação, normalmente um nome de arquivo, que é usado como entrada no sistema de build. Por exemplo, uma coleção de itens que representam os arquivos de origem pode ser passada para uma tarefa chamada Compile para compilá-los em um assembly.

Todos os itens são elementos filho dos elementos ItemGroup. O nome do item é o nome do elemento filho e o valor do item é o valor do atributo Include do elemento filho. Os valores dos itens com o mesmo nome são coletados em tipos de item do nome.  Por exemplo,

```xml
<ItemGroup>
    <Compile Include="Program.cs" />
    <Compile Include="Properties\AssemblyInfo.cs" />
</ItemGroup>
```

define um grupo de itens que contém dois itens. O tipo de item Compile tem dois valores: *Program.cs* e *Propriedades\AssemblyInfo.cs*.

O código a seguir cria o mesmo tipo de item declarando os dois arquivos em um atributo Include, separados por ponto e vírgula.

```xml
<ItemGroup>
    <Compile Include="Program.cs;Properties\AssemblyInfo.cs" />
</ItemGroup>
```

Para obter mais informações, consulte [Itens](../msbuild/msbuild-items.md).

> [!NOTE]
> Os caminhos do arquivo são relativos à pasta que contém o arquivo do projeto MSBuild, mesmo que o arquivo do projeto seja um arquivo de projeto importado. Há algumas exceções para isso, como ao usar elementos [Importação](import-element-msbuild.md) e [UsingTask.](usingtask-element-msbuild.md)

## <a name="examine-item-type-values"></a>Examinar os valores de tipo de item

 Para obter os valores de um tipo de item, use a seguinte sintaxe, em que ItemType é o nome do tipo de item:

```xml
@(ItemType)
```

Use essa sintaxe para examinar o tipo de item Compile no arquivo de projeto.

**Para examinar os valores do tipo de item:**

1. No editor de códigos, substitua a tarefa do destino HelloWorld por este código:

    ```xml
    <Target Name="HelloWorld">
      <Message Text="Compile item type contains @(Compile)" />
    </Target>
    ```

1. Salve o arquivo de projeto.

1. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

1. Examine a saída. Você deverá ver esta linha longa:

    ```
    Compile item type contains Form1.cs;Form1.Designer.cs;Program.cs;Properties\AssemblyInfo.cs;Properties\Resources.Designer.cs;Properties\Settings.Designer.cs
    ```

Por padrão, os valores de um tipo de item são separados por ponto e vírgula.

Para alterar o separador de um tipo de item, use a seguinte sintaxe, em que ItemType é o tipo de item e Separator é uma cadeia de caracteres de um ou mais caracteres de separação:

```xml
@(ItemType, Separator)
```

Altere a tarefa Message para usar retornos de carro e alimentações de linha (%0A%0D) para exibir os itens Compile em linhas individuais.

**Para exibir os valores de tipo de item em linhas individuais**

1. No editor de códigos, substitua a tarefa Message por esta linha:

    ```xml
    <Message Text="Compile item type contains @(Compile, '%0A%0D')" />
    ```

2. Salve o arquivo de projeto.

3. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

4. Examine a saída. Você deverá ver estas linhas:

    ```
    Compile item type contains Form1.cs
    Form1.Designer.cs
    Program.cs
    Properties\AssemblyInfo.cs
    Properties\Resources.Designer.cs
    Properties\Settings.Designer.cs
    ```

### <a name="include-exclude-and-wildcards"></a>Incluir, excluir e curingas

 Você pode usar os curingas "*", "\*\*" e "?" com o atributo Include para adicionar itens a um tipo de item. Por exemplo,

```xml
<Photos Include="images\*.jpeg" />
```

 adiciona todos os arquivos com a extensão de arquivo *.jpeg* na pasta *imagens* ao tipo de item Fotos, enquanto

```xml
<Photos Include="images\**\*.jpeg" />
```

 adiciona todos os arquivos com a extensão de arquivo *.jpeg* na pasta *imagens,* e todas as suas subpastas, ao tipo de item Fotos. Para mais exemplos, [veja Como: Selecione os arquivos a serem construídos](../msbuild/how-to-select-the-files-to-build.md).

 Observe que, conforme os itens são declarados, eles são adicionados ao tipo de item. Por exemplo,

```xml
<Photos Include="images\*.jpeg" />
<Photos Include="images\*.gif" />
```

 cria um tipo de item chamado Photo contendo todos os arquivos na pasta de *imagens* com uma extensão de arquivo *.jpeg* ou *.gif*. Isso é equivalente à seguinte linha:

```xml
<Photos Include="images\*.jpeg;images\*.gif" />
```

 Você pode excluir um item de um tipo de item com o atributo Exclude. Por exemplo,

```xml
<Compile Include="*.cs" Exclude="*Designer*">
```

 adiciona todos os arquivos com a extensão de arquivo *.cs* ao tipo de item Compile, exceto os arquivos cujos nomes contêm a cadeia de caracteres *Designer*. Para mais exemplos, [consulte Como: Excluir arquivos da compilação](../msbuild/how-to-exclude-files-from-the-build.md).

O atributo Exclude afeta somente os itens adicionados pelo atributo Include no elemento do item que contém ambos. Por exemplo,

```xml
<Compile Include="*.cs" />
<Compile Include="*.res" Exclude="Form1.cs">
```

não excluiria o arquivo *Form1.cs*, que foi adicionado no elemento do item anterior.

**Para incluir e excluir itens**

1. No editor de códigos, substitua a tarefa Message por esta linha:

    ```xml
    <Message Text="XFiles item type contains @(XFiles)" />
    ```

2. Adicione esse grupo de itens logo após o elemento Import:

    ```xml
    <ItemGroup>
       <XFiles Include="*.cs;properties/*.resx" Exclude="*Designer*" />
    </ItemGroup>
    ```

3. Salve o arquivo de projeto.

4. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

5. Examine a saída. Você deverá ver esta linha:

    ```
    XFiles item type contains Form1.cs;Program.cs;Properties/Resources.resx
    ```

## <a name="item-metadata"></a>Metadados do item

 Além das informações coletadas pelos atributos Include e Exclude, os itens podem conter metadados. Esses metadados podem ser usados por tarefas que exigem mais informações sobre os itens que apenas o valor do item.

 Os metadados de item são declarados no arquivo de projeto criando um elemento com o nome dos metadados como um elemento filho do item. Um item pode ter zero ou mais valores de metadados. Por exemplo, o seguinte item CSFile tem metadados Culture com um valor de "Fr":

```xml
<ItemGroup>
    <CSFile Include="main.cs">
        <Culture>Fr</Culture>
    </CSFile>
</ItemGroup>
```

 Para obter o valor dos metadados de um tipo de item, use a seguinte sintaxe, em que ItemType é o nome do tipo de item e MetaDataName é o nome dos metadados:

```xml
%(ItemType.MetaDataName)
```

**Para examinar os metadados do item:**

1. No editor de códigos, substitua a tarefa Message por esta linha:

    ```xml
    <Message Text="Compile.DependentUpon: %(Compile.DependentUpon)" />
    ```

2. Salve o arquivo de projeto.

3. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

4. Examine a saída. Você deverá ver estas linhas:

    ```output
    Compile.DependentUpon:
    Compile.DependentUpon: Form1.cs
    Compile.DependentUpon: Resources.resx
    Compile.DependentUpon: Settings.settings
    ```

Observe que "Compile.DependentUpon" aparece várias vezes. O uso de metadados com essa sintaxe em um destino causa o "envio em lotes". Envio em lote significa que as tarefas no destino são executadas uma vez para cada valor exclusivo dos metadados. Trata-se do equivalente em script do MSBuild ao constructo comum de programação "loop for". Para obter mais informações, consulte [Envio em lote](../msbuild/msbuild-batching.md).

### <a name="well-known-metadata"></a>Metadados conhecidos

 Sempre que um item é adicionado a uma lista de itens, esse item recebe alguns metadados conhecidos. Por exemplo, %(Filename) retorna o nome de arquivo de qualquer item. Para obter uma lista completa de metadados bem conhecidos, consulte [metadados de itens bem conhecidos](../msbuild/msbuild-well-known-item-metadata.md).

**Para examinar metadados bem conhecidos:**

1. No editor de códigos, substitua a tarefa Message por esta linha:

    ```xml
    <Message Text="Compile Filename: %(Compile.Filename)" />
    ```

2. Salve o arquivo de projeto.

3. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

4. Examine a saída. Você deverá ver estas linhas:

    ```output
    Compile Filename: Form1
    Compile Filename: Form1.Designer
    Compile Filename: Program
    Compile Filename: AssemblyInfo
    Compile Filename: Resources.Designer
    Compile Filename: Settings.Designer
    ```

Ao comparar os dois exemplos acima, você poderá ver que, embora nem todos os itens no tipo de item Compile tenham metadados DependentUpon, todos os itens têm os metadados conhecidos Filename.

### <a name="metadata-transformations"></a>Transformações de metadados

 As listas de itens podem ser transformadas em novas listas de itens. Para transformar uma lista de itens, use a seguinte sintaxe, em que \<ItemType> é o nome do tipo de item e \<MetadataName> é o nome dos metadados:

```xml
@(ItemType -> '%(MetadataName)')
```

Por exemplo, uma lista de itens dos arquivos de origem pode ser transformada em uma coleção de arquivos-objeto usando uma expressão como `@(SourceFiles -> '%(Filename).obj')`. Para obter mais informações, consulte [Transformações](../msbuild/msbuild-transforms.md).

**Para transformar itens usando metadados:**

1. No editor de códigos, substitua a tarefa Message por esta linha:

    ```xml
    <Message Text="Backup files: @(Compile->'%(filename).bak')" />
    ```

2. Salve o arquivo de projeto.

3. Na **janela Comando**, digite e execute esta linha:

    ```cmd
    msbuild buildapp.csproj -t:HelloWorld
    ```

4. Examine a saída. Você deverá ver esta linha:

    ```output
    Backup files: Form1.bak;Form1.Designer.bak;Program.bak;AssemblyInfo.bak;Resources.Designer.bak;Settings.Designer.bak
    ```

Observe que os metadados expressados nesta sintaxe não causam o envio em lote.

## <a name="next-steps"></a>Próximas etapas

 Para saber como criar um arquivo de projeto simples uma etapa de cada vez, experimente o [Passo a Passo: Criando um arquivo de projeto MSBuild do zero](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md).

## <a name="see-also"></a>Confira também

- [Visão geral do MSBuild](../msbuild/msbuild.md)
- [Referência do MSBuild](../msbuild/msbuild-reference.md)
