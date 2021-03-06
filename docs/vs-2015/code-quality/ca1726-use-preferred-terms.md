---
title: 'CA1726: usar os termos preferenciais | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 639a42e26442e31f7bbbbb2245af0289c6a04fd8
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75918224"
---
# <a name="ca1726-use-preferred-terms"></a>CA1726: usar termos preferenciais
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obter a documentação mais recente sobre o Visual Studio, consulte [CA1726: usar os termos preferenciais](/visualstudio/code-quality/ca1726-use-preferred-terms).

|||
|-|-|
|NomeDoTipo|UsePreferredTerms|
|CheckId|CA1726|
|Categoria|Microsoft.Naming|
|Alteração Significativa|Quebra-quando acionado em assemblies<br /><br /> Não separável-quando acionado em parâmetros de tipo|

## <a name="cause"></a>Causa
 O nome de um identificador visível externamente inclui um termo para o qual existe um termo preferido, alternativo. Como alternativa, o nome inclui o sinalizador de termo ou sinalizadores.

## <a name="rule-description"></a>Descrição da Regra
 Essa regra analisa um identificador em tokens. Cada único token e uma combinação de token duplo contígua é comparada com os termos criados na regra e na seção preterida de quaisquer dicionários personalizados. A tabela a seguir mostra os termos que são criados na regra e suas alternativas preferenciais.

|Termo obsoleto|Termo preferencial|
|-------------------|--------------------|
|`Arent`|`AreNot`|
|`Cancelled`|`Canceled`|
|`Cant`|`Cannot`|
|`ComPlus`|`EnterpriseServices`|
|`Couldnt`|`CouldNot`|
|`Didnt`|`DidNot`|
|`Doesnt`|`DoesNot`|
|`Dont`|`DoNot`|
|`Flag` ou `Flags`|Não há nenhum termo de substituição. Não use.|
|`Hadnt`|`HadNot`|
|`Hasnt`|`HasNot`|
|`Havent`|`HaveNot`|
|`Indices`|`Indexes`|
|`Isnt`|`IsNot`|
|`LogIn`|`LogOn`|
|`LogOut`|`LogOff`|
|`Shouldnt`|`ShouldNot`|
|`SignOn`|`SignIn`|
|`SignOff`|`SignOut`|
|`Wasnt`|`WasNot`|
|`Werent`|`WereNot`|
|`Wont`|`WillNot`|
|`Wouldnt`|`WouldNot`|
|`Writeable`|`Writable`|

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, substitua o termo pelo termo alternativo preferido.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Suprimir um aviso dessa regra somente se o nome do identificador for intencional e estiver relacionado especificamente ao termo original em vez do termo preferido.

## <a name="related-rules"></a>Regras relacionadas
 [Avisos de Nomenclatura](../code-quality/naming-warnings.md)
