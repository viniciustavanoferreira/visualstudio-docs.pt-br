---
title: VSTextBuffer Object | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a5ea44d2b22c96d49f334f2ea33f9db8d69b5eb0
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80697718"
---
# <a name="vstextbuffer-object"></a>Objeto VSTextBuffer
O objeto buffer de texto representa um fluxo de texto Unicode, que geralmente está associado a um arquivo. Um <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objeto pode ser usado fora do contexto do editor principal, como em, um assistente.

 A tabela a seguir `VSTextBuffer`mostra as interfaces de .

|Método|Descrição|
|------------|-----------------|
|[IOleCommandTarget](/windows/desktop/api/docobj/nn-docobj-iolecommandtarget)|Interface OLE padrão. Usado para desfazer/refazer o manuseio no buffer.|
|[Ipersistfile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Interface OLE padrão.|
|[Ipersiststream](/windows/desktop/api/objidl/nn-objidl-ipersiststream)|Interface OLE padrão.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Permite a criação de ações compostas (ou seja, ações agrupadas em uma única unidade de desfazer/refazer).|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Permite a persistência de dados de documentos gerenciados pelo buffer de texto.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Presta serviços básicos; usado por muitos clientes.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Usado para procurar um buffer.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Fornece recursos de leitura e gravação usando coordenadas bidimensionais. Herdada de `IVsTextBuffer`.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Fornece recursos de leitura e gravação usando coordenadas unidimensionais. Herdada de `IVsTextBuffer`.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Fornece acesso rápido, orientado a fluxo e seqüencial ao texto no buffer.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Fornece acesso a uma coleção genérica de propriedades. A propriedade mais importante é o nome, ou apelido, do buffer. Você pode armazenar seus próprios dados aleatórios no buffer com esta interface criando um GUID e usando-os como uma chave.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Suporta pontos de conexão para eventos.|

## <a name="remarks"></a>Comentários
 O `VSTextBuffer` é geralmente `QueryInterface` encontrado `IVsTextBuffer`por uma chamada em . Para obter mais informações, consulte [Buffer de texto](/visualstudio/extensibility/accessing-the-text-buffer-by-using-the-legacy-api?view=vs-2015).

## <a name="see-also"></a>Confira também
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>
- <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>
- [Edição de figuras](https://www.microsoft.com/download/details.aspx?id=55984)
