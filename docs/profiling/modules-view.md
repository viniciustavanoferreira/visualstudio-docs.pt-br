---
title: Exibição de Módulos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.view.modules
helpviewer_keywords:
- Modules view
- profiling tools reports, Modules view
- profiling tools, Modules view
ms.assetid: 4314a404-2120-425b-be42-180cd4bac840
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 89d9146b3f724b4883f21a43689a495eef252777
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778512"
---
# <a name="modules-view"></a>Exibição de módulos
A exibição de Módulos lista os módulos dos dados de criação de perfil. Cada módulo é o nó raiz de uma árvore hierárquica. As funções que tiveram o perfil criado do módulo são listadas abaixo do nó do módulo. Se os dados de criação de perfil foram coletados usando o método de amostragem, as informações de linha são listadas sob o nó de função e os dados de ponteiro de instrução são listados sob o nó de linha.

 Expandir ou recolher o nome do módulo para exibir ou fechar a exibição de dados de desempenho do módulo.

 Para adicionar ou remover colunas, clique com o botão direito do mouse na janela do relatório e, em seguida, **selecione Adicionar/Remover colunas**. Você pode classificar os dados em um nome de coluna. Para obter mais informações, [consulte Como: Personalizar colunas de exibição de relatórios](../profiling/how-to-customize-report-view-columns.md).

 As colunas que estão disponíveis na exibição de Módulos dependem do método de criação de perfil (amostragem ou instrumentação) usado para coletar os dados e se os dados de memória .NET foram coletados na execução da criação de perfil.

## <a name="see-also"></a>Confira também
- [Exibição Módulos](../profiling/modules-view-sampling-data.md)
- [Exibição Módulos](../profiling/modules-view-instrumentation-data.md)
- [Exibição Módulos – instrumentação](../profiling/modules-view-dotnet-memory-instrumentation-data.md)
- [Exibição de módulos - amostragem](../profiling/modules-view-dotnet-memory-sampling-data.md)
- [Exibição Módulos](../profiling/modules-view-contention-data.md)
