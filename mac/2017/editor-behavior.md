---
title: Formatação de código
description: Este artigo descreve as diferentes opções que podem ser usadas para modificar o comportamento do editor de texto no Visual Studio para Mac
author: heiligerdankgesang
ms.author: dominicn
ms.date: 05/06/2018
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: dca21119a73c03b63a273f7b4c22d70ecdb2a583
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "74984677"
---
# <a name="editor-behavior"></a>Comportamento do Editor

Comportamentos do editor podem ser definidos para permitir que o código seja formatado à medida que ele é escrito. Essas ações são definidas em **Visual Studio > Preferências > Editor de Texto > Comportamento**. Veja algumas das funções mais usadas descritas abaixo:

![Opções de Comportamento do Editor](media/source-editor-image9.png)

* Chaves de fechamento podem ser adicionadas automaticamente ao código ao criar novas classes, métodos ou propriedades. Quando essa opção é selecionada, digitar `{` adicionará `}` automaticamente.
* A formatação de código em tempo real é disparada por pressionamentos de caracteres, como ponto e vírgula ou chaves, que emularão as preferências de formatação definidas.
* Também é possível formatar o arquivo ao salvá-lo, o que permite escrever código o código conforme desejado e deixar o IDE responsável pela formatação do código conforme definido pelas preferências existentes.
* O recuo pode ser definido para Nenhum, Automático ou Inteligente. Essas opções representam o seguinte:
  * Nenhum – define o cursor para o início da próxima linha
  * Automático– define o cursor para a mesma coluna na próxima linha
  * Inteligente – recua a próxima linha com base no código
* O comportamento de quebra de palavras é diferente entre os sistemas operacionais e, para fins de navegação, o editor de texto precisa saber onde as palavras começam e terminam. A formatação pode ser definida para Unix ou do Windows.

Também é possível definir regras de formatação para XML, CSS, HTML e JSON.

## <a name="see-also"></a>Confira também

- [Preferências de estilo de código (Visual Studio no Windows)](/visualstudio/ide/code-styles-and-quick-actions)
