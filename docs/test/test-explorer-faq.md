---
title: Perguntas Frequentes sobre o Gerenciador de Testes
ms.date: 08/14/2019
ms.topic: conceptual
helpviewer_keywords:
- Test Explorer
- Test window
- Visual Studio Test Explorer
- summary line
- unit tests
- Test Explorer FAQ
ms.author: kehavens
ms.workload:
- multiple
author: kendrahavens
manager: jillfra
ms.openlocfilehash: cec8ea3ea091ab1ea65bcad2bd4cca139fd74042
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75846817"
---
# <a name="visual-studio-test-explorer-faq"></a>Perguntas frequentes sobre o Gerenciador de Testes do Visual Studio
::: moniker range=">=vs-2019"

## <a name="where-is-group-by-traits-in-visual-studio-2019"></a>Onde está o agrupamento por características no Visual Studio 2019?
Esse agrupamento por características foi movido para uma coluna. Com a hierarquia personalizável e de várias camadas no Visual Studio 2019 versão 16.2, pensamos que incluir características como um agrupamento resultou em uma complexidade visual desnecessária. Estamos atentos e receptivos a comentários sobre esse design! https://developercommunity.visualstudio.com/content/problem/588029/no-longer-able-to-group-by-trait-in-test-explorer.html

Por enquanto, você pode clicar com o botão direito do mouse na coluna no Gerenciador de Testes e selecionar Colunas. Marque a coluna Características e ela será exibida no Gerenciador de Testes. Agora você pode filtrar essa coluna por quais características está interessado.

![Exibir a coluna de características](media/vs-2019/trait-column.png)
![Filtrar a coluna de características](media/vs-2019/trait-column-filter.png)
::: moniker-end

## <a name="dynamic-test-discovery"></a>Detecção de testes dinâmica

**Test Explorer não está descobrindo meus testes que são dinamicamente definidos. (Por exemplo, teorias, adaptadores personalizados, traços personalizados, #ifdefs, etc.) Como posso descobrir esses testes?**

::: moniker range=">=vs-2019"
Crie seu projeto para executar a descoberta baseada em assembly.
::: moniker-end
::: moniker range="vs-2017"
Compile o projeto e verifique se a descoberta baseada em assembly está ativada em **Ferramentas** > **Opções** > **Teste**.
::: moniker-end
A [Detecção de testes em tempo real](https://devblogs.microsoft.com/dotnet/real-time-test-discovery/) é a detecção de testes baseada na origem. Ele não pode descobrir testes que usam teorias, `#ifdef` adaptadores personalizados, traços personalizados, declarações e muito mais porque são definidos em tempo de execução. Um build é necessário para que esses testes sejam localizados com precisão. No Visual Studio 2017 versão 15.6 e posteriores, a descoberta baseada em assembly (o detector tradicional) é executada somente depois dos builds. Essa configuração significa que a detecção de testes em tempo real localiza o máximo de testes possível enquanto você está editando e a descoberta baseada em assembly permite que os testes definidos dinamicamente apareçam após um build. A detecção de testes em tempo real melhora a capacidade de resposta, mas ainda permite que você obtenha resultados completos e precisos após um build.

## <a name="test-explorer--plus-symbol"></a>Sinal de "+" (adição) do Gerenciador de Testes

**O que significa o '+' (sinal de mais) que aparece na linha superior do Gerenciador de Testes?**

O símbolo '+' (sinal de adição) indica que mais testes poderão ser descobertos após um build quando a descoberta baseada em assembly for executada. Esse símbolo será exibido quando forem detectados testes definidos dinamicamente no projeto.

![Linha de resumo do sinal de adição](media/testex-plussymbol.png)

::: moniker range="vs-2017"
## <a name="assembly-based-discovery"></a>Descoberta baseada em assembly

**A descoberta baseada em montagem não está mais funcionando para o meu projeto. Como faço para ligá-lo de volta?**

Acesse **Ferramentas** > **Opções** > **Teste** e marque a caixa **Adicionalmente, descobrir testes de assemblies compilados após builds.**

![Opção baseada em assembly](media/testex-toolsoptions.png)
::: moniker-end

## <a name="real-time-test-discovery"></a>Detecção de testes em tempo real

**Os testes agora aparecem no Test Explorer enquanto eu digito, sem ter que construir meu projeto. O que mudou?**

Esse recurso é chamado de [Detecção de testes em tempo real](https://devblogs.microsoft.com/dotnet/real-time-test-discovery/). Ele usa um analisador Roslyn para encontrar testes e popular o Gerenciador de Testes em tempo real, sem exigir que você compile o projeto. Para obter mais informações sobre o comportamento da detecção de testes para testes definidos dinamicamente, como teorias ou características personalizadas, confira [Detecção de testes dinâmica](#dynamic-test-discovery).

## <a name="real-time-test-discovery-compatibility"></a>Compatibilidade da detecção de testes em tempo real

**Quais linguagens e estruturas de teste podem usar a detecção de testes em tempo real?**

A [Detecção de testes em tempo real](https://devblogs.microsoft.com/dotnet/real-time-test-discovery/) só funciona em linguagens gerenciadas (C# e Visual Basic), pois é compilada com o compilador Roslyn. Por enquanto, a detecção de testes em tempo real só funciona para as estruturas xUnit, NUnit e MSTest.

## <a name="test-explorer-logs"></a>Logs do Gerenciador de Testes

**Como faço para ativar logs no Gerenciador de Testes?**

Navegue até **o** > **teste** **de opções de ferramentas** > e encontre a seção Registro lá.

## <a name="uwp-test-discovery"></a>Detecção de testes da UWP

**Por que meus testes em projetos UWP não são detectados enquanto eu não implanto o aplicativo?**

Os testes UWP têm como destino um runtime diferente quando o aplicativo é implantado. Isso significa que para encontrar testes com precisão em projetos UWP, além de compilar seu projeto, você também precisa implantá-lo.

## <a name="test-explorer-sorting"></a>Classificação do Gerenciador de Testes

**Como funciona a classificação de resultados de teste no modo de exibição de hierarquia?**

O modo de exibição de hierarquia classifica os testes em ordem alfabética e não por resultado. As outras configurações de agrupamento normalmente classificam os resultados de teste por resultado e, em seguida, em ordem alfabética. Veja o grupo diferente pelas opções na imagem a seguir para comparação. Você pode fornecer comentários sobre o design [neste assunto do GitHub](https://github.com/Microsoft/vstest/issues/1425).

![SortingExamples](media/testex-sortingex.png)

## <a name="test-explorer-hierarchy-view"></a>Modo de exibição da hierarquia do Gerenciador de Testes

**Na exibição de hierarquia, há ícones passados, falhos, ignorados e não executados ao lado de agrupamentos de nós-pais. O que significam esses ícones?**

Os ícones ao lado dos agrupamentos Projeto, Namespace e Classe mostram o estado dos testes nesse agrupamento. Consulte a tabela a seguir.

![Ícones de Hierarquia do Gerenciador de Testes](media/testex-hierarchyicons.png)

## <a name="search-by-file-path"></a>Pesquisar por caminho do arquivo

**Não existe mais um filtro de "caminho do arquivo" na caixa de pesquisa do Gerenciador de Testes.**

O filtro do caminho de arquivo na caixa de pesquisa do **Gerenciador de Testes** foi removida do Visual Studio 2017 versão 15.7. Essa funcionalidade tinha pouco uso e o Gerenciador de Testes pode recuperar métodos de teste com mais rapidez excluindo essa funcionalidade. Se essa alteração interromper seu fluxo de desenvolvimento, informe-nos enviando comentários na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com/).

## <a name="remove-undocumented-interfaces"></a>Remover interfaces não documentadas

**Algumas APIs relacionadas ao teste não estão mais presentes no Visual Studio 2019. O que mudou?**

No Visual Studio 2019, serão removidas algumas APIs de janela de teste que foram marcadas como públicas anteriormente, mas nunca foram documentadas oficialmente. Elas foram marcadas como "preteridas" no Visual Studio 2017 para fornecer um aviso antecipado aos mantenedores de extensão. Para o nosso conhecimento, muito poucas extensões haviam encontrado essas APIs e criado uma dependência delas. Elas incluem `IGroupByProvider`, `IGroupByProvider<T>`, `KeyComparer`, `ISearchFilter`, `ISearchFilterToken`, `ISearchToken` e `SearchFilterTokenType`. Se essa alteração afetar sua extensão, fale conosco enviando um bug na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).

## <a name="test-adapter-nuget-reference"></a>Referência ao NuGet do adaptador de teste

**No Visual Studio 2017, versão 15.8, meus testes são detectados, mas não são executados**.

Todos os projetos de teste devem incluir a referência ao NuGet do adaptador de teste do .NET no arquivo .csproj. Caso contrário, a saída desse teste será exibida no projeto se a detecção por uma extensão do adaptador de teste for iniciada após um build, ou se o usuário tentar executar os testes selecionados:

**O {} projeto de teste não faz referência a nenhum adaptador .NET NuGet. A descoberta ou execução do teste pode não funcionar para este projeto. Recomenda-se fazer referência aos adaptadores de teste NuGet em cada projeto de teste .NET na solução.**

Em vez de usar extensões do adaptador de teste, os projetos são solicitados a usar os pacotes do adaptador de teste do NuGet. Esse requisito melhora bastante o desempenho e causa menos problemas com a integração contínua. Leia mais sobre a substituição da extensão do adaptador de teste do .NET nas [notas de versão](/visualstudio/releasenotes/vs2017-relnotes-v15.8#testadapterextension).

::: moniker range="vs-2017"
> [!NOTE]
> Se você estiver usando o adaptador de teste NUnit 2 e não conseguir migrar para o adaptador de teste NUnit 3, você pode desativar esse novo comportamento de detecção na versão 15.8 do Visual Studio no**Teste****de Opções de** >  **Ferramentas** > .

![Comportamento do Adaptador do Gerenciador de Testes nas opções de ferramentas](media/testex-adapterbehavior.png)
::: moniker-end

## <a name="uwp-testcontainer-was-not-found"></a>O TestContainer do UWP não foi encontrado

**Meus testes do UWP não estão mais sendo executados no Visual Studio 2017 versão 15.7 e posterior.**

Projetos de teste do UWP recentes especificam uma propriedade de build da plataforma de teste que permite um melhor desempenho para identificar aplicativos de teste. Se você tiver um projeto de teste UWP que foi inicializado antes da versão 15.7 do Visual Studio, você poderá ver esse erro nos testes **de saída:** > **Tests**

**System.AggregateException: Ocorreu um ou mais erros. ---> System.InvalidOperationException: O seguinte TestContainer não foi encontrado {} em Microsoft.VisualStudio.TestWindow.Controller.TestContainerProvider \<GetTestContainerAsync>d__61.MoveNext()**

Para corrigir esse erro: 

- Atualize a propriedade de build do projeto de teste usando o seguinte código:

```XML
<UnitTestPlatformVersion Condition="'$(UnitTestPlatformVersion)' == ''">$(VisualStudioVersion)</UnitTestPlatformVersion>
```

- Atualize a versão do SDK da TestPlatform usando o seguinte código:

```XML
<SDKReference Include="TestPlatform.Universal, Version=$(UnitTestPlatformVersion)" />
```

## <a name="using-feature-flags"></a>Como usar sinalizadores de recursos

**Como ativar sinalizadores de recursos para experimentar os novos recursos de teste?**

Sinalizadores de recursos são usados para enviar partes experimentais ou incompletas do produto para usuários ávidos que gostariam de fazer comentários antes que os recursos sejam fornecidos oficialmente. Eles podem desestabilizar a experiência de IDE. Use-os somente em ambientes de desenvolvimento seguros, como máquinas virtuais. Sinalizadores de recursos são sempre configurações que você usa por sua própria conta e risco. Você pode ativar funcionalidades experimentais com a [extensão de sinalizadores de recursos](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension) ou por meio do Prompt de Comando do Desenvolvedor.

![Extensão de sinalizador de recursos](media/testex-featureflag.png)

Para ativar um sinalizador de recursos por meio do prompt de comando de desenvolvedor do Visual Studio, use o comando a seguir. Altere o caminho para onde o Visual Studio está instalado em seu computador e altere a chave do Registro para o sinalizador de recurso que você deseja.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise" HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Você pode desativar o sinalizador com o mesmo comando, usando o valor 0 em vez de 1 após dword.

## <a name="see-also"></a>Confira também

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [Criar e executar testes de unidade para código existente](https://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [Unidade teste seu código](unit-test-your-code.md)
- [Perguntas frequentes sobre o Live Unit Testing](live-unit-testing-faq.md)
