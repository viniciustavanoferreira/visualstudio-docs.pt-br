---
title: Baixar o assembly satélite sob demanda usando o designer do ClickOnce
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows Forms, globalization
- ClickOnce deployment, globalization
- localization, Windows Forms
- ClickOnce, on-demand download
- Windows Forms, localization
- ClickOnce deployment, localization
- walkthroughs, localization
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f510ef4ad81188997e1d572e7aa3b52b65883269
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2019
ms.locfileid: "66263413"
---
# <a name="walkthrough-download-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>Passo a passo: Baixar os assemblies satélite por demanda com a implantação do ClickOnce usando o Designer de API
Aplicativos do Windows Forms podem ser configurados para várias culturas com o uso de assemblies satélite. Um *assembly satélite* é um assembly que contém os recursos de aplicativo para uma cultura que não seja a cultura padrão do aplicativo.

 Conforme discutido em [localizando aplicativos do ClickOnce](../deployment/localizing-clickonce-applications.md), você pode incluir vários assemblies de satélite para várias culturas dentro do mesmo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] implantação. Por padrão, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] baixará todos os assemblies de satélite em sua implantação para o computador cliente, embora um único cliente provavelmente exigirá apenas um assembly satélite.

 Este passo a passo demonstra como marcar seus assemblies satélites como opcionais e baixar somente o assembly precisa de um computador cliente para suas configurações de cultura.

> [!NOTE]
> Para fins de teste, os exemplos de código a seguir por meio de programação definem a cultura `ja-JP`. Consulte a seção "Próximas etapas" mais adiante neste tópico para obter informações sobre como ajustar esse código para um ambiente de produção.

### <a name="to-mark-satellite-assemblies-as-optional"></a>Para marcar os assemblies satélites como opcionais

1. Criar o projeto. Isso irá gerar assemblies de satélite para todas as culturas que você estiver localizando a.

2. Clique com botão direito no nome do projeto no Gerenciador de soluções e, em seguida, clique em **propriedades**.

3. Clique o **Publish** guia e, em seguida, clique em **arquivos de aplicativo**.

4. Selecione o **Mostrar todos os arquivos** caixa de seleção para exibir os assemblies satélites. Por padrão, todos os assemblies satélite serão incluídos em sua implantação e estarão visíveis na caixa de diálogo.

     Um assembly satélite terá um nome na forma  *\<isoCode > \ApplicationName.resources.dll*, onde \<isoCode > é um identificador de idioma no formato RFC 1766.

5. Clique em **New** na **grupo de Download** lista para cada identificador de idioma. Quando solicitado a fornecer um nome de grupo de download, insira o identificador de idioma. Por exemplo, para um assembly satélite japonês, você especificaria o nome do grupo de download `ja-JP`.

6. Fechar o **arquivos de aplicativo** caixa de diálogo.

### <a name="to-download-satellite-assemblies-on-demand-in-c"></a>Para baixar os assemblies satélite sob demanda em C\#

1. Abra o arquivo *Program.cs*. Se você não vir esse arquivo no Gerenciador de soluções, selecione seu projeto e sobre o **projeto** menu, clique em **Mostrar todos os arquivos**.

2. Use o código a seguir para baixar o assembly satélite adequado e iniciar o aplicativo.

     [!code-csharp[ClickOnce.SatelliteAssemblies#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.cs)]

### <a name="to-download-satellite-assemblies-on-demand-in-visual-basic"></a>Para baixar os assemblies satélite sob demanda no Visual Basic

1. No **propriedades** janela do aplicativo, clique no **aplicativo** guia.

2. Na parte inferior da página da guia, clique em **exibir eventos do aplicativo**.

3. Adicione as importações a seguir ao início do *ApplicationEvents* arquivo.

     [!code-vb[ClickOnce.SatelliteAssembliesVB#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.vb)]

4. Adicione o código a seguir à classe `MyApplication`.

     [!code-vb[ClickOnce.SatelliteAssembliesVB#2](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.vb)]

## <a name="next-steps"></a>Próximas etapas
 Em um ambiente de produção, provavelmente será necessário remover a linha nos exemplos de código que define <xref:System.Threading.Thread.CurrentUICulture%2A> como um valor específico, porque máquinas de cliente será tem o valor correto definido por padrão. Quando seu aplicativo é executado em um computador cliente japonês, por exemplo, <xref:System.Threading.Thread.CurrentUICulture%2A> será `ja-JP` por padrão. Defini-lo por meio de programação é uma boa maneira de testar seus assemblies satélites antes de implantar seu aplicativo.

## <a name="see-also"></a>Consulte também
- [Passo a passo: Baixar os assemblies satélite por demanda com a API de implantação do ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)
- [Localizar aplicativos ClickOnce](../deployment/localizing-clickonce-applications.md)
