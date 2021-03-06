---
title: Criar uma extensão com uma janela de ferramentas | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 94c8335b8d723ef20c04cfffe6b3788d71ecaa4f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62431843"
---
# <a name="creating-an-extension-with-a-tool-window"></a>Criando uma extensão com uma janela de ferramentas
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Neste procedimento, você aprenderá a usar o modelo de projeto do VSIX e o **janela de ferramenta personalizada** modelo de item para criar uma extensão com uma janela de ferramentas.  
  
## <a name="prerequisites"></a>Prerequisites  
 A partir do Visual Studio 2015, você não instale o SDK do Visual Studio no Centro de download. Ele é incluído como um recurso opcional na instalação do Visual Studio. Você também pode instalar o SDK do VS mais tarde. Para obter mais informações, consulte [instalando o SDK do Visual Studio](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="creating-a-tool-window"></a>Criação de uma janela de ferramentas  
  
1. Crie um projeto do VSIX chamado **FirstWindow**. Você pode encontrar o modelo de projeto VSIX na **novo projeto** diálogo sob **Visual c# / extensibilidade**.  
  
2. Quando o projeto aberto, adicione um modelo de item da janela de ferramenta denominado **FirstWindow**. No **Gerenciador de soluções**, clique com botão direito no nó do projeto e selecione **Add / Novo Item**. No **Adicionar Novo Item** caixa de diálogo, vá para **Visual c# / extensibilidade** e selecione **janela de ferramenta personalizada**. No **nome** campo na parte inferior da janela, altere o nome de arquivo da janela de ferramenta **FirstWindow.cs**.  
  
3. Compile o projeto e comece a depuração.  
  
     A instância experimental do Visual Studio é exibida. Para obter mais informações sobre a instância experimental, consulte [a instância Experimental](../extensibility/the-experimental-instance.md).  
  
4. Na instância experimental, vá para **exibição / Other Windows**.  
  
     Você deve ver um item de menu **FirstWindow**. Clique nele.  
  
     Você deverá ver uma janela de ferramenta com o título **FirstWindow** e uma fala botão **Click Me!.**
