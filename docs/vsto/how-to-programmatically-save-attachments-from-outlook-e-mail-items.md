---
title: Salvar anexos de itens de email do Outlook programaticamente
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- saving e-mail attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e7e0cff4761b26bac8265592b681d4e56f2ad92f
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2019
ms.locfileid: "67328957"
---
# <a name="how-to-programmatically-save-attachments-from-outlook-email-items"></a>Como: Salvar anexos de itens de email do Outlook de forma programática

Este exemplo salva anexos de email para uma pasta especificada quando o email é recebido na caixa de entrada.

> [!IMPORTANT]
> Este exemplo só funcionará se você adicionar uma pasta chamada **TestFileSave** na raiz do diretório C.

[!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Exemplo

[!code-csharp[Trin_OL_SaveAttachments#1](../vsto/codesnippet/CSharp/Trin_OL_SaveAttachments/thisaddin.cs#1)]

## <a name="see-also"></a>Consulte também

- [Trabalhar com itens de email](../vsto/working-with-mail-items.md)
- [Como: Recuperar uma pasta por nome de forma programática](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [Como: Executar ações programaticamente quando uma mensagem de email é recebida](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
- [Como: Pesquisar em uma pasta específica de forma programática](../vsto/how-to-programmatically-search-within-a-specific-folder.md)
