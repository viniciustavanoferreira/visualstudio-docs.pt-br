---
title: WinCounter | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 9455d596e27526f6075ad3b667ac441b12511d58
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779838"
---
# <a name="wincounter"></a>WinCounter
A opção **WinCounter** especifica um contador de desempenho do aplicativo ou do Windows para coletar em intervalos definidos durante o perfil de execução. Os contadores de desempenho do aplicativo e do Windows são listados como marcas no arquivo de dados de criação de perfil. Você pode especificar vários contadores de desempenho para coletar em opções separadas.

 Por padrão, os contadores são coletados a cada 500 milissegundos. Use a opção **AutoMark** para especificar um intervalo diferente de coleção.

 Apenas uma opção **AutoMark** é usada. Se várias opções **AutoMark** forem especificadas, a última será usada.

 A opção **WinCounter** só pode ser usada com a opção **Iniciar**.

## <a name="syntax"></a>Sintaxe

```cmd
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]
```

#### <a name="parameters"></a>parâmetros
 `Path` O contador de desempenho do Windows no formato de caminho de contador PDH.

## <a name="required-options"></a>Opções obrigatórias
 A opção **WinCounter** só pode ser usada com a opção **Iniciar**.

 **Iniciar:** `Method` A opção **Iniciar** inicializa o profiler para o método de criação de perfil especificado.

## <a name="exclusive-options"></a>Opções exclusivas
 A opção **AutoMark** só pode ser usada com a opção **WinCounter**.

 **Marca automática:** `Milliseconds` Especifica o número de milissegundos entre a coleta de dados do contador de desempenho do Windows.

## <a name="example"></a>Exemplo
 No exemplo a seguir, dois contadores de desempenho do Windows são especificados para serem coletados em um intervalo de 1000 milissegundos.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000
```

## <a name="see-also"></a>Confira também
- [Vsperfcmd](../profiling/vsperfcmd.md)
- [Aplicativos Autônomos de Perfil](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Criar o perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profile services (Serviços de perfil)](../profiling/command-line-profiling-of-services.md)
