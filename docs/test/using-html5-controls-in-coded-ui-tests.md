---
title: Usando controles HTML5 em testes de IU codificados
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: 13f5da784a43df5146a66ca868bb6add9a702906
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75585581"
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>Usando controles HTML5 em testes de IU codificados

Os teste de IU codificados incluem suporte a alguns dos controles HTML5 incluídos no Internet Explorer 9 e no Internet Explorer 10.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

**Requisitos**

- Visual Studio Enterprise

> [!WARNING]
> Em versões anteriores do Internet Explorer 10, era possível executar testes de UI codificados em um nível de privilégio mais alto em comparação do processo do Internet Explorer. Ao executar testes de UI codificados no Internet Explorer 10, o teste de IU codificado e o processo do Internet Explorer devem ser o mesmo nível de privilégio. Isso ocorre devido a recursos mais seguros do AppContainer no Internet Explorer 10.

> [!WARNING]
> Se você criar um teste de IU codificado no Internet Explorer 10, talvez eles não sejam executados no Internet Explorer 9 ou no Internet Explorer 8. Isso ocorre porque o Internet Explorer 10 inclui controles HTML5, como Audio, Video, ProgressBar e Slider. Esses controles HTML5 não são reconhecidos pelo Internet Explorer 9 ou pelo Internet Explorer 8. Da mesma forma, seu teste de IU codificado usando o Internet Explorer 9 pode incluir alguns controles do HTML5 que também não serão reconhecidos pelo Internet Explorer 8.

## <a name="audio-control"></a>Controle de áudio

**Controle de áudio:** ações no controle do HTML5 áudio são registradas e reproduzidas corretamente.

![Controle do HTML5 áudio](../test/media/codedui_html5_audio.png)

|Ação|Gravação|Código gerado|
|-|---------------|-|
|**Reproduzir áudio**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Play \<name> Audio from 00:00:00|HtmlAudio.Play(TimeSpan)|
|**Busca em uma hora específica no áudio**|Seek \<name> Audio to 00:01:48|HtmlAudio.Seek(TimeSpan)|
|**Pausar áudio**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Pause \<name> Audio at 00:01:53|HtmlAudio.Pause(TimeSpan)|
|**Desativar áudio**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Mute \<name> Audio|HtmlAudio.Mute()|
|**Ativar áudio**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Unmute \<name> Audio|HtmlAudio.Unmute()|
|**Alterar volume de áudio**|Definir volume de \<name> Audio to 79%|HtmlAudio.SetVolume(float)|

Confira [HTMLAudioElement](https://developer.mozilla.org/docs/Web/API/HTMLAudioElement) para obter uma lista de propriedades às quais você pode adicionar uma declaração.

**Propriedades de pesquisa:** As propriedades `HtmlAudio` de `Id` `Name` busca `Title`são , e .

**Propriedades do filtro:** As propriedades `HtmlAudio` do `Src` `Class`filtro `ControlDefinition` `TagInstance`para são , e .

> [!NOTE]
> O tempo de busca de Seek e Pause pode ser significativo. Durante a reprodução, o teste de IU codificado aguardará até que o tempo especificado em `(TimeSpan)` antes da pausa do áudio. Se por alguma circunstância especial, o tempo especificado tiver passado antes de atingir o comando Pause, uma exceção será lançada.

## <a name="video-control"></a>Controle de vídeo
**Controle de vídeo:** ações no controle de vídeo HTML5 são registradas e reproduzidas corretamente.

![Controle do HTML5 vídeo](../test/media/codedui_html5_video.png)

|Ação|Gravação|Código gerado|
|-|---------------|-|
|**Reproduzir vídeo**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Play \<name> Video  from 00:00:00|HtmlVideo.Play(TimeSpan)|
|**Busca em uma hora específica no vídeo**|Seek \<name> Video to 00:01:48|HtmlVideo.Seek(TimeSpan)|
|**Pausar vídeo**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Pause \<name> Video at 00:01:53|HtmlVideo.Pause(TimeSpan)|
|**Desativar vídeo**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Mute \<name> Video|HtmlVideo.Mute()|
|**Ativar vídeo**<br /><br /> Diretamente do controle ou do menu do clique com o botão direito do controle.|Unmute \<name> Video|HtmlVideo.Unmute()|
|**Alterar volume de vídeo**|Definir volume de \<name> Video to 79%||

Confira [HTMLVideoElement](https://developer.mozilla.org/docs/Web/HTML/Element/video) para obter uma lista de propriedades às quais você pode adicionar uma declaração.

**Propriedades de pesquisa:** As propriedades `HtmlVideo` de `Id` `Name` busca `Title`são , e .

**Propriedades do filtro:** As propriedades `HtmlVideo` do `Src` `Poster`filtro `Class` `ControlDefinition` para `TagInstance`são, e .

> [!NOTE]
> Se você Avançar ou retroceder rapidamente o vídeo usando rótulos-30s ou +30s, isso será agregado para buscar o momento apropriado.

## <a name="progressbar"></a>ProgressBar
**Controle de ProgressBar:** a ProgressBar é um controle não interagível. Você pode adicionar asserções nas propriedades `Value` e `Max` desse controle. Para obter mais informações, confira [HTMLProgressElement](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress).

![Controle ProgressBar do HTML5](../test/media/codedui_html5_progressbar.png)

## <a name="see-also"></a>Confira também

- [Elementos HTML](https://developer.mozilla.org/docs/Web/HTML/Element)
- [Usar a automação da interface do usuário para testar o código](../test/use-ui-automation-to-test-your-code.md)
- [Criar testes de IU codificados](../test/use-ui-automation-to-test-your-code.md)
- [Configurações e plataformas compatíveis para testes de IU codificados e gravações de ação](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
