---
title: Assemblies satélite de segurança e localizados | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
caps.latest.revision: 9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 866e313a36af5ef72f910a5eafbf7b31c971d890
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672907"
---
# <a name="security-and-localized-satellite-assemblies"></a>Assemblies satélite de segurança e localizados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Se seu assembly principal usar nomenclatura forte, assemblies satélites deverão ser assinados com a mesma chave privada que o assembly principal. Se o par de chave pública/privada não corresponder entre os assemblies satélites e principal, seus recursos não serão carregados. Para obter mais informações sobre a assinatura de assemblies, consulte [Como assinar um assembly com um nome forte](https://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).

 Em geral, você poderá precisar que o grupo de assinatura da sua organização ou uma organização de assinatura externa assine com a chave privada. Isso ocorre devido à natureza confidencial da chave privada: o acesso geralmente é limitado a algumas pessoas. Você pode usar assinatura atrasada durante o desenvolvimento. Para obter mais informações, consulte [Assinando um assembly com atraso](https://msdn.microsoft.com/library/9d300e17-5bf1-4360-97da-2aa55efd9070).

## <a name="see-also"></a>Veja também
 [Considerações sobre segurança de assembly](https://msdn.microsoft.com/library/1b5439c1-f3d5-4529-bd69-01814703d067) [principais conceitos de segurança](https://msdn.microsoft.com/library/3cfced4f-ea02-4e66-ae98-d69286363e98) [introdução a aplicativos internacionais com base na .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md) [Localizando aplicativos](../ide/localizing-applications.md) [Globalizando e Localizando aplicativos](../ide/globalizing-and-localizing-applications.md)
