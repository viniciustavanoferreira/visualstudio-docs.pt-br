---
title: Localizando o Visual Studio | Microsoft Docs
ms.date: 08/21/2017
ms.topic: conceptual
helpviewer_keywords:
- deployment, VSIX
ms.assetid: 680c3b25-7901-4768-8363-6d1fcd1ea636
ms.author: heaths
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a7187fbcc3e3aca990846176676a47f5d17aaf00
ms.sourcegitcommit: 62f42113ae4dae1ddfff1c4e02445acc09913445
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64878151"
---
# <a name="locate-visual-studio"></a>Localize o Visual Studio

Começando com o Visual Studio 2017, você pode instalar várias instâncias da mesma versão ou até mesmo edition. Isso é útil quando você deseja visualizar a nova funcionalidade no seu computador de desenvolvimento primário, mantendo sua instalação anterior. Por causa dessas alterações, não há nenhum valor de variável ou registro único ambiente que pode usar para localizar uma instância. Em vez disso, você pode usar um [API de consulta COM](https://msdn.microsoft.com/library/microsoft.visualstudio.setup.configuration.aspx) para localizar instâncias com base em critérios relevantes para sua extensão.

Esta é uma API rápida, somente leitura com pacotes do NuGet para código nativo e gerenciado.

| Código | Pacote |
| ---- | --- |
| Nativo | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Native |
| Gerenciado | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Interop |

Você pode localizar uma única instância, dada um caminho ou o processo atual ou enumerar todas as instâncias. Ver [nossos exemplos](https://github.com/Microsoft/vs-setup-samples) para obter exemplos completos de como localizar o Visual Studio.

## <a name="tools"></a>Ferramentas

Para localizar o Visual Studio e outras ferramentas em ambientes de compilação, scripts do PowerShell, instaladores e mais cenários, há uma série de ferramentas de código-fonte aberto, você pode usar diretamente ou redistribuir junto com seus próprios scripts.

| Projeto | Descrição |
| ------- | ----------- |
| [vswhere](https://github.com/Microsoft/vswhere) | Arquivo único executável nativo para localizar instâncias que atendem aos critérios como versão ou versão de pré-lançamento, o produto foi instalado e quais cargas de trabalho estão instaladas. Também dá suporte a localizar o Visual Studio 2010 e versões mais recentes, embora menos informações são retornadas que para o Visual Studio 2017 e mais recente. Consulte a [wiki](https://github.com/Microsoft/vswhere/wiki) para obter exemplos. |
| [Cmdlets do VSSetup](https://github.com/Microsoft/vssetup.powershell) | Suporte para cmdlets do PowerShell 2.0 e versões mais recentes que retornam informações ricas como objetos que você pode usar para localizar instâncias com base nos mesmos critérios de _vswhere_ e para descobrir as propriedades ainda mais sobre as instâncias. Consulte a [wiki](https://github.com/Microsoft/vssetup.powershell/wiki) para obter exemplos. |
| [VSIXBootstrapper](https://github.com/Microsoft/vsixbootstrapper) | Localiza automaticamente _VSIXInstaller_ e passa a linha de comando por meio de instalar um **VSIX* arquivo. Esse recurso pode ser útil em instaladores que não têm suporte direto para as APIs de consulta. Consulte a [wiki](https://github.com/Microsoft/vsixbootstrapper/wiki) para obter exemplos. |

## <a name="see-also"></a>Consulte também

* [Alterações na instalação do Visual Studio 2017](https://devblogs.microsoft.com/setup/changes-to-visual-studio-15-setup/)
* [Inicie o Visual Studio usando DTE](launch-visual-studio-dte.md)