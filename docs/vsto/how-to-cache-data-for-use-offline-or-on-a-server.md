---
title: Como armazenar em cache dados para uso offline ou em um servidor
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data caching [Office development in Visual Studio], server use
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- offline data [Office development in Visual Studio]
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio], offline use
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 551d27cf8d40f2e6e9c996b031fa6c4e0a233355
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189569"
---
# <a name="how-to-cache-data-for-use-offline-or-on-a-server"></a>Como armazenar em cache dados para uso offline ou em um servidor
  Você pode marcar um item de dados para ser armazenado em cache no documento, para que ele esteja disponível offline. Isso também possibilita que os dados no documento sejam manipulados por outro código quando o documento é armazenado em um servidor.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Você pode marcar um item de dados a ser armazenado em cache quando o item de dados for declarado em seu código ou, se você estiver usando um <xref:System.Data.DataSet>, definindo uma propriedade na janela **Propriedades** . Se você estiver armazenando em cache um item de dados que não é um <xref:System.Data.DataSet> ou <xref:System.Data.DataTable>, verifique se ele atende aos critérios para serem armazenados em cache no documento. Para obter mais informações, consulte [armazenar dados em cache](../vsto/caching-data.md).

> [!NOTE]
> Conjuntos de dados criados usando Visual Basic que são marcados como **armazenados em cache** e **WithEvents** (incluindo conjuntos de dados que são arrastados da janela **Data Sources** ou da **caixa de ferramentas** que têm a propriedade **CacheInDocument** definida como **true** ) têm um sublinhado prefixado para seus nomes no cache. Por exemplo, se você criar um conjunto de um e nomeá-lo como **Customers**, o nome do <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> será **_Customers** no cache. Ao usar <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> para acessar esse item em cache, você deve especificar **_Customers** em vez de **clientes**.

### <a name="to-cache-data-in-the-document-using-code"></a>Para armazenar em cache dados no documento usando código

1. Declare um campo público ou uma propriedade para o item de dados como um membro de uma classe de item de host em seu projeto, como a classe `ThisDocumen`t em um projeto do Word ou a classe `ThisWorkbook` em um projeto do Excel.

2. Aplique o atributo <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> ao membro para marcar o item de dados a ser armazenado no cache de dados do documento. O exemplo a seguir aplica esse atributo a uma declaração de campo para uma <xref:System.Data.DataSet>.

     [!code-csharp[Trin_VstcoreDataExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#11)]
     [!code-vb[Trin_VstcoreDataExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#11)]

3. Adicione o código para criar uma instância do item de dados e, se aplicável, para carregá-lo a partir dele.

     O item de dados é carregado somente quando é criado pela primeira vez; Depois disso, o cache permanece com o documento e você deve escrever outro código para atualizá-lo.

### <a name="to-cache-a-dataset-in-the-document-by-using-the-properties-window"></a>Para armazenar em cache um conjunto de um DataSet no documento usando o janela Propriedades

1. Adicione o conjunto de dados ao projeto usando ferramentas no designer do Visual Studio, por exemplo, adicionando uma fonte de dado ao seu projeto usando a janela **fontes de dados** .

2. Crie uma instância do conjunto de um, se você ainda não tiver um, e selecione a instância no designer.

3. Na janela **Propriedades** , defina a propriedade **CacheInDocument** como **true**.

     Para obter mais informações, consulte [Propriedades em projetos do Office](../vsto/properties-in-office-projects.md).

4. Na janela **Propriedades** , defina a propriedade **modificadores** como **público** (por padrão, ela é **interna**).

## <a name="see-also"></a>Consulte também
- [Dados de cache](../vsto/caching-data.md)
- [Como: armazenar em cache uma fonte de dados programaticamente em um documento do Office](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)
- [Como armazenar dados em cache em um documento protegido por senha](../vsto/how-to-cache-data-in-a-password-protected-document.md)
- [Acessar dados em documentos no servidor](../vsto/accessing-data-in-documents-on-the-server.md)
- [Salvar dados](../data-tools/save-data-back-to-the-database.md)
