---
title: Como importar uma página mestra ou tema | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2c5078d31e2dcb7f11e5c19e0f8cb228e2f75d50
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72984196"
---
# <a name="how-to-import-a-master-page-or-theme"></a>Como importar uma página mestra ou tema
  Você pode dar uma aparência consistente às páginas do seu site do SharePoint criando e usando páginas mestras e temas. o [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] não fornece modelos para esses elementos, mas você pode criá-los no SharePoint Designer e, em seguida, importá-los para o [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Para obter mais informações, consulte [bloco de construção: páginas e interface do usuário](/previous-versions/office/developer/sharepoint-2010/ee539040(v=office.14)) no site da Microsoft.

### <a name="to-import-a-master-page-or-theme"></a>Para importar uma página mestra ou tema

1. No [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], crie ou abra um projeto do SharePoint.

     Para obter informações sobre como criar um projeto do SharePoint, consulte [projeto do SharePoint e modelos de item de projeto](../sharepoint/sharepoint-project-and-project-item-templates.md).

2. Na barra de menus, escolha **Projeto** > **Adicionar Novo Item**.

3. Na caixa de diálogo **Adicionar novo item** , expanda o nó **SharePoint** e escolha o nó **2010** .

4. Na lista de modelos do SharePoint, escolha o modelo de **módulo** e, em seguida, especifique um nome para o módulo.

     Um módulo contém arquivos (por exemplo, página mestra ou arquivos de tema) para implantação em um local que você especificar no SharePoint.

5. No módulo, exclua o arquivo padrão, chamado *Sample. txt*.

6. Escolha o nó do módulo.

7. Na barra de menus, escolha **projeto** > **Adicionar item existente**e, em seguida, escolha a página mestra ou o arquivo de tema.

     Os arquivos de página mestra têm uma extensão. Master, e os arquivos de tema têm uma extensão. thmx.

8. Se você adicionou uma página mestra, altere sua configuração de **resolução de conflito de implantação** para **automática** nas propriedades do módulo.

    > [!NOTE]
    > Poderão ocorrer erros se o nome da página mestra for o mesmo que o nome de uma página mestra existente marcada como página mestra padrão ou página mestra personalizada. Para obter informações sobre como resolver esse problema, consulte [Walkthrough: importar uma página mestra personalizada e uma página do site com uma imagem](../sharepoint/walkthrough-import-a-custom-master-page-and-site-page-with-an-image.md).

9. No módulo, abra *Elements. xml*.

     Você deve atualizar o arquivo *Elements. xml* para fazer referência à página mestra ou ao tema que você adicionou.

10. Para uma página mestra, substitua a marcação de módulo existente pela marcação a seguir.

    ```xml
    <Module Name="[Module Name]" Url="_catalogs/masterpage">
        <File Path="[Module Name]\[Master Page Name].master"
          Url="[Master Page Name].master" Type="GhostableInLibrary" />
    </Module>
    ```

     Para um tema, substitua a marcação de módulo existente pela marcação a seguir.

    ```xml
    <Module Name="[Module Name]" Url="_catalogs/theme"
        <File Path="[Module Name]\[Theme Name].thmx" Url="[Theme
          Name].thmx" Type="GhostableInLibrary" />
    </Module>
    ```

     Certifique-se de substituir os valores de espaço reservado pelos nomes reais do módulo e da página mestra ou tema.

     O atributo `Type="GhostableInLibrary"` indica que o item é adicionado ao banco de dados de conteúdo e o atributo `Url` do módulo especifica onde armazenar o arquivo no banco de dados de conteúdo do SharePoint.

11. Para alterar o escopo de implantação de uma página mestra, em **Gerenciador de soluções**, abra o arquivo de recurso no designer de recursos e, em seguida, escolha um novo escopo de implantação na lista **escopo** .

     Um valor de **Web** significa que a página mestra se aplica somente ao site especificado no momento no projeto. Um valor de **site** significa que a página mestra se aplica ao conjunto de sites atual, que inclui todos os subsites e a Web raiz. Os outros valores não se aplicam.

    > [!NOTE]
    > Como os temas se aplicam somente ao nível de conjunto de sites, recomendamos que você não defina o escopo de um tema para qualquer coisa que não seja o **site**. Poderão ocorrer erros se um tema for usado em um subsite.

12. Na barra de menus, escolha **compilar** > **implantar solução**.

13. Para verificar se os arquivos foram implantados corretamente, abra o site do SharePoint, escolha o menu **ações do site** , escolha o comando **configurações do site** e escolha o link **páginas mestras** ou o link **temas** .

     A lista de páginas mestras ou temas é exibida e contém a página mestra ou o tema que você importou.

## <a name="see-also"></a>Consulte também
- [Páginas mestras](/previous-versions/office/developer/sharepoint-2010/ms443795(v=office.14))
- [Importando itens de um site existente do SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)
- [Criar páginas para o SharePoint](../sharepoint/creating-pages-for-sharepoint.md)
- [Usar módulos para incluir arquivos na solução](../sharepoint/using-modules-to-include-files-in-the-solution.md)
