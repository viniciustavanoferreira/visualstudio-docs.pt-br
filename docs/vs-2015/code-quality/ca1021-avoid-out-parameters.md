---
title: 'CA1021: evitar parâmetros de saída | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1021
- AvoidOutParameters
helpviewer_keywords:
- AvoidOutParameters
- CA1021
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ea5d943212122672b84376b9b3ddf5e72bb0e81f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661996"
---
# <a name="ca1021-avoid-out-parameters"></a>CA1021: evitar parâmetros de saída
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|NomeDoTipo|AvoidOutParameters|
|CheckId|CA1021|
|Categoria|Microsoft. Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um método público ou protegido em um tipo público tem um parâmetro `out`.

## <a name="rule-description"></a>Descrição da Regra
 A passagem de tipos por referência (usando `out` ou `ref`) requer experiência com ponteiros, compreendendo como tipos de valor e tipos de referência diferem e manipulando métodos com vários valores de retorno. Além disso, a diferença entre os parâmetros `out` e `ref` não é amplamente compreendida.

 Quando um tipo de referência é passado "por referência", o método pretende usar o parâmetro para retornar uma instância diferente do objeto. Passar um tipo de referência por referência também é conhecido como usar um ponteiro duplo, um ponteiro para um ponteiro ou um indireção duplo. Usando a Convenção de chamada padrão, que é Pass "por valor", um parâmetro que usa um tipo de referência já recebe um ponteiro para o objeto. O ponteiro, não o objeto ao qual ele aponta, é passado por valor. A passagem por valor significa que o método não pode alterar o ponteiro para que ele aponte para uma nova instância do tipo de referência. No entanto, ele pode alterar o conteúdo do objeto para o qual ele aponta. Para a maioria dos aplicativos, isso é suficiente e produz o comportamento desejado.

 Se um método precisar retornar uma instância diferente, use o valor de retorno do método para fazer isso. Consulte a classe <xref:System.String?displayProperty=fullName> para obter uma variedade de métodos que operam em cadeias de caracteres e retornam uma nova instância de uma cadeia. Quando esse modelo é usado, o chamador deve decidir se o objeto original é preservado.

 Embora os valores de retorno sejam comuns e muito usados, o aplicativo correto dos parâmetros `out` e `ref` exige habilidades de design e codificação intermediárias. Os arquitetos de biblioteca que projetam um público geral não devem esperar que os usuários façam o mestre de trabalho com parâmetros `out` ou `ref`.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra causada por um tipo de valor, faça com que o método retorne o objeto como seu valor de retorno. Se o método deve retornar vários valores, recrie-o para retornar uma única instância de um objeto que contém os valores.

 Para corrigir uma violação dessa regra causada por um tipo de referência, verifique se o comportamento desejado é retornar uma nova instância da referência. Se for, o método deve usar seu valor de retorno para fazer isso.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 É seguro suprimir um aviso dessa regra. No entanto, esse design pode causar problemas de usabilidade.

## <a name="example"></a>Exemplo
 A biblioteca a seguir mostra duas implementações de uma classe que gera respostas para os comentários de um usuário. A primeira implementação (`BadRefAndOut`) força o usuário da biblioteca a gerenciar três valores de retorno. A segunda implementação (`RedesignedRefAndOut`) simplifica a experiência do usuário retornando uma instância de uma classe de contêiner (`ReplyData`) que gerencia os dados como uma única unidade.

 [!code-csharp[FxCop.Design.NoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NoRefOrOut/cs/FxCop.Design.NoRefOrOut.cs#1)]

## <a name="example"></a>Exemplo
 O aplicativo a seguir ilustra a experiência do usuário. A chamada para a biblioteca remodelada (método `UseTheSimplifiedClass`) é mais simples e as informações retornadas pelo método são facilmente gerenciadas. A saída dos dois métodos é idêntica.

 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestNoRefOrOut/cs/FxCop.Design.TestNoRefOrOut.cs#1)]

## <a name="example"></a>Exemplo
 A biblioteca de exemplo a seguir ilustra como `ref` parâmetros para tipos de referência são usados e mostra uma maneira melhor de implementar essa funcionalidade.

 [!code-csharp[FxCop.Design.RefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefByRefNo/cs/FxCop.Design.RefByRefNo.cs#1)]

## <a name="example"></a>Exemplo
 O aplicativo a seguir chama cada método na biblioteca para demonstrar o comportamento.

 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefByRefNo/cs/FxCop.Design.TestRefByRefNo.cs#1)]

 Este exemplo gerencia a seguinte saída.

 **Alterando ponteiro-aprovado por valor:** 
**12345** 
**12345** 
**alteração de ponteiro passado por referência:** 
**12345** 
**12345 abcde** 1**passando pelo valor de retorno: **3**12345 abcde**
## <a name="try-pattern-methods"></a>Experimente os métodos de padrão

### <a name="description"></a>Descrição
 Métodos que implementam o padrão de **> Try \<Something** , como <xref:System.Int32.TryParse%2A?displayProperty=fullName>, não geram essa violação. O exemplo a seguir mostra uma estrutura (tipo de valor) que implementa o método <xref:System.Int32.TryParse%2A?displayProperty=fullName>.

### <a name="code"></a>Código
 [!code-csharp[FxCop.Design.TryPattern#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TryPattern/cs/FxCop.Design.TryPattern.cs#1)]

## <a name="related-rules"></a>Regras relacionadas
 [CA1045: não passar tipos por referência](../code-quality/ca1045-do-not-pass-types-by-reference.md)
