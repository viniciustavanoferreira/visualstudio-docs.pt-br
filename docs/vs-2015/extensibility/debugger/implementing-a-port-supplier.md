---
title: Implementando um fornecedor de porta | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ffa6daa20c08bd236657c88e762b2f453554cb74
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152680"
---
# <a name="implementing-a-port-supplier"></a>Implementando um fornecedor de porta
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Um fornecedor de porta fornece portas de solicitação para o Gerenciador de sessão de depuração (SDM). Um fornecedor de porta precisa ser implementado ao depurar para uma máquina não-DCOM ou quando um novo dispositivo precisa de suporte. Por exemplo, para fornecer um telefone celular de depuração, você pode implementar um fornecedor de porta que fornece as portas que se conectam para o telefone celular (talvez por meio do IR ou uma conexão de célula) e enumera os processos e programas em execução no telefone.  
  
 Para depuração de programas em computadores baseados em Windows (incluindo a depuração remota), o Visual Studio fornece os fornecedores de porta para nativo e processos de tempo de execução de linguagem comum (CLR), portanto, não há nenhuma necessidade de implementar seu próprio fornecedor de porta nesses casos.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Implementar e registrar um fornecedor de porta](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 Discute como o SDM interage com o fornecedor de porta e suas portas.  
  
 [Interfaces de fornecedor porta necessárias](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 Documenta as interfaces que devem ser implementadas para obter um fornecedor de porta.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Conceitos do depurador](../../extensibility/debugger/debugger-concepts.md)  
 Descreve os principais conceitos de arquiteturas de depuração.  
  
## <a name="see-also"></a>Consulte também  
 [Extensibilidade do depurador do Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
