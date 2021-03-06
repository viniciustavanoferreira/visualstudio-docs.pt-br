---
title: '&lt;assembly&gt; elemento (implantação do ClickOnce) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce deployment manifest]
ms.assetid: b8e3362a-f821-4696-b98d-571d4bbfe431
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b639a7f95cfb59844fa37963730e22ead450482
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62929072"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;assembly&gt; elemento (implantação do ClickOnce)
O elemento de nível superior para o manifesto de implantação.

## <a name="syntax"></a>Sintaxe

```xml

      <assembly  
   manifestVersion
/>
```

## <a name="elements-and-attributes"></a>Elementos e atributos
 O `assembly` elemento é o elemento raiz e é necessário. O primeiro elemento independente deve ser um `assemblyIdentity` elemento. Os elementos do manifesto devem estar nos seguintes namespaces: `urn:schemas-microsoft-com:asm.v1`, `urn:schemas-microsoft-com:asm.v2`, e `http://www.w3.org/2000/09/xmldsig#`. Elementos filho do assembly também devem ser nesses namespaces, por herança ou marcação.

 O `assembly` elemento tem o seguinte atributo.

|Atributo|Descrição|
|---------------|-----------------|
|`manifestVersion`|Necessário. Esse atributo deve ser definido como `1.0`.|

## <a name="example"></a>Exemplo
 O exemplo de código a seguir ilustra uma `assembly` elemento em um manifesto de implantação para um aplicativo implantado usando [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Este exemplo de código é parte de um exemplo maior fornecido para o [manifesto de implantação do ClickOnce](../deployment/clickonce-deployment-manifest.md) tópico.

```xml
<asmv1:assembly
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"
  manifestVersion="1.0"
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"
  xmlns="urn:schemas-microsoft-com:asm.v2"
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
```

## <a name="see-also"></a>Consulte também
- [Manifesto de implantação do ClickOnce](../deployment/clickonce-deployment-manifest.md)
- [Elemento \<assembly>](../deployment/assembly-element-clickonce-application.md)