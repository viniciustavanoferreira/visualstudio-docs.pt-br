---
title: Tornar membro estático
ms.date: 02/19/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 1ecc66cb58ad11bd431acb341dae0493ce8192da
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77515298"
---
# <a name="make-member-static"></a>Tornar membro estático

Esta refatoração aplica-se a:

- C#

**O que é isso?** Faça um membro estático.

**Quando:** Você quer que um membro não estático seja estático.

**Por que:** Membros estáticos melhoram a legibilidade: saber que o código específico é isolado facilita a compreensão, releitura e reutilização. 

## <a name="how-to"></a>Como fazer

1. Coloque seu cuidador no nome do membro.

2. Pressione **Ctrl**+**.** (período) para ativar o menu **Ações Rápidas e Refatorações.**

   ![Tornar membro estático](media/make-member-static.png)

3. Selecione **Tornar estático**.

## <a name="see-also"></a>Confira também

- [Refatoração](../refactoring-in-visual-studio.md)
