---
title: 'Como: Especifique um nome no Menu Iniciar para um aplicativo ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 30bb4050399bf7a6d9120f7e5454b26ce505af35
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149766"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Como: Especificar um nome no menu Iniciar para um aplicativo ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Quando um [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicativo é instalado para uso online e offline, uma entrada é adicionada para o **começar** menu e o **adicionar ou remover programas** lista. Por padrão, o nome de exibição é o mesmo que o nome do assembly do aplicativo, mas você pode alterar o nome de exibição, definindo **nome do produto** na **opções de publicação** caixa de diálogo.  
  
 **Nome do produto** será exibido na página Publish. htm; para um aplicativo offline instalado, ele será o nome da entrada na **começar** menu e ele também será o nome que aparece no **adicionar ou remover Programas**.  
  
 **Nome do publicador** será exibida na página Publish. htm acima **nome do produto**, e para um aplicativo offline instalado, ele também será o nome da pasta que contém o ícone do aplicativo na **iniciar**  menu.  
  
 Você pode definir as **nome do produto** e **nome do publicador** propriedades no **opções de publicação** caixa de diálogo, disponível no **publicar** página dos **Designer de projeto**.  
  
### <a name="to-specify-a-start-menu-name"></a>Para especificar um nome no menu Iniciar  
  
1. Com um projeto selecionado no **Gerenciador de Soluções**, no menu **Projeto**, clique em **Propriedades**.  
  
2. Clique o **publicar** guia.  
  
3. Clique o **opções** para abrir o **opções de publicação** caixa de diálogo.  
  
4. Clique em **descrição**.  
  
5. No **opções de publicação** caixa de diálogo, digite o nome a ser exibido no **nome do produto**.  
  
6. Opcionalmente, você pode inserir um nome de editor no **nome do publicador**.  
  
## <a name="see-also"></a>Consulte também  
 [Publicando aplicativos ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Como: Publicar um aplicativo ClickOnce usando o assistente de publicação](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
