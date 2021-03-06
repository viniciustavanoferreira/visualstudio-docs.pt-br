---
title: 'Como: anexar extensões de código gerenciado a documentos'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], attaching
- documents [Office development in Visual Studio], managed code extensions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8fb212f9c5441d697cfa92feee7dc18fab9270d2
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985973"
---
# <a name="how-to-attach-managed-code-extensions-to-documents"></a>Como: anexar extensões de código gerenciado a documentos
  Você pode anexar um assembly de personalização a um documento existente do Microsoft Office Word ou Microsoft Office pasta de trabalho do Excel. O documento ou a pasta de trabalho pode estar em qualquer formato de arquivo com suporte na Microsoft Office projetos e ferramentas de desenvolvimento no Visual Studio. Para obter mais informações, consulte [arquitetura de personalizações em nível de documento](../vsto/architecture-of-document-level-customizations.md).

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Para anexar uma personalização a um documento do Word ou do Excel, use o método <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> da classe <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>. Como a classe <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> foi projetada para ser executada em um computador que não tem o Microsoft Office instalado, você pode usar esse método em soluções que não estão diretamente relacionadas ao desenvolvimento de Microsoft Office (como um aplicativo de console ou Windows Forms).

> [!NOTE]
> A personalização não será carregada se o código espera controles que o documento especificado não tem.

### <a name="to-attach-managed-code-extensions-to-a-document"></a>Para anexar extensões de código gerenciado a um documento

1. Em um projeto que não requer Microsoft Office, como um aplicativo de console ou Windows Forms projeto, adicione uma referência à *Microsoft. VisualStudio. Tools. Applications. ServerDocument. dll* e  *Assemblies Microsoft. VisualStudio. Tools. Applications. Runtime. dll* .

2. Adicione as seguintes **importações** ou instruções **using** à parte superior do seu arquivo de código.

     [!code-csharp[Trin_VstcoreDeployment#4](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#4)]
     [!code-vb[Trin_VstcoreDeployment#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#4)]

3. Chame o método de <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> estático.

     O exemplo de código a seguir usa a sobrecarga de <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A>. Essa sobrecarga usa o caminho completo do documento e um <xref:System.Uri> que especifica o local do manifesto de implantação para a personalização que você deseja anexar ao documento. Este exemplo pressupõe que um documento do Word chamado **WordDocument1. docx** esteja na área de trabalho e que o manifesto de implantação esteja localizado em uma pasta chamada **Publish** que também esteja na área de trabalho.

     [!code-csharp[Trin_VstcoreDeployment#3](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#3)]
     [!code-vb[Trin_VstcoreDeployment#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#3)]

4. Compile o projeto e execute o aplicativo no computador em que você deseja anexar a personalização. O computador deve ter o tempo de execução do Visual Studio 2010 Tools for Office instalado.

## <a name="see-also"></a>Consulte também
- [Gerenciar documentos em um servidor usando a classe ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [Como remover extensões de código gerenciado de documentos](../vsto/how-to-remove-managed-code-extensions-from-documents.md)
- [Manifestos de aplicativo e implantação em soluções do Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)
