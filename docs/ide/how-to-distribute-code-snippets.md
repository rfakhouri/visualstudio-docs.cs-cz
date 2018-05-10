---
title: 'Postupy: distribuce fragmentů kódu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, distributing
ms.assetid: 5f717abd-e167-47ae-818c-6b0bae100ceb
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1841dc30fce8e3799191ff9e2d91b94c7d8ac96b
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-distribute-code-snippets"></a>Postupy: distribuce fragmentů kódu

Můžete poskytnout vaše fragmenty kódu přátelům a mít je instalace fragmenty kódu v jejich počítačích pomocí Správce fragmentů kódu. Ale pokud máte několik fragmenty kódu k distribuci nebo chcete je poměrně distribuovat, můžete zahrnout souboru fragment kódu v rozšíření sady Visual Studio, kteří uživatelé sady Visual Studio můžete nainstalovat.

Chcete-li vytvořit rozšíření Visual Studia, je nutné nainstalovat sadu Visual Studio SDK. Najít verzi VSSDK, který odpovídá instalace Visual Studia na [Visual Studio stáhne](https://www.visualstudio.com/downloads/).

## <a name="set-up-the-extension"></a>Nastavit rozšíření

V tomto postupu budeme používat stejné fragment kódu Hello, World vytvořené v [návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md). Nemůžeme se zadat *.snippet* text, takže není nutné přejít zpět a si ho.

1.  Vytvoření nového projektu VSIX s názvem **TestSnippet**. (**Soubor** > **nové** > **projektu** > **Visual C# (nebo Visual Basic)**  >  **Rozšiřitelnost**.)

2.  V **TestSnippet** projekt, přidejte nový soubor XML a pojmenujte ji *VBCodeSnippet.snippet*. Nahraďte obsah s následujícími službami:

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

### <a name="set-up-the-directory-structure"></a>Nastavit strukturu adresáře

1.  V **Průzkumníku řešení**, vyberte uzel projektu a přidejte složku, která má název, který chcete fragment kódu na **Správce fragmentů kódu**. V takovém případě by měla být **HelloWorldVB**.

2.  Přesunout *.snippet* do souboru *HelloWorldVB* složky.

3.  Vyberte *.snippet* v soubor **Průzkumníku řešení**a v **vlastnosti** okno zajistěte, aby **akce sestavení** je nastaven na **Obsahu**, **kopírovat do výstupního adresáře** je nastaven na **vždy Kopírovat**, a **zahrnout do VSIX** je nastaven na **true**.

### <a name="add-the-pkgdef-file"></a>Přidejte soubor .pkgdef

1.  Přidat na vytvoření textového souboru *HelloWorldVB* složku a pojmenujte ji *HelloWorldVB.pkgdef*. Tento soubor se používá k přidání určité klíče registru. V takovém případě přidá nový klíč pro:

     `HKCU\Software\Microsoft\VisualStudio\15.0\Languages\CodeExpansions\Basic`

2.  Přidejte následující řádky do souboru.

    ```txt
    // Visual Basic
    [$RootKey$\Languages\CodeExpansions\Basic\Paths]
    "HelloWorldVB"="$PackageFolder$"
    ```

    Pokud si projdete tento klíč, najdete v části Určení různé jazyky.

3.  Vyberte *.pkgdef* v soubor **Průzkumníku řešení**a v **vlastnosti** okno zajistěte, aby **akce sestavení** je nastaven na **Obsahu**, **kopírovat do výstupního adresáře** je nastaven na **vždy Kopírovat**, a **zahrnout do VSIX** je nastaven na **true**.

4.  Přidat *.pkgdef* souboru jako prostředek v manifestu VSIX. V *source.extension.vsixmanifest* souboru, přejděte na **prostředky** a klikněte na **nový**.

5.  V **přidat nový prostředek** dialogové okno, sada **typ** k **Microsoft.VisualStudio.VsPackage**, **zdroj** k **souboru na systém souborů**a **cesta** k **HelloWorldVB.pkgdef** (což by se zobrazují v rozevírací nabídce).

### <a name="test-the-snippet"></a>Testování fragmentu

1.  Teď můžete se ujistěte, že funguje fragmentu kódu zobrazeném v experimentální instanci sady Visual Studio. Experimentální instance je druhé kopie sady Visual Studio, která je oddělená od toho, který slouží k zápisu kódu. Umožňuje pracovat na rozšíření, aniž by to ovlivnilo vývojového prostředí.

2.  Sestavte projekt a spusťte ladění. Druhou instanci sady Visual Studio by se zobrazit.

3.  V experimentální instance, přejděte do **nástroje > Správce fragmentů kódu** a nastavte **jazyk** k **základní**. Měli byste vidět *HelloWorldVB* jako jednou ze složky a bude schopen rozbalte složku zobrazíte *HelloWorldVB* fragment kódu.

4.  Otestujte fragmentu. V experimentální instanci otevřete projektu jazyka Visual Basic a otevřete ho soubory kódu. Umístěte kurzor někde v kódu, klikněte pravým tlačítkem a v nabídce klikněte na kontext **Vložit fragment**.

5.  Měli byste vidět *HelloWorldVB* jako jedna ze složek. Dvojím kliknutím. Měli byste vidět automaticky otevíraného okna **Vložit fragment: HelloWorldVB >** rozevírací seznam s **HelloWorldVB**. Klikněte **HelloWorldVB** rozevíracího seznamu. Měli byste vidět na následujícím řádku přidat do souboru:

    ```vb
    Console.WriteLine("Hello, World!")
    ```

## <a name="see-also"></a>Viz také

- [Fragmenty kódu](../ide/code-snippets.md)