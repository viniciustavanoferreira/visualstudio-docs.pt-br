---
title: Conjuntos de dados tipados versus. não tipados
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: c83ba0bb-5425-4d47-8891-6b4dbf937701
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 430e57713f1bfb01219ea1ac8123f321ba0f5680
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586101"
---
# <a name="typed-vs-untyped-datasets"></a>Conjuntos de dados tipados versus. não tipados
Um conjunto de dados tipado é um conjunto de dados que é derivado primeiro da classe base <xref:System.Data.DataSet> e, em seguida, usa informações da **Designer de conjunto de dados**, que é armazenada em um arquivo. xsd, para gerar uma nova classe DataSet com rigidez de tipos. As informações do esquema (tabelas, colunas e assim por diante) são geradas e compiladas nessa nova classe de conjunto de dados como um conjunto de objetos e propriedades de primeira classe. Como um conjunto de dados tipado herda da classe base <xref:System.Data.DataSet>, a classe tipada pressupõe toda a funcionalidade da classe <xref:System.Data.DataSet> e pode ser usada com métodos que usam uma instância de uma classe <xref:System.Data.DataSet> como um parâmetro.

Um conjunto de um DataSet não tipado, por outro lado, não tem nenhum esquema interno correspondente. Como em um dataset tipado, um conjunto de um DataSet não tipado contém tabelas, colunas e assim por diante — mas eles são expostos apenas como coleções. (No entanto, depois que você criar manualmente as tabelas e outros elementos de dados em um DataSet não tipado, você poderá exportar a estrutura do DataSet como um esquema usando o método de <xref:System.Data.DataSet.WriteXmlSchema%2A> do DataSet.)

## <a name="contrast-data-access-in-typed-and-untyped-datasets"></a>Contraste o acesso a dados em datasets digitados e não tipados
A classe de um conjunto de dados tipado tem um modelo de objeto no qual suas propriedades assumem os nomes reais das tabelas e colunas. Por exemplo, se você estiver trabalhando com um dataset tipado, poderá fazer referência a uma coluna usando um código como o seguinte:

[!code-csharp[VbRaddataDatasets#4](../data-tools/codesnippet/CSharp/typed-vs-untyped-datasets_1.cs)]
[!code-vb[VbRaddataDatasets#4](../data-tools/codesnippet/VisualBasic/typed-vs-untyped-datasets_1.vb)]

Por outro lado, se você estiver trabalhando com um conjunto de um DataSet não tipado, o código equivalente será:

[!code-csharp[VbRaddataDatasets#5](../data-tools/codesnippet/CSharp/typed-vs-untyped-datasets_2.cs)]
[!code-vb[VbRaddataDatasets#5](../data-tools/codesnippet/VisualBasic/typed-vs-untyped-datasets_2.vb)]

O acesso digitado não é apenas mais fácil de ler, mas também tem suporte completo do IntelliSense no **Editor de código**do Visual Studio. Além de ser mais fácil de trabalhar com, a sintaxe para o dataset tipado fornece verificação de tipo em tempo de compilação, reduzindo significativamente a possibilidade de erros na atribuição de valores a membros de conjuntos de de DataSet. Se você alterar o nome de uma coluna em sua classe de <xref:System.Data.DataSet> e, em seguida, compilar seu aplicativo, receberá um erro de compilação. Ao clicar duas vezes no erro de compilação na **lista de tarefas**, você pode ir diretamente para a linha ou linhas de código que referenciam o nome de coluna antigo. O acesso a tabelas e colunas em um dataset tipado também é ligeiramente mais rápido no tempo de execução porque o acesso é determinado em tempo de compilação, não através de coleções em tempo de execução.

Mesmo que os conjuntos de linhas de texto tenham muitas vantagens, um conjunto de um DataSet não tipado é útil em várias circunstâncias. O cenário mais óbvio é quando nenhum esquema está disponível para o conjunto de um. Isso pode ocorrer, por exemplo, se seu aplicativo estiver interagindo com um componente que retorna um conjunto de dados, mas você não sabe com antecedência o que é sua estrutura. Da mesma forma, há ocasiões em que você está trabalhando com dados que não têm uma estrutura estática e previsível. Nesse caso, é impraticável usar um conjunto de dados tipado, pois você precisaria regenerar a classe DataSet tipada com cada alteração na estrutura de dado.

Em geral, há muitas vezes em que você pode criar um conjunto de um DataSet dinamicamente sem ter um esquema disponível. Nesse caso, o conjunto de dados é simplesmente uma estrutura conveniente na qual você pode manter informações, contanto que eles possam ser representados de forma relacional. Ao mesmo tempo, você pode aproveitar os recursos do conjunto de dados, como a capacidade de serializar as informações a serem passadas para outro processo ou para gravar um arquivo XML.

## <a name="see-also"></a>Veja também

- [Ferramentas do conjunto de dados](../data-tools/dataset-tools-in-visual-studio.md)
