---
title: Elemento ProjectItemFile | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFile element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 57c491c79030eea1a01024235c01aec425d5994c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62562356"
---
# <a name="projectitemfile-element"></a>Elemento ProjectItemFile
  Representa um arquivo do SharePoint, como o arquivo de elemento de recurso, para incluir com o item de projeto quando ele é implantado no SharePoint.

## <a name="syntax"></a>Sintaxe

```xml
<ProjectItemFile Source = "Name of the file"
    Target = "Deployment path of the file"
    Type = "Type of deployment for the file" />
```

## <a name="type"></a>Tipo
 **ProjectItemFileType**

## <a name="attributes-and-elements"></a>Atributos e elementos
 As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos

|Atributo|Descrição|
|---------------|-----------------|
|**Source**|Exigido **xs: string** atributo.<br /><br /> O nome do arquivo para implantar com o item de projeto.|
|**Target**|Opcional **xs: string** atributo.<br /><br /> O caminho onde o arquivo será implantado no SharePoint, em relação à pasta raiz de implantação. Pasta raiz de implantação é determinada pelo tipo de implantação especificado pelo **tipo** atributo. Se o **alvo** atributo não for especificado, o arquivo será implantado em uma pasta com o nome especificado na **origem** atributo.<br /><br /> Para obter mais informações, consulte as descrições para o **caminho de implantação** e **raiz da implantação** propriedades do SharePoint itens de projeto do [SharePoint desenvolver soluções](../sharepoint/developing-sharepoint-solutions.md).|
|**Tipo**|Exigido **xs: string** atributo.<br /><br /> O tipo de implantação para o arquivo. Para obter mais informações sobre os valores possíveis, consulte a descrição para o **tipo de implantação** propriedade de itens de projeto do SharePoint no [soluções do SharePoint desenvolver](../sharepoint/developing-sharepoint-solutions.md).|

### <a name="child-elements"></a>Elementos filho
 nenhuma.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Arquivos](../sharepoint/files-element.md)|Especifica os arquivos a serem incluídos com o item de projeto do SharePoint quando ele é implantado no SharePoint.|

## <a name="remarks"></a>Comentários
 Arquivos do SharePoint que normalmente são referenciados na **ProjectItemFile** elementos incluem arquivos de elemento de recurso (*Elements. XML*), arquivos de esquema para definições de lista (*Schema. XML*) e os arquivos de definição de Web Part de Web Parts (*WebPart*).

## <a name="element-information"></a>Informações sobre o elemento

|||
|-|-|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Nome do esquema**|Esquema de Item de projeto do SharePoint|
|**Arquivo de validação**|ProjectItemModelSchema.xsd|
|**Pode estar vazio**|Não|

## <a name="see-also"></a>Consulte também
- [Referência de esquema de item de projeto do SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
