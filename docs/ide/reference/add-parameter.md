---
title: Adicionar parâmetro a uma ação rápida de método
ms.date: 09/28/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 6720421fd5188688214665d85de682542b1c1357
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75595859"
---
# <a name="add-a-parameter-to-a-method-using-a-quick-action"></a>Adicionar um parâmetro a um método usando uma Ação Rápida

Esta geração de código aplica-se a:

- C#

- Visual Basic

**O que:** permite adicionar automaticamente um parâmetro a um método com base no uso.

**Quando:** você precisa adicionar um parâmetro a um método e deseja declará-lo automaticamente.

**Motivo:** você poderia adicionar o parâmetro para a declaração do método antes de chamá-lo, no entanto, esse recurso adiciona o parâmetro automaticamente com base na chamada de método.

## <a name="how-to-use-it"></a>Como usar

1. Adicione um argumento extra a uma chamada de método.

   Um rabisco vermelho aparece o nome do método onde você o chama.

2. Coloque o ponteiro sobre o rabisque vermelho até que o menu Ações rápidas apareça. Selecione a **seta para baixo** no menu Ações Rápidas e, em seguida, selecione **Adicionar parâmetro ao [método]**.

   ![Adicionar parâmetro a ação rápida de método no Visual Studio](media/add-parameter-to-method.png)

   > [!TIP]
   > Você também pode acessar o menu Ações Rápidas colocando o cursor na linha da chamada do método e, em seguida, pressionando **Ctrl**+**.** (período) ou selecionar o ícone da lâmpada na margem do arquivo.

   O Visual Studio adiciona o novo parâmetro à declaração de método.

> [!NOTE]
> Se você tiver outras chamadas para o método, elas podem produzir erros depois de usar essa Ação Rápida porque não especificam um argumento para o parâmetro recém-adicionado.

## <a name="see-also"></a>Confira também

- [Adicionar parâmetro ao construtor](generate-constructor.md#addparameter)
