---
title: Desligamento| Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 89a08808387067b934bfd826feb2dcfbcf949aab
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778278"
---
# <a name="shutdown"></a>Shutdown
A opção **Desligamento** aguarda qualquer processo com perfil finalizar ou desanexar e, em seguida, desativa o criador de perfil e fecha o arquivo de dados de criação de perfil. A opção **desligamento** deve ser o último comando de criação de um perfil.

 Se um parâmetro de tempo limite não for especificado, a opção **Desligamento** aguardará indefinidamente. Se um parâmetro de tempo limite for especificado, a opção retornará após o número especificado de segundos, sem desativar o criador de perfil ou fechar o arquivo de dados.

 A opção **desligamento** deve ser a única opção especificada na linha de comando.

## <a name="syntax"></a>Sintaxe

```cmd
VSPerfCmd.exe /Shutdown[:Timeout]
```

#### <a name="parameters"></a>parâmetros
`Timeout`
- (Opcional) Se especificado, a opção retorna após o número especificado de segundos sem desativar o criador de perfil ou fechar o arquivo de dados de criação de perfil.

## <a name="see-also"></a>Confira também
- [Vsperfcmd](../profiling/vsperfcmd.md)
- [Aplicativos Autônomos de Perfil](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Criar o perfil de aplicativos Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profile services (Serviços de perfil)](../profiling/command-line-profiling-of-services.md)
