---
title: CrossSession | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 06de982643a08e1af88073dde0fb0a9abc029900
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779448"
---
# <a name="crosssession"></a>CrossSession
A opção *VSPerfCmd.exe* **CrossSession** permite que o criador de perfil colete dados de qualquer sessão de console. A opção **CrossSession** deve ser usada com a opção **Iniciar**.

 Você pode usar a abreviação **CS** no lugar de **CrossSession**.

## <a name="syntax"></a>Sintaxe

```cmd
VSPerfCmd.exe /Start:Method /CrossSession [Options]
```

#### <a name="parameters"></a>parâmetros
 Nenhum

## <a name="valid-options"></a>Opções válidas
 Para habilitar a criação de perfil em outra sessão, a opção **CrossSession** deve ser especificada com a opção **Iniciar**. **CrossSession** também deve ser especificado em qualquer comando **Anexar do VSPerfCmd** e **Desanexar** subsequente.

 **Iniciar:** `Method` A opção **Iniciar** inicializa o profiler para o método de criação de perfil especificado.

 **Anexar:** _PID_[**,**_PID_] Começa a traçar o perfil dos processos especificados.

 **Desanexar**[**:**_PID_[,_PID_]] Interrompe a criação de perfil dos processos especificados.

## <a name="example"></a>Exemplo
 Neste exemplo, a opção **CrossSession** é usada para anexar a um aplicativo que foi iniciado em outra sessão de console.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession
VSPerfCmd.exe /Attach:12345 /CS
```

## <a name="see-also"></a>Confira também
- [Vsperfcmd](../profiling/vsperfcmd.md)
- [Aplicativos Autônomos de Perfil](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Criar o perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profile services (Serviços de perfil)](../profiling/command-line-profiling-of-services.md)
