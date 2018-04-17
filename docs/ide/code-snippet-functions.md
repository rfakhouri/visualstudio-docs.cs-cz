---
title: Funkce fragmentu kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets [Visual Studio], functions
- snippets [Visual Studio], functions
- IntelliSense code snippets, functions
ms.assetid: c0a2bf21-8fa5-4457-9281-f599beb53e7d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9229881eeb5b3b9b730101e2fb418c1a79d41cf4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="code-snippet-functions"></a>Funkce fragmentu kódu

Existují tři funkce, které jsou k dispozici pro použití s fragmenty kódu v C#. Funkce jsou určené v [funkce](../ide/code-snippets-schema-reference.md#function) element fragmentu kódu. Informace o vytváření fragmenty kódu najdete v tématu [výstřižky kódu](../ide/code-snippets.md).

## <a name="functions"></a>Funkce

Následující tabulka popisuje funkce dostupné pro použití s `Function` element v fragmenty kódu.

|Funkce|Popis|Jazyk|  
|--------------|-----------------|--------------|  
|`GenerateSwitchCases(` `EnumerationLiteral` `)`|Generuje příkaz switch a sadu case – příkazy pro členy výčtu určeného `EnumerationLiteral` parametr. `EnumerationLiteral` Parametr musí být odkaz na výčet literálu nebo výčtového typu.|[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]|  
|`ClassName()`|Vrací název třídy, která obsahuje vložené fragment kódu.|[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]|  
|`SimpleTypeName(` `TypeName` `)`|Snižuje *TypeName* parametr v kontextu, ve kterém byl vyvolán fragmentu své nejjednodušší podobě.|[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]|  
  
## <a name="example"></a>Příklad

Následující příklad ukazuje, jak používat `GenerateSwitchCases` funkce. Když tento fragment kódu je vložen a výčet je zadán do `$switch_on$` literálu, `$cases$` literál generuje `case` příkaz pro každou hodnotu ve výčtu.  

```xml
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

## <a name="example"></a>Příklad

Následující příklad ukazuje, jak používat `ClassName` funkce. Při vložení tento fragment kódu `$classname$` literál se nahradí název nadřazených třídy v tomto umístění v souboru kódu.

```xml
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
            <Code Language="csharp" Format="CData">  
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

## <a name="example"></a>Příklad

Tento příklad ukazuje způsob použití `SimpleTypeName` funkce. Když tento fragment kódu vložíte do souboru kódu `$SystemConsole$` literál nahradí nejjednodušší forma <xref:System.Console> typu v kontextu, ve kterém byl vyvolán fragmentu.  

```xml
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

## <a name="see-also"></a>Viz také

[Element – funkce](../ide/code-snippets-schema-reference.md#function)  
[Fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md)
