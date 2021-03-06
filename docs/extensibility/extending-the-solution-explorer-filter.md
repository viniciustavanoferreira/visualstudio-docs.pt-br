---
title: Ampliando o filtro do explorador de soluções | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Solution Explorer, extending
- extensibility [Visual Studio], projects and solutions
ms.assetid: df976c76-27ec-4f00-ab6d-a26a745dc6c7
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: af0824edd4188481bec8c0703d71043354f5dbcc
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80711566"
---
# <a name="extend-the-solution-explorer-filter"></a>Estender o filtro Solution Explorer
Você pode estender a funcionalidade do filtro **Solution Explorer** para mostrar ou ocultar diferentes arquivos. Por exemplo, você pode criar um filtro que mostra apenas arquivos de fábrica da classe C# no **Solution Explorer**, como este passo a passo demonstra.

## <a name="prerequisites"></a>Pré-requisitos
 A partir do Visual Studio 2015, você não instala o Visual Studio SDK a partir do centro de downloads. Ele está incluído como um recurso opcional na configuração do Visual Studio. Você também pode instalar o VS SDK mais tarde. Para obter mais informações, consulte [Instalar o Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

### <a name="create-a-visual-studio-package-project"></a>Crie um projeto de pacote visual studio

1. Crie um projeto `FileFilter`VSIX chamado . Adicione um modelo de item de comando personalizado chamado **FileFilter**. Para obter mais informações, consulte [Criar uma extensão com um comando menu](../extensibility/creating-an-extension-with-a-menu-command.md).

2. Adicione uma `System.ComponentModel.Composition` referência `Microsoft.VisualStudio.Utilities`a e .

3. Faça o comando do menu aparecer na barra de ferramentas **do Solution Explorer.** Abra o arquivo *FileFilterPackage.vsct.*

4. Altere `<Button>` o bloco para o seguinte:

    ```xml
    <Button guid="guidFileFilterPackageCmdSet" id="FileFilterId" priority="0x0400" type="Button">
        <Parent guid="guidSHLMainMenu" id="IDG_VS_TOOLBAR_PROJWIN_FILTERS" />
        <Icon guid="guidImages" id="bmpPic1" />
        <Strings>
            <ButtonText>FileNameFilter</ButtonText>
        </Strings>
    </Button>
    ```

### <a name="update-the-manifest-file"></a>Atualizar o arquivo de manifesto

1. No arquivo *source.extension.vsixmanifest,* adicione um ativo que é um componente MEF.

2. Na guia **Ativos,** escolha o botão **Novo.**

3. No **campo Tipo,** escolha **Microsoft.VisualStudio.MefComponent**.

4. No campo **Origem,** escolha **Um projeto na solução atual**.

5. No **campo Projeto,** escolha **FileFilter**e escolha o botão **OK.**

### <a name="add-the-filter-code"></a>Adicione o código do filtro

1. Adicione alguns GUIDs ao arquivo *FileFilterPackageGuids.cs:*

    ```csharp
    public const string guidFileFilterPackageCmdSetString = "00000000-0000-0000-0000-00000000"; // get your GUID from the .vsct file
    public const int FileFilterId = 0x100;
    ```

2. Adicione um arquivo de classe ao projeto FileFilter chamado *FileNameFilter.cs*.

3. Substitua o namespace vazio e a classe vazia pelo código abaixo.

     O `Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem rootItems)` método pega a coleção que contém`rootItems`a raiz da solução ( ) e devolve a coleção de itens a serem incluídos no filtro.

     O `ShouldIncludeInFilter` método filtra os itens na hierarquia **do Solution Explorer** com base na condição especificada.

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.ComponentModel.Composition;
    using System.Text.RegularExpressions;
    using System.Threading.Tasks;
    using Microsoft.Internal.VisualStudio.PlatformUI;
    using Microsoft.VisualStudio.Shell;

    namespace FileFilter
    {
        // Implements ISolutionTreeFilterProvider. The SolutionTreeFilterProvider attribute declares it as a MEF component
        [SolutionTreeFilterProvider(FileFilterPackageGuids.guidFileFilterPackageCmdSetString, (uint)(FileFilterPackageGuids.FileFilterId))]
        public sealed class FileNameFilterProvider : HierarchyTreeFilterProvider
        {
            SVsServiceProvider svcProvider;
            IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;

            // Constructor required for MEF composition
            [ImportingConstructor]
            public FileNameFilterProvider(SVsServiceProvider serviceProvider, IVsHierarchyItemCollectionProvider hierarchyCollectionProvider)
            {
                this.svcProvider = serviceProvider;
                this.hierarchyCollectionProvider = hierarchyCollectionProvider;
            }

            // Returns an instance of Create filter class.
            protected override HierarchyTreeFilter CreateFilter()
            {
                return new FileNameFilter(this.svcProvider, this.hierarchyCollectionProvider, FileNamePattern);
            }

            // Regex pattern for CSharp factory classes
            private const string FileNamePattern = @"\w*factory\w*(.cs$)";

            // Implementation of file filtering
            private sealed class FileNameFilter : HierarchyTreeFilter
            {
                private readonly Regex regexp;
                private readonly IServiceProvider svcProvider;
                private readonly IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;

                public FileNameFilter(
                    IServiceProvider serviceProvider,
                    IVsHierarchyItemCollectionProvider hierarchyCollectionProvider,
                    string fileNamePattern)
                {
                    this.svcProvider = serviceProvider;
                    this.hierarchyCollectionProvider = hierarchyCollectionProvider;
                    this.regexp = new Regex(fileNamePattern, RegexOptions.IgnoreCase);
                }

                // Gets the items to be included from this filter provider.
                // rootItems is a collection that contains the root of your solution
                // Returns a collection of items to be included as part of the filter
                protected override async Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem> rootItems)
                {
                    IVsHierarchyItem root = HierarchyUtilities.FindCommonAncestor(rootItems);
                    IReadOnlyObservableSet<IVsHierarchyItem> sourceItems;
                    sourceItems = await hierarchyCollectionProvider.GetDescendantsAsync(
                                        root.HierarchyIdentity.NestedHierarchy,
                                        CancellationToken);

                    IFilteredHierarchyItemSet includedItems = await hierarchyCollectionProvider.GetFilteredHierarchyItemsAsync(
                        sourceItems,
                        ShouldIncludeInFilter,
                        CancellationToken);
                    return includedItems;
                }

                // Returns true if filters hierarchy item name for given filter; otherwise, false</returns>
                private bool ShouldIncludeInFilter(IVsHierarchyItem hierarchyItem)
                {
                    if (hierarchyItem == null)
                    {
                        return false;
                    }
                    return this.regexp.IsMatch(hierarchyItem.Text);
                }
            }
        }
    }

    ```

4. Em *FileFilter.cs,* remova o código de posicionamento e manuseio do construtor FileFilter. O resultado deve ser assim:

    ```csharp
    private FileFilter(Package package)
    {
        if (package == null)
        {
            throw new ArgumentNullException("package");
        }

        this.package = package;
    }
    ```

     Remova `ShowMessageBox()` o método também.

5. Em *FileFilterPackage.cs,* substitua `Initialize()` o código no método pelo seguinte:

    ```csharp
    protected override void Initialize()
    {
        Debug.WriteLine (string.Format(CultureInfo.CurrentCulture, "Entering Initialize() of: {0}", this.ToString()));
        base.Initialize();
    }
    ```

### <a name="test-your-code"></a>Testar seu código

1. Compile e execute o projeto. Uma segunda instância do Visual Studio é exibida. Isso é chamado de instância experimental.

2. Na instância experimental do Visual Studio, abra um projeto C#.

3. Procure o botão que você adicionou na barra de ferramentas **do Solution Explorer.** Deve ser o quarto botão da esquerda.

4. Quando você clica no botão, todos os arquivos devem ser filtrados, e você deve ver **Todos os itens foram filtrados da vista.** no **Solution Explorer**.
