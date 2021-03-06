---
title: SDK do Visual Studio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
caps.latest.revision: 57
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 27dce16d9fe02063eae935af96c26184285e583d
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75850374"
---
# <a name="visual-studio-sdk"></a>SDK do Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O SDK do Visual Studio ajuda você a estender recursos do Visual Studio ou integrar novos recursos ao Visual Studio. Você pode distribuir suas extensões para outros usuários, bem como para a galeria do Visual Studio. A seguir estão algumas das maneiras pelas quais você pode estender o Visual Studio:  
  
- Adicionar comandos, botões, menus e outros elementos da interface do usuário ao IDE  
  
- Adicionar janelas de ferramentas para nova funcionalidade  
  
- Estender o IntelliSense para um determinado idioma ou fornecer IntelliSense para novas linguagens de programação  
  
- Use lâmpadas leves para fornecer dicas e sugestões que ajudem os desenvolvedores a escrever código melhor  
  
- Habilitar o suporte para uma nova linguagem  
  
- Adicionar um tipo de projeto personalizado  
  
- Alcance milhões de desenvolvedores por meio do Visual Studio Marketplace  
  
  Se você nunca escreveu uma extensão do Visual Studio antes, você deve encontrar mais informações sobre esses recursos e em [iniciando o desenvolvimento de extensões do Visual Studio](../extensibility/starting-to-develop-visual-studio-extensions.md).  
  
## <a name="installing-the-visual-studio-sdk"></a>Instalar o SDK do Visual Studio  
 A partir do Visual Studio 2015, você não instala o SDK do Visual Studio a partir do centro de download. Ele é incluído como um recurso opcional na instalação do Visual Studio. Você também pode instalar o SDK do VS mais tarde. Para obter mais informações, consulte [instalando o SDK do Visual Studio](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="whats-new-in-the-visual-studio-2015-sdk"></a>O que há de novo no SDK do Visual Studio 2015  
 O SDK do Visual Studio tem alguns recursos novos, incluindo lâmpadas leves e novos itens de projeto que permitem criar comandos de menu, janelas de ferramentas e extensões de editor usando um pacote VSIX. Para obter mais informações, consulte [What ' s New in the Visual Studio 2015 SDK](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md).  
  
## <a name="visual-studio-user-experience-guidelines"></a>Diretrizes da experiência do usuário do Visual Studio  
 Obtenha ótimas dicas para criar a interface do usuário para sua extensão nas [diretrizes de experiência do usuário do Visual Studio](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
 Você também pode aprender a fazer com que sua extensão fique ótima em dispositivos DPI altos com nosso tópico [abordando problemas de DPI](../extensibility/addressing-dpi-issues2.md) .  
  
 Aproveite o [catálogo e o serviço de imagem](../extensibility/image-service-and-catalog.md) para um excelente gerenciamento de imagens e suporte para DPI alto e temas.  
  
## <a name="finding-and-installing-existing-visual-studio-extensions"></a>Localizando e instalando extensões existentes do Visual Studio  
 Você pode encontrar extensões do Visual Studio na caixa de diálogo **extensões e atualizações** no menu **ferramentas** . Para obter mais informações, consulte [Localizando e usando extensões do Visual Studio](../ide/finding-and-using-visual-studio-extensions.md). Você também pode encontrar extensões no [Visual Studio Marketplace](https://marketplace.visualstudio.com/)  
  
## <a name="visual-studio-sdk-reference"></a>Referência ao SDK do Visual Studio  
 Você pode encontrar a referência de API do SDK do Visual Studio na [referência do SDK do Visual Studio](../extensibility/visual-studio-sdk-reference.md).  
  
## <a name="visual-studio-sdk-samples"></a>Exemplos do SDK do Visual Studio  
 Você pode encontrar exemplos de software livre de extensões do SDK do VS no GitHub em [exemplos do Visual Studio](https://github.com/Microsoft/VSSDK-Extensibility-Samples). Este repositório do GitHub contém exemplos que ilustram vários recursos extensíveis no Visual Studio.  
  
## <a name="other-visual-studio-sdk-resources"></a>Outros recursos do SDK do Visual Studio  
 Se você tiver dúvidas sobre o VSSDK ou quiser compartilhar suas experiências desenvolvendo extensões, poderá usar o fórum de [extensibilidade do Visual Studio](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx) ou o [chat do grupo ExtendVS](https://gitter.im/Microsoft/extendvs).  
  
 Você pode encontrar mais informações no [blog do VSX Arcana](https://blogs.msdn.microsoft.com/vsx/) e vários Blogs escritos por MVPs da Microsoft:  
  
- [Extensões do Visual Studio favoritas](https://scottdorman.blog/2014/10/05/favorite-visual-studio-extensions/)  
  
- [Extensibilidade do Visual Studio](http://www.visualstudioextensibility.com/overview/vs/)  
  
- [Estendendo o Visual Studio](https://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)  
  
## <a name="see-also"></a>Veja também  
 [Criando uma extensão com um comando de Menu](../extensibility/creating-an-extension-with-a-menu-command.md)   
 [Como: migrar projetos de extensibilidade para o Visual Studio 2015](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2015.md)   
 [Perguntas frequentes: convertendo suplementos em extensões VSPackage](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)   
 [Gerenciando vários threads em código gerenciado](../extensibility/managing-multiple-threads-in-managed-code.md)   
 [Estendendo menus e comandos](../extensibility/extending-menus-and-commands.md)   
 [Adicionando comandos a barras de ferramentas](../extensibility/adding-commands-to-toolbars.md)   
 [Estendendo e personalizando as janelas de ferramentas](../extensibility/extending-and-customizing-tool-windows.md)   
 [Extensões de serviço de editor e de linguagem](../extensibility/editor-and-language-service-extensions.md)   
 [Estendendo projetos](../extensibility/extending-projects.md)   
 [Estendendo configurações e opções de usuário](../extensibility/extending-user-settings-and-options.md)   
 [Criando modelos personalizados de projeto e Item](../extensibility/creating-custom-project-and-item-templates.md)   
 [Estendendo propriedades e a janela de propriedades](../extensibility/extending-properties-and-the-property-window.md)   
 [Estendendo outras partes do Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Usando e fornecendo serviços](../extensibility/using-and-providing-services.md)   
 [Estendendo serviços conectados](../extensibility/extending-connected-services.md)   
 [Gerenciando  VSPackages](../extensibility/managing-vspackages.md)  
   de [shell isolado do Visual Studio](../extensibility/visual-studio-isolated-shell.md)  
 [Enviando  de extensões do Visual Studio](../extensibility/shipping-visual-studio-extensions.md)  
 [Dentro do SDK do Visual Studio](../extensibility/internals/inside-the-visual-studio-sdk.md)   
 [Suporte para o SDK do Visual Studio](../extensibility/support-for-the-visual-studio-sdk.md)   
   de [arquivo](../extensibility/archive.md)  
 [Referência do SDK do Visual Studio](../extensibility/visual-studio-sdk-reference.md)
