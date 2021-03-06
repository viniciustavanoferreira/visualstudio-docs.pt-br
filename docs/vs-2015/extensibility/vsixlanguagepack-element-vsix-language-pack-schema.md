---
title: Elemento VSIXLanguagePack (esquema do pacote de idiomas do VSIX) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e2e1df362fddeab5be98ff90460a8a1a7d4b7876
ms.sourcegitcommit: bf2e9d4ff38bf5b62b8af3da1e6a183beb899809
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2020
ms.locfileid: "77557994"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>Elemento VSIXLanguagePack (esquema do pacote de idiomas do VSIX)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Necessário. Fornece o elemento raiz para um pacote de idiomas do VSIX. O pacote de idiomas do VSIX fornece informações de instalação localizadas para um pacote VSIX.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIÇÃO|  
|---------------|-----------------|  
|`xmlns`|O namespace XML no qual o esquema do pacote de idiomas do VSIX está definido.|  
  
## <a name="xmlns-attribute"></a>Atributo xmlns  
  
|Valor|DESCRIÇÃO|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|Necessário. O local do arquivo que define o esquema para pacotes de idiomas.|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|DESCRIÇÃO|  
|-------------|-----------------|  
|[Elemento LocalizedName](../extensibility/localizedname-element-vsix-language-pack-schema.md)|Necessário. O nome localizado da extensão a ser instalada.|  
|[Elemento LocalizedDescription](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|Necessário. A descrição localizada da extensão a ser instalada.|  
|[Elemento MoreInfoURL](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|Opcional. Um link para informações localizadas sobre a extensão.|  
|[Elemento License](../extensibility/license-element-vsix-language-pack-schema.md)|Opcional. O caminho de uma versão localizada do arquivo de licença para a extensão.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|DESCRIÇÃO|  
|-------------|-----------------|  
|Nenhum||  
  
## <a name="element-information"></a>Informações do elemento  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    espaço de nome    | `http://schemas.microsoft.com/developer/vsx-schema-lp/2010` |
|   Nome do Esquema   |                 Esquema do pacote de idiomas do VSIX                 |
| Arquivo de validação |                VSIXLanguagePackSchema.xsd                 |
|  Pode estar vazio   |                            Não                             |
  
## <a name="see-also"></a>Veja também  
 [Referência de esquema do pacote de idiomas do VSX](../extensibility/vsx-language-pack-schema-reference.md) [localizando pacotes VSIX](../extensibility/localizing-vsix-packages.md) [esquema de extensão do VSIX referência de 1,0](/previous-versions/dd393700(v=vs.110))
