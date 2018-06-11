---
title: Visual Studio 2017 pro vývojáře .NET
description: Přehled funkcí Visual Studio 2017 můžete napsat kód lepší .NET rychlejší.
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.date: 01/16/2018
ms.topic: conceptual
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: 4d353e6a9f52a11821799e6d20ec26bcb0045a71
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257469"
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>Visual Studio 2017 produktivitu Příručka pro vývojáře .NET

[Visual Studio 2017](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) umožňuje vývojářům zvýšit produktivitu než kdy dřív! Vylepšili výkon a spolehlivost pro spuštění řešení a zatížení, test zjišťování a zadáním latence. Také jsme přidali a pokročilé funkce, které umožňují rychlejší psaní lepší kódu. Mezi tyto funkce patří: navigace na decompiled sestavení, proměnné Název návrhy, jak budete zadávat, zobrazení hierarchie v **Průzkumníka testů**, přejděte na všechny (**Ctrl** +  **T**) přejděte na soubor nebo typ/člen nebo symbol deklarace inteligentního **pomocníka výjimka**, styl konfigurace a vynucení a mnoho refaktoring kódu a kódu opravy.

Postupujte podle tohoto průvodce k optimalizaci produktivitu.

##  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>Používá Moje klávesové zkratky z jiné rozšíření nebo editor/IDE.

Pokud jsou pocházejících z jiného IDE nebo kódování prostředí, může se stát, některou z následujících přípon užitečné instalaci:

- [EMACS emulace](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [Klávesové zkratky pro Visual Studio (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

Tady jsou oblíbených zkratky v sadě Visual Studio:

| Zástupce (všechny profily) | Příkaz | Popis |
|-|-|-|
| **CTRL**+**T** | Přejděte na všechny | Přejděte na všechny deklarace souboru nebo typ/člen nebo symbol |
| **F12** (také **Ctrl**+**klikněte na tlačítko**) | Přechod na definici | Přejděte do kterých byla definována symbol |
| **CTRL**+**F12** | Přejít na implementaci | Přejděte do jeho různé implementace ze základní typ nebo člen |
| **Posunutí**+**F12** | Najít všechny odkazy | Zobrazit všechny symbol nebo literálu odkazy |
| **CTRL**+**.** (také **Alt**+**zadejte** v profilu C#) | Rychlé akce a refaktoringy | Zobrazit, jaké kód opravy, akce generování kódu, refaktoring nebo jiných rychlé akce jsou k dispozici na výběr kurzoru pozici nebo kód |
| **CTRL**+**D** | Duplicitní řádku | Duplikuje řádek kódu, která kurzor se nachází v (k dispozici v **Visual Studio 2017 verze 15,6 operací** a novější) |
| **Posunutí**+**Alt**+**+**/**-** | Rozbalit/smlouvy výběr | Rozšiřuje nebo zužuje aktuální výběr v editoru (k dispozici v **Visual Studio 2017 verze 15,5** a novější) |
| **CTRL**+**D:** | Snadné spuštění | Hledání všechna nastavení sady Visual Studio |
| **F5** | Spuštění ladění | Spuštění ladění aplikace |
| **CTRL**+**F5** | Spustit bez ladění | Místní spuštění aplikace bez ladění |
| **CTRL**+**tisíc**,**D** (výchozí profil) nebo **Ctrl**+**E**,**D**  (C# profil) | Formátovat dokument | Vyčistí formátování porušení v souboru na základě vašeho znaky, mezery a nastavení odsazení |
| **CTRL**+**\\**,**E** (výchozí profil) nebo **Ctrl**+**W**, **E** (C# profil) | Seznam chyb zobrazit | Zobrazit všechny chyby v dokument, projekt nebo řešení |

> [!NOTE]
> Některá rozšíření odpojení klíčových výchozí sady Visual Studio vazeb. Pokud chcete použít následující příkazy, obnovit výchozí nastavení v sadě Visual Studio vaší klíčových vazeb přechodem na **nástroje** > **nastavení importu a exportu** > **Obnovit vše nastavení** nebo **nástroje** > **možnosti** > **klávesnice** > **resetovat** .

## <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>Potřebuji způsob, jak rychle přejděte na soubory nebo typy.
Visual Studio 2017 má funkci **přejděte na všechny** (**Ctrl**+**T**). Přejděte na všechny umožňuje rychle přejít do souboru, typu, člen nebo symbol deklarace.
- Změňte umístění tohoto panelu Hledat nebo vypnout v za provozu navigační náhledu s **zařízení** ikonu
- Filtrování výsledků pomocí našich syntaxe dotazu (například "t mytype"). Můžete také určit obor vyhledávání právě v aktuálním dokumentu.
- jsou podporovány camelCase odpovídající!

![Přejděte na všechny v sadě Visual Studio](../ide/media/VS2017Guide-go-to-all.png)

## <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>Moje team vynucuje pravidla stylu kódu v našem základu kódu.
Můžete použít *.editorconfig* souboru kodifikovat konvence psaní kódu a jejich přenášet společně s svůj zdroj.
- Doporučujeme nainstalovat [EditorConfig jazyk služeb rozšíření](https://aka.ms/editorconfig) pro přidání a úpravy *.editorconfig* souborů v sadě Visual Studio.
- Podívejte se [dokumentace](https://aka.ms/editorconfigDocs) pro všechny .NET kódování konvence možnosti.
- V tématu [tento gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) příklad *.editorconfig*.

![Vynucení styl kódu v sadě Visual Studio](../ide/media/VSGuide_CodeStyle.png)

## <a name="i-need-more-refactorings-and-code-fixes"></a>Potřebuji další Refaktoring a kód opravy.
Visual Studio 2017 se dodává s velkým množstvím refaktoring, kód generování akcí a kód opravy. Podtržení vlnovkou Red představují chyby, zelená podtržení vlnovkou představují upozornění a tři tečky šedé představují návrhy kódu. Přístupový kód opravy můžete kliknutím na ikonu žárovek/šroubovák nebo stisknutím kombinace kláves **Ctrl**+**.** nebo **Alt**+**zadejte**. Jednotlivé opravy se dodává s preview okno, které ukazuje ukázku kódu rozdílové toho, jak funguje opravu.

- Mezi oblíbené rychlé opravy a refaktoring patří:
  - *Přejmenovat*
  - *Extrahování metody*
  - *Podpis změny metod*
  - *Generování konstruktoru*
  - *Generování metody*
  - *Přesunout do souboru, typu*
  - *Přidání kontroly hodnotu Null*
  - *Přidání parametru*
  - *Odebrání nepotřebných direktiv Using*
  - V další informace naleznete v našem [dokumentace](https://aka.ms/refactorings)
- Psát vlastní kód nebo refaktoring opravy s [Roslyn analyzátorů](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix).
- Několik členy komunity vytvořilo bezplatné rozšíření, která přidat další kód kontroly:
  - [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
  - [SonarLint pro sadu Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
  - [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)

![Refaktoring v sadě Visual Studio](../ide/media/VSGuide_CodeAnalysis.png)

## <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>Potřebuji použití najít, přejděte k implementaci, přejděte k Decompiled sestavení
Visual Studio 2017 obsahuje mnoho funkcí pro usnadnění hledání a přejděte vaší základu kódu. Další informace o [Code vlastnosti navigace](../ide/navigating-code.md)

| Funkce | Zástupce | Podrobnosti nebo vylepšení |
|- | - | -|
| Najít všechny odkazy | **Posunutí**+**F12**| Výsledky jsou obarvené a lze seskupovat podle projektu, definice atd. Je také možné "zamknout" výsledky. |
| Přejít na implementaci | **CTRL**+**F12** | Můžete přejít k definici na `override` – klíčové slovo a přejděte do přepsaného člena |
| Přechod na definici | **F12** nebo **Ctrl**+**klikněte na**| Podržte **Ctrl** při kliknutí na k navgiate na definici |
| Funkce Náhled definice | **ALT**+**F12** | Vložené zobrazení definice |
| Struktura Vizualizéru | Šedé, s tečkami čáry mezi složené závorky | Pozastavte ukazatel myši zobrazíte strukturu kódu |
| Navigace na decompiled sestavení | **F12** nebo **Ctrl**+**klikněte na** | Přejděte na externí zdroj (decompiled s ILSpy) povolením funkce: **nástroje** > **možnosti** > **textového editoru**  >  **C#** > **Upřesnit** > **přepínat na decompiled zdroje**. |

![Přejděte na všechny a najít všechny odkazy](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="i-want-to-run-and-see-my-unit-tests"></a>Chcete spustit a najdete v části Moje testování částí.
V aplikaci Visual Studio 2017 jsme provedli mnoho vylepšení testování prostředí. Použijte některý z našich testování pomocí Mstestu v1, v2 Mstestu, NUnit nebo XUnit částí testování architektury.
- **Testování Explorer** testu zjišťování je rychlé ve verzi 15,6 operací (pro nejlepších výsledků dosáhnete, upgrade na nejnovější verzi adaptéru test).
- Uspořádání testů v Průzkumníka testů pomocí našeho nového *hierarchické řazení* ve verzi 15,6 operací.
- [Testování částí za provozu](../test/live-unit-testing.md) nepřetržitě spustí testy dopad změny kódu a aktualizace vložených editor ikony pokaždé stav testy. Zahrnout nebo vyloučit konkrétní testy nebo testování projektů z vaší *Live testování nastavit*.

![Zobrazení hierarchie pro Explorer Text v sadě Visual Studio](../ide/media/VSGuide_Testing.png)

## <a name="i-want-to-debug-my-code"></a>Chci ladění můj kód.
Přidali jsme tuny nové schopnosti ladění ve Visual Studio 2017.
- *Spustit a klikněte na tlačítko* umožňuje najeďte vedle řádek kódu, stiskněte tlačítko zelené ikony 'play', který se zobrazí, a spusťte svůj program, dokud nebude dosaženo daného řádku.
- Nové **pomocníka výjimka** PUT nejdůležitější informace, jako který proměnné je null v výjimky NullReferenceException na nejvyšší úrovni v dialogovém okně.
- [Krok zpět](../debugger/how-to-use-intellitrace-step-back.md) ladění můžete přejít zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti.
- [Ladění snímku](/azure/application-insights/app-insights-snapshot-debugger) umožňuje prozkoumat stav za provozu webové aplikace se momentálně došlo k výjimce (musí být v Azure).

![Nového pomocníka výjimka v VS2017](../ide/media/VSGuide_Debugging.png)

## <a name="i-want-to-use-version-control-with-my-projects"></a>Chci použití správy verzí s projekty.
Git nebo TFVC slouží k ukládání a aktualizujte kód v sadě Visual Studio.
- Uspořádání místní změny s **Team Explorer** a použít ke sledování čeká na potvrzení a změny stavový řádek.
- Nastavte průběžnou integraci a doručení pro projekty v sadě Visual Studio s naše [nastavené průběžné doručování tools pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) rozšíření a přijmout, pracovní postup agile developer.

![Správa zdrojového kódu v sadě Visual Studio](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-do-i-need-to-know-about"></a>Jaké další funkce potřebujete vědět o?
Tady je seznam funkcí editoru a produktivitu pro efektivní psaní kódu. Některé funkce možná muset povolit, protože jsou vypnout výchozím (se mohou indexu věci na váš počítač, jsou sporná nebo jsou aktuálně experimentální).

| Funkce | Podrobnosti | Postup povolení |
|-|-|-|
| Vyhledejte soubor v Průzkumníku řešení | Označuje aktivní soubor v Průzkumníku řešení | **Nástroje pro** > **možnosti** > **projekty a řešení** > **sledovat Active položky v Průzkumníku řešení** |
| Přidání direktiv using pro typy v referenční sestavení a balíčky NuGet | Zobrazuje žárovek s opravy kódu se nainstalovat balíček NuGet pro typ neregistrované | **Nástroje pro** > **možnosti** > **textového editoru** > **C#** > **Upřesnit**   >  **Navrhnout direktiv using pro typy v referenční sestavení** a **navrhnout direktiv using pro typy v balíčků NuGet** |
| Povolit úplnou analýzu řešení | Zobrazit všechny chyby ve vašem řešení v **seznam chyb** | **Nástroje pro** > **možnosti** > **textového editoru** > **C#** > **Upřesnit**   >  **Povolit úplnou analýzu řešení** |
| Povolení navigace na decompiled zdroje | Povolit přejít k definici na typy nebo členy z externích zdrojů a ILSpy decompiler znázornit těla – metoda | **Nástroje pro** > **možnosti** > **textového editoru** > **C#** > **Upřesnit**   >  **Přepínat na decompiled zdroje** |
| Režim dokončení/návrhu | Změny chování při dokončování IntelliSense--vývojářům IntelliJ pozadí mají tendenci se měnit nastavení sem z výchozího | **Nabídky** > **upravit** > **IntelliSense** > **přepnout režim dokončení** |
| [Codelensu](../ide/find-code-changes-and-other-history-with-codelens.md) | Zobrazí kód referenční informace a změnit historie v editoru | **Nástroje pro** > **možnosti** > **textového editoru** > **všechny jazyky**  >   **Codelensu** |
| [Fragmenty kódu](../ide/visual-csharp-code-snippets.md) | Nápověda se zakázaným inzerováním na běžné standardní |  Zadejte název fragmentu kódu a stiskněte klávesu **kartě** dvakrát. |

![Fragmenty kódu v sadě Visual Studio](../ide/media/VSGuide_SmartEditor.png)

## <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>Chybí funkce, která vám umožňuje produktivní nebo právě probíhá nízký výkon?
Chcete nám sdělit svůj názor několika způsoby:
- Žádosti o funkce rozhraní .NET můžete selhala na našem [úložiště GitHub](https://github.com/dotnet/roslyn/issues).
- Žádosti o funkce Visual Studio, chyb a problémů s výkonem můžete podává pomocí **odeslat zpětnou vazbu** ikonu v pravé horní okna aplikace Visual Studio.