---
title: Průzkumník testů sady Visual Studio – nejčastější dotazy
ms.date: 1/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Test Explorer
- Test window
- Visual Studio Test Explorer
- summary line
- unit tests
- Test Explorer FAQ
ms.author: kehavens
ms.workload:
- multiple
author: kendrahavens
manager: douge
ms.openlocfilehash: 4ac7aa7d9fbbf4e6f6ffbe5eafd82ff8f1e0bc44
ms.sourcegitcommit: e04e52bddf81239ad346efb4797f52e38de5cb98
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/27/2018
ms.locfileid: "43054553"
---
# <a name="visual-studio-test-explorer-faq"></a>Průzkumník testů sady Visual Studio – nejčastější dotazy

## <a name="dynamic-test-discovery"></a>Zjišťování dynamických testů
**Průzkumník testů není zjišťování mých testů, které jsou definována dynamicky. (Například teorie, vlastní adaptéry, vlastní vlastnosti, #ifdefs atd.) Jak lze zjistit tyto testy?**

  Sestavení projektu a ujistěte se, že je zapnuté zjišťování na základě sestavení **nástroje** > **možnosti** > **Test**.

  [Zjišťování testů v reálném čase](https://go.microsoft.com/fwlink/?linkid=862824) je založen zdroj testu zjišťování. Ho nelze zjistit testy, které používají teorie, vlastní adaptéry, vlastní vlastnosti `#ifdef` příkazy, atd. protože jsou definovány v době běhu. Sestavení je vyžadován pro tyto testy mají být zjišťované, přesně. V 15.6 Preview spustí zjišťování na základě sestavení (tradiční prozkoumání) až po sestavení. Toto nastavení znamená, že zjišťování testů v reálném čase zjistí libovolný počet testů, jak lze při úpravách a zjišťování na základě sestavení umožňuje dynamicky definované testů se zobrazí po sestavení. Zjišťování testů v reálném čase zlepšuje odezvu, ale nepřesahuje umožňují získat úplných a přesných výsledků po sestavení.

## <a name="test-explorer--plus-symbol"></a>Průzkumník testů "+" (plus) symbol
**Co dělá "+" (plus) symbol, který se zobrazí v horní zobrazený řádek znamená Průzkumník testů?**

  "+" (Plus) symbol označuje, že další testy mohou být zjištěny po sestavení, tak dlouho, dokud je zapnuté zjišťování na základě sestavení. Se zobrazí, pokud je definována dynamicky, že testy se zjistí ve vašem projektu.

  ![Souhrn řádku znaménko plus](media/testex-plussymbol.png)

## <a name="assembly-based-discovery"></a>Zjišťování na základě sestavení
**Zjišťování na základě sestavení je už nefunguje pro svůj projekt. Jak můžu ho znova zapnout?**

  Přejděte na **nástroje** > **možnosti** > **testovací** a zaškrtněte políčko u **můžete zjistit také ze zkompilovaných sestavení po testy sestavení.**

  ![Možnosti založené na sestavení](media/testex-toolsoptions.png)

## <a name="real-time-test-discovery"></a>Zjišťování testů v reálném čase
**Testy se teď zobrazují v Průzkumníku testů při psaní, aniž byste museli svůj projekt sestavovat. Co se změnilo?**

  Tato funkce se nazývá [zjišťování testů v reálném čase](https://go.microsoft.com/fwlink/?linkid=862824). Roslyn analyzátor používá k zjišťování testů a naplnit Průzkumníka testů v reálném čase, aniž by bylo potřeba svůj projekt sestavit. Další informace o chování zjišťování testů pro dynamicky definované testy, jako je například teorie nebo vlastní vlastnosti naleznete v tématu Nejčastější dotazy k č. 1.

## <a name="real-time-test-discovery-compatibility"></a>Kompatibilita zjišťování testů reálném čase
**Jaké jazyky a rozhraní pro testování můžete použít zjišťováním testů v reálném čase?**

  [Zjišťování testů v reálném čase](https://go.microsoft.com/fwlink/?linkid=862824) funguje pouze pro spravované jazyky (C# a Visual Basic), protože se vytvořil pomocí kompilátoru Roslyn. Prozatím se zjišťování testů v reálném čase funguje jenom pro xUnit, NUnit a MSTest architektur.

## <a name="test-explorer-logs"></a>Protokoly Průzkumníka testů
**Jak můžu zapnout protokolování pro Průzkumník testů?**

  Přejděte do **nástroje** > **možnosti** > **Test** a najdete v části protokolování existuje.

## <a name="uwp-test-discovery"></a>Zjišťování testů UPW
**Proč jsou mé testy v projektech UPW nezjištěné dokud nasadit aplikaci?**

  Testů UPW cílení různých běhových při nasazení aplikace. To znamená, že ke zjišťování testů pro projekty UWP přesně vám nejen na svůj projekt sestavit, ale také nasadit.

## <a name="test-explorer-sorting"></a>Test Explorer řazení
**Jak funguje řazení výsledků testů v zobrazení hierarchie?**

  Hierarchické zobrazení seřadí testy podle abecedy jako a podle výsledku. Podle nastavení skupiny obvykle řazení výsledků testů podle výsledku a pak podle abecedy. Možnosti na následujícím obrázku pro porovnání najdete v jiné skupině. Můžete poskytnout zpětnou vazbu o návrhu [v tento problém Githubu](https://github.com/Microsoft/vstest/issues/1425).

  ![SortingExamples](media/testex-sortingex.png)

## <a name="test-explorer-hierarchy-view"></a>Zobrazení hierarchie Průzkumníka testů
**V okně hierarchie existuje jsou předány, se nezdařilo, přeskočené a nelze spustit ikonami vedle jejich seskupení projektu, Namespace a třídy. Co znamenají tyto ikony?**

  Ikony vedle seskupení projektu, Namespace a třída odrážející stav testů v rámci tohoto seskupení. V následující tabulce.

  ![Ikony hierarchie Průzkumníka testů](media/testex-hierarchyicons.png)

## <a name="search-by-file-path"></a>Hledat podle cesta k souboru
**Do vyhledávacího pole Průzkumníka testů již není filtr "Cesta k souboru".**

Filtr cesty souboru v **Průzkumník testů** vyhledávacího pole byla odebrána v sadě Visual Studio 2017 verze 15.7 preview 3. Tato funkce má málo využívaných a Průzkumník testů může načíst testovací metody rychlejší vyloučením tuto funkci. Pokud se tato změna přerušení tok vývoj, dejte nám prosím vědět zasláním svého názoru na [komunity vývojářů](https://developercommunity.visualstudio.com/).

## <a name="test-adapter-nuget-reference"></a>Testovací adaptér referenční dokumentace pro NuGet
**V sadě Visual Studio 2017 verze 15.8 mé testy se zjistí, ale nemusíte spouštět.**

Všechny projekty testů musí obsahovat testovací adaptér jejich .NET NuGet odkaz v jejich souboru csproj. Pokud ne, zobrazí se následující výstup testu na projekt Pokud zjišťování adaptéru rozšířením test spustí se po sestavení, nebo pokud uživatel pokusí spustit vybrané testy: 

**Projekt testů {} neodkazuje na žádný adaptér NuGet pro rozhraní .NET. Pro tento projekt možná nebude fungovat zjišťování a spouštění testů. Doporučujeme odkaz NuGet adaptéry testu v každém projektu .NET testů v řešení.**

Namísto použití rozšíření adaptérů testů, jsou nutné k použití balíčků adaptéru NuGet testovací projekty. To výrazně zvyšuje výkon a způsobí, že snižuje počet možných problémů s využitím průběžné integrace. Další informace o vyřazení rozšíření adaptér testu .NET v [poznámky k verzi](/visualstudio/releasenotes/vs2017-preview-relnotes#testadapterextension).

## <a name="using-feature-flags"></a>Používání příznaků funkcí
**Jak můžu zapnout příznaky funkcí pro vyzkoušení nové funkce pro testování?**

Příznaky funkcí se používají k odeslání experimentální nebo nedokončené částech tohoto produktu avid uživatelům, kteří by chtěli poskytnout zpětnou vazbu před oficiálním dodávání funkcí. Se může omezit správnou funkci prostředí IDE. Je používejte pouze v nouzovém vývojových prostředích, jako jsou virtuální počítače. Příznaky funkcí jsou vždy použijte your vlastní rizikového nastavení. Můžete zapnout seznámit s experimentálními funkcemi, které se [příznaky funkcí rozšíření](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension), nebo prostřednictvím příkazového řádku pro vývojáře.

![Rozšíření příznak funkce](media/testex-featureflag.png)

Chcete-li zapnout příznak funkce prostřednictvím příkazového řádku pro vývojáře Visual Studio, použijte následující příkaz. Změňte cestu k instalaci sady Visual Studio na svém počítači a změňte klíč registru příznak požadované funkce.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise" HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Příznak s stejný příkaz, můžete vypnout pomocí hodnoty 0 namísto 1 po dword.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [Vytváření a spouštění testů jednotek pro existující kód](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [Testování částí kódu](unit-test-your-code.md)
- [Nejčastější dotazy týkající se testování jednotek za provozu](live-unit-testing-faq.md)
