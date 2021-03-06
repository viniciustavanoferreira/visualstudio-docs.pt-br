---
title: Página Serviços, Designer de Projeto | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
ms.assetid: 6dd9e0fa-acba-4d7d-b081-705b0fc86ff5
caps.latest.revision: 30
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 11e1cd997c76974e7b4b8771c0579c175469eca6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665484"
---
# <a name="services-page-project-designer"></a>Página Serviços, Designer de Projeto
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Os serviços de aplicativo cliente fornecem acesso simplificado ao logon, às funções e aos serviços de perfil do [!INCLUDE[ajax_current_short](../../includes/ajax-current-short-md.md)] por meio dos aplicativos Windows Forms e WPF (Windows Presentation Foundation). Você pode usar a página **Serviços** do **Designer de Projeto** para habilitar e configurar serviços de aplicativo cliente para seu projeto.

 Com os serviços de aplicativo cliente, você pode usar um servidor centralizado para autenticar usuários, determinar a função ou as funções atribuídas a cada usuário e armazenar configurações de aplicativo por usuário que você pode compartilhar pela rede. Para obter mais informações, consulte [Serviços de aplicativo cliente](https://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e).

 Para acessar a página **Serviços**, selecione um nó do projeto no **Gerenciador de Soluções** e, em seguida, clique em **Propriedades** no menu **Projeto**. Quando o **Designer de Projeto** for exibido, clique na guia **Serviços**.

> [!NOTE]
> Os serviços do aplicativo cliente exigem a versão completa do .NET Framework e não há suporte para o .NET Framework Client Profile. Se a caixa de seleção **Habilitar serviços do aplicativo cliente** estiver desabilitada, verifique se a **Estrutura de destino** está definida como .NET Framework 3.5 ou posterior. Para exibir a configuração da **Estrutura de destino** em C#, abra o Designer de Projeto e clique na página **Aplicativo**. Para exibir a configuração **Estrutura de destino** no Visual Basic, abra o Designer de Projeto, clique na página **Compilar** e, em seguida, clique em **Opções Avançadas de Compilação**.

## <a name="task-list"></a>Lista de Tarefas
 [Como: Configurar os serviços do aplicativo cliente](https://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)

## <a name="uielement-list"></a>Lista UIElement
 **Configuração** do Este controle não é editável nesta página. Para obter uma descrição desse controle, consulte [Página de compilação, Designer de Projeto (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) ou [Página de Build, Designer de Projeto (C#)](../../ide/reference/build-page-project-designer-csharp.md).

 **Plataforma** Esse controle não é editável nesta página. Para obter uma descrição desse controle, consulte [Página de compilação, Designer de Projeto (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) ou [Página de Build, Designer de Projeto (C#)](../../ide/reference/build-page-project-designer-csharp.md).

 **Habilitar serviços de aplicativo cliente** Selecione para habilitar os serviços de aplicativo cliente. Você deve especificar locais de serviço na página **Serviços** para usar serviços de aplicativo cliente.

 **Usar autenticação do Windows** Indica que o provedor de autenticação usará a autenticação baseada no Windows, ou seja, a identidade fornecida pelo sistema operacional Windows.

 **Usar autenticação de formulários** Indica que o provedor de autenticação usará a autenticação de formulários. Isso significa que seu aplicativo deve fornecer uma interface do usuário para logon. Para obter mais informações, confira [Como: Implementar logon de usuário com serviços de aplicativos cliente](https://msdn.microsoft.com/library/5431a671-eb02-4e18-a651-24764fccec9a).

 **Local do serviço de autenticação** Usado somente com a autenticação de formulários. Especifica o local do serviço de autenticação.

 **Opcional: O provedor de credenciais**  usado somente com a autenticação de formulários. Indica a implementação <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> que o serviço de autenticação usará para exibir uma caixa de diálogo de logon quando o aplicativo chamar o método `static`<xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> e passar cadeias de caracteres vazias ou `null` para os parâmetros. Se deixar essa caixa em branco, você deverá passar um nome de usuário válido e uma senha para o método <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName>. Você deve especificar o provedor de credenciais como um nome de tipo qualificado pelo assembly. Para obter mais informações, consulte <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> e [Assembly Names](https://msdn.microsoft.com/library/8f8c2c90-f15d-400e-87e7-a757e4f04d0e) (Nomes de assembly). Em sua forma mais simples, um nome de tipo qualificado pelo assembly é semelhante ao exemplo a seguir: `MyNamespace.MyLoginClass, MyAssembly`

 **Local do serviço de funções** Especifica o local do serviço de funções.

 **Local do serviço de configurações da Web** Especifica o local do serviço de perfil (configurações da Web).

 **Avançado** Abre a [caixa de diálogo Configurações avançadas para serviços](../../ide/reference/advanced-settings-for-services-dialog-box.md), que você pode usar para substituir o comportamento padrão. Por exemplo, você pode usar essa caixa de diálogo para especificar um banco de dados para armazenamento offline, em vez de usar o sistema de arquivos local. Para obter mais informações, consulte [Configurações Avançadas para a Caixa de Diálogo Serviços](../../ide/reference/advanced-settings-for-services-dialog-box.md).

## <a name="see-also"></a>Consulte também
 [Serviços de aplicativos](https://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e) [caixa de diálogo Configurações avançadas do cliente para serviços](../../ide/reference/advanced-settings-for-services-dialog-box.md) [How: Configurar página de compilação de](https://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8) [serviços de aplicativos de cliente, designer de projeto (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) [, designer de projeto (C#)](../../ide/reference/build-page-project-designer-csharp.md) [introdução ao designer de projeto](https://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7)
