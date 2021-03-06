---
title: 'Como: Verificar as atualizações de aplicativos programáticamente usando a API de implantação do ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5250e719cce945bdcce90a9d49d2ed8c27555612
ms.sourcegitcommit: 7b60e81414a82c6d34f6de1a1f56115c9cd26943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81444954"
---
# <a name="how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api"></a>Como verificar se há atualizações do aplicativo programaticamente usando a API de implantação do ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O ClickOnce fornece duas maneiras de atualizar um aplicativo assim que ele for implantado. No primeiro método, você pode configurar a implantação clickOnce para verificar automaticamente se há atualizações em determinados intervalos. No segundo método, você pode escrever <xref:System.Deployment.Application.ApplicationDeployment> código que usa a classe para verificar atualizações com base em um evento, como uma solicitação de usuário.  
  
 Os procedimentos a seguir mostram algum código para a realização de uma atualização programática e também descrevem como configurar sua implantação do ClickOnce para habilitar verificações de atualização programática.  
  
 Para atualizar um aplicativo ClickOnce de forma programática, você deve especificar um local para atualizações. Isso às vezes é referido como um provedor de implantação. Para obter mais informações sobre a configuração desta propriedade, consulte [Escolhendo uma estratégia de atualização de cliques](../deployment/choosing-a-clickonce-update-strategy.md).  
  
> [!NOTE]
> Você também pode usar a técnica descrita abaixo para implantar seu aplicativo a partir de um local, mas atualizá-lo de outro. Para obter mais informações, consulte [Como: Especificar um local alternativo para atualizações de implantação](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md).  
  
### <a name="to-check-for-updates-programmatically"></a>Para verificar se há atualizações programáticas  
  
1. Crie um novo aplicativo do Windows Forms usando sua linha de comando ou ferramentas visuais preferidas.  
  
2. Crie qualquer botão, item do menu ou outro item da interface do usuário que você deseja que seus usuários selecionem para verificar se há atualizações. A partir do manipulador de eventos desse item, ligue para o seguinte método para verificar e instalar atualizações.  
  
     [!code-cpp[ClickOnceAPI#6](../snippets/cpp/VS_Snippets_Winforms/ClickOnceAPI/cpp/form1.cpp#6)]
     [!code-csharp[ClickOnceAPI#6](../snippets/csharp/VS_Snippets_Winforms/ClickOnceAPI/CS/Form1.cs#6)]
     [!code-vb[ClickOnceAPI#6](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnceAPI/VB/Form1.vb#6)]  
  
3. Compile sua aplicação.  
  
### <a name="using-mageexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Usando o Mage.exe para implantar um aplicativo que verifica atualizações programáticamente  
  
- Siga as instruções para implantar seu aplicativo usando o Mage.exe conforme explicado no [Passo a Passo: Implantando manualmente um aplicativo ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Ao ligar para o Mage.exe para gerar o manifesto `providerUrl`de implantação, certifique-se de usar o switch de linha de comando e especificar a URL onde o ClickOnce deve verificar se há atualizações. Se o aplicativo `http://www.adatum.com/MyApp`for atualizado a partir de , por exemplo, sua chamada para gerar o manifesto de implantação pode parecer assim:  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### <a name="using-mageuiexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Usando mageUI.exe para implantar um aplicativo que verifica se há atualizações programáticas  
  
- Siga as instruções para implantar seu aplicativo usando o Mage.exe conforme explicado no [Passo a Passo: Implantando manualmente um aplicativo ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Na guia **Opções de implantação,** defina o campo **Iniciar localização** para o manifesto do aplicativo ClickOnce deve verificar se há atualizações. Na guia **Opções de atualização,** limpe o **aplicativo: "Este aplicativo deve verificar se há caixa** de seleção de atualizações".  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
 Seu aplicativo deve ter permissões de confiança total para usar atualização programática.  
  
## <a name="see-also"></a>Consulte Também  
 [Como: Especificar um local alternativo para atualizações de implantação](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [Escolhendo uma estratégia de atualização do ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Publicando aplicativos ClickOnce](../deployment/publishing-clickonce-applications.md)
