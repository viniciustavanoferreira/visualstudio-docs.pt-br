---
title: Folhas de estilos XSLT de edição
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 81bab324c58c06cc1ca553bae2f81faf474c4ad0
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75592835"
---
# <a name="edit-xslt-style-sheets"></a>Editar folhas de estilo XSLT

O editor de XML também pode ser usado para editar folhas de estilo XSLT. Você pode tirar proveito dos recursos do editor padrão como o IntelliSense, estruturação, snippets XML, e assim por diante. Além disso, há também os novos recursos que tornam ficar em XSLT.

## <a name="xslt-features"></a>Recursos de fonte

A tabela a seguir descreve os recursos específicos para trabalhar com folhas de estilos XSLT.

**Cor da sintaxe**

As palavras-chave XSLT, como `template` e `match`, são exibidas na cor da palavra-chave XSLT especificada pelas configurações de **fontes e cores** .

**Sublinhados ondulados**

O editor de XML usa o arquivo *XSLT. xsd* instalado para validar as folhas de estilo XSLT. Os erros de validação são mostrados como sublinhados ondulados azuis. O editor de XML também compila a folha de estilos em segundo plano e relata erros ou avisos do compilador com sublinhados ondulados apropriados.

**Suporte para blocos de script**

O código nos blocos de script é suportado pelo depurador XSLT para que você pode definir pontos de interrupção e percorrer o código de bloco de script.

**Exibir saída XSLT**

Você pode executar uma transformação XSL e exibir a saída do editor de XML. Para obter mais informações, consulte [como executar uma transformação XSLT no editor de XML](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md).

**Debug XSLT**

Você pode iniciar o depurador XSLT de um arquivo XSLT no editor de XML. O depurador oferece suporte pontos de interrupção no arquivo XSLT, estado de configuração de execução XSLT de exibição, e assim por diante. Passa sobre uma variável XSLT traz anterior um ToolTip com o valor da variável. O depurador pode ser usado para depurar uma folha de estilos, ou depurar uma transformação XSL compilado chamada de outro aplicativo. Para obter mais informações, consulte [DEBUGGING XSLT](../xml-tools/debugging-xslt.md).

## <a name="see-also"></a>Veja também

- [Editor de XML](../xml-tools/xml-editor.md)
