---
title: Guia do administrador do Visual Studio
titleSuffix: ''
description: Saiba mais sobre como implantar o Visual Studio em um ambiente corporativo.
ms.date: 03/09/2020
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: bda9a73a7a1aabb2d288653ff4d7b20b1c40db8c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79190281"
---
# <a name="visual-studio-administrator-guide"></a>Guia do administrador do Visual Studio

Em ambientes corporativos, é comum que administradores de sistema implantem instalações para os usuários finais de um compartilhamento de rede ou usando software de gerenciamento de sistemas. Projetamos o mecanismo de instalação do Visual Studio para dar suporte à implantação corporativa, dando aos administradores de sistema a capacidade de criar um local de instalação de rede, pré-configurar padrões de instalação, implantar chaves de produto durante o processo de instalação e gerenciar atualizações de produto depois de uma implementação com êxito.

Este guia do administrador fornece orientações com base em cenários para implantações corporativas em ambientes de rede.

## <a name="before-you-begin"></a>Antes de começar

Antes de implantar o Visual Studio em sua organização, há algumas decisões a serem tomadas e tarefas a concluir:

::: moniker range="vs-2019"

* Verifique se cada computador de destino atende aos [requisitos mínimos de instalação](/visualstudio/releases/2019/system-requirements/).

* Decida sobre suas necessidades de manutenção.

  Se sua empresa precisa ficar em um conjunto de recursos por mais tempo, mas ainda deseja atualizações de manutenção regulares, você deve planejar usar uma linha de base de manutenção. Para obter mais informações, consulte as ***opções de suporte para clientes Corporativos e Profissionais*** da página de vida e manutenção do [produto Visual Studio,](/visualstudio/releases/2019/servicing#support-options-for-enterprise-and-professional-customers) bem como o [How to: Update Visual Studio durante uma](update-servicing-baseline.md) página de base de manutenção.

  Se planeja aplicar atualizações de manutenção juntamente com atualizações de recursos cumulativas, você pode escolher as partes mais recentes.

* Escolha o modelo de atualização.

  Onde você deseja que computadores cliente individuais obtenham atualizações? Especificamente, decida se deseja obter atualizações da Internet ou de um compartilhamento de local de toda a empresa. Em seguida, se você escolheu usar um compartilhamento local, decida se os usuários individuais podem atualizar seus próprios clientes ou se você deseja que um administrador atualize os clientes por meio de programação.

* Decida quais [cargas de trabalho e componentes](workload-and-component-ids.md?view=vs-2019) sua empresa necessita.

* Decida se usará um [arquivo de resposta](automated-installation-with-response-file.md?view=vs-2019) (que simplifica o gerenciamento detalhes no arquivo de script).

* Decida se você deseja habilitar a Política de Grupo e se deseja configurar o Visual Studio para desabilitar os comentários do cliente em computadores individuais.

::: moniker-end

::: moniker range="vs-2017"

* Verifique se cada computador de destino atende aos [requisitos mínimos de instalação](/visualstudio/productinfo/vs2017-system-requirements-vs/).

* Decida sobre suas necessidades de manutenção.

  Se sua empresa precisa ficar em um conjunto de recursos por mais tempo, mas ainda deseja atualizações de manutenção regulares, você deve planejar usar uma linha de base de manutenção. Para obter mais informações, consulte o ***suporte para versões mais antigas da*** seção Visual Studio do ciclo de vida e manutenção do produto Visual [Studio,](/visualstudio/releases/2019/servicing#support-for-older-versions-of-visual-studio) bem como o [How to: Update Visual Studio durante uma](update-servicing-baseline.md) página de base de manutenção.

  Se planeja aplicar atualizações de manutenção juntamente com atualizações de recursos cumulativas, você pode escolher as partes mais recentes.

* Escolha o modelo de atualização.

  Onde você deseja que computadores cliente individuais obtenham atualizações? Especificamente, decida se deseja obter atualizações da Internet ou de um compartilhamento de local de toda a empresa. Em seguida, se você escolheu usar um compartilhamento local, decida se os usuários individuais podem atualizar seus próprios clientes ou se você deseja que um administrador atualize os clientes por meio de programação.

* Decida quais [cargas de trabalho e componentes](workload-and-component-ids.md?view=vs-2017) sua empresa necessita.

* Decida se usará um [arquivo de resposta](automated-installation-with-response-file.md?view=vs-2017) (que simplifica o gerenciamento detalhes no arquivo de script).

* Decida se você deseja habilitar a Política de Grupo e se deseja configurar o Visual Studio para desabilitar os comentários do cliente em computadores individuais.

::: moniker-end

::: moniker range="vs-2019"

## <a name="step-1---download-visual-studio-product-files"></a>Etapa 1 – baixar os arquivos de produto do Visual Studio

* [Selecione as cargas de trabalho e os componentes](workload-and-component-ids.md?view=vs-2019) que deseja instalar.

* [Crie um compartilhamento de rede para os arquivos de produto do Visual Studio](create-a-network-installation-of-visual-studio.md?view=vs-2019).

## <a name="step-2---build-an-installation-script"></a>Etapa 2 – criar um script de instalação

* Compile um script de instalação que use [parâmetros de linha de comando](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) para controlar a instalação.

  >[!NOTE]
  > Você pode simplificar scripts usando um [arquivo de resposta](automated-installation-with-response-file.md?view=vs-2019). É preciso que você crie um arquivo de resposta que contenha sua opção de instalação padrão.

* (Opcional) [Aplique uma chave do produto de licença de volume](automatically-apply-product-keys-when-deploying-visual-studio.md?view=vs-2019) como parte do script de instalação para que os usuários não precisem ativar o software separadamente.

* (Opcional) Atualize o layout de rede para [controlar o período e o local de origem em que as atualizações de produto serão entregues aos usuários finais](controlling-updates-to-visual-studio-deployments.md?view=vs-2019).

* (Opcional) Defina políticas de registro que afetam a implantação do Visual Studio, como onde alguns pacotes compartilhados com outras versões ou instâncias são instalados, [onde os pacotes são armazenados em cache](set-defaults-for-enterprise-deployments.md?view=vs-2019) ou [se os pacotes são armazenados em cache](disable-or-move-the-package-cache.md?view=vs-2019).

* (Opcional) Defina a Política de Grupo. Você também pode [configurar o Visual Studio para desabilitar os comentários do cliente](../ide/visual-studio-experience-improvement-program.md) em computadores individuais.

## <a name="step-3---deploy"></a>Etapa 3 – implantar

* Use a tecnologia de implantação de sua escolha para executar o script nas estações de trabalho do desenvolvedor de destino.

## <a name="step-4---deploy-updates"></a>Etapa 4 – implantar atualizações

* [Atualize seu local de rede com as atualizações mais recentes](update-a-network-installation-of-visual-studio.md?view=vs-2019) do Visual Studio ao executar o comando usado na etapa 1 regularmente para adicionar componentes atualizados.

  Você pode atualizar o Visual Studio usando um script de atualização. Para isso, use [`update`](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) o parâmetro de linha de comando.

## <a name="step-5---optional-use-visual-studio-tools"></a>Etapa 5 – (opcional) usar ferramentas do Visual Studio

Temos várias ferramentas disponíveis para ajudar você a [detectar e gerenciar instâncias do Visual Studio instaladas](tools-for-managing-visual-studio-instances.md?view=vs-2019) em computadores cliente.

## <a name="advanced-configuration"></a>Configuração avançada

Por padrão, a instalação do Visual Studio permite a inclusão de tipos personalizados em pesquisas de Bing a partir da lista de erros F1 e links de código. Você pode configurar o Visual Studio para desativar o mecanismo de pesquisa de incluir quaisquer tipos de usuário personalizados alterando o valor da seguinte chave de registro por política:

**"PutCustomtypeINBingSearch" DWORD 0**

O registro está localizado no *Software\Microsoft\VisualStudio\16.0_{InstanceId}\Roslyn\Internal\Diagnostics\* diretório de sua colmeia de registro privado. Para obter instruções sobre como abrir a colmeia de registro, consulte [a edição do registro de uma instância do Visual Studio](tools-for-managing-visual-studio-instances.md?view=vs-2019#editing-the-registry-for-a-visual-studio-instance).

::: moniker-end

::: moniker range="vs-2017"

## <a name="step-1---download-visual-studio-product-files"></a>Etapa 1 – baixar os arquivos de produto do Visual Studio

* [Selecione as cargas de trabalho e os componentes](workload-and-component-ids.md?view=vs-2017) que deseja instalar.

* [Crie um compartilhamento de rede para os arquivos de produto do Visual Studio](create-a-network-installation-of-visual-studio.md?view=vs-2017).

## <a name="step-2---build-an-installation-script"></a>Etapa 2 – criar um script de instalação

* Compile um script de instalação que use [parâmetros de linha de comando](use-command-line-parameters-to-install-visual-studio.md?view=vs-2017) para controlar a instalação.

  >[!NOTE]
  > Você pode simplificar scripts usando um [arquivo de resposta](automated-installation-with-response-file.md?view=vs-2017). É preciso que você crie um arquivo de resposta que contenha sua opção de instalação padrão.

* (Opcional) [Aplique uma chave do produto de licença de volume](automatically-apply-product-keys-when-deploying-visual-studio.md?view=vs-2017) como parte do script de instalação para que os usuários não precisem ativar o software separadamente.

* (Opcional) Atualize o layout de rede para [controlar o período e o local de origem em que as atualizações de produto serão entregues aos usuários finais](controlling-updates-to-visual-studio-deployments.md?view=vs-2017).

* (Opcional) Defina políticas de registro que afetam a implantação do Visual Studio, como onde alguns pacotes compartilhados com outras versões ou instâncias são instalados, [onde os pacotes são armazenados em cache](set-defaults-for-enterprise-deployments.md?view=vs-2019) ou [se os pacotes são armazenados em cache](disable-or-move-the-package-cache.md?view=vs-2017).

* (Opcional) Defina a Política de Grupo. Você também pode [configurar o Visual Studio para desabilitar os comentários do cliente](../ide/visual-studio-experience-improvement-program.md) em computadores individuais.

## <a name="step-3---deploy"></a>Etapa 3 – implantar

* Use a tecnologia de implantação de sua escolha para executar o script nas estações de trabalho do desenvolvedor de destino.

## <a name="step-4---deploy-updates"></a>Etapa 4 – implantar atualizações

* [Atualize seu local de rede com as atualizações mais recentes](update-a-network-installation-of-visual-studio.md?view=vs-2017) do Visual Studio ao executar o comando usado na etapa 1 regularmente para adicionar componentes atualizados.

  Você pode atualizar o Visual Studio usando um script de atualização. Para isso, use [`update`](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) o parâmetro de linha de comando.

## <a name="step-5---optional-use-visual-studio-tools"></a>Etapa 5 – (opcional) usar ferramentas do Visual Studio

Temos várias ferramentas disponíveis para ajudar você a [detectar e gerenciar instâncias do Visual Studio instaladas](tools-for-managing-visual-studio-instances.md?view=vs-2017) em computadores cliente.

## <a name="advanced-configuration"></a>Configuração avançada

Por padrão, a instalação do Visual Studio permite a inclusão de tipos personalizados em pesquisas de Bing a partir da lista de erros F1 e links de código. Você pode configurar o Visual Studio para desativar o mecanismo de pesquisa de incluir quaisquer tipos de usuário personalizados alterando o valor da seguinte chave de registro por política:

**"PutCustomtypeINBingSearch" DWORD 0**

O registro está localizado no *Software\Microsoft\VisualStudio\15.0_{InstanceId}\Roslyn\Internal\Diagnostics\* diretório de sua colmeia de registro privado. Para obter instruções sobre como abrir a colmeia de registro, consulte [a edição do registro de uma instância do Visual Studio](tools-for-managing-visual-studio-instances.md?view=vs-2017#editing-the-registry-for-a-visual-studio-instance).

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Confira também

* [Exemplos de parâmetro de linha de comando](command-line-parameter-examples.md)
* [Instalar os certificados necessários para instalação offline do Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Importar ou exportar configurações de instalação](import-export-installation-configurations.md)
* [Arquivos de instalação do Visual Studio](https://devblogs.microsoft.com/setup/tag/vs2017/)
* [Ciclo de vida e manutenção do produto Visual Studio](/visualstudio/releases/2019/servicing/)
* [Configurações de carregamento automático síncrono](../extensibility/synchronously-autoloaded-extensions.md)
