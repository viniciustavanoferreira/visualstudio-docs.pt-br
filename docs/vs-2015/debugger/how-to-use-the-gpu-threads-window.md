---
title: 'Como: Usar a janela de Threads GPU | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.gputthreads
- vs.debug.gputhreads
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, GPU threads window
ms.assetid: c647c502-a9f0-48e0-a430-976744a5fa51
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c7b97c346cc933e14292fbb1198bfb69ecf59717
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65696170"
---
# <a name="how-to-use-the-gpu-threads-window"></a>Como: Usar a janela Threads de GPU
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Na janela Threads da GPU, você pode examinar e trabalhar com threads que estão sendo executadas no GPU no aplicativo que você está depurando. Para obter mais informações sobre aplicativos que são executados na GPU, consulte [visão geral do C++ AMP](https://msdn.microsoft.com/library/9e593b06-6e3c-43e9-8bae-6d89efdd39fc).  
  
 A janela de Threads da GPU contém uma tabela na qual cada linha representa um conjunto de threads de GPU que têm os mesmos valores em todas as colunas. Você pode classificar, reorganizar, remover e agrupar os itens que estão nas colunas. Você pode sinalizar, remover sinalização, congelar (suspender) e descongelar (retomar) threads da janela de Threads da GPU. As colunas a seguir são exibidas na janela Threads da GPU:  
  
- A coluna do sinalizador, na qual você pode marcar um thread ao qual deseja prestar atenção especial.  
  
- A coluna thread ativo, em que uma seta amarela indica um thread ativo. Uma seta indica um thread onde a execução interrompe no depurador.  
  
- A coluna **Contagem de Threads**, que exibe o número de segmentos na mesma localização.  
  
- A coluna de **Linha**, que exibe a linha de código em que cada grupo de segmentos está localizado.  
  
- A coluna de **Endereço** que exibe o endereço da instrução em que cada grupo de threads está localizado. Por padrão, essa coluna está ocultada.  
  
- A coluna **Localização**, que é a localização no código-fonte.  
  
- A coluna **Status**, que mostra se o thread está ativo, bloqueado, não iniciado ou concluído.  
  
- A coluna **Lado a lado**, que mostra o índice lado a lado para os segmentos na linha.  
  
  O cabeçalho da tabela mostra que o quadro e o thread estão sendo exibidos.  
  
  [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-display-the-gpu-threads-window"></a>Para exibir a janela Threads da GPU  
  
1. No **Gerenciador de Soluções**, abra o menu de atalho para o projeto e escolha **Propriedades**.  
  
2. Na janela **Páginas de Propriedades** para o projeto, em **Propriedades de Configuração**, escolha **Depuração**.  
  
3. Na lista **Depurador a iniciar**, selecione **Depurador Local do Windows**. Na lista **Tipo de Depurador**, selecione **Somente GPU**. Você deve escolher este depurador para parar em pontos de interrupção no código executado no GPU.  
  
4. Escolha o botão **OK**.  
  
5. Defina um ponto de interrupção no código do GPU.  
  
6. Na barra de menus, escolha **Depurar**, **Iniciar Depuração**. Aguarde até que o aplicativo atinja o ponto de interrupção.  
  
7. Na barra de menus, escolha **Depurar**, **Janelas**, **Threads da GPU**.  
  
### <a name="to-change-to-a-different-active-thread"></a>Para alterar para um thread ativo diferente  
  
- Clique duas vezes na coluna. (Teclado: Selecione a linha e escolha Enter.)  
  
### <a name="to-display-a-particular-tile-and-thread"></a>Para exibir um determinado bloco e o thread  
  
1. Escolha o botão **Expandir o Comutador de Thread** na janela Threads da GPU.  
  
2. Insira os valores do quadro e de thread nas caixas de texto.  
  
3. Escolha o botão que tem a seta.  
  
### <a name="to-display-or-hide-a-column"></a>Para exibir ou ocultar uma coluna  
  
- Abra o menu de atalho para a janela Threads da GPU, escolha **Colunas** e, em seguida, escolha a coluna que você quer exibir ou ocultar.  
  
### <a name="to-sort-by-a-column"></a>Para classificar por coluna  
  
- Selecione o título da coluna.  
  
### <a name="to-group-threads"></a>Para agrupar threads  
  
- Abra o menu de atalho da janela Threads da GPU, escolha **Agrupar por** e escolha um dos nomes de coluna exibidos. Escolha **Nenhum** para desagrupar os threads.  
  
### <a name="to-freeze-or-thaw-a-row-of-threads"></a>Para congelar ou descongelar uma linha de threads  
  
- Abra o menu de atalho da linha e escolha **Congelar** ou **Descongelar**.  
  
### <a name="to-flag-or-unflag-a-row-of-threads"></a>Para sinalizar ou remover sinalização de uma linha de threads  
  
- Selecione a coluna do sinalizador do thread ou abra o menu de atalho do thread e escolha **Sinalizar** ou **Remover Sinalização**.  
  
### <a name="to-display-only-flagged-threads"></a>Para exibir somente threads sinalizados  
  
- Escolha o botão de sinalizador na janela Threads da GPU.  
  
## <a name="see-also"></a>Consulte também  
 [Depurar aplicativos multi-threaded](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Como: Usar a janela Inspeção Paralela](../debugger/how-to-use-the-parallel-watch-window.md)   
 [Passo a passo: depurar um aplicativo C++ AMP](https://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)
