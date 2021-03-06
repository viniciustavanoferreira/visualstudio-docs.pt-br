---
title: Limitações na depuração do WCF | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging limitations
ms.assetid: 8e0333c4-1ddc-4abe-8f1c-d19bf6a2a07a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c70195cdc0a6a03395744c63f556ce8c2970aa30
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72731502"
---
# <a name="limitations-on-wcf-debugging"></a>Limitações da depuração WCF
Há três modos de começar a depuração de um serviço WCF:

- Você está depurando um processo de cliente que chama um serviço. O depurador entra no serviço. O serviço não tem que estar na mesma solução que o aplicativo cliente.

- Você está depurando um processo de cliente que faz a solicitação para um serviço. O serviço deve fazer parte de sua solução.

- Você usa **Anexar ao Processo** para anexar a um serviço que está em execução no momento. A depuração começa dentro do serviço.

  Este tópico descreve limitações nesses cenários.

## <a name="limitations-on-stepping-into-a-service"></a>Limitações para entrar em um serviço
 Para entrar em um serviço de aplicativos cliente que você está depurando, as seguintes condições devem ser atendidas:

- O cliente deve chamar o serviço usando um objeto do cliente síncrono.

- A operação do contrato não pode ser unidirecional.

- Se o servidor for assíncrono, você não poderá exibir a pilha de chamadas completa enquanto estiver executando o código no serviço.

- A depuração deve estar habilitada com o seguinte código no arquivo app.config ou no Web.config:

    ```xml
    <system.web>
      <compilation debug="true" />
    </system.web>
    ```

     Esse código só precisa ser adicionado uma vez. Você pode adicionar esse código editando o arquivo .config ou anexando ao serviço usando **Anexar ao Processo**. Quando você usa **Anexar ao Processo** em um serviço, o código de depuração é adicionado automaticamente ao arquivo .config. Depois disso, você pode depurar e entrar no serviço sem precisar editar o arquivo .config.

## <a name="limitations-on-stepping-out-of-a-service"></a>Limitações para sair de um serviço
 Sair de um serviço e voltar para o cliente tem as mesmas restrições descritas para entrar em um serviço. Além disso, o depurador deve ser anexado ao cliente. Se você estiver depurando um cliente e entrando em um serviço, o depurador permanecerá anexado ao serviço. Isso será verdadeiro se você tiver iniciado o cliente usando **Iniciar Depuração** ou anexado ao cliente usando **Anexar ao Processo**. Se você tiver começado a depurar anexando ao serviço, o depurador ainda não estará anexado ao cliente. Nesse caso, se você tiver que sair do serviço e voltar ao cliente, primeiro deverá usar **Anexar ao Processo** para anexar manualmente ao cliente.

## <a name="limitations-on-automatic-attach-to-a-service"></a>Limitações de anexar automaticamente a um serviço
 Anexar automaticamente a um serviço tem as seguintes limitações:

- O serviço deve fazer parte da solução do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] que você está depurando.

- O serviço deve ser hospedado. Ele pode fazer parte de um projeto do site (Sistema de Arquivos e HTTP), projeto de aplicativo Web (Sistema de Arquivos e HTTP) ou projeto da biblioteca de serviço WCF. Os projetos da biblioteca de serviço WCF podem ser bibliotecas de serviço ou bibliotecas de serviço de fluxo de trabalho.

- O serviço deve ser chamado de um cliente WCF.

- A depuração deve estar habilitada com o seguinte código no arquivo app.config ou no Web.config:

  ```xml
  <system.web>
    <compilation debug="true" />
  <system.web>
  ```

## <a name="self-hosting"></a>Auto-hospedagem
 Um *serviço auto-hospedado* é um serviço WCF que não é executado dentro do IIS, do Host de Serviço WCF ou do [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server. Para obter informações sobre como depurar um serviço hospedado automaticamente, consulte [como depurar um serviço WCF auto-hospedado](../debugger/how-to-debug-a-self-hosted-wcf-service.md).

## <a name="self-hosting"></a>Auto-hospedagem
 Para habilitar a depuração de aplicativos do [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 ou 3.5, o [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 ou 3.5 deve ser instalado antes que o [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] seja instalado. Se o [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] for instalado antes do [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 ou 3.5, um erro ocorrerá quando você tentar depurar um aplicativo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 ou 3.5. A mensagem de erro é "Não é possível entrar automaticamente no servidor". Para corrigir esse problema, use o **painel de controle** do Windows  > **programas e recursos** para reparar a instalação do [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].

## <a name="see-also"></a>Consulte também
- [Depurando serviços WCF](../debugger/debugging-wcf-services.md)
- [Como depurar um serviço WCF auto-hospedado](../debugger/how-to-debug-a-self-hosted-wcf-service.md)
