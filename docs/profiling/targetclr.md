---
title: TargetCLR | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: fffcab1d841840c15957e8dae0ff0f87b20de28d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74771575"
---
# <a name="targetclr"></a>TargetCLR
A opção **TargetCLR** especifica a versão do CLR (Common Language Runtime) cujo perfil deverá ser criado quando mais de uma versão do CLR for carregada em um aplicativo.

 Por padrão, as Ferramentas de Criação de Perfil [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] têm como destino a primeira versão do CLR carregada pelo aplicativo.

## <a name="syntax"></a>Sintaxe

```cmd
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]
```

#### <a name="parameters"></a>parâmetros
 `ClrVersion` O número de versão do CLR. Use o formato de versão **vN.N.NNNNN**.

## <a name="required-options"></a>Opções obrigatórias
 A opção **TargetCLR** pode ser usada somente com as opções de **Inicialização** ou **Anexar**.

 **Lançamento:** `AppName` Inicia o aplicativo especificado e começa a traçar o perfil.

 **Anexar:** `PID` Começa a traçar o perfil do processo especificado.

## <a name="example"></a>Exemplo
 Nesse exemplo, a opção TargetCLR é usada para garantir que a versão 4.0.11003 do CLR tenha um perfil criado.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003
```
