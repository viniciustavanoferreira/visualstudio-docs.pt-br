---
title: 'Soluções do SharePoint: Criar recursos personalizados, regras de validação de pacote'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a10118a0c83f9e17e32efd293a9a824e38a0942a
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2019
ms.locfileid: "66835932"
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>Como: Criar pacote e um recurso personalizado de regras de validação para soluções do SharePoint
  Você pode criar regras de validação personalizada para verificar se o pacote da solução gerado pelo Visual Studio. Você pode executar uma validação completa em um recurso inteiro ou um pacote, selecionando **Validate** no menu de contexto de um pacote ou recurso nas **PackagingExplorer**. Validação parcial é executada quando você adiciona novos itens de projeto do SharePoint ou recursos para o projeto para determinar se o pacote ou recurso seria em um estado válido.

### <a name="to-create-a-custom-package-validation-rule"></a>Para criar uma regra de validação de pacote personalizado

1. Crie um projeto de biblioteca de classes.

2. Adicione referências aos assemblies a seguir:

    - Microsoft.VisualStudio.SharePoint

    - System.ComponentModel.Composition

3. Crie uma classe que implementa uma das seguintes interfaces:

    - Para criar uma regra de validação de pacote, implemente o <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> interface.

    - Para criar uma regra de validação de recurso, implemente o <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> interface.

4. Adicionar o <xref:System.ComponentModel.Composition.ExportAttribute> à classe. Este atributo permite que o Visual Studio descobrir e carregar sua regra de validação. Passe o <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> ou <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> tipo para o construtor de atributo.

## <a name="example"></a>Exemplo
 O exemplo de código a seguir demonstra como criar uma regra de validação de recurso personalizada.

 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]

## <a name="compile-the-code"></a>Compilar o código
 Este exemplo requer referências aos assemblies a seguir:

- Microsoft.VisualStudio.SharePoint.

- System.ComponentModel.Composition.

## <a name="deploy-the-extension"></a>Implantar a extensão
 Para implantar a extensão, crie um [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] pacote de extensão (VSIX) para o assembly e outros arquivos que você deseja distribuir com a extensão. Para obter mais informações, consulte [das ferramentas de implantar extensões para o SharePoint no Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Consulte também
- [Estender o SharePoint empacotamento e implantação](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
