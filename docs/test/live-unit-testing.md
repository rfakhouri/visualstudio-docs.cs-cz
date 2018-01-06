---
title: "Live jednotky testování v sadě Visual Studio | Microsoft Docs"
ms.date: 2017-03-07
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
ms.assetid: 5b51fb96-94f4-4926-92b9-262156c05b85
author: rpetrusha
ms.author: ronpet
ms.workload: dotnet
ms.openlocfilehash: af8e902f4d56d18097e99a06f76958d3bf2fcff2
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="live-unit-testing-with-visual-studio-2017"></a>Testování částí pomocí Visual Studio 2017 za provozu

Jako vyvíjíte aplikaci, Live testování částí automaticky spustí všechny testy jednotek dopad na pozadí a zobrazí výsledky a pokrytí kódu za provozu v prostředí Visual Studio IDE v reálném čase. Úpravou kódu Live testování částí poskytuje zpětnou vazbu na jaký vliv na stávající testy změny a zda nový kód jste přidali se vztahuje na jeden nebo více existujících testů. To vám zápis testů částí při provedení oprav chyb a přidání nových funkcí jemně připomene.

> [!NOTE]
> Testování částí za provozu je k dispozici pro projekty C# a Visual Basic, které cílí na .NET Core nebo rozhraní .NET Framework v Enterprise Edition nástroje Visual Studio 2017.

Při použití Live testování částí pro testy Live testování částí dál data o stavu testů. Schopnost použití trvalých dat umožňuje za provozu testování částí a nabídnout vynikající výkon při spuštění testů dynamicky v reakci na změny kódu.
 
## <a name="supported-test-frameworks"></a>Systémů podporované testování
Za provozu testování částí funguje s tři architektury testování oblíbených jednotky uvedené v následující tabulce. Minimální podporovaná verze jejich adaptérů a architektury je také uvedené v tabulce. Jsou všechny dostupné z NuGet.org architektury testování jednotky.
 
<table> 
<tr>
   <th>Test Framework</th>
   <th>Visual Studio adaptér minimální verze</th>
   <th>Minimální verze Framework</th>
</tr>
<tr>
   <td>xUnit.net</td>
   <td> 2.2.0-beta3-build1187 xunit.Runner.VisualStudio verze</td>
   <td>xunit 1.9.2</td> 
</tr>
<tr>
   <td>NUnit</td>
   <td>NUnit3TestAdapter verzí 3.5.1</td>  
   <td>NUnit verze 3.5.0</td>
</tr>
<tr>
   <td>MSTest</td>
   <td>MSTest.TestAdapter 1.1.4-preview</td>
   <td>MSTest.TestFramework 1.0.5-preview</td>
</tr>
</table>

Pokud máte starší Mstestu na základě projektů testů, které odkazují na `Microsoft.VisualStudio.QualityTools.UnitTestFramework` a můžete si jej nepřejete přesunout do novější balíčky NuGet Mstestu, upgradujte na verzi Visual Studio 2017 verzi 15.4. 

V některých případech budete muset explicitně obnovování balíčků NuGet odkazuje projekty v řešení v pořadí pro Live testování částí pro práci. Musíte buď pomocí tohoto postupu explicitní sestavení řešení (vyberte **sestavení**, **znovu sestavit řešení** nejvyšší úrovně nabídce sady Visual Studio) nebo obnovují se balíčky v řešení (klikněte pravým tlačítkem na řešení a vyberte **obnovení balíčků NuGet**) před povolením testování částí životností. 

#   <a name="configuring-live-unit-testing"></a>Konfigurace testování částí za provozu

Live jednotkové testování můžete nakonfigurovat tak, že vyberete **nástroje**, **možnosti** z nejvyšší úrovně nabídce sady Visual Studio a pak vyberete **Live jednotkové testování** v levém podokně **Možnosti** dialogové okno. Následující obrázek znázorňuje Live testování částí možnosti konfigurace k dispozici v dialogovém okně.

  ![Image](./media/lut-options.png)

Mezi konfigurovatelné možnosti patří:

- Jestli Live testování částí pozastaví při řešení sestavit a ladit
 
- Jestli Live testování částí pozastaví při systému energie z baterie klesne pod zadanou prahovou hodnotu.
- Jestli Live testování částí spustí automaticky při otevření řešení.
- Adresář, do které chcete uložit trvalá data.   
   **Odstranit Data trvalé** tlačítko umožňuje odstranit všechny trvalá data. To je užitečné, když Live testování částí chová nepředvídatelným nebo neočekávané způsobem, což naznačuje, že byla poškozena trvalá data.   
- Interval, po jejímž uplynutí testovacího případu časového limitu; Výchozí hodnota je 30 sekund. 
- Maximální počet procesů testů, které Live jednotkové testování vytváří. 
- Maximální množství paměti, která dokáže zpracovat Live testování částí procesy.
- Úroveň informací zapsána do Live jednotky testování **výstup** okno.   
   Mezi možnosti patří žádné protokolování (**žádné**), chybové zprávy jenom (**chyba**), chybové zprávy a informační zprávy (**informace**, výchozí), nebo všechny podrobnosti (**podrobné** ).

Můžete také zobrazit podrobný výstup v za provozu jednotky testování **výstup** okno přiřadit hodnotu "1" úrovni uživatele systémové proměnné s názvem `VS_UTE_DIAGNOSTICS` a spustit sadu Visual Studio. 

Chcete-li zaznamenat podrobné zprávy MSBuild protokolu ze za provozu testování částí do souboru, nastavte `LiveUnitTesting_BuildLog` proměnnou prostředí individuální k názvu souboru, který se obsahovat protokol.

Jakmile je povoleno Live testování částí (naleznete v části Další [spuštění, pozastavení a ukončení Live testování částí](#starting-pausing-and-stopping-live-unit-testing), můžete také otevřít **možnosti** dialogové okno výběrem **testovací**, **Za provozu testování částí**, **možnosti**.

## <a name="starting-pausing-and-stopping-live-unit-testing"></a>Spuštění, pozastavení a zastavení Live testování částí

Povolit za provozu testování částí výběrem **Test**, **Live testování částí**, **spustit** nejvyšší úrovně nabídce sady Visual Studio. Pokud je povolená Live testování částí, možnosti dostupné v **Live testování částí** nabídky změnu z jednu položku, **spustit**do **pozastavení**, **Zastavit**, a **resetovat Vyčistit**.

> [!NOTE]
> Pokud spustíte Live testování částí v řešení, která nezahrnuje projektu testů jednotek, **pozastavení**, **Zastavit**, a **resetovat čistou** možnosti se zobrazí na **živé Testování částí** nabídce, ale za provozu testování částí se nespustí. **Výstup** okně se zobrazí zpráva, která začíná "žádné podporované testovací adaptéry odkazuje toto řešení..."  

Kdykoli můžete dočasně pozastavit nebo úplně zastavit Live testování jednotky. Můžete to provést, například pokud se právě Refaktoring a vědět, že testy se přeruší nějakou dobu. Nabídky tři možnosti jsou:

- **Pozastavení**, které dočasně pozastaví Live testování jednotky. 
 
    Když Live testování částí je pozastavena, vizualizace vašeho pokrytí nezobrazí v editoru, ale je zachovají všechna data, která nebyla shromážděna. Chcete-li pokračovat, Live testování částí, vyberte **pokračovat** z nabídky Live testování jednotky. Testování částí za provozu nepodporuje potřebné práce, kterou je dostatečné pro všechny úpravy, které byly provedeny, když byla pozastavena a aktualizuje glyfy správně. 

- **Zastavit**, úplně zastavit Live testování jednotky. Všechna data, která se budou shromažďovat v za provozu jednotkové testování zahodí.

- **Resetování Vyčistit**, která zastaví Live testování částí, odstraní trvalá data a restartuje Live testování jednotky.

- **Možnosti**, otevře **možnosti** dialogové okno popsané v [konfigurace Live jednotkové testování](#configuring-live-unit-testing) části.
 
##  <a name="viewing-coverage-visualization-in-the-editor-as-you-type"></a>Zobrazení pokrytí vizualizace v editoru, jako je typ

Jednou povoleno aktualizací Live testování částí, které se každého řádku kódu v editoru Visual Studio ukázat vám, zda kód psaní je předmětem testy částí a zda jsou předávání testů, které se týkají ho.  Následující obrázek znázorňuje řádků kódu se předávání i selhání testy, jakož i řádků kódu, které nejsou předmětem testy. Řádky dekorované se zeleným "✓", se vztahují pouze předávání testů, řádky dekorované červeným "x", se vztahují jeden nebo více testů selhání a řádky dekorované podle blue "➖" nespadají žádné testem.

  ![Image](./media/lut-codewindow.png)

Za provozu, testování částí pokrytí vizualizace je aktualizovat okamžitě, jako je upravit kód v editoru kódu. Při zpracování úprav, vizualizace změny znamenat, že data nejsou aktuální přidáním zaokrouhlí časovač bitovou kopii níže předávání, neúspěšné a nejsou zahrnuté symboly, jak ukazuje následující obrázek.

  ![Image](./media/lut-codeupdating.png)
 
## <a name="getting-information-on-successful-or-failed-tests"></a>Získávání informací o úspěšném nebo neúspěšném testů

Ukazatele myši na symbol úspěšné nebo neúspěšné v okně kód, lze zjistit, kolik testů nedosáhli daného řádku. Pokud kliknete na symbol, zobrazí se stav jednotlivých testů, jak ukazuje následující obrázek:
 
  ![Image](./media/lut-failedinfo.png) 

Kromě názvy a výsledky testů, umožňuje popisku můžete znovu spustit sadu testů, spusťte sadu testů pomocí ladicího programu. Pokud vyberete jeden nebo více testů v popisu tlačítka, můžete také spustit nebo ladění právě tyto testy. To umožňuje ladění testů, aniž by museli opustit okno kódu. Při ladění, kromě sledování žádné zarážky mohou být již nastavena, pozastaví spuštění programu při ladicí program provede [ `Assert` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert) metodu, která vrátí neočekávaný výsledek. 

Po přesunutí ukazatele myši neúspěšných testů v popisu tlačítka, rozšíří poskytnout další informace o selhání, jak je znázorněno na následujícím obrázku. Pokud dvakrát kliknete na neúspěšných testů v popisu tlačítka, můžete přejít přímo na.

  ![Image](./media/lut-failedmsg.png) 

Když přejdete k neúspěšných testů, Live testování částí také vizuálně označuje v podpis metody testy, které byly úspěšně (uvedenými půl úplné kádinky společně s zelená "✓"), se nezdařilo (půl úplné kádinky spolu se zobrazí červený "🞩"), nebo nejsou součástí Live testování částí (půl úplné kádinky společně s blue "➖"). Metody non-test nejsou dekorované symbolem. Následující obrázek znázorňuje všechny čtyři typy metod.
 
  ![Image](media/lut-testsource.png)
 
## <a name="diagnosing-and-correcting-test-failures"></a>Diagnostikování a odstranění selhání při testu

Z neúspěšných testů můžete snadno ladění kódu produktu, proveďte úpravy a pokračovat ve vývoji vaší aplikace. Protože za provozu testování částí běží na pozadí, nemáte, zastavte a restartujte Live testování částí během ladění, upravit a pokračovat cyklu.

Například selhání testu vidět na předchozím obrázku bylo způsobeno nesprávnou předpokládá v metodě test, který vrátí neabecedními znaky `true` když předána <xref:System.Char.IsLower%2A?displayProperty=fullName> metoda. Po jsme opravte metodu test, najít jsme, že všechny testy byly úspěšné. Když jsme se v takovém případě nemáme pozastavení nebo ukončení Live testování jednotky.

## <a name="live-unit-testing-and-test-explorer"></a>Testování částí za provozu a Průzkumníka testů

Obvykle je **testování Explorer** poskytuje rozhraní, které umožňuje spouštět, ladění a analýza výsledků testu. Testování částí za provozu se integruje s **Průzkumníka testů**. Když Live testování jednotky není povolena nebo je zastavena, **testování Explorer** zobrazí stav testování částí poslední čas spuštění testu. Změny kódu zdroje vyžadují, znovu spusťte testy. Pokud je povoleno Live testování částí, stav jednotky se testů v **Průzkumníka testů** je aktualizovat okamžitě. Již nepotřebujete explicitně spouštění testů jednotek. 

> [!NOTE]
> Můžete otevřít **Průzkumníka testů** výběrem **Test**, **Windows**, **Průzkumníka testů** nejvyšší úrovně nabídce sady Visual Studio.  

Můžete si povšimnout v **Průzkumníka testů** okno, které jsou některé testy barevně limitu. Například když povolíte Live testování částí po otevření dříve uloženou projektu, **testování Explorer** okno měl barevně se všechny ale neúspěšných testů, jak ukazuje následující obrázek. V takovém případě Live testování částí se znovu spustit neúspěšných testů, ale ho nebyl znovu spusťte testy úspěšné, protože Live testování částí pro trvalé data označuje, že vzhledem k tomu, že byly testy poslední spuštěné úspěšně nebyly provedeny žádné změny.

  ![Image](media/lut-test-explorer.png)

Můžete znovu spustit všechny testy, které se zobrazují barevně výběrem **spustit všechny** nebo **spustit** možnosti z **Průzkumníka testů** nabídky, nebo vyberte jeden nebo více testů v **Průzkumníka testů** nabídce kliknete pravým tlačítkem a vyberete **spuštění testů vybrané** nebo **ladění vybrané testy** z místní nabídky. Jak testy se spouštějí se vyvolat horní.

Existují určité rozdíly mezi Live testování částí automaticky spuštění a aktualizaci výsledků testů a explicitně testů z **testování Explorer**. Tyto rozdíly patří:

- Spuštěna nebo k ladění testy z okna Průzkumníka testů spustí regulární binární soubory, zatímco Live testování částí spouští instrumentované binární soubory. 
- Za provozu jednotkové testování nevytvoří nové domény aplikace ke spuštění testů, ale spíš spustí testy z výchozí domény. Spouštění testů z **Průzkumníka testů** okno Vytvořit novou doménu aplikace.
- Testování částí za provozu spustí testy v každém testu sestavení postupně. Pokud spouštíte více testů z **Průzkumníka testů** okno a **spuštění testů paralelně** výběru tlačítka, paralelní spuštění testů.

## <a name="live-unit-testing-and-large-solutions"></a>Testování částí za provozu a velké řešení

Pokud má vaše řešení 10 nebo více projektů po spuštění Live testování částí a není žádná trvalá data, nebo když vyberete **Test**, **Live testování částí**, **resetovat čistou** možnost nejvyšší úrovně nabídce sady Visual Studio, Visual Studio zobrazí následující dialogové okno s upozorněním na dynamické zpracování velkého počtu testů v rozsáhlých projektů může vážně ovlivnit výkon. Pokud vyberete **OK**, Live testování částí provede všechny texty v řešení. Pokud vyberete **zrušit**, můžete vybrat testy provést. Informace o tom, jak to udělat, najdete v následující části [zahrnutí a vyloučení testování projektů a testování metody](#including-and-excluding-test-projects-and-test-methods).  

 ![Za provozu dialogu pro rozsáhlých projektů testování částí](media/lut-large-project.png)

## <a name="including-and-excluding-test-projects-and-test-methods"></a>Zahrnutí a vyloučení testování projektů a testování metody

Řešení s mnoha projektů testování můžete řídit co projekty a jaké jednotlivé metody v projektu účastnit Live testování jednotky. Například pokud máte řešení se stovkami projektů testování, můžete vybrat sadu cílových projektů testování k účasti v za provozu testování částí. Existuje několik způsobů, jak to provést, v závislosti na tom, jestli chcete vyloučit všechny testy na projekt nebo řešení, zda chcete zahrnout nebo vyloučit Většina testů, nebo jestli chcete vyloučit testy jednotlivě. Za provozu jednotkové testování uloží stav zahrnutí a vyloučení jako uživatelské nastavení a zapamatuje, když je řešení zavřít a znovu otevřít. 

**S výjimkou všechny testy v projekt nebo řešení**

Vyberte jednotlivé projekty při testech jednotek, proveďte následující kroky po spuštění Live testování částí:

1.  Klikněte pravým tlačítkem v Průzkumníku řešení a zvolte **Live testy**, **vyloučit** vyloučit celé řešení.
1.  Klikněte pravým tlačítkem na každý projekt test, který chcete zahrnout do testů a zvolte **Live testy**, **zahrnout**.

**S výjimkou jednotlivých testů v okně editor kódu**

Okna editoru kódu můžete zahrnout nebo vyloučit jednotlivé testy metody. Klikněte pravým tlačítkem na podpis metody testu v okně editoru kódu a vyberte **Live testy**, **zahrnují [vybranou metodu]**, **Live testy**,  **Vyloučit [vybranou metodu]**, nebo **Live testy**, **vyloučit všechny ale [vybranou metodu]**, kde "vybraný způsob" je název metody, které jste vybrali v kódu okno. 

**S výjimkou testy prostřednictvím kódu programu** 

Můžete použít <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> atribut prostřednictvím kódu programu vyloučené z hlášení jejich pokrytí v za provozu testování částí metody, třídy a struktury.

Můžete také následující atributy z Live testování částí vyloučit jednotlivé metody:

- Pro xUnit:`[Trait("Category", "SkipWhenLiveUnitTesting")]`
- Pro NUnit:`[Category("SkipWhenLiveUnitTesting")]`
- Pro Mstestu:`[TestCategory("SkipWhenLiveUnitTesting")]` 
 
## <a name="see-also"></a>Viz také

[Kód testovací nástroje](https://www.visualstudio.com/vs/testing-tools/)   
[Live Blog testování částí](https://go.microsoft.com/fwlink/?linkid=842514)   
[Live nejčastější dotazy k testování částí](live-unit-testing-faq.md)    
[Channel 9 Video: Testování v aplikaci Visual Studio 2017 za provozu částí](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105)

