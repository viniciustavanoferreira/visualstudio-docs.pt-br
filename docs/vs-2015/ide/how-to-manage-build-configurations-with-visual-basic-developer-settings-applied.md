---
title: Como gerenciar configurações de build com as configurações do Visual Basic Developer aplicadas | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, building with Visual Basic settings
- MSBuild, debug build
- advanced build configurations
- building with Visual Basic developer settings
- debug builds
- MSBuild, release build
- release builds
ms.assetid: eaea6e0b-6c61-4869-8d63-d372c745a23c
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a5f8568edc636955558ec93b55c0aedebf0065d3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651832"
---
# <a name="how-to-manage-build-configurations-with-visual-basic-developer-settings-applied"></a>Como gerenciar configurações de build com as configurações do Visual Basic Developer aplicadas
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Por padrão, todas as opções avançadas de configuração de build ficam ocultas com as configurações do [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Developer aplicadas. Este tópico explica como habilitar essas configurações manualmente.

## <a name="enabling-advanced-build-configurations"></a>Habilitando configurações de build avançadas
 Por padrão, as configurações do [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Developer ocultam a opção de abrir a caixa de diálogo do **Configuration Manager** e as listas **Configuração** e **Plataforma** no [Designer de Projeto](https://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7).

#### <a name="to-enable-advanced-build-configurations"></a>Para habilitar configurações de build avançadas

1. No menu **Ferramentas**, clique em **Opções**.

2. Expanda **Projetos e Soluções** e clique em **Geral**.

    > [!NOTE]
    > O nó **Geral** permanece visível mesmo que a opção **Mostrar todas as configurações** seja desmarcada. Se quiser ver todas as opções disponíveis, clique em **Mostrar todas as configurações**.

3. Clique em **Mostrar configurações avançadas de build**.

4. Clique em **OK**.

     No menu **Build**, **Configuration Manager** agora está disponível e as listas **Configuração** e **Plataforma** estão visíveis no Designer de Projeto.

## <a name="see-also"></a>Veja também
 [Compreendendo as configurações de compilação](../ide/understanding-build-configurations.md) [compilando e](../ide/compiling-and-building-in-visual-studio.md) compilando
