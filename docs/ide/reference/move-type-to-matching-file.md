---
title: Mover um tipo para uma refatoração de arquivo correspondente
description: Mova o tipo para um arquivo separado com o mesmo nome. Clique com o botão direito do mouse no tipo, selecione Ações Rápidas e Refatorações e selecione Mover Tipo para <TypeName>.cs.
ms.date: 01/26/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: ba082e90c2447d1da7510ce16f888f67a52b5ac0
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75585265"
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>Refatoração Mover um tipo para um arquivo correspondente

Esta refatoração aplica-se a:

- C#

- Visual Basic

**O quê:** permite mover o tipo selecionado para um arquivo separado com o mesmo nome.

**Quando:** você tem várias classes, structs, interfaces, etc. no mesmo arquivo que deseja separar.

**Por quê:** colocar vários tipos no mesmo arquivo pode dificultar a localização desses tipos. Ao mover os tipos de arquivos com o mesmo nome, o código torna-se mais legível e mais fácil de navegar.

## <a name="how-to"></a>Como fazer

1. Coloque o cursor dentro do nome do tipo de onde ele está definido. Por exemplo: 

   ```csharp
   class Person
   ```

   ```vb
   Class Person
   ```

2. Depois, siga um destes procedimentos:

   - Pressione **Ctrl**+**.**
   - Clique com o botão direito do mouse sobre o nome do tipo e selecione **Ação Rápidas e Refatorações**

1. Selecione **Mover tipo para *NomeDoTipo*.cs** no menu, em que *NomeDoTipo* é o nome do tipo selecionado.

   O tipo é movido para um novo arquivo no projeto que possui o mesmo nome do tipo.

   - C#:

      ![Resultado embutido – C#](media/movetype-result-cs.png)

   - Visual Basic:

      ![Resultado embutido – Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>Confira também

- [Refatoração](../refactoring-in-visual-studio.md)
