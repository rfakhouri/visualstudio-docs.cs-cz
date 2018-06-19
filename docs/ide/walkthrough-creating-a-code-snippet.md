---
title: 'Návod: Vytvoření fragmentu kódu'
ms.date: 10/27/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, creating
- code snippets, shortcut
- code snippets, template
- code snippets, replacements
- code snippets, references
- code snippets, imports
ms.assetid: 0dcaae11-39cf-4463-9c90-2494321251c2
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 6a9890be18e3d43f4c036da72bf2794801e5ec70
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425154"
---
# <a name="walkthrough-create-a-code-snippet"></a>Návod: Vytvoření fragmentu kódu
Fragment kódu můžete vytvořit pomocí pouhých několika krocích. Všechny, které musíte udělat je vytvořte soubor XML, vyplňte příslušná elementy a přidejte do ní váš kód. Můžete také přidat odkazy a nahrazující parametry do vašeho kódu. Fragment k instalaci sady Visual Studio můžete přidat pomocí **Import** na tlačítko **Správce fragmentů kódu** (**nástroje**  >   **Správce fragmentů kódu**).

## <a name="snippet-template"></a>Fragment kódu šablony
 Toto je šablona základní fragment kódu:

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets
    xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title></Title>
        </Header>
        <Snippet>
            <Code Language="">
                <![CDATA[]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

### <a name="create-a-code-snippet"></a>Vytvoření fragmentu kódu

1.  Vytvořte nový soubor XML v sadě Visual Studio a přidání šablony uvedené výše.

2.  Zadejte název fragmentu, například "Hello World VB" v **název** elementu.

3.  Zadejte jazyk fragmentu v **jazyky** atribut **kód** element. V tomto příkladu použijte "VB".

4.  Přidejte kód **CDATA** části uvnitř **kód** elementu, například:

    ```xml
    <Code Language="VB">
        <![CDATA[Console.WriteLine("Hello, World!")]]>
    </Code>
    ```

5.  Uložit fragmentu jako *VBCodeSnippet.snippet*.

### <a name="add-a-code-snippet-to-visual-studio"></a>Přidat fragment kódu pro Visual Studio

1.  Pomocí Správce fragmentů kódu můžete přidat vlastní výstřižky do instalace Visual Studia. Otevřete **Správce fragmentů kódu** (**nástroje** > **Správce fragmentů kódu**).

2.  Klikněte **Import** tlačítko.

3.  Přejděte do umístění, kam jste uložili fragmentu kódu zobrazeném v předchozím postupu, vyberte ho a klikněte na tlačítko **otevřete**.

4.  **Fragment kódu importu** otevře dialogové okno s výzvou, abyste vybrat místo pro přidání fragmentu z možností v pravém podokně. Jedna z těchto možností by měla být **Moje fragmenty kódu**. Vyberte ho a klikněte na tlačítko **Dokončit**, pak **OK**.

5.  Fragment zkopírován do následujícího umístění:

     *%USERPROFILE%\Documents\Visual studio 2017\Code Snippets\Visual Basic\My fragmenty kódu*

6.  Otestujte fragment otevřením projektu jazyka Visual Basic a otevření souboru kódu. V souboru zvolte **fragmenty** > **Vložit fragment** z kontextové nabídky, pak **Moje fragmenty kódu**. Měli byste vidět fragment s názvem **Moje fragment kódu jazyka Visual Basic**. Dvojím kliknutím.

    `Console.WriteLine("Hello, World!")` je vložen do souboru kódu.

### <a name="add-description-and-shortcut-fields"></a>Přidat pole Popis a zástupce

1.  Pole Popis zadejte další informace o fragment kódu při zobrazení ve Správci fragmentů kódu. Zástupce je značky, který mohou uživatelé, aby bylo možné vložit fragment. Upravit fragmentu jste přidali, a soubor otevřít *%USERPROFILE%\Documents\Visual Studio 2017\Code Snippets\Visual Basic\My kód Snippet\VBCodeSnippet.snippet*.

2.  Přidat **Autor** a **popis** elementů **záhlaví** elementu a vyplňte je.

3.  **Záhlaví** element by měl vypadat přibližně takto:

    ```xml
    <Header>
        <Title>Hello World VB</Title>
        <Author>Myself</Author>
        <Description>Says Hello to the world.</Description>
    </Header>
    ```

4.  Otevřete **Správce fragmentů kódu** a vyberte fragment kódu. V pravém podokně měli vidět, který **popis** a **Autor** pole se vyplní teď.

5.  Chcete-li přidat zástupce, přidejte **zástupce** element společně **Autor** a **popis** element:

    ```xml
    <Header>
        <Title>Hello World VB</Title>
        <Author>Myself</Author>
        <Description>Says Hello to the world.</Description>
        <Shortcut>hello</Shortcut>
    </Header>
    ```

6.  Uložte soubor fragment kódu znovu.

7.  Chcete-li otestovat zástupce, otevřete projektu jazyka Visual Basic a otevření souboru kódu. Typ `hello` v souboru a stiskněte klávesu **kartě** dvakrát.

    Je vložit fragment kódu.

### <a name="add-references-and-imports"></a>Přidání odkazů a importy

1.  Můžete přidat odkaz na projekt pomocí **odkazy** elementu a přidejte deklaraci importy pomocí **importy** element. (Tento postup funguje pro jazyk C# také.) Například, pokud změníte `Console.WriteLine` v příkladu kódu k `MessageBox.Show`, budete muset přidat *System.Windows.Forms.dll* sestavení do projektu.

2.  Otevřete váš fragment kódu.

3.  Přidat **odkazy** prvek v rámci **fragment kódu** element:

    ```xml
    <References>
        <Reference>
            <Assembly>System.Windows.Forms.dll</Assembly>
        </Reference>
    </References>
    ```

4.  Přidat **importy** prvek v rámci **fragment kódu** element:

    ```xml
    <Imports>
        <Import>
           <Namespace>System.Windows.Forms</Namespace>
        </Import>
    </Imports>
    ```

5.  Změna **CDATA** části pro následující:

    ```xml
    <![CDATA[MessageBox.Show("Hello, World!")]]>
    ```

6.  Uložte fragmentu.

7.  Otevřete projekt Visual Basic a přidejte fragment.

8.  Zobrazí se `Imports` příkaz v horní části souboru kódu:

    ```vb
    Imports System.Windows.Forms
    ```

9. Podívejte se na vlastnosti projektu. **Odkazy** karta obsahuje odkaz na *System.Windows.Forms.dll*.

### <a name="add-replacements"></a>Přidat nahrazení

1.  Můžete chtít součástí vaší fragmenty kódu nahradit za uživatele, například pokud přidat proměnnou a má uživatel k nahrazení proměnné s jedním v aktuálním projektu. Můžete zadat dva typy náhrady: literály a objekty. Literály jsou řetězce, typu (textové literály, názvy proměnných nebo řetězec reprezentace číselné hodnoty). Objekty jsou instance typu než řetězec. V tomto postupu budete deklarovat literálu náhradní a nahrazení objektu a změnit kód tak, aby odkazovaly tyto nahrazení.

2.  Otevřete váš fragment kódu.

3.  Tento příklad používá připojovací řetězec SQL, takže budete muset změnit **importy** a **odkazy** elementy: přidejte příslušné odkazy na:

    ```xml
    <References>
        <Reference>
            <Assembly>System.Data.dll</Assembly>
        </Reference>
        <Reference>
            <Assembly>System.Xml.dll</Assembly>
        </Reference>
    </References>
    <Imports>
        <Import>
            <Namespace>System.Data</Namespace>
        </Import>
        <Import>
            <Namespace>System.Data.SqlClient</Namespace>
        </Import>
    </Imports>
    ```

4.  Deklarovat literálu náhradní server pro připojovací řetězec SQL, přidejte **deklarace** prvek v rámci **fragment kódu** elementu a v ní přidat **literálu** element s dílčí prvky pro ID, popis a výchozí hodnota pro nahrazení:

    ```xml
    <Declarations>
        <Literal>
            <ID>SqlConnString</ID>
            <ToolTip>Replace with a SQL connection string.</ToolTip>
            <Default>"SQL connection string"</Default>
        </Literal>
    </Declarations>
    ```

5.  Deklarovat nahrazení objektu pro připojení k SQL, přidejte **objekt** element uvnitř **deklarace** elementu a přidejte dílčí prvky pro ID typu objektu, popis a výchozí hodnota hodnota. Výsledná **deklarace** element by měla vypadat takto:

    ```xml
    <Declarations>
        <Literal>
            <ID>SqlConnString</ID>
            <ToolTip>Replace with a SQL connection string.</ToolTip>
            <Default>"SQL connection string"</Default>
        </Literal>
        <Object>
            <ID>SqlConnection</ID>
            <Type>System.Data.SqlClient.SqlConnection</Type>
            <ToolTip>Replace with a connection object in your application.</ToolTip>
            <Default>dcConnection</Default>
        </Object>
    </Declarations>
    ```

6.  V části kódu odkazovat náhrady s malé znaky $, například `$replacement$`:

    ```xml
    <Code Language="VB" Kind="method body">
        <![CDATA[Dim daCustomers As SqlDataAdapter
            Dim selectCommand As SqlCommand

            daCustomers = New SqlClient.SqlDataAdapter()
            selectCommand = new SqlClient.SqlCommand($SqlConnString$)
            daCustomers.SelectCommand = selectCommand
            daCustomers.SelectCommand.Connection = $SqlConnection$]]>
    </Code>
    ```

7.  Uložte fragmentu.

8.  Otevřete projekt Visual Basic a přidejte fragment.

9. Kód by měl vypadat jako následující, kde nahrazení `SQL connection string` a `dcConnection` jsou vyznačené na světla oranžová. Zvolte **kartě** přejděte z jeden na druhý.

    ```vb
    Dim daCustomers As SqlDataAdapter
    Dim selectCommand As SqlCommand

    daCustomers = New SqlClient.SqlDataAdapter()
    selectCommand = New SqlClient.SqlCommand("SQL connection string")
    daCustomers.SelectCommand = selectCommand
    daCustomers.SelectCommand.Connection = dcConnection
    ```

## <a name="see-also"></a>Viz také

- [Fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md)