---
title: Desabilitar análise de código herdado
ms.date: 10/04/2019
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 42d981505817a4de72ed60b896742d4551ca0ee4
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75587492"
---
# <a name="how-to-enable-and-disable-binary-code-analysis-for-managed-code"></a>Como habilitar e desabilitar a análise de código binário para código gerenciado

Você pode configurar a análise de código herdado (análise binária) para ser executada após cada compilação de um projeto de código gerenciado. Você também pode ter configurações diferentes para cada configuração de compilação, por exemplo, Debug e Release.

> [!NOTE]
> A análise herdada não está disponível para tipos de projeto mais novos, como .NET Core e .NET Standard aplicativos. Esses projetos usam [analisadores de código baseados em .net Compiler Platform](roslyn-analyzers-overview.md) para analisar o código, tanto ao vivo quanto ao tempo de compilação. Para obter informações sobre como desabilitar a análise de código-fonte nesses projetos, consulte [como desabilitar a análise de código-fonte](disable-code-analysis.md).

Para habilitar ou desabilitar a análise de código herdado:

1. Em **Gerenciador de soluções**, clique com o botão direito do mouse no projeto e escolha **Propriedades**.

2. Na caixa de diálogo Propriedades do projeto, escolha a guia **análise de código** .

3. Especifique o tipo de compilação na **configuração** e a plataforma de destino na **plataforma**. (Somente projetos padrão Non-.NET Core/. NET.)

::: moniker range="vs-2017"

4. Para habilitar ou desabilitar a análise automática de código, marque ou desmarque a caixa de seleção **Habilitar análise de código na compilação** .

::: moniker-end

::: moniker range=">=vs-2019"

4. Para habilitar ou desabilitar a análise automática de código, marque ou desmarque a caixa de seleção **executar na compilação** na seção **analisadores binários** .

   ![Executar análise de código binário na opção de compilação no Visual Studio](media/run-on-build-binary-analyzers.png)

::: moniker-end

> [!NOTE]
> Desabilitar a análise de código binário na compilação não afeta os [analisadores de código baseados em .net Compiler Platform](roslyn-analyzers-overview.md), que sempre são executados no Build se você os instalou como um pacote NuGet. Para obter informações sobre como desabilitar a análise desses analisadores, consulte [como desabilitar a análise de código-fonte](disable-code-analysis.md).
