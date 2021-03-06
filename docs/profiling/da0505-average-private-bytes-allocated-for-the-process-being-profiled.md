---
title: 'DA0505: média de bytes privados alocados para o processo do qual o perfil está sendo criado | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0505
- vs.performance.rules.DA0505
- vs.performance.505
ms.assetid: 32c612ea-d077-44ba-8e6f-3a96333bad00
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: b905b0de69110f5f7cd684deb6fe6c5955bb4b0c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74777397"
---
# <a name="da0505-average-private-bytes-allocated-for-the-process-being-profiled"></a>DA0505: média de bytes particulares alocados para o processo com criação de perfil

|||
|-|-|
|ID de regra|DA0505|
|Categoria|Gerenciamento de recursos|
|Método de criação de perfil|Todos|
|Mensagem|Essas informações foram coletadas apenas para fins informativos. O contador Bytes privados do processo mede a memória virtual alocada pelo processo do qual o perfil está sendo criado. O valor relatado é a média calculada de todos os intervalos de medição.|
|Tipo de regra|Informações|

 Ao criar o perfil usando a amostragem, a memória do .NET ou métodos de contenção de recursos, é necessário coletar pelo menos 10 amostras para disparar essa regra.

## <a name="rule-description"></a>Descrição da regra
 Essa mensagem relata a quantidade média de memória virtual que o processo alocou em bytes (Bytes privados). Os bytes privados representam os locais de memória virtual que foram alocados pelo processo que podem ser acessados somente por threads em execução no processo.

 Para processos de 32 bits em execução em um computador de 32 bits, o limite superior da parte privada do espaço de endereço do processo é de 2 GB. Ao usar a opção [/3GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) Boot.ini, os processos de 32 bits podem adquirir até 3 GB de memória virtual. Um processo de 32 bits em execução em um computador de 64 bits pode adquirir até 4 GB de memória virtual privada.

 Um processo de 64 bits em execução em um computador de 64 bits pode adquirir até 8 TB de memória virtual privada.

 O valor relatado é a média de todos os intervalos de medição em que o processo do qual o perfil está sendo criado estava ativo.

 Para obter mais informações sobre espaços de endereço do processo, consulte [Espaço de endereço virtual](/windows/win32/memory/virtual-address-space) na documentação do Gerenciamento de memória do Windows.

## <a name="how-to-use-rule-data"></a>Como usar dados de regra
 Use o valor relatado para comparar o desempenho de diferentes versões ou compilações do programa ou para entender o desempenho do aplicativo em diferentes cenários de criação de perfil.
