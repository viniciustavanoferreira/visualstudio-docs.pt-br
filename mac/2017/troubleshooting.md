---
title: Solucionar problemas
description: Problemas comuns e resoluções para usuários do Visual Studio para Mac.
ms.topic: troubleshooting
author: heiligerdankgesang
ms.author: dominicn
ms.date: 05/06/2018
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.openlocfilehash: 6073e0bf2a601bf5183798a1df4fd835d0b93427
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2020
ms.locfileid: "74985155"
---
# <a name="troubleshooting"></a>Solução de problemas

## <a name="viewing-logs-in-visual-studio-for-mac"></a>Exibindo logs no Visual Studio para Mac

Os logs podem ser encontrados navegando para o item de menu **Ajuda > abrir Diretório de Log**, conforme ilustrado abaixo:

![Item de menu Abrir diretório de logs](media/troubleshooting-image1.png)

## <a name="viewing-exceptions"></a>Visualizando exceções

Quando uma exceção é detectada, uma bolha de exceção é exibida. Para exibir mais detalhes, selecione o botão **Exibir detalhes**:

![Exibir mais detalhes sobre uma exceção](media/troubleshooting-image2.png)

Isso exibe a caixa de diálogo **Mostrar Detalhes**, fornecendo mais informações sobre a exceção:

![Mostrar a caixa de diálogo de detalhes](media/troubleshooting-image3.png)

Seções importantes da caixa de diálogo, numeradas acima, são descritas em detalhes a seguir:

1. O tipo de exceção, que mostra o nome completo do tipo de exceção que está sendo observado.
2. A mensagem de exceção, que mostra o valor da propriedade Message do objeto de exceção.
3. O tipo de exceção interna, que mostra o nome completo do tipo de exceção para a exceção selecionada no momento no modo de exibição de árvore de Exceção interna.
4. A mensagem da Exceção interna, que mostra o valor da propriedade Message da exceção selecionada no modo de exibição de árvore Exceção interna.
5. Exibição de rastreamento de pilha. Pode ser recolhida por meio de uma seta de divulgação de informações e contém entradas de registros de ativação.
6. Exemplo de entradas de código que não são do usuário.
7. Exemplo de entradas de código do usuário.
8. Exibição Propriedades, que mostra todas as propriedades e campos da exceção. Pode ser recolhida por meio de uma seta de divulgação.
9. Modo de exibição de árvore de Exceção interna. Selecione as exceções internas nesta exibição usando as teclas para cima/para baixo do tecla, com o mouse ou com o trackpad.
10. Por padrão, isso é definido para o mesmo que a opção **Depurar somente o código do projeto** nas configurações do depurador. Marcar essa caixa permitirá que todo o código que não é do usuário seja recolhido em uma linha no rastreamento de pilha.
11. Um botão Copiar para copiar a saída de `exception.ToString()` para a área de transferência.

Observe que algumas dessas seções só ficam visíveis quando a exceção tem uma exceção interna.

## <a name="see-also"></a>Confira também

- [Recursos para solução de problemas de erros do IDE (Visual Studio no Windows)](/visualstudio/ide/reference/resources-for-troubleshooting-integrated-development-environment-errors)