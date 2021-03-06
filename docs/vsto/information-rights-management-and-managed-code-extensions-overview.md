---
title: Gerenciamento de direitos de informação & extensões de código gerenciado
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Information Rights Management [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- IRM [Office development in Visual Studio]
- documents [Office development in Visual Studio], restricted permissions
- rights management [Office development in Visual Studio]
- Office documents [Office development in Visual Studio, restricted permissions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 753f3d2da201c67cd86c697eccf7580596a40d6e
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68872059"
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>Visão geral do gerenciamento de direitos de informação e extensões de código gerenciado
  Microsoft Office Word e Microsoft Office Excel fornecem informações Rights Management (IRM), um recurso que pode ajudá-lo a impedir que pessoas não autorizadas exibam ou alterem informações confidenciais. Para obter detalhes sobre como as informações Rights Management funcionam, consulte a ajuda no aplicativo específico do Office.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="run-code-behind-documents-with-restricted-permissions"></a>Executar code-behind de documentos com permissões restritas
 Se sua solução contiver um documento ou pasta de trabalho que usa o IRM, por padrão, o Word e o Excel não permitirão a execução de qualquer código. Se você for o autor do documento ou tiver acesso de controle total, poderá alterar o padrão para que sua solução funcione. Para obter mais informações, confira [Como: Permitir que o código execute por trás de documentos](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)com permissões restritas.

 O IRM impede o <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> uso do para recuperar ou manipular dados armazenados em cache no documento.

## <a name="end-users-to-restrict-permissions-to-documents-that-use-managed-code-extensions"></a>Usuários finais para restringir permissões a documentos que usam extensões de código gerenciado
 Qualquer pessoa que tenha acesso de controle total ao documento ou pasta de trabalho em sua solução pode usar o IRM para restringir permissões. Por exemplo, se um usuário final no departamento de contabilidade usar uma solução que preenche automaticamente uma planilha com dados de um banco de dado, esse usuário poderá querer permitir acesso de alteração somente a pessoas em seu departamento e acesso de leitura a outras pessoas. Quando o usuário adiciona as permissões restritas, por padrão, o código por trás da planilha não pode ser executado e a planilha não será preenchida com dados.

 Para corrigir o problema, alguém com acesso de controle total ao documento ou pasta de trabalho deve alterar as configurações de permissão padrão para permitir o acesso programático ao modelo de objeto. Para obter mais informações, confira [Como: Permitir que o código execute por trás de documentos](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)com permissões restritas.

## <a name="see-also"></a>Consulte também
- [Proteção de documentos em soluções de nível de documento](../vsto/document-protection-in-document-level-solutions.md)
- [Proteção por senha em documentos do Office](../vsto/password-protection-on-office-documents.md)
- [Proteger soluções do Office](../vsto/securing-office-solutions.md)
- [Implantar uma solução do Office](../vsto/deploying-an-office-solution.md)
- [Projetar e criar soluções do Office](../vsto/designing-and-creating-office-solutions.md)
