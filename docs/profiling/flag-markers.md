---
title: Marcadores de sinalizador | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.markers.flag
ms.assetid: f3ec919e-63e5-484b-adbf-8f0e79342e75
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ccc0c7aa3386e906ad13331a596953db70240701
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "62969925"
---
# <a name="flag-markers"></a>Marcadores de sinalizador
Um marcador de sinalizador representa algo que ocorreu em um instante de tempo em um aplicativo. Um sinalizador pode representar muitos tipos de eventos de aplicativo. Por exemplo, um sinalizador pode mostrar quando um determinado item de trabalho foi agendado ou quando uma exceção foi lançada. Runtimes, como a Biblioteca de Paralelismo de Tarefas, também podem gerar sinalizadores.

## <a name="flag-importance"></a>Importância do sinalizador
 Sinalizadores são exibidos em tamanhos diferentes dependendo de sua importância. Como qualquer marcador, a importância pode ser baixa, normal, alta ou crítica.  Esta ilustração mostra a aparência dos marcadores segundo seu nível de importância:

 ![Marcadores de importância baixa, normal, alta e crítica](../profiling/media/cvmarkerimportance.png "CVMarkerImportance") Marcadores mostrando a importância da bandeira

## <a name="flag-category"></a>Categoria do sinalizador
 Um sinalizador pode ser exibido em cinco cores diferentes, dependendo de sua categoria. As cores são reutilizadas se houver mais de cinco categorias. Não é possível escolher a cor. Como qualquer marcador, a categoria pode ser qualquer inteiro. A ilustração a seguir mostra as cores das cinco primeiras categorias.

 ![Cinco cores de marcadores de categoria](../profiling/media/cvmarkercategory.png "CVMarkerCategoria") Marcadores mostrando categorias

## <a name="alerts"></a>Alertas
 Um alerta é um sinalizador vermelho que representa um evento crítico do aplicativo, como uma exceção.  Este é um alerta:

 ![O marcador de alerta do visualizador de caixa de concorrência](../profiling/media/cvmarkeralert.png "CVMarkerAlert") Um marcador de alerta

## <a name="aggregation-flags"></a>Sinalizadores de agregação
 Às vezes, os sinalizadores ocorrem tão próximos uns dos outros na Visualização Simultânea que não podem ser desenhados individualmente. Quando isso ocorre, um *sinalizador agregação* cinza, que representa os sinalizadores subjacentes, é exibido. Quando você posiciona o ponteiro em desses ícones, uma dica de ferramenta exibe o número de sinalizadores subjacentes representados. Para exibir os sinalizadores, amplie. Se ampliar completamente e ainda obtiver um sinalizador de agregação, você pode exibir os sinalizadores subjacentes no [Relatório de marcadores](../profiling/markers-report.md).

 Sinalizadores de agregação são desenhados em tamanhos diferentes. O tamanho depende do nível de importância do sinalizador mais importante da agregação. A ilustração a seguir mostra sinalizadores de agregação em ordem crescente de importância.

 ![Bandeiras agregadas mostrando quatro níveis de importância](../profiling/media/cvmarkeraggregate.png "AGREGADO CVMarker") Bandeiras de agregação por nível de importância

## <a name="see-also"></a>Confira também
- [Marcadores da Visualização Simultânea](../profiling/concurrency-visualizer-markers.md)
- [SDK da Visualização Simultânea](../profiling/concurrency-visualizer-sdk.md)