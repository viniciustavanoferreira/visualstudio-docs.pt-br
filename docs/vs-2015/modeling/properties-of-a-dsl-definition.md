---
title: Propriedades de uma definição de DSL | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
ms.assetid: 38debcfe-e1a6-4a3f-9d69-3ab07520f2b6
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8755b1b70051c54157fa87ee0b66dbc9340b5024
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668463"
---
# <a name="properties-of-a-dsl-definition"></a>Propriedades de uma definição de DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

As propriedades DslDefinition definem propriedades *de definição de linguagem específicas de domínio* , como numeração de versão. As propriedades DslDefinition aparecem na janela **Propriedades** quando você clica em uma área aberta do diagrama na *Designer de linguagem específica de domínio*.

 Para obter mais informações, consulte [como definir uma linguagem específica de domínio](../modeling/how-to-define-a-domain-specific-language.md). Para obter mais informações sobre como usar essas propriedades, consulte [Personalizando e estendendo uma linguagem específica de domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

 DslDefinition tem as propriedades na tabela a seguir:

|propriedade|Descrição|Padrão|
|--------------|-----------------|-------------|
|Modificador de acesso|Determina se o modificador de acesso para a classe de domínio é público ou interno.|públicos|
|Atributos personalizados|Atributos definidos personalizados para a classe de domínio.<br /><br /> **Observação** Use o botão procurar para adicionar um atributo.|\<nenhum>|
|Nome da empresa|O nome do nome da empresa atual no registro do sistema.|Nome da empresa atual|
|Name|O nome desta classe de domínio.|Nome atual|
|espaço de nome|O namespace afiliado a esta classe de domínio.|Namespace atual|
|GUID do pacote|O GUID para o pacote de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] gerado para essa DSL.|\<nenhum>|
|Namespace do pacote|O namespace para o pacote de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] gerado para essa DSL.|\<nenhum>|
|Nome do produto|O nome do produto que será registrado para o pacote de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] gerado para essa DSL.|\<nenhum>|
|Anotações|Observações associadas a esta classe de domínio.|\<nenhum>|
|Descrição|Descrição para esta classe de domínio.|\<nenhum>|
|Nome de Exibição|O nome que será exibido no designer gerado para essa classe de domínio.|\<nenhum>|
|Palavra-chave de ajuda|A palavra-chave Help associada a essa classe de domínio.|\<nenhum>|
|Build|O número de Build incremental para esta definição de linguagem específica de domínio.|0|
|Versão principal|O número de Build principal incremental para essa definição de linguagem específica de domínio.|1|
|Versão secundária|O número de Build secundário incremental para essa definição de linguagem específica de domínio.|0|
|Revisão|O número da versão da revisão incremental para essa definição de linguagem específica de domínio.|0|

## <a name="see-also"></a>Consulte também
 [Glossário das Ferramentas de Linguagem Específica de Domínio](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
