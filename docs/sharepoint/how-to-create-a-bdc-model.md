---
title: 'Como: Criar um modelo BDC | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9126a0d3bb552f525247cbfb2243504a1effaa92
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435465"
---
# <a name="how-to-create-a-bdc-model"></a>Como: Criar um modelo BDC
  Você pode criar um modelo de conectividade de dados comerciais (BDC) usando o modelo para esse tipo de item e, em seguida, adicionando o modelo a qualquer projeto do SharePoint. Para obter mais informações, consulte [criar um modelo de conectividade de dados de negócios](../sharepoint/creating-a-business-data-connectivity-model.md). Para obter mais informações sobre como projetar o modelo, consulte [criar um modelo de conectividade de dados corporativos](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-a-bdc-project"></a>Para criar um projeto BDC

1. Na barra de menus, selecione **Arquivo** > **Novo** > **Projeto**.

    > [!NOTE]
    > Se o seu IDE for definido para usar configurações de desenvolvimento do Visual Basic, escolha **arquivo** > **novo projeto**.

     A caixa de diálogo **Novo Projeto** é aberta.

2. Em um **Visual Basic** ou **Visual c#**, escolha **Office/SharePoint**, **soluções do SharePoint**.

3. No **modelos** painel, escolha o **SharePoint 2013 - projeto vazio** item e, em seguida, escolha o **Okey** botão.

     O **Assistente para personalização do SharePoint** é aberta.

4. Sobre o **especificar o nível de site e segurança para depuração** página, especifique a URL de um site do SharePoint no computador local, escolha o **implantar como solução de farm** botão de opção e, em seguida, escolha o **Concluir** botão.

     Você testará o modelo no site do SharePoint que você especificou.

    > [!IMPORTANT]
    > Você deve implantar o projeto como uma solução de farm porque os modelos de BDC suportam somente soluções de farm.

     Um projeto vazio do SharePoint é criado.

5. Na barra de menus, escolha **Projeto** > **Adicionar Novo Item**.

6. No **Adicionar Novo Item** diálogo caixa, escolha o **Office/SharePoint** nó.

7. Na lista de modelos do SharePoint, escolha **modelo de conectividade de dados corporativos (somente solução de Farm)**.

8. No **nome** caixa, especifique um nome para o modelo BDC e, em seguida, escolha o **Add** botão.

     Um **modelo de conectividade de dados corporativos** item é adicionado ao projeto. Por padrão, o modelo aparece no designer de BDC. Para obter mais informações, consulte [criar um modelo de conectividade de dados de negócios](../sharepoint/creating-a-business-data-connectivity-model.md).

## <a name="see-also"></a>Consulte também
- [Criar um modelo de conectividade de dados corporativos](../sharepoint/creating-a-business-data-connectivity-model.md)
- [Como: Adicionar um arquivo de modelo BDC existente a um projeto do SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)
- [Como: Use um arquivo de recurso para especificar nomes localizados, propriedades e permissões](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)
- [Como: Incluir um assembly personalizado em uma recurso BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)
- [Integrando dados corporativos ao SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
