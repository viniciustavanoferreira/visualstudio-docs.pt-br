---
title: Configurações e plataformas com suporte em testes de IU codificados e gravações de ação | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests
ms.assetid: 544742b5-4ec1-4d51-b941-72b2f6ff17bc
caps.latest.revision: 108
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 946373cc304e4eddb9f724941d583ab653cfe140
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75851750"
---
# <a name="supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings"></a>Configurações e plataformas compatíveis para testes de IU codificados e gravações das ações
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

As configurações e as plataformas de testes de IU codificados com suporte no Visual Studio Enterprise são listadas na tabela a seguir. Essas configurações também se aplicam às gravações de ação criadas usando o [!INCLUDE[MTRlong](../includes/mtrlong-md.md)].

> [!NOTE]
> O processo de teste de IU codificado deve ter os mesmos privilégios que o aplicativo testado.

 **Requirements**

- Visual Studio Enterprise

## <a name="supported-configurations"></a>Configurações com suporte

|Configuração do|Com suporte|
|-------------------|---------------|
|Sistemas operacionais|[!INCLUDE[win7](../includes/win7-md.md)]<br /><br /> [!INCLUDE[winsvr08_r2](../includes/winsvr08-r2-md.md)]<br /><br /> [!INCLUDE[win8](../includes/win8-md.md)]<br /><br /> Windows 10|
|Suporte para 32 bits/64 bits|O Windows de 32 bits que está executando o [!INCLUDE[TCMext](../includes/tcmext-md.md)] de 32 bits pode testar aplicativos de 32 bits.<br /><br /> O Windows de 64 bits que está executando o [!INCLUDE[TCMext](../includes/tcmext-md.md)] de 32 bits pode testar os aplicativos WOW de 32 bits que têm Sincronização de IU.<br /><br /> O Windows de 64 bits que está executando o [!INCLUDE[TCMext](../includes/tcmext-md.md)] de 32 bits pode testar aplicativos do Windows Forms e do WPF que não têm Sincronização de IU.|
|Arquitetura|x86 e x64 **Observação:** não há suporte para o Internet Explorer no modo de 64 bits, exceto quando executado no [!INCLUDE[win8](../includes/win8-md.md)] ou em versões posteriores.|
|.NET|.NET 2.0, 3.0, 3.5, 4 e 4.5. **Observação:** [!INCLUDE[TCMext](../includes/tcmext-md.md)] e o Visual Studio exigirão que o .NET 4 funcione. No entanto, há suporte para os aplicativos desenvolvidos usando as versões listadas do .NET.|

> [!NOTE]
> *Sincronização de interface do usuário* é um recurso em que a reprodução é verificada na fila de mensagens de cada controle. Se um controle não respondeu ao evento enviado para ele, o evento será enviado novamente.

## <a name="platform-support"></a>Suporte de plataforma

|Platform|Nível de suporte|
|--------------|----------------------|
|Aplicativos do Windows Phone|Somente aplicativos do Phone com base em WinRT-XAML são compatíveis.|
|Aplicativos da Windows Store|Há suporte apenas para os aplicativos da Store baseados em XAML.|
|Aplicativos universais do Windows|Há suporte para Aplicativos Universais do Windows baseados em XAML somente no Windows Phone e Desktop.|
|{1&gt;Borda&lt;1}|No Visual Studio 2015 Atualização 2 e posterior, usando a [extensão de Teste de IU Codificado Entre Navegadores](https://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d)|
|Internet Explorer 8<br /><br /> Internet Explorer 9<br /><br /> Internet Explorer 10 **Importante:** há suporte para o Internet Explorer 10 somente na área de trabalho. <br /><br /> Internet Explorer 11 **Importante:** há suporte para o Internet Explorer 11 somente na área de trabalho.|Suporte total.<br /><br /> -   **Suporte para HTML5 no Internet Explorer 9 e Internet Explorer 10:** registro de suporte de testes de IU codificados, reprodução e validação dos controles HTML5: Audio, Video, ProgressBar e Slider. Para obter mais informações, consulte [Usar Controles HTML5 em Testes de IU Codificados](../test/using-html5-controls-in-coded-ui-tests.md). **Aviso:**      se você criar testes de IU codificados no Internet Explorer 10, eles poderão não ser executados no Internet Explorer 9 ou no Internet Explorer 8. Isso ocorre porque o Internet Explorer 10 inclui controles HTML5, como Audio, Video, ProgressBar e Slider. Esses controles HTML5 não são reconhecidos pelo Internet Explorer 9 ou pelo Internet Explorer 8. Da mesma forma, seu teste de IU codificado usando o Internet Explorer 9 pode incluir alguns controles do HTML5 que também não serão reconhecidos pelo Internet Explorer 8.<br />-   **Suporte para verificação ortográfica do Internet Explorer 10:** o Internet Explorer 10 inclui funcionalidades de verificação ortográfica para todas as caixas de texto. Isso permite que você escolha entre uma lista de correções sugeridas. O Teste de IU Codificado ignorará essas ações do usuário, como a seleção de uma sugestão de ortografia alternativa. Será gravado apenas o texto digitado final na caixa de texto.<br />     As seguintes ações são registradas para o teste de IU codificado que usa o controle de verificação ortográfica: Adicionar ao Dicionário, Copiar, Selecionar Tudo, Adicionar ao Dicionário e Ignorar.<br />-   **Suporte para Internet Explorer de 64 bits executado no Windows 8:** anteriormente, não havia suporte para versões de 64 bits do Internet Explorer para gravação e reprodução. Com o [!INCLUDE[win8](../includes/win8-md.md)] e o [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], os testes de IU codificados foram habilitados para versões de 64 bits do Internet Explorer. **Aviso:** o suporte de 64 bits para o Internet Explorer se aplica somente quando você executa o [!INCLUDE[win8](../includes/win8-md.md)] ou posterior.<br />-   **Suporte para sites fixos no Internet Explorer 9:** no Internet Explorer 9, foram introduzidos sites fixos. Com os sites fixos, você pode acessar seus sites favoritos diretamente da barra de tarefas do Windows, sem ter de abrir o Internet Explorer primeiro. Os testes de IU codificados agora podem gerar ações intencionais em sites fixos. Para obter mais informações sobre sites fixos, consulte [Sites fixos](https://windows.microsoft.com/en-US/internet-explorer/products/ie-9/features/pinned-sites).<br />-   **Suporte para marcas semânticas do Internet Explorer 9:** o Internet Explorer 9 introduziu as seguintes marcas semânticas: section, nav, article, aside, hgroup, header, footer, figure, figcaption e mark. Os testes de IU codificados ignoram todas essas marcas semânticas durante a gravação. Você pode adicionar asserções nessas marcas usando o Construtor de Teste de IU Codificado. Você pode usar o seletor de navegação no Construtor de Teste de IU Codificado para navegar para qualquer um desses elementos e exibir suas propriedades.<br />-   **Tratamento direto de caracteres de espaço em branco entre versões do Internet Explorer:** há diferenças no tratamento de caracteres de espaço em branco entre o Internet Explorer 8, o Internet Explorer 9 e o Internet Explorer 10. O Teste de IU Codificado trata dessas diferenças perfeitamente. Portanto, um teste de IU codificado criado no Internet Explorer 8, por exemplo, executará com êxito no Internet Explorer 9 e no Internet Explorer 10.<br />-   **A área de notificação do Internet Explorer agora é registrada com o conjunto de atributos “Continuar com erro”:** todas as ações na área de notificação do Internet Explorer agora são registradas com o conjunto de atributos “Continuar com erro”. Se a barra de notificação não aparecer durante a reprodução, as ações nela serão ignoradas e o teste de IU codificado continuará com a próxima ação.|
|Controles de terceiros no Windows Forms e no WPF|Suporte total.<br /><br /> Para habilitar os controles de terceiros em aplicativos do Windows Forms e do WPF, você deve adicionar referências e código. Para obter mais informações, consulte [Habilitar testes de IU codificados dos controles](../test/enable-coded-ui-testing-of-your-controls.md).|
|Internet Explorer 6<br /><br /> Internet Explorer 7|{1&gt;Sem suporte.&lt;1}|
|Chrome<br /><br /> Firefox|Não há suporte para a gravação de etapas de ação. Os testes de IU codificados podem ser executados novamente nos navegadores Chrome e Firefox com a Atualização 4 do Visual Studio 2012 ou posterior. Acesse [aqui](https://msdn.microsoft.com/library/jj835758.aspx) para obter mais detalhes.|
|Opera<br /><br /> Safari|{1&gt;Sem suporte.&lt;1}|
|Silverlight|{1&gt;Sem suporte.&lt;1}<br /><br /> No entanto, para o Visual Studio 2013, é possível baixar o [Plug-in do Teste de IU Codificado do Microsoft Visual Studio 2013 para Silverlight](https://marketplace.visualstudio.com/items?itemName=PrachiBoraMSFT.MicrosoftVisualStudio2013CodedUITestPluginforSilve) na Galeria do Visual Studio.|
|Flash/Java|{1&gt;Sem suporte.&lt;1}|
|Windows Forms 2.0 e posterior|Suporte total. **Observação:** os controles NetFx têm suporte completo, mas nem todos os controles de terceiros têm suporte.|
|WPF 3.5 e posterior|Suporte total.<br /><br /> **Observação** Os controles NetFx têm suporte completo, mas nem todos os controles de terceiros têm suporte.|
|Windows Win32|Pode funcionar com alguns problemas conhecidos, mas sem suporte oficial.|
|MFC|Suporte parcial. Consulte o [site da Microsoft](https://blogs.msdn.com/b/vstsqualitytools/archive/2010/04/15/uitest-framework-mfc-support-in-vs-2010.aspx) a seguir para obter detalhes dos recursos com suporte.|
|SharePoint|Suporte total.|
|Aplicativos clientes do Office|{1&gt;Sem suporte.&lt;1}|
|Cliente Web do Dynamics CRM|Suporte total.|
|Cliente do Dynamics (Ax) 2012|A gravação e reprodução de ações têm suporte parcial. Consulte o [site da Microsoft](https://blogs.msdn.com/b/dave_froslie/archive/2011/09/01/visual-studio-10-coded-ui-action-recordings-support-for-microsoft-dynamics-ax-2012.aspx) a seguir para obter detalhes.|
|SAP|{1&gt;Sem suporte.&lt;1}|
|Citrix/Serviços de Terminal|Não recomendamos o uso de ações de gravação em um servidor Host da Sessão da Área de Trabalho Remota. O gravador não dá suporte a várias instâncias ao mesmo tempo.|
|PowerBuilder|Suporte parcial.<br /><br /> O suporte é habilitado na acessibilidade de extensões para controles PowerBuilder.|

 Para obter informações sobre como criar extensões para dar suporte a outras plataformas, consulte [Habilitar testes de IU codificados dos controles](../test/enable-coded-ui-testing-of-your-controls.md) e [Estendendo testes de IU codificados e gravações de ação para dar suporte ao Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md).

## <a name="see-also"></a>Veja também
 [Use a automação da interface do usuário para testar seu código](../test/use-ui-automation-to-test-your-code.md) [gerando um teste de IU codificado de uma gravação de ação existente](https://msdn.microsoft.com/library/56736963-9027-493b-b5c4-2d4e86d1d497)
