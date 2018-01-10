---
title: "Generování testů částí kódu s IntelliTest | Microsoft Docs"
ms.custom: 
ms.date: 2015-10-05
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.UnitTest.CreateIntelliTest
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 4ec391c698a53caa93796634ccf6fd8bf6bdcb41
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="generate-unit-tests-for-your-code-with-intellitest"></a>Generování testů částí kódu s IntelliTest
Jsou zde popsány IntelliTest ke generování testovacích datech a sada testů částí kódu .NET. Pro každý příkaz v kódu, je generována testovací vstup, spustí tento příkaz. Case analýzy se provádí pro každou podmíněného větve v kódu. Například `if` příkazů, kontrolní výrazy a všechny operace, které můžete vyvolat výjimky jsou analyzovány. Této analýze slouží ke generování testovacích dat pro testování částí parametrizované pro každou z vaší metody vytváření testů jednotek s pokrytí vysoké kódu.  
  
 Při spuštění IntelliTest snadno uvidíte které testy se nedaří a přidejte všechny nezbytné kód je opravit. Můžete vybrat, které generovaného testů uložit do testovacího projektu zajistit sada regrese. Při změně kódu se znovu spustí IntelliTest pro synchronizaci generovaného testy s vašimi změnami kódu.  

## <a name="availability-and-extensions"></a>Dostupnost a rozšíření

**Vytvořit IntelliTest** a **spustit IntelliTest** příkazy nabídky:

* Jsou k dispozici v pouze v Enterprise Edition ze sady Visual Studio 2015 a novější.

* Podporují pouze C# kód, který cílí rozhraní .NET Framework.

* Jsou [extensible](#extend-framework)a podporu generování testů v Mstestu, Mstestu V2, NUnit, xUnit formátu.
  
* Nepodporují x64 konfigurace.  
  
## <a name="explore-use-intellitest-to-explore-your-code-and-generate-unit-tests"></a>Prozkoumejte: Použití IntelliTest a prozkoumejte kódu generování testů částí  
 Generování testů částí, vaše typy musí být veřejné. V opačném [vytvářet testy částí](#NoRun) první před generováním je.  
  
1.  Otevřete řešení v sadě Visual Studio. Poté otevřete soubor třídy, který obsahuje metody, které chcete testovat.  
  
2.  Klikněte pravým tlačítkem na metodu ve vašem kódu a vyberte **spustit IntelliTest** pro generování testů částí pro kód ve své metodě.  
  
     ![Pravé & č. 45; klikněte v metodu pro generování testů částí](../test/media/runpex.png "RunPEX")  
  
     IntelliTest spustí kód tolikrát, kolikrát se různé vstupy. Každé spuštění je reprezentována v tabulka zobrazující vstupní testovací data a výsledná výstupní nebo výjimky.  
  
     ![Zobrazí se okno výsledků zkoumání s testy](../test/media/pexexplorationresults.png "PEXExplorationResults")  
  
     Pro generování testů částí pro všechny veřejné metody ve třídě, jednoduše klikněte pravým tlačítkem na třídu, nikoli konkrétní metody. Zvolte **spustit IntelliTest**. Pomocí rozevíracího seznamu v okně výsledky zkoumání můžete zobrazit testy částí a vstupní data pro jednotlivé metody ve třídě.  
  
     ![Výsledky testů, které chcete zobrazit v seznamu vyberte](../test/media/selectpextest.png "SelectPEXTest")  
  
     Pro testy, které předat, zkontrolujte, zda hlášené výsledky ve sloupci výsledek odpovídat vašim požadavkům na váš kód. Testy, které nesplní opravte kódu podle potřeby. Poté znovu spusťte IntelliTest ověření opravy.  
  
## <a name="persist-save-the-unit-tests-as-a-regression-suite"></a>Zachovat: Testování částí uložte jako sada regrese  
  
1.  Vyberte řádky dat, na které chcete uložit s testu parametrizované jednotek do testovacího projektu.  
  
     ![Vyberte testy; p & č. 45; klikněte na tlačítko a zvolte Uložit](../test/media/savepextests.png "SavePEXTests")  
  
     Můžete si zobrazit k testovacímu projektu a parametrizované jednotky test, který byl vytvořen - testování jednotlivých částí, odpovídající každé řádků, se ukládají do. soubor g.cs k testovacímu projektu a testování částí parametrizované je uložen v jeho odpovídající soubor .cs. Můžete spustit testy jednotek a zobrazit výsledky z Průzkumníka testů, stejně jako pro všechny testy jednotek, které jste vytvořili ručně.  
  
     ![Soubor otevřít třídu v testovací metoda zobrazíte testování částí](../test/media/testmethodpex.png "TestMethodPEX")  
  
     Všechny nezbytné odkazy budou přidány také pro projekt test.  
  
     Pokud metoda kód změní, spusťte znovu IntelliTest aby testování částí synchronizovaná se změnami.  
  
## <a name="assist-use-intellitest-to-focus-code-exploration"></a>Assist: Použití IntelliTest k zaměření zkoumání kódu  
  
1.  Pokud máte složitější kódu, IntelliTest pomáhá zajistit s zaměřením zkoumání kódu. Například pokud máte metodu, která má rozhraní jako parametr, a je více než jednu třídu, která implementuje rozhraní, IntelliTest zjistí tyto třídy a sestavy upozornění.  
  
     Zobrazte upozornění k rozhodování, co chcete udělat.  
  
     ![Zobrazit upozornění](../test/media/pexviewwarning.png "PEXViewWarning")  
  
2.  Po zkoumání kódu a pochopit, co chcete testovat, můžete je vyřešit upozornění zvolit které třídy sloužící k testování rozhraní.  
  
     ![P & č. 45; klikněte na upozornění a zvolte opravu](../test/media/pexfixwarning.png "PEXFixWarning")  
  
     Tato volba se přidá do souboru PexAssemblyInfo.cs.  
  
     `[assembly: PexUseType(typeof(Camera))]`  
  
3.  Nyní můžete znovu spustit IntelliTest testovacích dat pouze pomocí třídy, která je pevná a vygenerování testu parametrizované jednotky.  
  
     ![Znovu spustit IntelliTest ke generování testovacích datech](../test/media/pexwarningsfixed.png "PEXWarningsFixed")  
  
## <a name="specify-use-intellitest-to-validate-correctness-properties-that-you-specify-in-code"></a>Zadejte: Použití IntelliTest ověřit správnost vlastnosti, které zadáte v kódu  

Zadejte obecné vztah mezi vstupy a výstupy, které chcete testů generovaného jednotky k ověření. Tato specifikace je zapouzdřený v metodu, která vypadá jako metodu testu, ale je všeobecně kvantifikovány. Toto je metoda testovací parametrizované jednotky a všechny kontrolní výrazy, které provedete musí platit pro všechny možné vstupní hodnoty, které mohou generovat IntelliTest.  
  
##  <a name="QandALink"></a>MODUL OTÁZKY A ODPOVĚDI  
  
### <a name="q-can-you-use-intellitest-for-unmanaged-code"></a>Otázka: je možné použít pro nespravovaného kódu IntelliTest?  

**Odpověď:** Ne, IntelliTest funguje jenom se spravovaným kódem.  
  
### <a name="q-when-does-a-generated-test-pass-or-fail"></a>Otázka: když testu generovaného úspěch nebo selhání?  

**Odpověď:** předává jako další jednotky otestovat, pokud dojde k žádné výjimky. Se nezdaří, pokud žádné kontrolní výraz selže, nebo pokud testovaného kódu vyvolá k neošetřené výjimce.  
  
 Pokud máte test, který může uplynout, pokud nastanou určité výjimky, můžete nastavit jednu z následujících atributů podle svých požadavků na metoda testu, test třídu nebo sestavení úrovně:  
  
-   **PexAllowedExceptionAttribute**  
  
-   **PexAllowedExceptionFromTypeAttribute**  
  
-   **PexAllowedExceptionFromTypeUnderTestAttribute**  
  
-   **PexAllowedExceptionFromAssemblyAttribute**  
  
### <a name="q-can-i-add-assumptions-to-the-parameterized-unit-test"></a>Otázka: je možné přidat předpoklady k testovací parametrizované jednotku?  

**Odpověď:** Ano, použijte k určení, které testovací data se nevyžaduje, pro testování jednotky pro konkrétní metody předpoklady. Použití <xref:Microsoft.Pex.Framework.PexAssume> třída přidat předpoklady. Například můžete přidat předpokládá, že proměnná délky není null takto.  
  
 `PexAssume.IsNotNull(lengths);`  
  
 Pokud přidáte předpokládá a znovu spusťte IntelliTest, odebere se testovací data, která již není relevantní.  
  
### <a name="q-can-i-add-assertions-to-the-parameterized-unit-test"></a>Otázka: je možné přidat kontrolní výrazy k testovací parametrizované jednotku?  

**Odpověď:** Ano, IntelliTest zkontroluje, zda co uplatňujete v příkazu je ve skutečnosti správný při spuštění testování částí. Použití <xref:Microsoft.Pex.Framework.PexAssert> třídu nebo assertion rozhraní API, která se dodává s test framework pro přidání kontrolních výrazů. Například můžete přidat kontrolní výrazy, dvě proměnné, které jsou stejné.  
  
 `PexAssert.AreEqual(a, b);`  
  
 Pokud přidáte kontrolní výrazy a znovu spusťte IntelliTest, zkontroluje, že vaše kontrolní výraz je platná a test se nezdaří, pokud není.  
  
###  <a name="NoRun"></a>Otázka: je možné generování testů částí parametrizované bez spuštění IntelliTest nejprve?  

**Odpověď:** Ano, klikněte pravým tlačítkem na třída nebo metoda, a potom vyberte **vytvořit IntelliTest**.  
  
 ![P & č. 45; klikněte na editor, zvolte Vytvořit IntelliTest](../test/media/pexcreateintellitest.png "PEXCreateIntelliTest")  
  
 Přijměte výchozí formát ke generování testů nebo změnit, jak jsou pojmenované projekt a testy. Můžete vytvořit nový projekt testu nebo uložit testů do existujícího projektu.  
  
 ![Vytvoření IntelliTest pomocí Mstestu výchozí](../test/media/pexcreateintellitestmstest.png "PEXCreateIntelliTestMSTest")  

<a name="extend-framework"></a>  
### <a name="q-can-i-use-other-unit-test-frameworks-with-intellitest"></a>Otázka: je možné použít jiné systémů testů jednotek s IntelliTest?  

**Odpověď:** Ano, postupujte podle těchto kroků [najít a nainstalovat ostatní platformy](../test/install-third-party-unit-test-frameworks.md).
Test framework – rozšíření jsou k dispozici také v Visual Studio Marketplace:

* [Rozšíření NUnit pro Test generátory](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [Rozšíření xUnit.net pro Test generátory](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)


Po restartování sady Visual Studio a znovu otevřete řešení, klikněte pravým tlačítkem na třída nebo metoda, a potom vyberte **vytvořit IntelliTest**. Vyberte nainstalované framework tady:  
  
![Vyberte jiné částí unit test framework pro IntelliTest](../test/media/pexcreateintellitestextensions.png "PEXCreateIntelliTestExtensions")  
  
Spusťte IntelliTest ke generování testování jednotlivých částí v jejich odpovídajících. g.cs soubory.  

  
### <a name="q-can-i-learn-more-about-how-the-tests-are-generated"></a>Otázka: je možné I Další informace o tom, jak jsou generovány testy?  

**Odpověď:** Ano, chcete-li získat základní přehled načíst tato [příspěvku na blogu](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/05/intellitest-one-test-to-rule-them-all.aspx).
