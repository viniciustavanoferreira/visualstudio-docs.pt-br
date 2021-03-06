---
title: Obter dados para o nó SharePoint interno no Gerenciador de servidores
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b90582c9b8d352f95d3d5abb3bbb7fb69283b06b
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66401414"
---
# <a name="how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer"></a>Como: Obter dados para um nó SharePoint interno no Gerenciador de servidores
  Para cada nó SharePoint interno no **Gerenciador de servidores**, você pode obter dados para o componente subjacente do SharePoint que o nó representa. Para obter mais informações, consulte [estender o nó de conexões do SharePoint no Gerenciador de servidores](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).

## <a name="example"></a>Exemplo
 O exemplo de código a seguir demonstra como obter dados para a lista do SharePoint subjacente que representa o nó de uma lista de **Gerenciador de servidores**. Por padrão, nós da lista têm um **exibir no navegador** item de menu de contexto que você pode clicar para abrir a lista em um navegador da Web. Este exemplo amplia a nós da lista, adicionando um **modo de exibição no Visual Studio** item de menu de contexto que abre as listas diretamente no Visual Studio. O código acessa os dados da lista para o nó obter a URL da lista para abrir no Visual Studio.

 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#10)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#10)]

 Este exemplo usa o serviço de projeto do SharePoint para obter o <xref:EnvDTE.DTE> lista do objeto que é usado para abrir no Visual Studio. Para obter mais informações sobre o serviço de projeto do SharePoint, consulte [usar o serviço de projeto do SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

 Para obter mais informações sobre as tarefas básicas para criar uma extensão para um nó do SharePoint, consulte [como: Estender um nó SharePoint no Gerenciador de servidores](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).

## <a name="compile-the-code"></a>Compilar o código
 Este exemplo requer referências aos assemblies a seguir:

- EnvDTE

- Microsoft.VisualStudio.SharePoint

- Microsoft.VisualStudio.SharePoint.Explorer.Extensions

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Implantar a extensão
 Para implantar o **Gerenciador de servidores** extensão, crie um [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] pacote de extensão (VSIX) para o assembly e outros arquivos que você deseja distribuir com a extensão. Para obter mais informações, consulte [implantar extensões para ferramentas do SharePoint no Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Consulte também
- [Estender o nó de conexões do SharePoint no Gerenciador de servidores](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)
- [Como: Estender um nó SharePoint no Gerenciador de servidores](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)
- [Usar o serviço de projeto do SharePoint](../sharepoint/using-the-sharepoint-project-service.md)
- [Implantar extensões para ferramentas do SharePoint no Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)
