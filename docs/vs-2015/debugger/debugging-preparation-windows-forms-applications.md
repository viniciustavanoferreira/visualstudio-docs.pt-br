---
title: 'Preparação de depuração: Aplicativos de formulários do Windows | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
helpviewer_keywords:
- debugging Windows applications
- Windows applications, debugging
- debugging [Visual Studio], Windows applications
- debugging [J#], Windows applications
- debugging [C#], Windows applications
- debugging [Visual Basic], Windows applications
ms.assetid: 7092ee7f-8378-4def-aef8-1695bd97cf14
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5b11855fbd19dc464f92b4339684ef8346556c21
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691142"
---
# <a name="debugging-preparation-windows-forms-applications"></a>Preparação de depuração: Aplicativos dos Windows Forms
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O modelo de projeto do Windows Forms (.NET) cria um aplicativo do Windows Forms. Depurar esse tipo de aplicativo no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] é simples. Para obter mais informações, consulte [criando um projeto de aplicativo do Windows](https://msdn.microsoft.com/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Quando você cria um projeto do Windows Forms com o modelo de projeto, o [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] cria automaticamente as configurações necessárias para as configurações de depuração e versão. Se necessário, você pode alterar essas configurações. Essas configurações podem ser alteradas na caixa de diálogo **\<nome do projeto> Páginas de Propriedades** (**Meu Projeto** em Visual Basic).  
  
 Para obter mais informações, consulte [configurações de propriedade recomendadas](../debugger/managed-debugging-recommended-property-settings.md).  
  
 A tabela a seguir exibe uma configuração de propriedade recomendada adicional.  
  
### <a name="configuration-properties-in-debug-tab"></a>Propriedades de configuração na guia Depurar  
  
|**Nome da propriedade**|**Configuração**|  
|-----------------------|-----------------|  
|**Iniciar ação**|–   Definido como **Iniciar projeto,** na maioria das vezes. Definido como **Iniciar programa externo** se você quiser iniciar outro executável ao iniciar a depuração (geralmente para depuração de DLLs).|  
  
 Você pode depurar aplicativos do Windows Forms de dentro do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ou anexando a um aplicativo já em execução. Para obter mais informações sobre como anexar, consulte [anexar a processos em execução](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>Para depurar um aplicativo C#, F# ou Windows Forms do Visual Basic  
  
1. Abra o projeto no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
2. Crie pontos de interrupção conforme o necessário.  
  
    Como os aplicativos do Windows Forms são controlados por eventos, seus pontos de interrupção entrarão no código do manipulador de eventos ou nos métodos chamados pelo código do manipulador de eventos. Eventos comuns nos quais colocar pontos de interrupção incluem:  
  
   1. Os eventos associados a um controle, como Clique, Insira etc.  
  
   2. Os eventos associados à inicialização e o desligamento do aplicativo, como Carregar, Ativado etc.  
  
   3. Foco e eventos de validação.  
  
      Para obter mais informações, consulte [Criando manipuladores de eventos nos Windows Forms](https://msdn.microsoft.com/library/6514e530-c6b8-489c-a8d2-eda7b7072701).  
  
3. No menu **Depurar**, clique em **Iniciar**.  
  
4. Depuração usando as técnicas discutidas [Noções básicas do depurador](../debugger/debugger-basics.md).  
  
## <a name="see-also"></a>Consulte também  
 [Depurando código gerenciado](../debugger/debugging-managed-code.md)   
 [Tipos de projeto do C#, F# e Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Como: Definir as configurações de depuração e de versão](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Configurações do projeto para configurações de depuração de C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Configurações do projeto para uma configuração de depuração do Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Anexar a processos em execução](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](https://msdn.microsoft.com/library/627df1e9-b254-41af-bbac-9a4f02810c54)
