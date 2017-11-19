---
title: "Začínáme s testování částí – Vytvoření testovacích plánů | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: unit testing, create unit test plans
ms.assetid: 2171CD69-FBB1-4994-9DCC-3BFFDFD26662
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: 17113215615ff87ef0af611a5bc2061ca0126911
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="get-started-with-unit-testing"></a>Začínáme s testování částí

Pomocí sady Visual Studio můžete definovat a spouštění testů jednotek Udržovat kód stavu, zkontrolujte pokrytí kódu a k nalezení chyb a závad před vašich zákazníků.

<a name="create-tests"></a>
## <a name="create-unit-tests"></a>Vytvářet testy částí

Vytvářet testy částí a spustit je často a ujistěte se, že váš kód pracuje správně.

1. Vytvoření projektu testování částí.
        
   ![Přidání projektu testů jednotek do řešení](media/createunittest1.png)
    
1. Název projektu.
        
   ![Šablona projektu testů jednotek](media/createunittest2.png)
  
   Projekt se přidá do vašeho řešení.
    
   ![Projektu testů jednotek v Průzkumníku řešení](media/createunittest5.png)
    
1. V projektu testování částí přidáte odkaz na projekt, který chcete testovat.
        
   ![Přidat odkaz na vaši projektu testování částí](media/createunittest6.png)
    
1. Vyberte projekt, který obsahuje kód, který budete testovat.
        
   ![Vyberte odkazu pro přidání](media/createunittest7.png)
    
1. Vaše testování částí kódu.

   ![Přidání kódu do vaší testování částí](media/createunittest8.png) 

Můžete také vytvořit testování částí zástupných procedury metoda s [ **vytvořit testování částí** příkaz](create-unit-tests-menu.md).
Nebo můžete použít [různých částí unit test framework](#frameworks) pro vytvoření testů pro jazyky jiný kód.

![Pomocí příkazu Vytvořit testy jednotek](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>Spouštění testování částí

1. Otevřete Průzkumníka testů.
        
   ![V nabídce testovací otevřete Průzkumníka testů](media/rununittest1.png) 

1. Spouštění testů jednotek.
        
   ![Spouštění testů jednotek v Průzkumníka testů](media/rununittest2.png) 

   Uvidíte, že jednotka testy, které předán nebo selhání v Průzkumníka testů.
      
   ![Zkontrolujte výsledky testů jednotek v Průzkumníku testování](media/rununittest3.png) 

## <a name="view-live-unit-test-results"></a>Zobrazení výsledků testů jednotek za provozu

Pokud používáte Mstestu, xUnit nebo NUnit testování framework v Visual Studio 2017 nebo vyšší, uvidíte za provozu výsledky testů jednotek ve Visual Studiu.

1. Zapnout testování z částí za provozu **Test** nabídky.

   ![Zapnout za provozu testování částí](media/live-test-results-start.png) 

1. Zápis a úpravy kódu zobrazte výsledky testů v okně editoru kódu.

   ![Přejděte na položku a klikněte na indikátory výsledků testu](media/live-test-results-ui.png) 

1. Přejděte na položku a klikněte na indikátory výsledků testu zobrazíte další informace.

   ![Zobrazit výsledky testů](media/live-test-results-details.png) 

Další podrobnosti najdete v tématu [Live jednotkové testování v sadě Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2016/11/18/live-unit-testing-visual-studio-2017-rc/).

<a name="intellitest"></a>
## <a name="generate-unit-tests-with-intellitest"></a>Generování testů částí s IntelliTest

Při spuštění IntelliTest snadno uvidíte které testy se nedaří a přidejte všechny nezbytné kód je opravit. Můžete vybrat, které generovaného testů uložit do testovacího projektu zajistit sada regrese. Při změně kódu se znovu spustí IntelliTest pro synchronizaci generovaného testy s vašimi změnami kódu. Další informace, jak zjistit, [generování testů částí kódu s IntelliTest](https://docs.microsoft.com/visualstudio/test/generate-unit-tests-for-your-code-with-intellitest).

![Generování testů jednotek s IntelliTest](media/intellitest.png)

<a name="unit-tests"></a>
## <a name="run-unit-tests-with-test-explorer"></a>Spouštění testů jednotek pomocí Průzkumníka testů

Pomocí Průzkumníka testů spouštění testování částí v sadě Visual Studio nebo projektů testování částí třetích stran, seskupení testů do kategorií, filtrování seznamu testů a vytvořit, uložit a spustit seznamy stop testů. Můžete také ladění testy a analyzovat pokrytí test výkonu a kód. Další informace, jak zjistit, [spouštění testů jednotek pomocí Průzkumníka testů](https://docs.microsoft.com/visualstudio/test/run-unit-tests-with-test-explorer).

![Spouštění testů jednotek pomocí Průzkumníka testů](media/testexplorer.png)

<a name="code-coverage"></a>
## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>Použití pokrytí kódu k určení, kolik kódu se testuje

Funkci pokrytí kódu sady Visual Studio lze použít ke zjištění toho, jaký podíl kódu projektu je skutečně testován kódovanými testy, jako jsou například jednotkové testy. Pro efektivní ochranu před chybami je vhodné testovat, neboli „pokrýt“, velkou část kódu projektu. Další informace, jak zjistit, [použití pokrytí kódu k určení jak mnohem kódu se testuje](https://docs.microsoft.com/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested).

![Použití pokrytí kódu k určení, kolik kódu se testuje](media/codecoverage.png)

## <a name="q--a"></a>Dotazy a odpovědi

<!-- BEGINSECTION class="m-qanda" -->

<a name="frameworks"></a>
####Otázka: lze spustit testy jednotek v sadě Visual Studio je-li použít jinou jednotku test framework?

Odpověď: Ano, použijte modul plug-in dané platformy, že Visual Studio test runner mohli pracovat s dané platformy. Zde jsou některé [testování framework moduly plug-in pro sadu Visual Studio částí](http://go.microsoft.com/fwlink/?LinkID=246630).

1. Pomocí Správce rozšíření sady Visual Studio můžete stáhnout modul plug-in.
        
   ![Vyberte jednotky 3. stran testování moduly plug-in pomocí Správce rozšíření](media/install3rdpartyunittestframeworks1.png) 

1. Stáhnout modul plug-in z Galerie Visual Studio v rámci nástroje/testování nebo vyhledejte, pokud znáte název.
        
   ![Stáhnout modul plug-in](media/install3rdpartyunittestframeworks2.png) 

1. Vytvoření projektu knihovny tříd.
        
   ![Vytvoření projektu knihovny tříd](media/create3rdpartyunittest1.png) 

   Přidejte projekt pro vaše řešení.
    
   ![Název projektu knihovny tříd a přidejte ji](media/create3rdpartyunittest3.png) 

1. V projektu knihovny tříd spusťte NuGet k instalaci modulu plug-in.

   ![Správa balíčků NuGet k instalaci modulu plug-in](media/create3rdpartyunittest3a.png) 

   [NuGet](https://www.nuget.org/) je rozšíření sady Visual Studio, který můžete použít k přidání a aktualizace knihovny a nástroje pro projekty.

1. Nainstalujte modul plug-in. Pokud znáte název, můžete hledat je online.

   ![Nainstalujte rozhraní framework vaší strany 3.](media/create3rdpartyunittest4.png) 

   Rozhraní framework odkazuje ve vašem projektu.
        
   ![Referenční dokumentace pro systém testování částí 3. stran se přidá do vašeho řešení](media/create3rdpartyunittest6.png) 

1. V projektu knihovny tříd přidejte odkaz na projekt, který chcete testovat.
        
   ![Přidat odkaz na projekt](media/createunittest6.png) 

1. Vyberte projekt, který obsahuje kód, který budete testovat.
        
   ![Vyberte kód projekt testování](media/createunittest7.png) 

1. Vaše testování částí kódu.

   ![Přidání kódu do vaší testování částí](media/create3rdpartyunittest7.png)   

<!-- ENDSECTION -->

## <a name="see-also"></a>Viz také

* [Vytvoření příkazu testování částí](create-unit-tests-menu.md)
* [Generování testů s IntelliTest](generate-unit-tests-for-your-code-with-intellitest.md)
* [Spouštění testů pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md)
* [Určení pokrytí kódu](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Zlepšení kvality kódu](improve-code-quality.md)
