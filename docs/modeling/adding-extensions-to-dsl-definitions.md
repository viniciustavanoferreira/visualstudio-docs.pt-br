---
title: Adicionando extensões a definições de DSL
ms.date: 11/04/2016
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f3e44c79783479c46247e4026788725d6ae16da7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747651"
---
# <a name="add-extensions-to-dsl-definitions"></a>Adicionar extensões a definições de DSL

A extensão de definição de DSL permite que você crie um pacote de extensões para uma DSL (linguagem específica de domínio). A extensão de DSL, que está contida em uma extensão de integração do Visual Studio (VSIX), pode ser instalada no computador de um usuário da mesma maneira que uma DSL. Os recursos adicionais podem ser habilitados e desabilitados dinamicamente em tempo de execução. As DSLs não precisam ser explicitamente projetadas para extensão, e as extensões podem ser criadas posteriormente, ou por terceiros, sem alterar a DSL estendida.

As extensões de DSL podem incluir os seguintes recursos:

- Propriedades para elementos de modelo e apresentação

- Decoradores para formas e conectores

- Classes, relações, formas e conectores

- Restrições de validação

- Itens e guias da caixa de ferramentas

Um usuário de uma DSL estendida pode criar e salvar um modelo que contém instâncias dos recursos adicionais. O modelo pode ser lido por outros usuários que instalaram a extensão apropriada. Os usuários que não instalaram a extensão não podem usar os recursos adicionais, mas eles podem atualizar e salvar um modelo sem perder os recursos adicionais.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Consulte também

- [Postagens de blog relacionadas](https://devblogs.microsoft.com/devops/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/)
