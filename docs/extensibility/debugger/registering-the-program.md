---
title: Cadastrando o Programa | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- programs, registration
- debugging [Debugging SDK], program registration
ms.assetid: d726a161-7db3-4ef4-b258-9f6a5be68418
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b68fa67f784d155288482ad724b632ed5ba5fa41
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80713166"
---
# <a name="register-the-program"></a>Registre o programa
Depois que o mecanismo de depuração adquiriu uma porta, representada por uma interface [IDebugPort2,](../../extensibility/debugger/reference/idebugport2.md) o próximo passo para permitir que o programa seja depurado é registrá-lo na porta. Uma vez registrado, o programa está disponível para depuração por um dos seguintes meios:

- O processo de anexação, que permite que o depurador obtenha controle completo de depuração de um aplicativo em execução.

- Depuração just-in-time (JIT), que permite a depuração após o fato de um programa que é executado independentemente de um depurador. Quando a arquitetura em tempo de execução pega uma falha, o depurador é notificado antes que o sistema operacional ou o ambiente em tempo de execução libere a memória e os recursos do programa de falha.

## <a name="registering-procedure"></a>Procedimento de registro

### <a name="to-register-your-program"></a>Para registrar seu programa

1. Ligue para o método [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) implementado pela porta.

     `IDebugPortNotify2::AddProgramNode`requer um ponteiro para uma interface [IDebugProgramNode2.](../../extensibility/debugger/reference/idebugprogramnode2.md)

     Normalmente, quando o sistema operacional ou o ambiente em tempo de execução carrega um programa, ele cria o nó do programa. Se o mecanismo de depuração (DE) for solicitado a carregar o programa, o DE criará e registrará o nó do programa.

     O exemplo a seguir mostra o mecanismo de depuração iniciando o programa e registrando-o com uma porta.

    > [!NOTE]
    > Esta amostra de código não é a única maneira de iniciar e retomar um processo; este código é principalmente um exemplo de registro de um programa com uma porta.

    ```cpp
    // This is an IDebugEngineLaunch2 method.
    HRESULT CDebugEngine::LaunchSuspended(/* omitted parameters */,
                                          IDebugPort2 *pPort,
                                          /* omitted parameters */,
                                          IDebugProcess2**ppDebugProcess)
    {
        // do stuff here to set up for a launch (such as handling the other parameters)
        ...

        // Now get the IPortNotify2 interface so we can register a program node
        // in CDebugEngine::ResumeProcess.
        CComPtr<IDebugDefaultPort2> spDefaultPort;
        HRESULT hr = pPort->QueryInterface(&spDefaultPort);
        if (SUCCEEDED(hr))
        {
            CComPtr<IDebugPortNotify2> spPortNotify;
            hr = spDefaultPort->GetPortNotify(&spPortNotify);
            if (SUCCEEDED(hr))
            {
                // Remember the port notify so we can use it in ResumeProcess.
                m_spPortNotify = spPortNotify;

                // Now launch the process in a suspended state and return the
                // IDebugProcess2 interface
                CComPtr<IDebugPortEx2> spPortEx;
                hr = pPort->QueryInterface(&spPortEx);
                if (SUCCEEDED(hr))
                {
                    // pass on the parameters we were given (omitted here)
                    hr = spPortEx->LaunchSuspended(/* omitted parameters */,ppDebugProcess)
                }
            }
        }
        return(hr);
    }

    HRESULT CDebugEngine::ResumeProcess(IDebugProcess2 *pDebugProcess)
    {
        // Make a program node for this process
        HRESULT hr;
        CComPtr<IDebugProgramNode2> spProgramNode;
        hr = this->GetProgramNodeForProcess(pProcess, &spProgramNode);
        if (SUCCEEDED(hr))
        {
            hr = m_spPortNotify->AddProgramNode(spProgramNode);
            if (SUCCEEDED(hr))
            {
                // resume execution of the process using the port given to us earlier.
               // (Querying for the IDebugPortEx2 interface is valid here since
               // that's how we got the IDebugPortNotify2 interface in the first place.)
                CComPtr<IDebugPortEx2> spPortEx;
                hr = m_spPortNotify->QueryInterface(&spPortEx);
                if (SUCCEEDED(hr))
                {
                    hr  = spPortEx->ResumeProcess(pDebugProcess);
                }
            }
        }
        return(hr);
    }

    ```

## <a name="see-also"></a>Confira também
- [Obtendo um porto](../../extensibility/debugger/getting-a-port.md)
- [Permitindo que um programa seja depurado](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)
