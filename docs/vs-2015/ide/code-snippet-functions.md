---
title: Funções de snippet de código | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets [Visual Studio], functions
- snippets [Visual Studio], functions
- IntelliSense code snippets, functions
ms.assetid: c0a2bf21-8fa5-4457-9281-f599beb53e7d
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 92533b90e6a2da9f29a67d13c6e0eee2c31dbcfe
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72620228"
---
# <a name="code-snippet-functions"></a>Funções de snippet de código
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Há três funções disponíveis para uso com os snippets de código de [!INCLUDE[csprcs](../includes/csprcs-md.md)]. As funções são especificadas no elemento [Function](https://msdn.microsoft.com/572c5549-5821-4e15-8ecd-0fa86c1c65df) do snippet de código. Para obter informações sobre como criar snippets de código, consulte [Snippets de Código](../ide/code-snippets.md).

## <a name="functions"></a>Funções
 A tabela a seguir descreve as funções disponíveis para uso com o elemento `Function` em snippets de código.

|Função|DESCRIÇÃO|Idioma|
|--------------|-----------------|--------------|
|`GenerateSwitchCases(` `EnumerationLiteral` `)`|Gera uma instrução de opção e um conjunto de instruções de maiúsculas e minúsculas para os membros da enumeração especificada pelo parâmetro `EnumerationLiteral`. O parâmetro `EnumerationLiteral` deve ser uma referência a uma literal de enumeração ou a um tipo de enumeração.|[!INCLUDE[csprcs](../includes/csprcs-md.md)]|
|`ClassName()`|Retorna o nome da classe que contém o snippet inserido.|[!INCLUDE[csprcs](../includes/csprcs-md.md)]|
|`SimpleTypeName(` `TypeName` `)`|Reduz o parâmetro *TypeName* para sua forma mais simples no contexto em que o snippet foi invocado.|[!INCLUDE[csprcs](../includes/csprcs-md.md)]|

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra como usar a função `GenerateSwitchCases`. Quando este snippet for inserido e uma enumeração for inserida no literal `$switch_on$`, o literal `$cases$` gerará uma instrução `case` para cada valor na enumeração.

```
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>switch</Title>
            <Shortcut>switch</Shortcut>
            <Description>Code snippet for switch statement</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>expression</ID>
                    <ToolTip>Expression to switch on</ToolTip>
                    <Default>switch_on</Default>
                </Literal>
                <Literal Editable="false">
                    <ID>cases</ID>
                    <Function>GenerateSwitchCases($expression$)</Function>
                    <Default>default:</Default>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    switch ($expression$)
                    {
                        $cases$
                    }
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra como usar a função `ClassName`. Quando este snippet for inserido, o literal `$classname$` será substituído pelo nome da classe delimitadora nesse local no arquivo de código.

```
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Common constructor pattern</Title>
            <Shortcut>ctor</Shortcut>
            <Description>Code Snippet for a constructor</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>type</ID>
                    <Default>int</Default>
                </Literal>
                <Literal>
                    <ID>name</ID>
                    <Default>field</Default>
                </Literal>
                <Literal default="true" Editable="false">
                    <ID>classname</ID>
                    <ToolTip>Class name</ToolTip>
                    <Function>ClassName()</Function>
                    <Default>ClassNamePlaceholder</Default>
                </Literal>
            </Declarations>
            <Code Language="vjsharp" Format="CData">
                <![CDATA[
                    public $classname$ ($type$ $name$)
                    {
                        this._$name$ = $name$;
                    }
                    private $type$ _$name$;
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="example"></a>Exemplo
 Este exemplo mostra como usar a função `SimpleTypeName`. Quando este snippet for inserido em um arquivo de código, o literal `$SystemConsole$` será substituído pela forma mais simples do tipo <xref:System.Console> no contexto em que o snippet foi invocado.

```
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Console_WriteLine</Title>
            <Shortcut>cw</Shortcut>
            <Description>Code snippet for Console.WriteLine</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal Editable="false">
                    <ID>SystemConsole</ID>
                    <Function>SimpleTypeName(global::System.Console)</Function>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    $SystemConsole$.WriteLine();
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="see-also"></a>Veja também
 [Referência de esquema de trechos de código](../ide/code-snippets-schema-reference.md) [do elemento Function (trechos de código IntelliSense)](https://msdn.microsoft.com/572c5549-5821-4e15-8ecd-0fa86c1c65df)
