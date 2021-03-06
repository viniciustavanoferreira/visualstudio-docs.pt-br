---
title: Usar modelos no processo de desenvolvimento
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UML, using models
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 601a49126dd266b6c080b4d79cd215616321837a
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115047"
---
# <a name="use-models-in-your-development-process"></a>Usar modelos no processo de desenvolvimento

No Visual Studio, você pode usar um modelo para ajudá-lo a entender e alterar um sistema, aplicativo ou componente. Um modelo pode ajudá-lo a visualizar o mundo em que seu sistema funciona, esclarecer as necessidades dos usuários, definir a arquitetura do seu sistema, analisar o código e garantir que seu código atenda aos requisitos. Consulte [vídeo do Channel 9: melhorar a arquitetura por meio de modelagem](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012-Improving-architecture-through-modeling).

Para ver quais versões do Visual Studio oferecem suporte a cada tipo de modelo, consulte [suporte de versão para ferramentas de arquitetura e modelagem](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

Os modelos podem ajudá-lo de várias maneiras:

- Diagramas de modelagem de desenho ajuda a esclarecer os conceitos envolvidos em requisitos, arquitetura e design de alto nível. Para obter mais informações, consulte [requisitos de usuário de modelo](../modeling/model-user-requirements.md).

- Trabalhar com modelos pode ajudá-lo a expor inconsistências nos requisitos.

- A comunicação com modelos ajuda a comunicar conceitos importantes menos de forma ambígua do que com linguagem natural. Para obter mais informações, consulte [modelar a arquitetura do aplicativo](../modeling/model-your-app-s-architecture.md).

- Às vezes, você pode usar modelos para gerar código ou outros artefatos, como esquemas ou documentos de banco de dados. Por exemplo, os componentes de modelagem do Visual Studio são gerados a partir de um modelo. Para obter mais informações, consulte [gerar e configurar seu aplicativo de modelos](../modeling/generate-and-configure-your-app-from-models.md).

Você pode usar modelos em uma ampla variedade de processos, de extrema agilidade a uma cerimônia de alta.

## <a name="use-models-to-reduce-ambiguity"></a>Usar modelos para reduzir a ambiguidade

A linguagem de modelagem é menos ambígua do que a linguagem natural e foi projetada para expressar as ideias normalmente necessárias durante o desenvolvimento de software.

Se o seu projeto tiver uma equipe pequena seguindo as práticas Agile, você poderá usar modelos para ajudá-lo a esclarecer as histórias de usuários. Em discussões com o cliente sobre suas necessidades, a criação de um modelo pode gerar perguntas úteis muito mais rapidamente e, em uma área mais ampla do produto, do que escrever código de pico ou protótipo.

Se seu projeto for grande e incluir equipes em diferentes partes do mundo, você poderá usar modelos para ajudar a comunicar os requisitos e a arquitetura com muito mais eficiência do que você pode em texto sem formatação.

Em ambos os casos, a criação de um modelo quase sempre resulta em uma redução significativa em inconsistências e ambiguidades. Diferentes participantes com frequência têm diferentes entendimentos do mundo de negócios em que o sistema funciona, e diferentes desenvolvedores com frequência têm diferentes entendimentos de como o sistema funciona. O uso de um modelo como o foco de uma discussão geralmente expõe essas diferenças. Para obter mais informações sobre como usar um modelo para reduzir inconsistências, consulte [requisitos de usuário de modelo](../modeling/model-user-requirements.md).

## <a name="use-models-with-other-artifacts"></a>Usar modelos com outros artefatos

Um modelo não é, por si só, uma especificação de requisitos ou uma arquitetura. É uma ferramenta para expressar alguns aspectos dessas coisas de forma mais clara, mas nem todos os conceitos necessários durante o design de software podem ser expressos. Os modelos devem, portanto, ser usados junto com outros meios de comunicação, como páginas do OneNote ou parágrafos, Microsoft Office documentos, itens de trabalho no Team Foundation ou notas auto-adesivas no mural da sala de projeto. Além do último item, todos esses tipos de objeto podem ser vinculados a partes de elementos do modelo.

Outros aspectos da especificação que normalmente são usados juntamente com modelos incluem o seguinte. Dependendo da escala e do estilo do seu projeto, você pode usar vários desses aspectos ou não usar nenhum:

- Histórias de usuários. Uma história de usuário é uma breve descrição, discutida com usuários e outros participantes, de um aspecto do comportamento do sistema que será entregue em uma das iterações do projeto. Uma história de usuário típica começa "o cliente poderá...." Uma história de usuário pode introduzir um grupo de casos de uso ou pode definir extensões de casos de uso que foram desenvolvidos anteriormente. Definir ou estender os casos de uso ajuda a tornar a história do usuário mais clara.

- Solicitações de alteração. Uma solicitação de alteração em um projeto mais formal é muito semelhante a uma história de usuário em um projeto ágil. A abordagem ágil trata todos os requisitos como alterações no que foi desenvolvido em iterações anteriores.

- Descrição do caso de uso. Um caso de uso representa uma maneira na qual um usuário interage com o sistema para atingir uma meta específica. Uma descrição completa inclui as sequências meta, principal e alternativa de eventos e resultados excepcionais. Um diagrama de caso de uso ajuda a resumir e fornecer uma visão geral dos casos de uso.

- Exemplos. Um cenário é uma descrição bem detalhada de uma sequência de eventos que mostra como o sistema, os usuários e outros sistemas trabalham juntos para fornecer valor aos participantes. Ele pode assumir a forma de uma apresentação de slides da interface do usuário ou de um protótipo da interface do usuário. Ele pode descrever um caso de uso ou uma sequência de casos de uso.

- Glossário. O Glossário de requisitos do projeto descreve as palavras com as quais os clientes discutem seu mundo. Os modelos de interface do usuário e requisitos também devem usar esses termos. Um diagrama de classe pode ajudar a esclarecer as relações entre a maioria desses termos. Criar os diagramas e o Glossário não apenas reduz os incompreendimentos insuficientes entre usuários e desenvolvedores, mas também expõe quase sempre os incompreendidos entre diferentes participantes comerciais.

- Regras de negócio. Muitas regras de negócio podem ser expressas como restrições invariáveis nas associações e atributos no modelo de classe de requisitos e como restrições em diagramas de sequência.

- Design de alto nível. Descreve as principais partes e como elas se encaixam. Os diagramas de componente, sequência e interface são uma parte importante de um design de alto nível.

- Padrões de design. Descreva as regras de design que são compartilhadas entre as diferentes partes do sistema.

- Especificações de teste. Scripts de teste e os designs de código de teste podem fazer uso bom de diagramas de atividade e de sequência para descrever sequências de etapas de teste. Os testes do sistema devem ser expressos em termos do modelo de requisitos para que possam ser facilmente alterados quando os requisitos forem alterados.

- Plano do projeto. O plano de projeto ou a pendência define quando cada recurso será entregue. Você pode definir cada recurso declarando os casos de uso e as regras de negócio que ele implementa ou estende. Você pode consultar os casos de uso e as regras de negócios diretamente no plano, ou pode definir um conjunto de recursos em um documento separado e usar os títulos de recursos no plano.

## <a name="use-models-in-iteration-planning"></a>Usar modelos no planejamento de iteração

Embora todos os projetos sejam diferentes em sua escala e organização, um projeto típico é planejado como uma série de iterações entre duas e seis semanas. É importante planejar iterações suficientes para permitir que os comentários de iterações iniciais sejam usados para ajustar o escopo e os planos para iterações posteriores.

Você pode achar as sugestões a seguir úteis para ajudar a perceber os benefícios da modelagem em um projeto iterativo.

### <a name="sharpen-focus-as-each-iteration-approaches"></a>Ajustar o foco à medida que cada iteração se aproxima

À medida que cada iteração se aproxima, use modelos para ajudar a definir o que será entregue no final da iteração.

- Não modele tudo em detalhes nas iterações iniciais. Na primeira iteração, crie um diagrama de classe para os itens principais no Glossário do usuário, desenhe um diagrama dos principais casos de uso e desenhe um diagrama dos principais componentes. Não Descreva nenhum desses detalhes, pois os detalhes serão alterados posteriormente no projeto. Use os termos definidos neste modelo para criar uma lista de recursos ou histórias de usuários principais. Atribua os recursos a iterações de forma a balancear aproximadamente a carga de trabalho estimada em todo o projeto. Essas atribuições serão alteradas posteriormente no projeto.

- Tente implementar versões simplificadas de todos os casos de uso mais importantes em uma iteração inicial. Estenda os casos de uso em iterações posteriores. Essa abordagem ajuda a reduzir o risco de descobrir uma falha nos requisitos ou a arquitetura tarde demais no projeto para fazer algo sobre ele.

- Próximo ao final de cada iteração, mantenha um workshop de requisitos para definir em detalhes os requisitos ou as histórias de usuários que serão desenvolvidos na próxima iteração. Convide usuários e participantes de negócios que podem decidir sobre prioridades, bem como desenvolvedores e testadores de sistemas. Permita três horas para definir os requisitos para uma iteração de 2 semanas.

- O objetivo do workshop é que todos concordem com o que será realizado no final da próxima iteração. Use modelos como uma das ferramentas para ajudar a esclarecer os requisitos. A saída do workshop é uma pendência de iteração: ou seja, uma lista de tarefas de desenvolvimento no Team Foundation e conjuntos de testes no [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)].

- No workshop de requisitos, discuta o design apenas insofár, pois você precisa determinar as estimativas para as tarefas de desenvolvimento. Caso contrário, mantenha a discussão sobre o comportamento do sistema que os usuários podem enfrentar diretamente. Mantenha o modelo de requisitos separado do modelo arquitetônico.

- Os participantes não técnicos geralmente não têm problemas para entender os diagramas UML, com algumas diretrizes de você.

### <a name="link-model-to-work-items"></a>Vincular modelo a itens de trabalho

Após o workshop de requisitos, elabore os detalhes do modelo de requisitos e vincule o modelo às tarefas de desenvolvimento. Você pode fazer isso vinculando itens de trabalho no Team Foundation a elementos no modelo.

Você pode vincular qualquer elemento a itens de trabalho, mas os elementos mais úteis são os seguintes:

- Comentários que descrevem regras de negócio ou requisitos de qualidade de serviço. Para obter mais informações, consulte [requisitos de usuário de modelo](../modeling/model-user-requirements.md).

### <a name="link-model-to-tests"></a>Vincular modelo a testes

Use o modelo de requisitos para guiar o design dos testes de aceitação. Crie esses testes simultaneamente com o trabalho de desenvolvimento.

Para saber mais sobre essa técnica, consulte [desenvolver testes de um modelo](../modeling/develop-tests-from-a-model.md).

### <a name="estimate-remaining-work"></a>Estimar o trabalho restante

Um modelo de requisitos pode ajudar a estimar o tamanho total do projeto em relação ao tamanho de cada iteração. Avaliar o número e a complexidade dos casos de uso e das classes pode ajudá-lo a estimar o trabalho de desenvolvimento que será necessário. Quando você tiver concluído as primeiras iterações, uma comparação dos requisitos cobertos e dos requisitos que ainda devem ser abordados poderá proporcionar uma medida aproximada do custo e do escopo do restante do projeto.

Próximo ao final de cada iteração, examine a atribuição de requisitos para futuras iterações. Pode ser útil representar o estado do seu software no final de cada iteração como um subsistema em um diagrama de caso de uso. Em suas discussões, você pode mover casos de uso e extensões de caso de uso de um desses subsistemas para outro.

## <a name="levels-of-abstraction"></a>Níveis de abstração

Os modelos têm uma variedade de abstração em relação ao software. Os modelos mais concretos representam diretamente o código do programa, e os modelos mais abstratos representam os conceitos de negócios que podem ou não ser representados no código.

Um modelo pode ser exibido por meio de vários tipos de diagramas. Para obter informações sobre modelos e diagramas, consulte [criar modelos para seu aplicativo](../modeling/create-models-for-your-app.md).

Tipos diferentes de diagrama são úteis para descrever o design em diferentes níveis de abstração. Muitos dos tipos de diagrama são úteis em mais de um nível. Esta tabela mostra como cada tipo de diagrama pode ser usado.

|Nível de design|Tipos de diagrama|
|-|-|
|Processo empresarial<br /><br /> A compreensão do contexto no qual seu sistema será usado ajuda você a entender o que os usuários precisam dele.|-Os diagramas de classe conceitual descrevem os conceitos de negócios usados no processo de negócios.|
|Requisitos do usuário<br /><br /> Definição do que os usuários precisam do seu sistema.|-As regras de negócios e os requisitos de qualidade de serviço podem ser descritos em documentos separados.|
|Design de alto nível<br /><br /> A estrutura geral do sistema: os principais componentes e como eles se juntam.|-Diagramas de dependência descrevem como o sistema é estruturado em partes interdependentes. Você pode validar o código do programa em relação a diagramas de dependência para garantir que ele esteja de acordo com a arquitetura.|
|Análise de código<br /><br /> Os diagramas podem ser gerados a partir do código.|-Diagramas de dependência mostram as dependências entre classes. O código atualizado pode ser validado em relação a um diagrama de dependência.<br />-Os diagramas de classe mostram as classes no código.|

## <a name="external-resources"></a>Recursos externos

|**Categoria**|**Links**|
|-|-|
|**Vídeos**|![link para vídeo](../data-tools/media/playvideo.gif) [vídeos como faço para do MSDN: como criar e usar diagramas e modelos UML (Visual Studio 2010 Ultimate)](/previous-versions/visualstudio/visual-studio-2010/dd831853(v=vs.100))<br /><br /> link do ![para vídeo](../data-tools/media/playvideo.gif) [Channel 9: UML com o Visual Studio 2010](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-1-brainstorming-a-project)<br /><br /> ![link para vídeo](../data-tools/media/playvideo.gif) [série como faço para o MSDN: ferramentas e EXTENSIBILIDADE UML (Visual Studio 2010 Ultimate)](/previous-versions/visualstudio/visual-studio-2010/dd831853(v=vs.100))|
|**Fóruns**|[ferramentas de modelagem & de visualização do Visual Studio](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch) - <br />[SDK de modelagem do & de visualização do Visual Studio (ferramentas DSL)](https://social.msdn.microsoft.com/Forums/home?forum=dslvsarchx) - |
|**Blogs**|[Microsoft DevOps](https://devblogs.microsoft.com/devops/)|
|**Artigos técnicos e diários**|[Centro de arquitetura do MSDN](/previous-versions/dn630665(v=msdn.10))<br /><br /> [Diretrizes de ferramentas de arquitetura do Visual Studio](../modeling/visual-studio-architecture-tooling-guidance.md)|

## <a name="see-also"></a>Veja também

- [Usar modelos no desenvolvimento ágil](https://msdn.microsoft.com/592ac27c-3d3e-454a-9c38-b76658ed137f)
- [Criar modelos para o aplicativo](../modeling/create-models-for-your-app.md)
- [Requisitos de usuário do modelo](../modeling/model-user-requirements.md)
- [Modelar a arquitetura do aplicativo](../modeling/model-your-app-s-architecture.md)
- [Desenvolver testes por meio de um modelo](../modeling/develop-tests-from-a-model.md)
- [Estruturar a solução de modelagem](../modeling/structure-your-modeling-solution.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
