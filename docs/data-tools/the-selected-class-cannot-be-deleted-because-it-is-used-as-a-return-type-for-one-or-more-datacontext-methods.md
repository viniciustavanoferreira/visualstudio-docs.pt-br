---
title: A classe selecionada não pode ser excluída porque é usada como um tipo de retorno para um ou mais métodos DataContext
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 249a5338985983509f04e0ff268b2f30e2773f71
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76113552"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>A classe selecionada não pode ser excluída porque é usada como um tipo de retorno para um ou mais métodos DataContext

O tipo de retorno de um ou mais métodos de <xref:System.Data.Linq.DataContext> é a classe de entidade selecionada. Excluir uma classe de entidade que é usada como o tipo de retorno para um método <xref:System.Data.Linq.DataContext> faz com que a compilação do projeto falhe. Para excluir a classe selecionada de entidade, identifica os métodos de <xref:System.Data.Linq.DataContext> que a usam e definem seus tipos de retorno para uma classe diferente de entidade.

Para reverter os tipos de retorno de métodos de <xref:System.Data.Linq.DataContext> para seus tipos gerados automaticamente de original, primeiro excluir o método de <xref:System.Data.Linq.DataContext> do painel **Métodos** e arraste então o objeto de **Gerenciador de Servidores**/**Gerenciador de Banco de Dados** no **Designer Relacional de Objetos** novamente.

## <a name="to-correct-this-error"></a>Para corrigir esse erro

1. Identifica os métodos de <xref:System.Data.Linq.DataContext> que usam a classe de entidade como um tipo de retorno selecionando um método de <xref:System.Data.Linq.DataContext> no painel **Métodos** e inspecionando a propriedade de **Tipo de Retorno** na janela **Propriedades**.

2. Definir **Tipo de Retorno** a uma classe diferente de entidade ou exclui o método de <xref:System.Data.Linq.DataContext> do painel métodos.

## <a name="see-also"></a>Veja também

- [Ferramentas do LINQ to SQL no Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
