---
title: Como abrir um modelo a partir de um arquivo no código do programa
ms.date: 11/04/2016
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fae71f748f1f64480c046ae157e1fbca0dd0bec9
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75594611"
---
# <a name="how-to-open-a-model-from-file-in-program-code"></a>Como abrir um modelo a partir de um arquivo no código do programa

Você pode abrir modelos de DSL em qualquer aplicativo.

A partir de uma extensão do Visual Studio, você pode usar ModelBus para essa finalidade. O ModelBus fornece um mecanismo padrão para referenciar um modelo ou elementos em um modelo e para localizar o modelo se ele tiver sido movido. Para obter mais informações, consulte [integrando modelos usando o Visual Studio ModelBus](../modeling/integrating-models-by-using-visual-studio-modelbus.md).

## <a name="target-framework"></a>Estrutura de destino

Defina a **estrutura de destino** do seu projeto de aplicativo para .NET Framework 4 ou posterior.

1. Abra o projeto do Visual Studio para o aplicativo no qual você deseja ler um modelo DSL.

2. Em **Gerenciador de soluções**, clique com o botão direito do mouse no projeto e clique em **Propriedades**.

3. Na janela Propriedades do projeto, na guia **aplicativo** , defina o campo **estrutura de destino** como **.NET Framework 4** (ou posterior).

> [!NOTE]
> A estrutura de destino não deve ser **.NET Framework perfil de cliente 4**.

## <a name="references"></a>Referências

Adicione estas referências ao seu projeto de aplicativo do Visual Studio:

- `Microsoft.VisualStudio.Modeling.Sdk.11.0`

  - Se você não vir isso na guia **.net** da caixa de diálogo **Adicionar referências** , clique na guia **procurar** e navegue até `%Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Common\Assemblies\`.

- Seu assembly DSL, que será encontrado na pasta bin do seu projeto DSL. Seu nome normalmente é do formato: *suaempresa*.`.Dsl.dll`*seuprojeto* .

## <a name="important-classes-in-the-dsl"></a>Classes importantes na DSL

Antes de escrever o código que lê sua DSL, você deve saber os nomes de algumas das classes geradas por sua DSL. Na sua solução de DSL, abra o projeto **DSL** e procure na pasta **GeneratedCode** . Como alternativa, clique duas vezes no assembly DSL em suas **referências**de projeto e abra o namespace DSL no **pesquisador de objetos**.

Essas são as classes que você deve identificar:

- *YourDslRootClass* -este é o nome da classe raiz em seu `DslDefinition.dsl`.

- *YourDslName* `SerializationHelper`-essa classe é definida em `SerializationHelper.cs` em seu projeto DSL.

- *YourDslName* `DomainModel`-essa classe é definida em `DomainModel.cs` em seu projeto DSL.

## <a name="read-from-a-file"></a>Ler de um arquivo

O exemplo a seguir foi projetado para ler uma DSL na qual as classes importantes são as seguintes:

- FamilyTreeModel

- FamilyTreeSerializationHelper

- FamilyTreeDomainModel

A outra classe de domínio nessa DSL é Person.

```csharp
using System;
using Microsoft.VisualStudio.Modeling;
using Company.FamilyTree; // Your DSL namespace

namespace StandaloneReadDslConsole
{ class Program
  { static void Main(string[] args)
    {
      // The path of a DSL model file:
      string dslModel = @"C:\FamilyTrees\Tudor.ftree";
      // Set up the Store to read your type of model:
      Store store = new Store(
        typeof(Company.FamilyTree.FamilyTreeDomainModel));
      // The Model type generated by the DSL:
      FamilyTreeModel familyTree;
      // All Store changes must be in a Transaction:
      using (Transaction t =
        store.TransactionManager.BeginTransaction("Load model"))
      {
        familyTree =
           FamilyTreeSerializationHelper.Instance.
              LoadModel(store, dslModel, null, null, null);
        t.Commit(); // Don't forget this!
      }
      // Now we can read the model:
      foreach (Person p in familyTree.People)
      {
        Console.WriteLine(p.Name);
        foreach (Person child in p.Children)
        {
          Console.WriteLine("    " + child.Name);
        }
} } } }
```

## <a name="save-to-a-file"></a>Salvar em um arquivo

O seguinte acréscimo ao código anterior faz uma alteração no modelo e, em seguida, salva-o em um arquivo.

```csharp
using (Transaction t =
  store.TransactionManager.BeginTransaction("update model"))
{
  // Create a new model element:
  Person p = new Person(store);
  // Set its embedding relationship:
  p.FamilyTreeModel = familyTree;
  // - same as: familyTree.People.Add(p);
  // Set its properties:
  p.Name = "Edward VI";
  t.Commit(); // Don't forget this!
}
// Save the model:
try
{
  SerializationResult result = new SerializationResult();
  FamilyTreeSerializationHelper.Instance
    .SaveModel(result, familyTree, @"C:\FamilyTrees\Tudor-upd.ftree");
  // Report any error:
  if (result.Failed)
  {
    foreach (SerializationMessage message in result)
    {
      Console.WriteLine(message);
    }
  }
}
catch (System.IO.IOException ex)
{ ... }
```
