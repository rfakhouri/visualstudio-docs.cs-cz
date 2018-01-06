---
title: "Postupy: distribuce fragmentů kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code snippets, distributing
ms.assetid: 5f717abd-e167-47ae-818c-6b0bae100ceb
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 39f6006ec6dfe754efc58f2ccdc7b09d803de6b3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-distribute-code-snippets"></a>Postupy: Distribuce fragmentů kódu
Jednoduše můžete poskytnout vaše fragmenty kódu přátelům a jejich instalace fragmenty kódu v jejich počítačích pomocí Správce fragmentů kódu. Ale pokud máte několik fragmenty kódu k distribuci nebo chcete je poměrně distribuovat, můžete zahrnout souboru fragment kódu v rozšíření sady Visual Studio, kteří uživatelé sady Visual Studio můžete nainstalovat.  

Chcete-li vytvořit rozšíření Visual Studia, je nutné nainstalovat sadu Visual Studio SDK. Najít verzi VSSDK, který odpovídá instalace Visual Studia na [Visual Studio stáhne](https://www.visualstudio.com/downloads/).  

## <a name="setting-up-the-extension"></a>Nastavení rozšíření  
V tomto postupu budeme používat stejné fragment kódu Hello, World vytvořené v [návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md). Poskytne jsme .snippet text, takže není nutné přejít zpět a si ho.  

1.  Vytvoření nového projektu VSIX s názvem **TestSnippet**. (**Soubor**, **nové**, **projektu**, **Visual C# (nebo Visual Basic)**, **rozšiřitelnost**.)  

2.  V **TestSnippet** projekt, přidejte nový soubor XML a pojmenujte ji **VBCodeSnippet.snippet**. Nahraďte obsah s následujícími službami:  

    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <CodeSnippets  
        xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
      <CodeSnippet Format="1.0.0">  
        <Header>  
          <Title>Hello World VB</Title>  
          <Shortcut>HelloWorld</Shortcut>  
          <Description>Inserts code</Description>  
          <Author>MSIT</Author>  
          <SnippetTypes>  
            <SnippetType>Expansion</SnippetType>  
            <SnippetType>SurroundsWith</SnippetType>  
          </SnippetTypes>  
        </Header>  
        <Snippet>  
          <Code Language="VB">  
            <![CDATA[Console.WriteLine("Hello, World!")]]>  
          </Code>  
        </Snippet>  
      </CodeSnippet>  
    </CodeSnippets>  
    ```  

#### <a name="setting-up-the-directory-structure"></a>Nastavení strukturu adresáře  

1.  V Průzkumníku řešení vyberte uzel projektu a přidejte složku, která má název, který chcete fragment kódu tak, aby měl ve Správci fragmentů kódu. V takovém případě by měl být **HelloWorldVB**.  

2.  Soubor .snippet přesunout **HelloWorldVB** složky.  

3.  V Průzkumníku řešení a vyberte soubor .snippet **vlastnosti** okno zajistěte, aby **akce sestavení** je nastaven na **obsahu**, **kopírování výstupu do mezipaměti Adresář** je nastaven na **vždy Kopírovat**, a **zahrnout do VSIX** je nastaven na **true**.  

#### <a name="adding-the-pkgdef-file"></a>Přidání souboru .pkgdef  

1.  Přidat na vytvoření textového souboru **HelloWorldVB** složku a pojmenujte ji **HelloWorldVB.pkgdef**. Tento soubor se používá k přidání určité klíče registru. V takovém případě přidá nový klíč k  

     **HKCU\Software\Microsoft\VisualStudio\15.0\Languages\CodeExpansions\Basic**.  

2.  Přidejte následující řádky do souboru.  

    ```  
    // Visual Basic   
    [$RootKey$\Languages\CodeExpansions\Basic\Paths]   
    "HelloWorldVB"="$PackageFolder$"  
    ```  

    Pokud si projdete tento klíč, najdete v části Určení různé jazyky.  

3.  V Průzkumníku řešení a vyberte soubor .pkgdef **vlastnosti** okno zajistěte, aby **akce sestavení** je nastaven na **obsahu**, **kopírovat do výstupního adresáře**  je nastaven na **vždy Kopírovat**, a **zahrnout do VSIX** je nastaven na **true**.  

4.  Přidejte soubor .pkgdef jako prostředek v manifestu VSIX. V souboru source.extension.vsixmanifest, přejděte na **prostředky** a klikněte na **nový**.  

5.  V **přidat nový prostředek** dialogové okno, sada **typ** k **Microsoft.VisualStudio.VsPackage**, **zdroj** k **souboru na systém souborů**a **cesta** k **HelloWorldVB.pkgdef** (což by se zobrazují v rozevírací nabídce).  

### <a name="testing-the-snippet"></a>Testování fragmentu  

1.  Teď můžete se ujistěte, že funguje fragmentu kódu zobrazeném v experimentální instanci sady Visual Studio. Experimentální instance je druhé kopie sady Visual Studio, která je oddělená od toho, který slouží k zápisu kódu. Umožňuje pracovat na rozšíření, aniž by to ovlivnilo vývojového prostředí.  

2.  Sestavte projekt a spusťte ladění. Druhou instanci sady Visual Studio by se zobrazit.  

3.  V experimentální instance, přejděte do **nástroje / kód Správce fragmentů** a nastavte **jazyk** k **základní**. Měli byste vidět HelloWorldVB jako jedna ze složek a nyní byste měli mít rozbalte složku zobrazíte fragmentu HelloWorldVB.  

4.  Otestujte fragmentu. V experimentální instanci otevřete projektu jazyka Visual Basic a otevřete ho soubory kódu. Umístěte kurzor někde v kódu, klikněte pravým tlačítkem a v nabídce klikněte na kontext **Vložit fragment**.  

5.  Měli byste vidět HelloWorldVB jako jedna ze složek. Dvojím kliknutím. Měli byste vidět automaticky otevíraného okna **Vložit fragment: HelloWorldVB >** rozevírací seznam s **HelloWorldVB**. Klikněte na rozevírací seznam HelloWorldVB. Měli byste vidět na následujícím řádku přidat do souboru:  

    ```vb  
    Console.WriteLine("Hello, World!")  
    ```  

## <a name="see-also"></a>Viz také  
[Fragmenty kódu](../ide/code-snippets.md)
