---
title: Anotando o comportamento de bloqueio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Releases_nonreentrant_lock_
- _Lock_kind_mutex_
- _Lock_kind_critical_section_
- _Acquires_lock_
- _Releases_lock_
- _Has_lock_kind_
- _Releases_exclusive_lock_
- _Post_same_lock_
- _Requires_exclusive_lock_held_
- _Requires_shared_lock_held_
- _Lock_kind_semaphore_
- _Requires_lock_held_
- _Acquires_exclusive_lock_
- _Create_lock_level_
- _Acquires_nonreentrant_lock_
- _Releases_shared_lock_
- _Has_lock_level_
- _Lock_kind_spin_lock_
- _Requires_lock_not_held_
- _Acquires_shared_lock_
- _Requires_no_locks_held_
- _Lock_level_order_
- _Lock_kind_event_
ms.assetid: 07769c25-9b97-4ab7-b175-d1c450308d7a
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: 00d3c90ce7e21ab4e9852ed937481103c351609b
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "77271597"
---
# <a name="annotating-locking-behavior"></a>Anotando o comportamento de bloqueio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para evitar bugs de simultaneidade em seu programa multithread, sempre siga uma disciplina de bloqueio apropriada e use anotações SAL.  
  
 Os bugs de simultaneidade são notoriamente difíceis de reproduzir, diagnosticar e depurar porque são não determinísticos. O raciocínio da intercalação de threads é difícil na melhor das hipóteses e torna-se impraticável quando você está criando um corpo de código que tem mais de alguns threads. Portanto, é uma boa prática seguir uma disciplina de bloqueio em seus programas multithread. Por exemplo, obedecer a uma ordem de bloqueio ao adquirir vários bloqueios ajuda a evitar deadlocks e adquirir o bloqueio de proteção adequado antes de acessar um recurso compartilhado ajuda a evitar condições de corrida.  
  
 Infelizmente, as regras de bloqueio aparentemente simples podem ser surpreendentemente difíceis de serem seguidas na prática. Uma limitação fundamental nas linguagens de programação e nos compiladores de hoje é que elas não oferecem suporte direto à especificação e à análise de requisitos de simultaneidade. Os programadores precisam contar com comentários de código informais para expressar suas intenções sobre como eles usam bloqueios.  
  
 As anotações de SAL de simultaneidade são projetadas para ajudá-lo a especificar efeitos colaterais de bloqueio, responsabilidade de bloqueio, Data Guardian, hierarquia de ordem de bloqueio e outro comportamento de bloqueio esperado. Ao tornar explícitas as regras implícitas, as anotações de simultaneidade SAL fornecem uma maneira consistente de você documentar como seu código usa regras de bloqueio. As anotações de simultaneidade também aprimoram a capacidade das ferramentas de análise de código de encontrar condições de corrida, deadlocks, operações de sincronização incompatíveis e outros erros sutis de simultaneidade.  
  
## <a name="general-guidelines"></a>Diretrizes gerais  
 Usando anotações, você pode declarar os contratos que são implícitos por definições de função entre implementações (chamadas) e clientes (chamadores) e invariáveis expressas e outras propriedades do programa que podem melhorar ainda mais a análise.  
  
 O SAL dá suporte a muitos tipos diferentes de primitivos de bloqueio — por exemplo, seções críticas, exclusões mútuas, bloqueios de rotação e outros objetos de recurso. Muitas anotações de simultaneidade usam uma expressão de bloqueio como um parâmetro. Por convenção, um bloqueio é indicado pela expressão de caminho do objeto de bloqueio subjacente.  
  
 Algumas regras de Propriedade do thread a serem consideradas:  
  
- Bloqueios de rotação são bloqueios sem desconto que têm propriedade de thread clara.  
  
- Mutexes e seções críticas são bloqueios contados que têm propriedade de thread clara.  
  
- Semáforos e eventos são bloqueios contados que não têm propriedade de thread clara.  
  
## <a name="locking-annotations"></a>Anotações de bloqueio  
 A tabela a seguir lista as anotações de bloqueio.  
  
|Anotação|DESCRIÇÃO|  
|----------------|-----------------|  
|`_Acquires_exclusive_lock_(expr)`|Anota uma função e indica que, no estado de post, a função é incrementada por uma contagem de bloqueios exclusiva do objeto de bloqueio nomeado por `expr`.|  
|`_Acquires_lock_(expr)`|Anota uma função e indica que, no estado de post, a função é incrementada por uma contagem de bloqueios do objeto de bloqueio nomeado por `expr`.|  
|`_Acquires_nonreentrant_lock_(expr)`|O bloqueio nomeado pelo `expr` é adquirido.  Um erro será relatado se o bloqueio já estiver em retenção.|  
|`_Acquires_shared_lock_(expr)`|Anota uma função e indica que, no estado de post, a função é incrementada por uma contagem de bloqueios compartilhada do objeto de bloqueio nomeado por `expr`.|  
|`_Create_lock_level_(name)`|Uma instrução que declara o símbolo `name` ser um nível de bloqueio para que ele possa ser usado nas anotações `_Has_Lock_level_` e `_Lock_level_order_`.|  
|`_Has_lock_kind_(kind)`|Anota qualquer objeto para refinar as informações de tipo de um objeto de recurso. Às vezes, um tipo comum é usado para diferentes tipos de recursos e o tipo sobrecarregado não é suficiente para distinguir os requisitos semânticos entre vários recursos. Aqui está uma lista de parâmetros de `kind` predefinidos:<br /><br /> `_Lock_kind_mutex_`<br /> ID do tipo de bloqueio para mutexes.<br /><br /> `_Lock_kind_event_`<br /> ID de tipo de bloqueio para eventos.<br /><br /> `_Lock_kind_semaphore_`<br /> ID do tipo de bloqueio para semáforos.<br /><br /> `_Lock_kind_spin_lock_`<br /> ID do tipo de bloqueio para bloqueios de rotação.<br /><br /> `_Lock_kind_critical_section_`<br /> ID do tipo de bloqueio para seções críticas.|  
|`_Has_lock_level_(name)`|Anota um objeto de bloqueio e dá a ele o nível de bloqueio de `name`.|  
|`_Lock_level_order_(name1, name2)`|Uma instrução que fornece a ordem de bloqueio entre `name1` e `name2`.|  
|`_Post_same_lock_(expr1, expr2)`|Anota uma função e indica que, em estado de postagem, os dois bloqueios, `expr1` e `expr2`, são tratados como se fossem o mesmo objeto de bloqueio.|  
|`_Releases_exclusive_lock_(expr)`|Anota uma função e indica que, no estado de post, a função diminui em uma contagem de bloqueios exclusiva do objeto de bloqueio nomeado por `expr`.|  
|`_Releases_lock_(expr)`|Anota uma função e indica que, no estado de post, a função diminui em uma contagem de bloqueios do objeto de bloqueio nomeado por `expr`.|  
|`_Releases_nonreentrant_lock_(expr)`|O bloqueio nomeado pelo `expr` é liberado. Um erro será relatado se o bloqueio não for mantido no momento.|  
|`_Releases_shared_lock_(expr)`|Anota uma função e indica que, no estado de post, a função diminui em uma contagem de bloqueios compartilhada do objeto de bloqueio nomeado por `expr`.|  
|`_Requires_lock_held_(expr)`|Anota uma função e indica que, em pré-estado, a contagem de bloqueios do objeto nomeado por `expr` é pelo menos uma.|  
|`_Requires_lock_not_held_(expr)`|Anota uma função e indica que, em pré-estado, a contagem de bloqueios do objeto nomeado por `expr` é zero.|  
|`_Requires_no_locks_held_`|Anota uma função e indica que as contagens de bloqueios de todos os bloqueios conhecidos pelo verificador são zero.|  
|`_Requires_shared_lock_held_(expr)`|Anota uma função e indica que, em pré-estado, a contagem de bloqueios compartilhada do objeto que é nomeada por `expr` é pelo menos uma.|  
|`_Requires_exclusive_lock_held_(expr)`|Anota uma função e indica que, em pré-estado, a contagem de bloqueios exclusiva do objeto que é nomeado por `expr` é pelo menos uma.|  
  
## <a name="sal-intrinsics-for-unexposed-locking-objects"></a>SAL intrínseco para objetos de bloqueio não expostos  
 Determinados objetos de bloqueio não são expostos pela implementação das funções de bloqueio associadas.  A tabela a seguir lista as variáveis intrínsecas SAL que habilitam anotações em funções que operam nesses objetos de bloqueio não expostos.  
  
|Anotação|DESCRIÇÃO|  
|----------------|-----------------|  
|`_Global_cancel_spin_lock_`|Descreve o cancelamento do bloqueio de rotação.|  
|`_Global_critical_region_`|Descreve a região crítica.|  
|`_Global_interlock_`|Descreve operações interbloqueadas.|  
|`_Global_priority_region_`|Descreve a região de prioridade.|  
  
## <a name="shared-data-access-annotations"></a>Anotações de acesso a dados compartilhados  
 A tabela a seguir lista as anotações para acesso a dados compartilhados.  
  
|Anotação|DESCRIÇÃO|  
|----------------|-----------------|  
|`_Guarded_by_(expr)`|Anota uma variável e indica que sempre que a variável é acessada, a contagem de bloqueios do objeto de bloqueio nomeado por `expr` é pelo menos uma.|  
|`_Interlocked_`|Anota uma variável e é equivalente a `_Guarded_by_(_Global_interlock_)`.|  
|`_Interlocked_operand_`|O parâmetro de função anotada é o operando de destino de uma das várias funções interbloqueadas.  Esses operandos devem ter propriedades adicionais específicas.|  
|`_Write_guarded_by_(expr)`|Anota uma variável e indica que sempre que a variável é modificada, a contagem de bloqueios do objeto de bloqueio nomeado por `expr` é pelo menos uma.|  
  
## <a name="see-also"></a>Consulte Também  
 [Usando anotações de sal para reduzir os defeitosC++ de C/código](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [Compreendendo o SAL](../code-quality/understanding-sal.md)   
 [Anotando parâmetros de função e valores de retorno](../code-quality/annotating-function-parameters-and-return-values.md)   
 [Comportamento de função de anotação](../code-quality/annotating-function-behavior.md)   
 [Anotando structs e Classes](../code-quality/annotating-structs-and-classes.md)   
 [Especificando quando e onde uma anotação se aplica](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [Funções intrínsecas](../code-quality/intrinsic-functions.md)   
 [Práticas recomendadas e exemplos](../code-quality/best-practices-and-examples-sal.md)   
 [Blog da equipe de análise de código](https://blogs.msdn.com/b/codeanalysis/)
