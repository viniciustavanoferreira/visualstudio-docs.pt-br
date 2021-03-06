---
title: 'Preparação de depuração: Projetos de console | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], console applications
- debugging console applications
- console applications, debugging
ms.assetid: 9641f1d9-2d5a-48b1-8731-6525e8f67892
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5ac87f6c5ef5fcf9fc7ca5532fe7436dedb8ba97
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691213"
---
# <a name="debugging-preparation-console-projects"></a>Preparação de depuração: Projetos de console
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Preparar para depurar um projeto de console é semelhante à preparar para depurar um projeto do Windows, com algumas considerações adicionais. Para obter mais informações, consulte [aplicativos do Windows Forms](../debugger/debugging-preparation-windows-forms-applications.md), e [preparação de depuração: Aplicativos (.NET) do Windows Forms](https://msdn.microsoft.com/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5). Devido à semelhança de todos os aplicativos do console, este tópico abrange os seguintes tipos de projeto:  
  
- Aplicativo do Console C#  
  
- Aplicativo do Console do Visual Basic  
  
- Aplicativo do Console C++ (.NET)  
  
- Aplicativo do Console C++ (Win32)  
  
  Talvez seja preciso especificar argumentos de linha de comando para o aplicativo de console. Para obter mais informações, consulte [configurações do projeto para uma configuração de depuração de C++](../debugger/project-settings-for-a-cpp-debug-configuration.md), [configurações do projeto para uma configuração de depuração do Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), ou [configurações do projeto para configurações de depuração do c# ](../debugger/project-settings-for-csharp-debug-configurations.md).  
  
  Como todas as propriedades do projeto, esses argumentos persistem entre sessões de depuração e entre sessões do Visual Studio. Em virtude disso, se o aplicativo de console for um que você tenha depurado anteriormente, lembre-se de que pode haver argumentos das sessões anteriores inseridos na caixa de diálogo **\<Projeto> Páginas de Propriedades**.  
  
  Um aplicativo de console usa a janela **Console** para aceitar a entrada e exibir mensagens de saída. Para gravar o **Console** janela, seu aplicativo deve usar o **Console** objeto em vez do objeto de depuração. Para gravar na janela de **Saída do Visual Studio**, use o objeto de depuração, como de costume. Confira se você sabe onde seu aplicativo está sendo gravado ou você pode procurar mensagens no local errado. Para obter mais informações, confira [Classe de console](https://msdn.microsoft.com/library/system.console.aspx), [Classe de depuração](https://msdn.microsoft.com/library/system.diagnostics.debug.aspx) e [Janela de Saída](../ide/reference/output-window.md).  
  
## <a name="starting-the-application"></a>Iniciando o aplicativo  
 Quando alguns aplicativos do console iniciarem, eles são executados até a conclusão e, em seguida, são fechados. Esse comportamento pode não oferecer tempo suficiente para interromper a execução e a depuração. Para poder depurar um aplicativo, use um dos seguintes procedimentos para iniciar o aplicativo:  
  
- O aplicativo inicia a execução e é executado até alcançar o ponto de interrupção.  
  
- Seus aplicativo inicia e é interrompido imediatamente na primeira linha do código-fonte.  
  
- Em uma janela de código fonte, uma linha com o botão direito e selecione **executar até o cursor**.  
  
   Seu aplicativo é iniciado e executado até a linha selecionada, ou até um ponto de interrupção, se o ponto de interrupção for atingido antes da linha.  
  
  Quando você depura um aplicativo de console, inicie o aplicativo do prompt de comando em vez do Visual Studio. Nesse caso, você poderá iniciar o aplicativo de prompt de comando e anexar o depurador do Visual Studio a ele. Para obter mais informações, consulte [anexar a processos em execução](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
  Quando você inicia um aplicativo de console do Visual Studio, a janela **Console** às vezes aparece por trás da janela do Visual Studio. Se você tentar iniciar o aplicativo de console do Visual Studio e nada acontecer, tente mover a janela do Visual Studio.  
  
## <a name="see-also"></a>Consulte também  
 [Depurando código nativo](../debugger/debugging-native-code.md)   
 [Depurando código gerenciado](../debugger/debugging-managed-code.md)   
 [Tipos de projeto do Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [Tipos de projeto do C#, F# e Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Configurações do projeto para uma configuração de depuração do C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Segurança do depurador](../debugger/debugger-security.md)
