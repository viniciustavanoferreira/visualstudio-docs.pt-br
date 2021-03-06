---
title: 'CA1812: evitar classes internas não instanciadas | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
caps.latest.revision: 28
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f5a36ee8cffc221d15243ff72e2e71558e867319
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72645403"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: evitar classes internas sem instâncias
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|Categoria|Microsoft. performance|
|Alteração Significativa|Sem interrupção|

## <a name="cause"></a>Causa
 Uma instância de um tipo no nível de assembly não é criada pelo código no assembly.

## <a name="rule-description"></a>Descrição da Regra
 Essa regra tenta localizar uma chamada para um dos construtores do tipo e relata uma violação se nenhuma chamada for encontrada.

 Os seguintes tipos não são examinados por essa regra:

- Tipos de valor

- Tipos abstratos

- Enumerações

- Delegados

- Tipos de matriz emitidos pelo compilador

- Tipos que não podem ser instanciados e que definem apenas os métodos `static` (`Shared` em Visual Basic).

  Se você aplicar <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> ao assembly que está sendo analisado, essa regra não ocorrerá em nenhum construtor marcado como `internal` porque você não pode saber se um campo está sendo usado por outro assembly de `friend`.

  Embora você não possa solucionar essa limitação na análise de código [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], o FxCop autônomo externo ocorrerá em construtores internos se cada assembly de `friend` estiver presente na análise.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, remova o tipo ou adicione o código que o utiliza. Se o tipo contiver apenas métodos estáticos, adicione um dos seguintes ao tipo para impedir que o compilador emitisse um construtor de instância pública padrão:

- Um Construtor privado para tipos que visam [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] versões 1,0 e 1,1.

- O modificador de `static` (`Shared` no Visual Basic) para os tipos que se destinam [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)].

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É seguro suprimir um aviso dessa regra. É recomendável suprimir esse aviso nas seguintes situações:

- A classe é criada por meio de métodos de reflexão de associação tardia, como <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.

- A classe é criada automaticamente pelo tempo de execução ou [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Por exemplo, classes que implementam <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> ou <xref:System.Web.IHttpHandler?displayProperty=fullName>.

- A classe é passada como um parâmetro de tipo genérico que tem uma nova restrição. Por exemplo, o exemplo a seguir gerará essa regra.

  ```csharp
  internal class MyClass
  {
      public DoSomething()
      {
      }
  }
  public class MyGeneric<T> where T : new()
  {
      public T Create()
      {
          return new T();
      }
  }
  // [...]
  MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
  mc.Create();
  ```

  Nessas situações, é recomendável suprimir esse aviso.

## <a name="related-rules"></a>Regras relacionadas
 [CA1811: evitar código privado não chamado](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1801: examinar parâmetros não usados](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: remover locais não usados](../code-quality/ca1804-remove-unused-locals.md)
