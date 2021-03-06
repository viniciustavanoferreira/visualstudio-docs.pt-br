---
title: Interfaces de fornecedores portuários obrigatórias | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bf2aeb1f26f81d773e171aa3fed6b0f2ef976c91
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80713158"
---
# <a name="required-port-supplier-interfaces"></a>Interfaces de fornecedores de portas necessárias
Um fornecedor de porta deve implementar a interface [IDebugPortSupplier2.](../../extensibility/debugger/reference/idebugportsupplier2.md) [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)

 Um fornecedor portuário fornece portos e os implementa. Portanto, ele deve executar as seguintes interfaces:

- [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)

  Descreve a porta e enumera todos os processos em execução na porta.

- [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)

  Fornece para iniciar e encerrar processos na porta.

- [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)

  Fornece um mecanismo para que os programas executados dentro do contexto desta porta o notifiquem da criação e destruição de nós do programa. Para obter mais informações, consulte [nós do programa](../../extensibility/debugger/program-nodes.md).

- `IConnectionPointContainer`

  Fornece um ponto de conexão para [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md).

## <a name="port-supplier-operation"></a>Operação do fornecedor portuário
 O [dissipador IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) recebe notificações quando o processo e os programas são criados e destruídos em uma porta. Uma porta é necessária para enviar [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) quando um processo é criado e [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) quando um processo é destruído na porta. Uma porta também é necessária para enviar [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) quando um programa é criado e [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) quando um programa é destruído em um processo em execução na porta.

 Uma porta normalmente envia eventos de criação e destruição de programas em resposta aos métodos [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) e [RemoveProgramNode,](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) respectivamente.

 Como uma porta pode iniciar e encerrar processos físicos e programas lógicos, as seguintes interfaces também devem ser implementadas pelo mecanismo de depuração:

- [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)

  Descreve o processo físico. Pelo menos os seguintes métodos devem ser implementados:

  - [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)

  - [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)

  - [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)

  - [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)

  - [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)

  - [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)

- [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)

  Fornece uma maneira para o SDM se conectar e se desvincular de um processo.

- [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)

  Descreve o programa lógico. Pelo menos os seguintes métodos devem ser implementados:

  - [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)

  - [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)

  - [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)

- [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)

  Fornece uma maneira para o SDM anexar a este programa.

## <a name="see-also"></a>Confira também
- [Implementação de um fornecedor portuário](../../extensibility/debugger/implementing-a-port-supplier.md)
