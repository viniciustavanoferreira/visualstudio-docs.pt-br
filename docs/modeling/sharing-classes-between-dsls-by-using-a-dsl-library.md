---
title: Compartilhando classes entre DSLs por meio de uma biblioteca de DSLs
ms.date: 11/04/2016
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4bfadc1777dfb4ba0c8ea712cfd39becc47f54a1
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76111365"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>Compartilhando classes entre DSLs por meio de uma biblioteca de DSLs
No SDK de visualização e modelagem do Visual Studio, você pode criar uma definição de DSL incompleta que pode ser importada para outra DSL. Isso permite que você preveja partes comuns de modelos semelhantes.

## <a name="creating-and-using-dsl-libraries"></a>Criando e usando bibliotecas de DSL

#### <a name="to-create-a-dsl-library"></a>Para criar uma biblioteca de DSL

1. Crie um novo projeto DSL e escolha o modelo de solução de biblioteca de DSL.

     Um único projeto DSL será criado com um modelo vazio.

2. Você pode adicionar classes de domínio, relações, formas e assim por diante.

     Os elementos na biblioteca não precisam formar uma única árvore de incorporação.

     Para definir uma relação que importadores podem usar, crie duas classes de domínio e crie a relação entre elas.

     Considere definir o **modificador de herança** das classes de domínio para `Abstract`.

3. Você pode adicionar elementos que você define no Gerenciador de DSL, como construtores de conexão.

4. Você pode adicionar personalizações que exigem código adicional, como restrições de validação.

5. Clique em **transformar todos os modelos**.

6. Crie o projeto.

7. Ao distribuir a DSL para outras pessoas usarem, você deve fornecer o assembly compilado (DLL) e o arquivo `DslDefinition.dsl`. Você pode encontrar o assembly compilado em uma pasta em `Dsl\bin\*`

#### <a name="to-import-a-dsl-library"></a>Para importar uma biblioteca de DSL

1. Em outra definição de DSL, no **Gerenciador de DSL**, clique com o botão direito do mouse na classe raiz da DSL e clique em **Adicionar nova importação de DslLibrary**.

2. Na janela Propriedades, defina o **caminho do arquivo** da biblioteca. Você pode usar um caminho relativo ou absoluto.

    A biblioteca importada aparece no Gerenciador de DSL, no modo somente leitura.

3. Você pode usar as classes importadas como classes base. Crie uma classe de domínio na importação de DSL e, na janela Propriedades, defina a **classe base** como uma classe importada.

4. Clique em Transformar Todos os Modelos.

5. Adicione ao projeto DSL uma referência ao assembly (DLL) criado pelo projeto de biblioteca de DSL.

6. {1&gt;Compile a solução.&lt;1}

   Uma biblioteca de DSL pode importar outras bibliotecas. Quando você importa uma biblioteca, suas importações também aparecem automaticamente no Gerenciador de DSL.

## <a name="see-also"></a>Veja também

- [Como definir uma linguagem específica de domínio](../modeling/how-to-define-a-domain-specific-language.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
