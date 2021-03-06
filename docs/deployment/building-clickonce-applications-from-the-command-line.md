---
title: Criando aplicativos ClickOnce a partir da linha de comando | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 065eea058ffa78c84428e031832e24837eb81d08
ms.sourcegitcommit: af9bbf9116a63c0631ff2f4f3a878564aa63cd8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74797205"
---
# <a name="build-clickonce-applications-from-the-command-line"></a>Compilar aplicativos ClickOnce usando a linha de comando
No [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], você pode criar projetos a partir da linha de comando, mesmo que eles sejam criados no ambiente de desenvolvimento integrado (IDE). Na verdade, você pode recriar um projeto criado com [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] em outro computador que tenha apenas o .NET Framework instalado. Isso permite que você reproduza uma compilação usando um processo automatizado, por exemplo, em um laboratório de compilação central ou usando técnicas de script avançadas além do escopo da criação do projeto em si.

## <a name="use-msbuild-to-reproduce-clickonce-application-deployments"></a>Usar o MSBuild para reproduzir implantações de aplicativo ClickOnce
 Quando você invoca o MSBuild/target: publish na linha de comando, ele diz ao sistema MSBuild para compilar o projeto e criar um aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] na pasta de publicação. Isso é equivalente a selecionar o comando **Publish** no IDE.

 Esse comando executa o *MSBuild. exe*, que está no caminho no ambiente de prompt de comando do Visual Studio.

 Um "destino" é um indicador do MSBuild sobre como processar o comando. Os principais destinos são o destino "Build" e o destino "Publish". O destino da compilação é o equivalente a selecionar o comando de compilação (ou pressionar F5) no IDE. Se você quiser apenas compilar seu projeto, poderá conseguir isso digitando `msbuild`. Esse comando funciona porque o destino da compilação é o destino padrão para todos os projetos gerados pelo [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Isso significa que você não precisa especificar explicitamente o destino da compilação. Portanto, digitar `msbuild` é a mesma operação que a digitação `msbuild /target:build`.

 O comando `/target:publish` informa ao MSBuild para invocar o destino de publicação. O destino de publicação depende do destino da compilação. Isso significa que a operação de publicação é um superconjunto da operação de compilação. Por exemplo, se você fez uma alteração em um dos arquivos de origem C# ou Visual Basic, o assembly correspondente seria automaticamente recriado pela operação de publicação.

 Para obter informações sobre como gerar uma implantação de [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] completa usando a ferramenta de linha de comando Mage. exe para criar o manifesto [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], consulte [passo a passos: implantar manualmente um aplicativo ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).

## <a name="create-and-build-a-basic-clickonce-application-with-msbuild"></a>Criar e compilar um aplicativo ClickOnce básico com o MSBuild

#### <a name="to-create-and-publish-a-clickonce-project"></a>Para criar e publicar um projeto ClickOnce

1. Abra o Visual Studio e crie um projeto.

    Escolha o modelo de projeto de **aplicativo da área de trabalho do Windows** e nomeie o projeto `CmdLineDemo`.

1. No menu **Compilar** , clique no comando **publicar** .

    Essa etapa garante que o projeto esteja configurado corretamente para produzir uma implantação de aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].

    O Assistente de Publicação será exibido.

1. No assistente de publicação, clique em **concluir**.

    O Visual Studio gera e exibe a página da Web padrão, chamada *Publish. htm*.

1. Salve seu projeto e anote o local da pasta em que ele está armazenado.

   As etapas acima criam um projeto [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] que foi publicado pela primeira vez. Agora você pode reproduzir a compilação fora do IDE.

#### <a name="to-reproduce-the-build-from-the-command-line"></a>Para reproduzir a compilação a partir da linha de comando

1. Saia do [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].

2. No menu **Iniciar** do Windows, clique em **todos os programas**, **Microsoft Visual Studio**, em seguida, **Ferramentas do Visual Studio**, em seguida, prompt de **comando do Visual Studio**. Isso deve abrir um prompt de comando na pasta raiz do usuário atual.

3. No **prompt de comando do Visual Studio**, altere o diretório atual para o local do projeto que você acabou de criar acima. Por exemplo, digite `chdir My Documents\Visual Studio\Projects\CmdLineDemo`.

4. Para remover os arquivos existentes produzidos em "para criar e publicar um projeto [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]", digite `rmdir /s publish`.

    Essa etapa é opcional, mas garante que os novos arquivos foram todos produzidos pela compilação de linha de comando.

5. Digite `msbuild /target:publish`.

   As etapas acima produzirão uma implantação de aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] completa em uma subpasta do projeto chamada **Publish**. *CmdLineDemo. Application* é o manifesto de implantação [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. A pasta *CmdLineDemo_1.0.0.0* contém os arquivos *CmdLineDemo. exe* e *CmdLineDemo. exe. manifest*, o manifesto do aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. *Setup. exe* é o bootstrapper, que, por padrão, é configurado para instalar o .NET Framework. A pasta DotNetFX contém os pacotes redistribuíveis para o .NET Framework. Esse é o conjunto inteiro de arquivos de que você precisa para implantar seu aplicativo na Web ou via UNC ou CD/DVD.
   
> [!NOTE]
> O sistema MSBuild usa a opção **PublishDir** para especificar o local da saída, por exemplo `msbuild /t:publish /p:PublishDir="<specific location>"`.

## <a name="publish-properties"></a>Publicar propriedades
 Quando você publica o aplicativo nos procedimentos acima, as propriedades a seguir são inseridas em seu arquivo de projeto pelo assistente de publicação. Essas propriedades influenciam diretamente como o aplicativo de [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] é produzido.

 Em *CmdLineDemo.vbproj* / *CmdLineDemo.csproj*:

```xml
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>
<GenerateManifests>true</GenerateManifests>
<TargetZone>LocalIntranet</TargetZone>
<PublisherName>Microsoft</PublisherName>
<ProductName>CmdLineDemo</ProductName>
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>
<Install>true</Install>
<ApplicationVersion>1.0.0.*</ApplicationVersion>
<ApplicationRevision>1</ApplicationRevision>
<UpdateEnabled>true</UpdateEnabled>
<UpdateRequired>false</UpdateRequired>
<UpdateMode>Foreground</UpdateMode>
<UpdateInterval>7</UpdateInterval>
<UpdateIntervalUnits>Days</UpdateIntervalUnits>
<UpdateUrlEnabled>false</UpdateUrlEnabled>
<IsWebBootstrapper>true</IsWebBootstrapper>
<BootstrapperEnabled>true</BootstrapperEnabled>
```

 Você pode substituir qualquer uma dessas propriedades na linha de comando sem alterar o próprio arquivo do projeto. Por exemplo, o seguinte criará o [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] implantação de aplicativo sem o bootstrapper:

```cmd
msbuild /target:publish /property:BootstrapperEnabled=false
```

 As propriedades de publicação são controladas em [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] das páginas de propriedades de **publicação**, **segurança**e **assinatura** do **Designer de projeto**. Abaixo está uma descrição das propriedades de publicação, juntamente com uma indicação de como cada uma é definida nas várias páginas de propriedades do designer de aplicativo:

- `AssemblyOriginatorKeyFile` determina o arquivo de chave usado para assinar seus manifestos de aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Essa mesma chave também pode ser usada para atribuir um nome forte aos seus assemblies. Essa propriedade é definida na página de **assinatura** do **Designer de projeto**.

  As propriedades a seguir são definidas na página **segurança** :

- **Habilitar configurações de segurança do ClickOnce** determina se [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestos são gerados. Quando um projeto é criado inicialmente, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] geração de manifesto é desativada por padrão. O assistente ativará esse sinalizador automaticamente quando você publicar pela primeira vez.

- **TargetZone** determina o nível de confiança a ser emitido em seu manifesto do aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Os valores possíveis são "Internet", "LocalIntranet" e "Custom". Internet e LocalIntranet farão com que um conjunto de permissões padrão seja emitido em seu manifesto do aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. LocalIntranet é o padrão e basicamente significa confiança total. Personalizado especifica que apenas as permissões especificadas explicitamente no arquivo *. manifest do aplicativo* base devem ser emitidas no manifesto do aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. O arquivo *app. manifest* é um arquivo de manifesto parcial que contém apenas as definições de informações de confiança. É um arquivo oculto, adicionado automaticamente ao seu projeto quando você configura permissões na página **segurança** .

  As propriedades a seguir são definidas na página **publicar** :

- `PublishUrl` é o local onde o aplicativo será publicado no IDE. Ele será inserido no manifesto do aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] se nem a propriedade `InstallUrl` ou `UpdateUrl` for especificada.

- `ApplicationVersion` especifica a versão do aplicativo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Este é um número de versão de quatro dígitos. Se o último dígito for um "*", o `ApplicationRevision` será substituído pelo valor inserido no manifesto no momento da compilação.

- `ApplicationRevision` especifica a revisão. Esse é um inteiro que é incrementado cada vez que você publica no IDE. Observe que ele não é incrementado automaticamente para compilações executadas na linha de comando.

- `Install` determina se o aplicativo é um aplicativo instalado ou um aplicativo de execução da Web.

- `InstallUrl` (não mostrado) é o local do qual os usuários instalarão o aplicativo. Se especificado, esse valor será gravado no bootstrapper *Setup. exe* se a propriedade `IsWebBootstrapper` estiver habilitada. Ele também será inserido no manifesto do aplicativo se o `UpdateUrl` não for especificado.

- `SupportUrl` (não mostrado) é o local vinculado na caixa de diálogo **Adicionar/remover programas** para um aplicativo instalado.

  As propriedades a seguir são definidas na caixa de diálogo **atualizações do aplicativo** , acessadas na página **publicar** .

- `UpdateEnabled` indica se o aplicativo deve verificar se há atualizações.

- `UpdateMode` especifica atualizações em primeiro plano ou atualizações em segundo plano.

- `UpdateInterval` especifica com que frequência o aplicativo deve verificar se há atualizações.

- `UpdateIntervalUnits` especifica se o valor de `UpdateInterval` está em unidades de horas, dias ou semanas.

- `UpdateUrl` (não mostrado) é o local do qual o aplicativo receberá atualizações. Se especificado, esse valor será inserido no manifesto do aplicativo.

  As propriedades a seguir são definidas na caixa de diálogo **Opções de publicação** , acessadas na página **publicar** .

- `PublisherName` especifica o nome do publicador exibido no prompt mostrado ao instalar ou executar o aplicativo. No caso de um aplicativo instalado, ele também é usado para especificar o nome da pasta no menu **Iniciar** .

- `ProductName` especifica o nome do produto exibido no prompt mostrado ao instalar ou executar o aplicativo. No caso de um aplicativo instalado, ele também é usado para especificar o nome do atalho no menu **Iniciar** .

  As propriedades a seguir são definidas na caixa de diálogo **pré-requisitos** , acessada na página **publicar** .

- `BootstrapperEnabled` determina se o bootstrapper *Setup. exe* deve ser gerado.

- `IsWebBootstrapper` determina se o bootstrapper *Setup. exe* funciona na Web ou em modo baseado em disco.

## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallURL, SupportUrl, PublishURL e UpdateURL
 A tabela a seguir mostra as quatro opções de URL para implantação do ClickOnce.

|Opção de URL|Descrição|
|----------------|-----------------|
|`PublishURL`|Necessário se você estiver publicando seu aplicativo ClickOnce em um site da Web.|
|`InstallURL`|Opcional. Defina essa opção de URL se o site de instalação for diferente do `PublishURL`. Por exemplo, você pode definir o `PublishURL` como um caminho de FTP e definir o `InstallURL` como uma URL da Web.|
|`SupportURL`|Opcional. Defina essa opção de URL se o site de suporte for diferente do `PublishURL`. Por exemplo, você pode definir o `SupportURL` para o site de suporte ao cliente da sua empresa.|
|`UpdateURL`|Opcional. Defina essa opção de URL se o local de atualização for diferente do `InstallURL`. Por exemplo, você pode definir o `PublishURL` como um caminho de FTP e definir o `UpdateURL` como uma URL da Web.|

## <a name="see-also"></a>Consulte também
- <xref:Microsoft.Build.Tasks.GenerateBootstrapper>
- <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>
- <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>
- [Segurança e implantação do ClickOnce](../deployment/clickonce-security-and-deployment.md)
- [Passo a passo: implantar um aplicativo ClickOnce manualmente](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)
