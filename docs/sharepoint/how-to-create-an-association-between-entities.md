---
title: 'Como: criar uma associação entre entidades | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- AssociationGroupTool
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associations between entities
- BDC [SharePoint development in Visual Studio], associations between entities
- Business Data Connectivity service [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associate external content types
- Business Data Connectivity service [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], associate external content types
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: cba9d712e2bcfa90ae37d47e3c518697f10b6add
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72981840"
---
# <a name="how-to-create-an-association-between-entities"></a>Como: criar uma associação entre entidades
  Você pode definir relações entre entidades em seu modelo de BDC (conectividade de dados corporativos) Criando associações. O Visual Studio gera métodos que fornecem aos consumidores do modelo informações sobre cada associação. Esses métodos podem ser consumidos por Web Parts do SharePoint, listas ou aplicativos personalizados para exibir relações de dados em uma interface do usuário.

 Você pode criar dois tipos de associações no designer do BDC: associações baseadas em chave estrangeira e associações de chaves estrangeiras externas. Para obter mais informações, consulte [criar uma associação entre entidades](../sharepoint/creating-an-association-between-entities.md).

### <a name="to-create-an-association-between-entities"></a>Para criar uma associação entre entidades

1. Na guia **BusinessDataConnectivity** da caixa de **ferramentas**, escolha o item de **Associação** .

2. No BDC designer, escolha a entidade de origem e, em seguida, escolha a entidade de destino.

     O **Editor de associação** é exibido.

3. Se você quiser criar uma associação baseada em chave estrangeira, marque a caixa de seleção **é Associação de chave estrangeira** .

    1. Na coluna **ID da origem** da tabela de **mapeamento de identificadores** , escolha o identificador ao lado de cada descritor de tipo correspondente que aparece na coluna **campo** .

         Por exemplo, na coluna **ID de origem** , selecione `ContactID` ao lado do descritor de tipo `ReadList.salesOrderList.SalesOrderList.SalesOrder.ContactID` e o descritor de tipo `ReadItem.salesOrder.SalesOrder.ContactID`.

4. Se você quiser criar uma associação de um reless estrangeiro, desmarque a caixa de seleção **é Associação de chave estrangeira** .

5. Selecione o botão **OK**.

6. No BDC designer, uma linha que representa a associação aparece entre a entidade de origem e a entidade de destino.

     O Visual Studio adiciona um método de navegador de associação à classe de serviço da entidade de destino e a classe de serviço da entidade de origem. Para obter mais informações sobre métodos de navegação de associação, consulte [operações com suporte](/previous-versions/office/developer/sharepoint-2010/ee557363(v=office.14)).

7. No método de navegador de associação da entidade de origem, adicione o código que retorna uma coleção de entidades de destino.

8. No método de navegador de associação da entidade de destino, adicione o código que retorna a entidade de origem relacionada.

     Para obter exemplos de métodos do navegador de associação, consulte [criar uma associação entre entidades](../sharepoint/creating-an-association-between-entities.md).

## <a name="see-also"></a>Consulte também
- [Criar uma associação entre entidades](../sharepoint/creating-an-association-between-entities.md)
- [Criar um modelo de conectividade de dados corporativos](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Como adicionar um método localizador](../sharepoint/how-to-add-a-finder-method.md)
- [Como adicionar um método localizador específico](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Como: adicionar um método de criador](../sharepoint/how-to-add-a-creator-method.md)
- [Como adicionar um método excluidor](../sharepoint/how-to-add-a-deleter-method.md)
- [Como adicionar um método de atualizador](../sharepoint/how-to-add-an-updater-method.md)
- [Visão geral das ferramentas de design de modelo do BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Como: adicionar um parâmetro a um método](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Como definir uma instância de método](../sharepoint/how-to-define-a-method-instance.md)
- [Como definir o descritor de tipo de um parâmetro](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [Walkthrough: criar uma lista externa no SharePoint usando dados corporativos](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)
