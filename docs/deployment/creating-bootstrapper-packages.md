---
title: Criar pacotes de bootstrapper
ms.date: 05/02/2018
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], prerequisites
- deploying applications [Visual Studio], custom prerequisites
- prerequisites, custom
- RedistList file
- custom prerequisites
- redistributables list
ms.assetid: ba1a785b-693d-446b-bcae-b88cadee73d1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f84f91ebedd47df8c0804adee35dcbec18d8551
ms.sourcegitcommit: 95f26af1da51d4c83ae78adcb7372b32364d8a2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "79301989"
---
# <a name="create-bootstrapper-packages"></a>Criar pacotes de bootstrapper
O programa de instalação é um instalador genérico que pode ser configurado para detectar e instalar componentes redistribuíveis como arquivos do Windows Installer (*.msi*) e programas executáveis. O instalador também é conhecido como bootstrapper. Ele é programado por um conjunto de manifestos XML que especificam os metadados para gerenciar a instalação do componente.  Cada componente avermelhado, ou pré-requisito, que aparece na caixa de diálogo **Pré-requisitos** para ClickOnce é um pacote bootstrapper. Um pacote de bootstrapper é um grupo de diretórios e arquivos que contém arquivos de manifesto que descrevem como o pré-requisito deve ser instalado.

O bootstrapper primeiro detecta se qualquer um dos pré-requisitos já está instalado. Se os pré-requisitos não estiverem instalados, primeiro o bootstrapper mostra os contratos de licença. Em segundo lugar, depois que o usuário final aceita os contratos de licença, a instalação dos pré-requisitos começa. Caso contrário, se forem detectados todos os pré-requisitos, o bootstrapper apenas inicia o instalador do aplicativo.

## <a name="create-custom-bootstrapper-packages"></a>Crie pacotes personalizados de bootstrapper
Você pode gerar os manifestos bootstrapper usando o Editor XML no Visual Studio. Para ver um exemplo de criação de um pacote bootstrapper, consulte [Passo a Passo: Crie um bootstrapper personalizado com um prompt de privacidade](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md).

Para criar um pacote bootstrapper, você tem que criar um manifesto de produto e, para cada versão localizada de um componente, um manifesto de pacote também.

* O manifesto do produto, *product.xml,* contém quaisquer metadados neutros em linguagem para a embalagem. Esse manifesto contém metadados comuns a todas as versões localizadas do componente redistribuível.  Para criar este arquivo, [consulte Como: Criar um Manifesto de Produto](../deployment/how-to-create-a-product-manifest.md).

* O manifesto do pacote, *package.xml,* contém metadados específicos do idioma; ele normalmente contém mensagens de erro localizadas. Um componente deve ter, pelo menos, um pacote de manifesto para cada versão localizada desse componente. Para criar este arquivo, [consulte Como: Criar um Manifesto de Pacote](../deployment/how-to-create-a-package-manifest.md).

Depois que esses arquivos são criados, coloque o arquivo de manifesto do produto em uma pasta indicada para o bootstrapper personalizado. O arquivo de manifesto do pacote vai para uma pasta nomeada de acordo com a localidade. Por exemplo, se o arquivo de manifesto do pacote for para redistribuição em inglês, coloque o arquivo em uma pasta chamada en. Repita esse processo para cada localidade, como ja para japonês e de para alemão. O pacote final de bootstrapper personalizado pode ter estrutura de pastas a seguir.

```
CustomBootstrapperPackage
  product.xml
  CustomBootstrapper.msi
  de
    eula.rtf
    package.xml
  en
    eula.rtf
    package.xml
  ja
    eula.rtf
    package.xml
```

Em seguida, copie os arquivos redistributíveis no local da pasta bootstrapper. Para obter mais informações, consulte [Como: Criar um pacote de bootstrapper localizado](../deployment/how-to-create-a-localized-bootstrapper-package.md).

```
*\Program Files (x86)\Microsoft SDKs\ClickOnce Bootstrapper*
```

ou, para versões mais antigas do Visual Studio

```
*\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
```

ou

```
*\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
```

Você também pode encontrar o local da pasta bootstrapper a partir do valor **Path** na seguinte chave de registro:

```
*HKLM\Software\Microsoft\GenericBootstrapper*
```

Em sistemas de 64 bits, use a seguinte chave do Registro:

```
*HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper*
```

Cada componente redistribuível aparece em sua própria subpasta no diretório de pacotes. O manifesto do produto e os arquivos avermelhados devem ser colocados nesta subpasta. As versões localizadas dos manifestos de componentes e pacotes devem ser colocadas em subpastas nomeadas de acordo com o Nome da Cultura.

Após esses arquivos serem copiados na pasta do bootstrapper, o pacote de bootstrapper aparece automaticamente na caixa de diálogo de **Pré-requisitos** do Visual Studio. Se o pacote personalizado de bootstrapper não aparecer, feche e reabra a caixa de diálogo **Pré-requisitos**. Para obter mais informações, consulte [caixa de diálogo Pré-requisitos](../ide/reference/prerequisites-dialog-box.md).

A tabela a seguir mostra as propriedades que são preenchidas automaticamente pelo bootstrapper.

|Propriedade|Descrição|
|--------------|-----------------|
|ApplicationName|O nome do aplicativo.|
|ProcessorArchitecture|O processador e bits por palavra da plataforma de destino de um executável. Os valores incluem o seguinte:<br /><br /> – Intel<br />– IA64<br />– AMD64|
|[Versão9x](/windows/desktop/Msi/version9x)|O número de versão para os sistemas operacionais Microsoft Windows 95, Windows 98 ou Windows ME. A sintaxe da versão é Major.Minor.ServicePack.|
|[VersionNT](/windows/desktop/Msi/versionnt)|O número de versão para os sistemas operacionais Windows NT, Windows 2000, Windows XP, Windows Vista, Windows Server 2008 ou Windows 7. A sintaxe da versão é Major.Minor.ServicePack.|
|[VersionMSI](/windows/desktop/Msi/versionmsi)|A versão do conjunto do Instalador do Windows (msi.dll) para ser executada durante a instalação.|
|[Adminuser](/windows/desktop/Msi/adminuser)|Essa propriedade será definida se o usuário tiver privilégios de administrador. Os valores são verdadeiro ou falso.|
|InstallMode|O modo de instalação indica de onde o componente precisa ser instalado. Os valores incluem o seguinte:<br /><br /> – HomeSite – os pré-requisitos são instalados do site do fornecedor.<br />– SpecificSite – os pré-requisitos são instalados da localização selecionada.<br />– SameSite – os pré-requisitos são instalados da mesma localização que o aplicativo.|

## <a name="separate-redistributables-from-application-installations"></a>Retribuíveis separados das instalações de aplicativos
Você pode evitar que seus arquivos redistribuíveis sejam implantados em projetos de instalação. Para fazer isso, crie uma lista redistribuível na pasta RedistList em seu diretório NET Framework:

`%ProgramFiles%\Microsoft.NET\RedistList`

A lista redistributable é um arquivo XML que você deve nomear usando o seguinte formato: * \<Nome da empresa\<>. Nome do componente>. RedistList.xml*. Assim, por exemplo, se o componente for chamado de DataWidgets feito por Acme, use *Acme.DataWidgets.RedistList.xml*. Um exemplo de conteúdo da lista redistribuível pode ser semelhante a:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<FileList Redist="Acme.DataWidgets" >
<File AssemblyName="Acme.DataGrid" Version="1.0.0.0" PublicKeyToken="b03f5f7f11d50a3a" Culture="neutral" ProcessorArchitecture="MSIL" InGAC="true" />
</FileList>
```

## <a name="see-also"></a>Confira também
- [Como: Instalar pré-requisitos com um aplicativo ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
- [Caixa de diálogo pré-requisitos](../ide/reference/prerequisites-dialog-box.md)
- [Referência de esquema de produto e pacote](../deployment/product-and-package-schema-reference.md)
- [Use o Bootstrapper do Visual Studio 2005 para iniciar sua instalação](https://msdn.microsoft.com/magazine/cc163899.aspx)
