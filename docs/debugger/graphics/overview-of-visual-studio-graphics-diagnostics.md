---
title: Visão geral do diagnóstico de gráficos | Microsoft Docs
ms.custom: seodec18
ms.date: 02/09/2017
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0bf8cbcc699f015cae954400744d9bd724d70c57
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73187919"
---
# <a name="overview-of-visual-studio-graphics-diagnostics"></a>Visão geral do diagnóstico de gráficos do Visual Studio
O Visual Studio *diagnóstico de gráficos* é um conjunto de ferramentas para gravar e analisar problemas de desempenho e renderização em aplicativos Direct3D. Diagnóstico de Gráficos pode ser usado em aplicativos que estão sendo executados localmente no seu computador Windows ou em um computador ou dispositivo remoto.

## <a name="using-graphics-diagnostics-to-debug-rendering-problems"></a>Usando o Diagnóstico de Gráficos para depurar problemas de renderização
 Depurar problemas de renderização em um aplicativo cheio de recursos gráficos não é tão simples quanto iniciar um depurador e percorrer alguns códigos. Em cada quadro, centenas de milhares de pixels exclusivos são produzidos, cada um de acordo com um conjunto complexo de estados, dados, parâmetros e códigos, e dentre eles, talvez apenas alguns pixels exibirão o problema que você está tentando diagnosticar. Para complicar ainda mais, o código que gera cada pixel é executado em hardware especializado que processa centenas de pixels paralelamente. As ferramentas e técnicas tradicionais de depuração (cujo aproveitamento é difícil mesmo no código em thread bastante simples) são ineficazes quando se deparam com grandes quantidades de dados.

 As ferramentas de Diagnóstico de Gráficos no [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] foram desenvolvidas para ajudar a localizar problemas de renderização, a começar pelos artefatos visuais que indicam o problema e rastreiam de volta para a origem do problema focando apenas o código de sombreador, os estágios de pipeline, as chamadas de desenho e o estado do dispositivo que são relevantes, no próprio código-fonte do aplicativo.

## <a name="directx-version-compatibility"></a>Compatibilidade de versão do DirectX
 O Diagnóstico de Gráficos dá suporte a aplicativos que usam o Direct3D 10 ou superior e fornece suporte limitado para aplicativos que usam o Direct2D. Ele não oferece suporte a aplicativos que usam versões anteriores do Direct3D, DirectDraw ou outras APIs gráficas.

### <a name="windows-10-and-direct3d-12"></a>Windows 10 e Direct3D 12
 O Windows 10 introduziu o *Direct3D 12*, que é substancialmente diferente do Direct3D 10 e do Direct3D 11. Essas diferenças trazem o DirectX de volta ao alinhamento com o hardware de gráficos moderno e liberando seu potencial completo, mas também trazem grandes alterações de API e colocam maior responsabilidade no programador para gerenciar tempos de vida e contenção de recursos. Apesar das diferenças, Diagnóstico de Gráficos com o Direct3D 12 mantém a paridade de recursos com Diagnóstico de Gráficos com o Direct3D 11,2.

 O Windows 10 também mantém o suporte para versões anteriores do Direct3D e os jogos e aplicativos que dependem deles. Diagnóstico de Gráficos no Visual Studio continua a dar suporte ao Direct3D 10 e ao Direct3D 11 no Windows 10.

### <a name="limited-direct2d-support"></a>Suporte limitado ao Direct2D
 Como o Direct2D é uma API de modo de usuário que foi criada com base no Direct3D, você pode usar o Diagnóstico de Gráficos para ajudar na depuração de problemas de renderização em aplicativos que usam o Direct2D. No entanto, como apenas os eventos do Direct3D subjacentes são gravados, em vez de eventos do Direct2D de nível mais alto, os eventos do Direct2D não aparecerão na Lista de Eventos de Gráficos. Além disso, como a relação entre os eventos do Direct2D e os eventos resultantes do Direct3D nem sempre é clara, usar o Diagnóstico de Gráficos para depurar problemas de renderização em aplicativos que usam o Direct2D não é algo simples. Ainda assim, você pode usar o Diagnóstico de Gráficos para obter informações sobre problemas de renderização de nível baixo em aplicativos que usam o Direct2D.

## <a name="graphics-diagnostics-features-in-visual-studio"></a>Diagnóstico de Gráficos recursos no Visual Studio
 Diagnóstico de Gráficos tem uma interface dedicada – a janela do analisador de gráficos-para diagnosticar problemas de renderização, mas também adiciona algumas ferramentas à interface do Visual Studio.

### <a name="the-graphics-toolbar-visual-studio"></a>A barra de ferramentas de gráficos (Visual Studio)
 A barra de ferramentas de gráficos fornece acesso rápido aos comandos Diagnóstico de Gráficos.

 O botão **Iniciar Diagnóstico** executa o aplicativo no Diagnóstico de Gráficos. Quando um aplicativo é executado em Diagnóstico de Gráficos, o botão **capturar o próximo quadro renderizado** é habilitado.

### <a name="diagnostics-capture-interface"></a>Interface de captura de diagnóstico
 Quando você executa seu aplicativo em Diagnóstico de Gráficos, o Visual Studio exibe uma interface de sessão de diagnóstico que você pode usar para capturar quadros e que também exibe a CPU atual e a carga de GPU. A carga de CPU e GPU é exibida para ajudá-lo a identificar quadros que talvez você queira capturar devido a suas características de desempenho, em vez de renderizar erros.

 No entanto, essa não é a única maneira de capturar quadros. Você também pode capturar quadros usando a interface de captura programática ou usando o programa de captura de linha de comando, dxcap. exe.

 Consulte [capturando informações de gráficos](capturing-graphics-information.md) para obter mais informações.

### <a name="gpu-usage"></a>Uso de GPU
 Diagnóstico de Gráficos também pode criar o perfil do desempenho do seu aplicativo do Direct3D. Como os dados de criação de perfil seriam distorcidos pela gravação de detalhes de eventos gráficos, isso é separado da captura de quadros a serem usados examinados com o analisador de gráficos.

 Consulte [uso de GPU](../../profiling/gpu-usage.md) para obter mais informações.

### <a name="directx-control-panel"></a>Painel de controle do DirectX
 O painel de controle do DirectX é um componente do DirectX que você pode usar para alterar o comportamento do DirectX. Por exemplo, é possível habilitar a versão de depuração dos componentes de tempo de execução do DirectX, selecionar os tipos de mensagem de depuração que são relatados e impedir que determinados recursos de hardware gráfico sejam usados para emular um hardware menos capaz. Esse nível de controle sobre o DirectX pode ajudar você a depurar e testar seu aplicativo DirectX. É possível acessar o painel de controle do DirectX do Visual Studio.

#### <a name="to-open-the-directx-control-panel"></a>Para abrir o painel de controle do DirectX

- Na barra de menus, escolha **Depurar**, **Gráficos**, **Painel de Controle do DirectX**.

## <a name="graphics-analyzer"></a>Analisador de gráficos
 O Analisador de Gráficos do Visual Studio é uma interface dedicada para examinar problemas de desempenho e renderização em quadros que você já capturou. Dentro do analisador de gráficos, você encontrará várias ferramentas para ajudá-lo a explorar e entender o comportamento de renderização de seu aplicativo. Cada ferramenta expõe um tipo diferente de informações sobre o quadro que está sendo inspecionado, e as ferramentas são projetadas para serem usadas em conjunto para restringir intuitivamente a origem de um problema de renderização, começando da sua aparência no framebuffer.

 Esta ilustração mostra um layout típico de ferramentas no analisador de gráficos.

 ![Todas as janelas do depurador de gráficos](media/graphicsdebuggerwindows.png "GraphicsDebuggerWindows")

### <a name="the-graphics-toolbar-graphics-analyzer"></a>A barra de ferramentas de gráficos (analisador de gráficos)
 A barra de ferramentas de gráficos fornece acesso rápido às janelas de ferramenta do analisador de gráficos.

 ![A barra de ferramentas de gráficos no modo de diagnóstico de gráficos](media/vsg_toolbar.png "vsg_toolbar")

### <a name="graphics-log-document"></a>Documento de log de gráficos
 Dentro do analisador de gráficos, o documento de log de gráficos é a janela de ferramentas mais proeminente. Essa janela representa todos os quadros capturados executando seu aplicativo em Diagnóstico de Gráficos. A partir daqui, você pode selecionar um quadro diferente para examinar ou selecionar um pixel específico que você deseja examinar com a ferramenta de histórico de pixel. A imagem framebuffer exibida neste documento é alterada para refletir o evento atualmente selecionado para que você possa ver como o framebuffer é afetado ao longo do tempo.

 O [documento de log de gráficos](graphics-log-document.md) também é o ponto de entrada para a ferramenta de análise de quadros, que ajuda você a entender o desempenho de um quadro, alterando a maneira como determinados aspectos da renderização são configurados e fornecendo resultados de benchmark para comparar com o original.

### <a name="event-list"></a>Lista de eventos
 Os eventos gráficos marcam cada chamada à API do Direct3D e o evento definido pelo usuário.

 A [lista de eventos](graphics-event-list.md) mostra todos os eventos gráficos que foram registrados durante o quadro que você está examinando. Para ajudá-lo a encontrar o que é importante, a lista de eventos pode ser exibida hierarquicamente, com alterações de estado recentes abaixo da chamada de desenho subsequente — ou como uma linha do tempo. Além disso, os eventos são codificados por cores com base na fila à qual pertencem e você pode filtrar a lista para incluir apenas os eventos nos quais você está interessado.

 Quando você seleciona um evento na lista, o restante das ferramentas de análise de gráficos reflete o estado do quadro no momento do evento. Dessa forma, você pode ver o efeito de qualquer evento na GPU. Por exemplo, você pode ver o efeito imediato de qualquer chamada de desenho no framebuffer, mesmo se ele se tornar obscuro por chamadas de desenho subsequentes. Alguns eventos também têm hiperlinks que você pode seguir para ver mais detalhes sobre seus parâmetros ou objetos de recursos relacionados.

### <a name="pipeline-stages"></a>Estágios do pipeline
 Cada chamada de desenho em seu aplicativo passa pelo pipeline de gráficos fornecido pelo Direct3D. Em cada estágio do pipeline, a saída do estágio anterior é transformada por um pequeno programa, chamado de sombreador e, em seguida, passada para o próximo estágio até que ele seja finalmente processado para a tela. Muitos erros de renderização ocorrem no limite entre os estágios de pipeline quando o formato de saída é diferente do esperado próximo estágio ou quando qualquer um deles simplesmente produz resultados incorretos. Normalmente, você só obtém os resultados finais como veria na tela e não pode dizer com facilidade onde ocorreu o erro no pipeline.

 A janela [estágios de pipeline](graphics-pipeline-stages.md) visualiza o resultado de cada estágio de forma independente, para que você possa determinar mais facilmente em qual estágio um problema de renderização aparece primeiro. Depois de determinar qual estágio é, você pode começar a depurar seu sombreador diretamente na janela estágios de pipeline.

### <a name="graphics-state"></a>Estado gráfico
 As operações de renderização dependem de muitos Estados que normalmente se espalham por vários objetos. Muitos tipos de problemas de renderização são causados por um estado mal configurado.

 A janela de [estado](graphics-state.md) coleta as informações de estado relevantes para cada chamada de desenho em um único local para que seja mais fácil de localizar e também realça as alterações de estado ocorridas desde a chamada de desenho anterior.

### <a name="pixel-history"></a>Histórico de pixel
 Em cenas complexas, não é incomum que um pixel seja sombreado várias vezes em um único quadro. Às vezes, a cor anterior é substituída, mas outras vezes as cores são combinadas para obter efeitos como transparência. Quando o resultado da combinação deles não tem a aparência certa, você não consegue dizer facilmente se é porque uma das cores estava incorreta ou se há um problema com a maneira como elas foram combinadas. Em outras ocasiões, um objeto pode parecer estar ausente porque sua contribuição para o pixel foi rejeitada por algum motivo.

 A janela de [histórico de pixel](graphics-pixel-history.md) visualiza o histórico completo do sombreador de cada pixel no quadro, incluindo contribuições rejeitadas. Para contribuições que não foram rejeitadas, ele exibe os resultados brutos do sombreador e como cada nova cor foi combinada com a anterior. Com essas informações, é muito mais fácil localizar a fonte de erros em pixels que misturam os resultados do sombreador ou quando um objeto renderizado está ausente porque sua contribuição para o pixel foi rejeitada incorretamente.

### <a name="event-call-stack"></a>Pilha de chamadas do evento
 O código do sombreador não é a única fonte de problemas de renderização em um aplicativo do Direct3D, às vezes, o código-fonte do aplicativo passa o parâmetro incorreto ou não configura o Direct3D bem à direita. Um tipo de erro que o recurso abordado anteriormente, histórico de pixel, pode ajudá-lo a encontrar quando um objeto renderizado está ausente porque todos os seus pixels foram rejeitados. Esse tipo de erro geralmente ocorre quando você configurou incorretamente uma configuração, como aquela que controla como o teste de profundidade é executado, e geralmente você pode encontrar o erro em algum lugar na pilha de chamadas da chamada de desenho do objeto ausente.

 A janela [pilha de chamadas de evento](graphics-event-call-stack.md) exibe a pilha de chamadas completa de cada evento de gráficos na lista de eventos e até mesmo permite que você salte para o código-fonte do aplicativo se as informações de depuração estiverem disponíveis. Essa é uma ferramenta poderosa para seguir um erro de onde ele aparece pela primeira vez, na GPU, de volta para onde ele se originou no código-fonte do seu aplicativo.

### <a name="object-table"></a>Tabela de objetos
 Cada quadro que seu aplicativo renderiza é provavelmente apoiado por centenas ou até milhares de objetos de recursos. Eles podem incluir buffers de fundo e renderizar destinos, texturas, buffers de vértice, buffers de índice, buffers gerais – quase tudo o que os membros do Direct3D é um objeto.

 A [tabela de objetos](graphics-object-table.md) exibe todos os objetos que existem no momento do evento de gráficos selecionado na lista de eventos. Como a maioria dos objetos em um aplicativo típico são texturas, a lista de eventos é otimizada para mostrar os detalhes relevantes às imagens rapidamente. A coluna tipo informa que tipo de objeto está em cada linha e a coluna de formato mostra ainda mais o subtipo ou a versão do objeto. Outros detalhes também são mostrados. Alguns objetos também têm hiperlinks que você pode seguir para exibir o objeto com um visualizador mais especializado, como texturas (você pode exibir a textura como uma imagem) ou buffers (você pode escolher como o Visualizador de buffer analisa e exibe os bytes brutos do buffer definindo o buffer formato).

### <a name="frame-analysis"></a>Análise de quadro
 Os elementos gráficos do seu aplicativo não precisam apenas ser corretos. eles também precisam ser rápidos. Mesmo em dispositivos menos poderosos, como laptops, com gráficos integrados ou celulares. E eles ainda precisam ser ótimos.

 A ferramenta de [análise de quadros](graphics-frame-analysis.md) explora otimizações de desempenho potenciais alterando automaticamente a maneira como o aplicativo usa o Direct3D e fornece resultados de benchmark para comparação. Por exemplo, a análise de quadros pode habilitar o mapeamento de MIP em cada textura, o que pode revelar texturas que poderiam se beneficiar do mapeamento de MIP, mas que não estão habilitadas no momento. Em hardware que dá suporte a ele, a análise de quadros também apresenta informações coletadas dos contadores de desempenho da GPU – esse nível de informações pode identificar problemas de desempenho no nível de hardware, como altos números de interrupções de busca de textura ou erros de cache.

 Mas a análise de quadros não está prestes a ficar rápido. é sobre obter a maior parte do desempenho que você pode, ao mesmo tempo, fornecer a menor quantidade de qualidade visual. Às vezes, um efeito caro que parece ótimo em uma exibição grande não faz o mesmo impacto quando exibido na tela pequena de um telefone, em que um efeito mais simples pode parecer muito bom sem descarregar a bateria. As alterações automáticas e os parâmetros de comparação que a análise gráfica fornece podem ajudá-lo a encontrar o equilíbrio certo para seu aplicativo em uma variedade de dispositivos.

## <a name="see-also"></a>Consulte também
- [Ferramenta de captura de linha de comando](command-line-capture-tool.md)
- [Depurador HLSL](hlsl-shader-debugger.md)