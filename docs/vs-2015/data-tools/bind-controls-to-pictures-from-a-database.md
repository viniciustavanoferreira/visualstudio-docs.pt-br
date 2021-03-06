---
title: Associar controles a imagens de um banco de dados | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0b8f6ee192399c8af8a508b2f9c2817db954bb36
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72673010"
---
# <a name="bind-controls-to-pictures-from-a-database"></a>Associar controles a imagens de um banco de dados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode usar a janela **Data Sources** para associar uma imagem em um banco de dados a um controle em seu aplicativo. Por exemplo, você pode associar uma imagem a um controle de <xref:System.Windows.Controls.Image> em um aplicativo WPF ou a um controle de <xref:System.Windows.Forms.PictureBox> em um aplicativo Windows Forms.

 As imagens em um banco de dados normalmente são armazenadas como matrizes de bytes. Os itens na janela **fontes de dados** que são armazenados como matrizes de bytes têm seu tipo de controle definido como **nenhum** por padrão, pois as matrizes de bytes podem conter qualquer coisa de uma matriz simples de bytes para o arquivo executável de um aplicativo grande. Para criar um controle de associação de dados para um item de matriz de bytes na janela **fontes de dados** que representa uma imagem, você deve selecionar o controle a ser criado.

 O procedimento a seguir pressupõe que a janela de **fontes de dados** já esteja preenchida com um item associado à sua imagem.

## <a name="bind-a-picture-in-a-database-to-a-control"></a>Associar uma imagem em um banco de dados a um controle

1. Verifique se a superfície de design à qual você deseja adicionar o controle está aberta no designer do WPF ou na Designer de Formulários do Windows.

2. Na janela **fontes de dados** , expanda a tabela ou o objeto desejado para exibir suas colunas ou propriedades.

3. Selecione a coluna ou propriedade que contém os dados da imagem e selecione um dos seguintes controles na lista suspensa controle:

    - Se o designer do WPF estiver aberto, selecione **imagem**.

    - Se o designer de Windows Forms estiver aberto, selecione **PictureBox**.

    - Como alternativa, você pode selecionar um controle diferente que dá suporte à vinculação de dados e que pode exibir imagens. Se o controle que você deseja usar não estiver na lista de controles disponíveis, você poderá adicioná-lo à lista e, em seguida, selecioná-lo. Para obter mais informações, consulte [Adicionar controles personalizados à janela fontes de dados](../data-tools/add-custom-controls-to-the-data-sources-window.md).

## <a name="see-also"></a>Consulte também
 [Associar controles WPF a dados no Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)
