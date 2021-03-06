---
title: 'Como: incluir pré-requisitos com um aplicativo ClickOnce | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94ed90b9fcdd0c4ffe35789d00de4bbbd4aaa355
ms.sourcegitcommit: bf2e9d4ff38bf5b62b8af3da1e6a183beb899809
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2020
ms.locfileid: "77557637"
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Como incluir pré-requisitos com um aplicativo ClickOnce
Antes que possa distribuir o software necessário com um aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], primeiro você deverá baixar os pacotes de instalador desses pré-requisitos em seu computador de desenvolvimento. Quando você publicar um aplicativo e escolher **Baixar pré-requisitos da mesma localização que meu aplicativo baixa**, ocorrerá um erro se os pacotes de instalador não estiverem na pasta **Pacotes**.

> [!NOTE]
> Para adicionar um pacote do instalador para o .NET Framework, consulte [.NET Framework guia de implantação para desenvolvedores](/dotnet/framework/deployment/deployment-guide-for-developers).

## <a name="Package"></a> Para adicionar um pacote de instalador ao usar Package.xml

1. No Explorador de Arquivos, abra a pasta **Pacotes**.

    Por padrão, o caminho é `%ProgramFiles(x86)%\Microsoft SDKs\ClickOnce Bootstrapper\Packages\`.

2. Abra a pasta do pré-requisito que você deseja adicionar e, em seguida, abra a pasta do idioma da versão instalada de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (por exemplo, **en** para inglês).

3. No Bloco de Notas, abra o arquivo *Package.xml*.

4. Localize o elemento **Name** que contém `http://go.microsoft.com/fwlink`e copie a URL. Inclua a parte **LinkID**.

   > [!NOTE]
   > Se nenhum elemento **Name** contiver `http://go.microsoft.com/fwlink`, abra o arquivo **Product. xml** na pasta raiz para obter o pré-requisito e localize a cadeia de caracteres **fwlink** .

   > [!IMPORTANT]
   > Alguns pré-requisitos têm vários pacotes de instalador (por exemplo, para sistemas de 32 bits ou 64 bits). Se vários elementos **Name** contiverem **fwlink**, você deverá repetir as etapas restantes para cada um deles.

5. Cole a URL na barra de endereços de seu navegador e, quando a execução ou gravação for solicitada, escolha **Salvar**.

    Essa etapa baixará o arquivo do instalador em seu computador.

6. Copie o arquivo na pasta raiz do pré-requisito.

    Por exemplo, para o pré-requisito Windows Installer 4.5, copie o arquivo na pasta *\Packages\WindowsInstaller4_5*.

    Agora você poderá distribuir o pacote de instalador com seu aplicativo.

## <a name="see-also"></a>Consulte também
- [Como instalar pré-requisitos com um aplicativo ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
