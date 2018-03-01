---
title: "Návod: Vytvoření fragmentu kódu | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code snippets, creating
- code snippets, shortcut
- code snippets, template
- code snippets, replacements
- code snippets, references
- code snippets, imports
ms.assetid: 0dcaae11-39cf-4463-9c90-2494321251c2
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2ac4cef411bb6304e4033de1850e6c428e34285e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-code-snippet"></a>Návod: Vytvoření fragmentu kódu
Fragment kódu můžete vytvořit pomocí pouhých několika krocích. Všechny, které musíte udělat je vytvořte soubor XML, vyplňte příslušná elementy a přidejte do ní váš kód. Můžete také přidat odkazy a nahrazující parametry do vašeho kódu. Můžete přidat fragment k instalaci sady Visual Studio pomocí tlačítka Import na Správce fragmentů kódu (**nástroje**, **Správce fragmentů kódu...** ).  
  
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
  
### <a name="to-create-a-code-snippet"></a>K vytvoření fragmentu kódu  
  
1.  Vytvořte nový soubor XML v sadě Visual Studio a přidání šablony uvedené výše.  
  
2.  Zadejte název fragmentu, například "Hello World VB", v názvu elementu.  
  
3.  Zadejte jazyk fragment kódu v jazycích atributu element kódu. V tomto příkladu použijte "VB".  
  
4.  Přidáte kód v oddílu CDATA uvnitř elementu kódu, například:  
  
    ```xml  
    <Code Language="VB">  
        <![CDATA[Console.WriteLine("Hello, World!")]]>  
    </Code>
    ```  
  
5.  Uložte jako VBCodeSnippet.snippet fragmentu.  
  
### <a name="to-add-a-code-snippet-to-visual-studio"></a>Chcete-li přidat fragment kódu pro Visual Studio  
  
1.  Pomocí Správce fragmentů kódu můžete přidat vlastní výstřižky do instalace Visual Studia. Otevřete Správce fragmentů kódu (**nástroje**, **Code fragmenty správce...** ).  
  
2.  Klikněte **Import** tlačítko.  
  
3.  Přejděte do umístění, kam jste uložili fragmentu kódu zobrazeném v předchozím postupu, vyberte ho a klikněte na tlačítko **otevřete**.  
  
4.  **Fragment kódu importu** otevře dialogové okno s výzvou, abyste vybrat místo pro přidání fragmentu z možností v pravém podokně. Jedna z těchto možností by měla být **Moje fragmenty kódu**. Vyberte ho a klikněte na tlačítko **Dokončit**, pak **OK**.  
  
5.  Fragment zkopírován do následujícího umístění:  
  
     %USERPROFILE%\Documents\Visual studio 2017\Code Snippets\Visual Basic\My fragmenty kódu  
  
6.  Otestujte fragment otevřením projektu jazyka Visual Basic a otevření souboru kódu. V souboru zvolte **fragmenty**, **Vložit fragment** z kontextové nabídky, pak **Moje fragmenty kódu**. Měli byste vidět fragment s názvem **Moje fragment kódu jazyka Visual Basic**. Dvojím kliknutím.  
  
    `Console.WriteLine("Hello, World!")`je vložen do souboru kódu.  
  
### <a name="adding-description-and-shortcut-fields"></a>Přidání zástupce pole a popis  
  
1.  Pole Popis zadejte další informace o fragment kódu při zobrazení ve Správci fragmentů kódu. Zástupce je značky, který mohou uživatelé, aby bylo možné vložit fragment. Upravte fragment kódu, který jste přidali otevřením souboru %USERPROFILE%\Documents\Visual Studio 2017\Code Snippets\Visual Basic\My kód Snippet\VBCodeSnippet.snippet.  
  
2.  Přidejte elementy autora a popis pro Header element a vyplňte je.  
  
3.  Header element by měl vypadat přibližně takto:  
  
    ```xml  
    <Header>  
        <Title>Hello World VB</Title>  
        <Author>Myself</Author>  
        <Description>Says Hello to the world.</Description>  
    </Header>
    ```  
  
4.  Otevřete Správce fragmentů kódu a vyberte fragment kódu. V pravém podokně byste měli vidět, teď naplní pole Popis a autor se.  
  
5.  Pokud chcete přidat zástupce, přidáte zástupce element společně se na autora a Description – element:  
  
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
  
### <a name="to-add-references-and-imports"></a>Chcete-li přidat odkazy a importy  
  
1.  Můžete přidat odkaz na projekt pomocí elementu odkazy a přidat deklarace importy pomocí importy elementu. (Tento postup funguje pro jazyk C# také.) Například, pokud změníte `Console.WriteLine` v příkladu kódu k `MessageBox.Show`, budete muset přidat System.Windows.Forms.dll sestavení do projektu.  
  
2.  Otevřete váš fragment kódu.  
  
3.  Přidání odkazů na prvek v rámci elementu fragment kódu:  
  
    ```xml  
    <References>  
        <Reference>  
            <Assembly>System.Windows.Forms.dll</Assembly>  
        </Reference>  
    </References>
    ```  
  
4.  Add – element importy pod elementem fragment kódu:  
  
    ```xml  
    <Imports>  
        <Import>  
           <Namespace>System.Windows.Forms</Namespace>  
        </Import>  
    </Imports>
    ```  
  
5.  V části CDATA změňte na následující:  
  
    ```xml  
    <![CDATA[MessageBox.Show("Hello, World!")]]>  
    ```  
  
6.  Uložte fragmentu.  
  
7.  Otevřete projekt Visual Basic a přidejte fragment.  
  
8.  Zobrazí se příkazu importy v horní části souboru kódu:  
  
    ```vb  
    Imports System.Windows.Forms
    ```  
  
9. Podívejte se na vlastnosti projektu. Na kartě odkazy obsahuje odkaz na System.Windows.Forms.dll.  
  
### <a name="adding-replacements"></a>Přidání nahrazení  
  
1.  Můžete chtít součástí vaší fragmenty kódu nahradit za uživatele, například pokud přidat proměnnou a má uživatel k nahrazení proměnné s jedním v aktuálním projektu. Můžete zadat dva typy náhrady: literály a objekty. Literály jsou řetězce, typu (textové literály, názvy proměnných nebo řetězec reprezentace číselné hodnoty). Objekty jsou instance typu než řetězec. V tomto postupu budete deklarovat literálu náhradní a nahrazení objektu a změnit kód tak, aby odkazovaly tyto nahrazení.  
  
2.  Otevřete váš fragment kódu.  
  
3.  Tento příklad používá připojovací řetězec SQL, takže budete muset změnit elementy importy a odkazy na přidejte příslušné odkazy na:  
  
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
  
4.  Deklarovat literálu náhradní server pro připojovací řetězec SQL, přidejte deklarace prvek v rámci elementu fragment kódu a v ní přidejte pro ID, popis a výchozí hodnota pro nahrazení literálu element s dílčí prvky:  
  
    ```xml  
    <Declarations>  
        <Literal>  
            <ID>SqlConnString</ID>  
            <ToolTip>Replace with a SQL connection string.</ToolTip>  
            <Default>"SQL connection string"</Default>  
        </Literal>  
    </Declarations>
    ```  
  
5.  Deklarovat nahrazení objektu pro připojení k SQL, přidejte element objekt uvnitř elementu deklarace a přidat dílčí prvky pro ID typu objektu, popis a výchozí hodnota. Výsledného prvku deklarace by měl vypadat takto:  
  
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
[Fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md)