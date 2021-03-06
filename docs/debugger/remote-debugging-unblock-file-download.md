---
title: Desbloquear o download de ferramentas remotas
ms.date: 07/19/2018
ms.topic: troubleshooting
helpviewer_keywords:
- remote debugging, unblock download
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a243033bf5831952d83fdf688302651e02b76b7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62903012"
---
# <a name="how-to-unblock-the-download-of-the-remote-tools-on-windows-server"></a>Como: Desbloquear o download das ferramentas remotas no Windows Server

As configurações de segurança padrão no Internet Explorer no Windows Server podem tornar demorado baixar os componentes, como as ferramentas remotas.

* Configuração de segurança aprimorada está habilitada no Internet Explorer, que impede você de abertura de sites e acessar recursos da web, a menos que o domínio que contém o recurso seja explicitamente permitido (ou seja, confiável). Você pode desativar essa configuração, não recomendamos-lo porque ele pode representar um risco de segurança.

* No Windows Server 2016, uma configuração padrão **opções da Internet** > **segurança** > **Internet**  >   **Nível personalizado** > **Downloads** também desabilita downloads de arquivos. Se você optar por baixar as ferramentas remotas diretamente no Windows Server, você deve habilitar o download do arquivo.

Para baixar as ferramentas no Windows Server, recomendamos um dos seguintes:

* Baixe as ferramentas remotas em um computador diferente, como a um Visual Studio em execução e, em seguida, copie o *.exe* arquivo para o Windows Server.

* Executar o depurador remoto [de um compartilhamento de arquivo](../debugger/remote-debugging.md#fileshare_msvsmon) em seu computador do Visual Studio.

* Baixe as ferramentas remotas diretamente no Windows Server e aceite os prompts para adicionar sites confiáveis. Sites modernos geralmente incluem diversos recursos de terceiros, portanto, isso pode resultar em muitos prompts. Além disso, todos os links redirecionados talvez precise ser adicionadas manualmente. Você pode optar por adicionar alguns dos sites confiáveis antes de iniciar o download. Vá para **opções da Internet > Segurança > Sites confiáveis > Sites** e adicione os seguintes sites.

  * visualstudio.microsoft.com
  * download.visualstudio.microsoft.com
  * sobre: em branco

  Para versões mais antigas do depurador em my.visualstudio.com, adicione esses sites adicionais para certificar-se de que o logon for bem-sucedido:

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * my.visualstudio.com
  * login.microsoftonline.com
  * login.live.com
  * secure.aadcdn.microsoftonline-p.com
  * msft.sts.microsoft.com
  * auth.gfx.ms
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.prod.cms.rt.microsoft.com

    Se você optar por adicionar esses domínios ao baixar as ferramentas remotas, escolha **adicionar** quando solicitado.

    ![Caixa de diálogo de conteúdo bloqueado](../debugger/media/remotedbg-blocked-content.png)

    Ao baixar o software, você obterá algumas solicitações adicionais para conceder permissão para carregar vários scripts do site da web e recursos. Em my.visualstudio.com, recomendamos que você adicione os domínios adicionais para certificar-se de que o logon for bem-sucedido.