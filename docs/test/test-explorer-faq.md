---
title: "Visual Studio Průzkumníka testů – nejčastější dotazy | Microsoft Docs"
ms.date: 1/15/2018
ms.technology: vs-ide-test
ms.topic: article
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
manager: ghogen
ms.openlocfilehash: 1ca63ce299cb95546100e7f7ce7f98eb1c1616c2
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio Průzkumníka testů – nejčastější dotazy

## <a name="test-discovery"></a>Test zjišťování

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-are-dynamically-defined-for-example-theories-custom-adapters-custom-traits-ifdefs-etc-how-can-i-discover-these-tests"></a>1. Průzkumníka testů není zjišťování Moje testů, které jsou definovány dynamicky. (Například teorií vlastní adaptéry, vlastní vlastnosti, #ifdefs, atd.) Jak mohou zjistit tyto testy?

  Sestavení projektu a zajistěte, aby na základě sestavení zjišťování zapnutý **nástroje > Možnosti > Test**.

  [Test zjišťování reálném čase](https://go.microsoft.com/fwlink/?linkid=862824) je zjišťování testů založené na zdroje. Ho nemůže najít testy, které používají teorií, vlastní adaptéry, vlastní vlastnosti `#ifdef` příkazy, protože jsou definovány v době běhu apod. Sestavení je vyžadována pro tyto testy mají být zjišťované přesně. V 15.6 verze Preview sestavení na základě zjišťování (tradiční discoverer) se spustí až po sestavení. Toto nastavení znamená zjištění testovací reálném čase zjistí tolik testy, jak můžete při úpravách a zjišťování na základě sestavení umožňuje dynamicky definované testy se objeví po sestavení. Test zjišťování reálném čase zlepšuje odezvu, ale nepřesahuje umožňují získat úplné a přesné výsledky po sestavení.

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2. Jaké '+' (symbol, který se zobrazí v horní řádek Průzkumníka testů střední plus)?

  '+' (A) symbol označuje další testy mohou být zjištěny po sestavení tak dlouho, dokud zjišťování na základě sestavení je zapnutý. Zobrazí se Pokud dynamicky definované, že testy jsou zjištěna v projektu.

  ![Souhrn řádku symbol plus](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3. Zjišťování na základě sestavení již nefunguje pro moje projekt. Jak lze zapnout ji zpět na?

  Přejděte na **nástroje > Možnosti > Test** a zaškrtněte políčko pro **kromě zjistit testů z předdefinovaných sestavení po sestavení.**

  ![Možnosti založené na sestavení](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4. Testy se teď zobrazují v Průzkumníka testů při psaní, aniž by museli sestavení projektu. Co se změnilo?

  Tato funkce je volána [reálném čase testu zjišťování](https://go.microsoft.com/fwlink/?linkid=862824). Analyzátor Roslyn používá ke zjištění testy a naplnit Průzkumníka testů v reálném čase, aniž by bylo potřeba sestavení projektu. Další informace o chování testu zjišťování pro dynamicky definované testy například teorií nebo vlastní vlastnosti najdete v části Nejčastější dotazy k č. 1.

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5. Jaké jazyků a rozhraní test můžete použít zjišťování testování reálném čase?

  [Test zjišťování reálném čase](https://go.microsoft.com/fwlink/?linkid=862824) funguje pouze pro spravované jazyky (C# a Visual Basic), protože je sestaven pomocí Roslyn kompilátoru. Prozatím se reálném čase testu zjišťování funguje výhradně u xUnit, NUnit a Mstestu architektury.

### <a name="6-how-can-i-turn-on-logs-for-the-test-explorer"></a>6. Jak se můžete zapnout na protokoly pro Průzkumníka testů?

  Přejděte na **nástroje > Možnosti > Test** a najdete v části protokolování existuje.

### <a name="7-why-are-my-tests-in-uwp-projects-not-discovered-until-i-deploy-my-app"></a>7. Proč se Moje testů v projekty UWP nezjištěné dokud nasadit mé aplikace?

  Testy UWP cíle jiný modul runtime při nasazení aplikace. To znamená, že ke zjišťování testů přesně pro projekty UWP nejen potřebujete sestavení projektu, ale také nasadit.

### <a name="8-how-does-sorting-test-results-work-in-the-hierarchy-view"></a>8. Jak funguje řazení výsledků testů v zobrazení hierarchie?

  Zobrazení hierarchie seřadí testy abecedně jako naproti tomu mají podle výsledek. Jiné skupiny nastavením normálně seřadit výsledky testů výsledek a pak podle abecedy. Pomocí možností na následujícím obrázku pro porovnání najdete v jiné skupině. Můžete poskytnout zpětnou vazbu návrh [v potíže Githubu](https://github.com/Microsoft/vstest/issues/1425).

  ![SortingExamples](media/testex-sortingex.png)

### <a name="9-in-the-hierarchy-view-there-are-passed-failed-skipped-and-not-run-icons-next-to-the-project-namespace-and-class-groupings-what-do-these-icons-mean"></a>9. V zobrazení hierarchie existuje jsou předány, selhalo, bylo vynecháno a není spuštění ikonami vedle projektu, Namespace a třída seskupení. Co znamenají tyto ikony?

  Ikony vedle seskupení projektu, Namespace a třída odrážející stav testů v rámci tohoto seskupení. Najdete v následující tabulce.

  ![Ikony hierarchie Průzkumníka testů](media/testex-hierarchyicons.png)

## <a name="features"></a>Funkce

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>Jak lze zapnout funkci příznaky vyzkoušet nové funkce testování?

Funkce příznaky se používají pro odeslání experimentální nebo nedokončených součástí produktu avid uživatelům, kteří chtěli váš názor dříve, než funkce dodáte oficiálně. Může se destabilizovat prostředí IDE. Je používejte jenom v bezpečném vývojových prostředí, jako jsou virtuální počítače. Funkce příznaky jsou vždy použijte vaše vlastníte rizikového nastavení. Můžete zapnout s povolenými experimentálními funkcemi [rozšíření funkce příznaky](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension), nebo prostřednictvím příkazového řádku vývojáře.

![Příznak rozšíření funkce](media/testex-featureflag.png)

Chcete-li zapnout funkci příznak prostřednictvím příkazového řádku vývojáře Visual Studia, použijte následující příkaz. Změňte cestu k nainstalovaným Visual Studio v počítači a změňte klíč registru pro příznak požadované funkce.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise” HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Příznak pomocí stejného příkazu můžete vypnout pomocí hodnoty 0 namísto 1 po dword.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [Vytváření a spouštění testování částí pro existujícího kódu](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [Testování částí kódu](unit-test-your-code.md)
- [Nejčastější dotazy k funkci Live Unit Testing](live-unit-testing-faq.md)