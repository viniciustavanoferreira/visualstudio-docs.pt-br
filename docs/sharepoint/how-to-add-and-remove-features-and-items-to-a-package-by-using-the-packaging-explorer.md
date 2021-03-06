---
title: 'Packaging Explorer: Adicionar e remover recursos e itens de pacote'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackagingExplorer
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0f01ecb67cb82ffe325ea471ad5fb5913c8e4d28
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66401557"
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>Como: Adicionar e remover funcionalidades e itens de um pacote usando o Packaging Explorer
  Para configurar um pacote para implantar recursos e itens do SharePoint, você pode usar o Packaging Explorer. Você pode ajustar os itens de projeto do SharePoint e recursos em seu arquivo. wsp.

 Como alternativa, você pode usar o Designer de empacotamento para exibir e reordenar os recursos para alterar a ordem de ativação. Para obter mais informações, confira [Como: Adicionar e remover funcionalidades e itens de um pacote usando o Designer de pacote](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).

## <a name="open-the-packaging-explorer"></a>Abra o Gerenciador de empacotamento
 Você pode usar o procedimento a seguir para abrir o Gerenciador de pacotes, se sua solução do Visual Studio tem pelo menos um projeto do SharePoint. Como alternativa, o Packaging Explorer é aberto automaticamente quando você exibe um designer de pacote ou recurso. Depois de fechar todos os designers de recurso e pacote, também fecha o Packaging Explorer.

#### <a name="to-open-the-packaging-explorer"></a>Para abrir o Gerenciador de empacotamento

1. Na barra de menus, escolha **modo de exibição** > **Other Windows** > **Packaging Explorer**.

     O **Packaging Explorer** aparece na **caixa de ferramentas**.

## <a name="adding-a-feature-to-a-package"></a>Adicionar um recurso a um pacote
 Você pode adicionar recursos novos e existentes a um pacote usando o Packaging Explorer.

#### <a name="to-add-a-sharepoint-feature"></a>Para adicionar um recurso do SharePoint

1. Abra o **Packaging Explorer**, abra o menu de atalho para o projeto e, em seguida, escolha **adicionar recurso**.

#### <a name="to-move-an-existing-sharepoint-feature"></a>Para mover um recurso existente do SharePoint

1. Abra o **Packaging Explorer**e, em seguida, execute uma das seguintes etapas:

    - Arraste uma **recurso** de um projeto para outro projeto.

    - Abra o menu de atalho para um recurso, escolha **Recortar**, abra o menu de atalho para o projeto ao qual você deseja mover o recurso e, em seguida, escolha **colar**.

    > [!NOTE]
    > Use este procedimento se você tiver mais de um projeto do SharePoint em sua solução.

## <a name="validate-a-feature-or-package"></a>Validar um pacote ou recurso
 Você pode identificar problemas potenciais nos recursos do SharePoint e os pacotes por meio da validação de arquivos. Avisos e erros são exibidos na janela lista de erros e janela de saída.

#### <a name="to-validate-a-sharepoint-feature-or-package"></a>Para validar um pacote ou recurso do SharePoint

1. Abra o **Packaging Explorer**.

2. Abra um menu de atalho para um recurso ou pacote e, em seguida, escolha **validar**.

## <a name="see-also"></a>Consulte também
- [Empacotar e implantar soluções do SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
