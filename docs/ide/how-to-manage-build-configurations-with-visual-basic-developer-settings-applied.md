---
title: Gerenciar configurações de build com as definições do desenvolvedor do Visual Basic
ms.date: 11/21/2018
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- advanced build configurations
- building with Visual Basic developer settings (Visual Studio)
- debug builds
- release builds
ms.assetid: eaea6e0b-6c61-4869-8d63-d372c745a23c
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5243223e554f8e31fe2ffa9d667c09d0a3e1dbc0
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "76115150"
---
# <a name="how-to-manage-build-configurations-with-visual-basic-developer-settings-applied"></a>Como gerenciar configurações de build com configurações de desenvolvedor do Visual Basic aplicadas

Por padrão, todas as opções avançadas de configuração de build ficam ocultas quando as configurações do desenvolvedor do Visual Basic são aplicadas. Este artigo explica como habilitar manualmente essas configurações de build.

## <a name="enable-advanced-build-configurations"></a>Habilitar configurações de build avançadas

Por padrão, as configurações de desenvolvedor do Visual Basic ocultam a opção de abrir a caixa de diálogo **Configuration Manager** e as listas **Configuração** e **Plataforma** no [Designer de Projeto](../ide/reference/application-page-project-designer-visual-basic.md).

1. No menu **Ferramentas** , clique em **Opções**.

2. Expanda **Projetos e Soluções** e clique em **Geral**.

    > [!NOTE]
    > O nó **Geral** permanece visível mesmo que a opção **Mostrar todas as configurações** seja desmarcada. Se quiser ver todas as opções disponíveis, clique em **Mostrar todas as configurações**.

3. Clique em **Mostrar configurações avançadas de build**.

4. Clique em **OK**.

     O **Configuration Manager** agora está disponível no menu **Build** e as listas **Configuração** e **Plataforma** estão visíveis no **Designer de Projeto**.

## <a name="see-also"></a>Confira também

- [Compreender configurações de build](../ide/understanding-build-configurations.md)
- [Compilação e construção](../ide/compiling-and-building-in-visual-studio.md)
- [Configurações do ambiente](../ide/environment-settings.md)
