---
title: Visual Studio 2017 pro vývojáře .NET | Microsoft Docs
description: Přehled funkcí Visual Studio 2017 můžete napsat kód lepší .NET rychlejší.
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.date: 01/16/2018
ms.topic: article
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: 2dac5f48f69ce00ae914929638f08cf35f5a96ac
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>Visual Studio 2017 produktivitu Příručka pro vývojáře .NET

[Visual Studio 2017](https://www.visualstudio.com/downloads/) umožňuje vývojářům zvýšit produktivitu než kdy dřív! Vylepšili výkon a spolehlivost pro spuštění řešení a zatížení, test zjišťování a zadáním latence. Také jsme přidali a pokročilé funkce, které umožňují rychlejší psaní lepší kódu. Mezi tyto funkce patří: navigace na decompiled sestavení, proměnné Název návrhy, jak budete zadávat, zobrazení hierarchie v Průzkumníka testů, přejděte na všechny (**Ctrl + T**) přejděte na soubor nebo typ/člen nebo symbol deklarace inteligentní pomocníka výjimka, konfigurace styl kódu a vynucení a opravy mnoha Refaktoring a kód. 

Postupujte podle tohoto průvodce k optimalizaci produktivitu.

##  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>Používá Moje klávesové zkratky z jiné rozšíření nebo editor/IDE.

Pokud jsou pocházejících z jiného IDE nebo kódování prostředí, může se stát, některou z následujících přípon užitečné instalaci:

- [EMACS emulace](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [HotKeys for Visual Studio (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

![Galerie rozšíření sady Visual Studio](../ide/media/VSIDE_Productivity_Extensibility.png)

Níže jsou uvedeny oblíbených zkratky v sadě Visual Studio. 

> [!NOTE]
> Některá rozšíření odpojení klíčových vazeb výchozí sady Visual Studio, takže je nutné obnovit používat následující příkazy. Obnovit vaše klíčových vazeb na výchozí hodnoty v sadě Visual Studio na webu: **nástroje > Import a Export nastavení > Obnovit nastavení** nebo **nástroje > Možnosti > klávesnice > resetovat**.

| Zástupce (všechny profily) | Příkaz | Popis |
|-|-|-|
| **Ctrl+T** | Přejděte na všechny | Přejděte na všechny deklarace souboru nebo typ/člen nebo symbol |
| **F12** (také **Ctrl + kliknutí**) | Přechod na definici | Přejděte do kterých byla definována symbol |
| **Ctrl+F12** | Přejít na implementaci | Přejděte do jeho různé implementace ze základní typ nebo člen |
| **Shift+F12** | Najít všechny odkazy | Zobrazit všechny symbol nebo literálu odkazy |
| **Ctrl**+**.** (také **Alt + zadejte** v profilu C#) | Rychlé akce a refaktoringy | Zobrazit, jaké kód opravy, akce generování kódu, refaktoring nebo jiných rychlé akce jsou k dispozici na výběr kurzoru pozici nebo kód |
| **Ctrl**+**D** | Duplicitní řádku | Duplikuje řádek kódu, která kurzor se nachází v (k dispozici v **Visual Studio 2017 verze 15,6 operací** a novější) |
| **Posunutí**+**Alt**+**+**/**-** | Rozbalit/smlouvy výběr | Rozšiřuje nebo zužuje aktuální výběr v editoru (k dispozici v **Visual Studio 2017 verze 15,5** a novější) |
| **Ctrl+Q** | Snadné spuštění | Hledání všechna nastavení sady Visual Studio |
| **F5** | Spuštění ladění | Spuštění ladění aplikace |
| **Ctrl+F5** | Spustit bez ladění | Místní spuštění aplikace bez ladění |
| **CTRL + K, D** (výchozí profil) nebo **Ctrl + E, D** (C# profil) | Formátovat dokument | Vyčistí formátování porušení v souboru na základě vašeho znaky, mezery a nastavení odsazení |
| **CTRL +\\, E** (výchozí profil) nebo **Ctrl + W, E** (C# profil) | Seznam chyb zobrazit | Zobrazit všechny chyby v dokument, projekt nebo řešení |

## <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>Potřebuji způsob, jak rychle přejděte na soubory nebo typy.
Visual Studio 2017 má funkci _přejděte na všechny_ (**Ctrl + T**). Přejděte na všechny umožňuje rychle přejít do souboru, typu, člen nebo symbol deklarace.
- Změňte umístění tohoto panelu Hledat nebo vypnout v za provozu navigační náhledu s **zařízení** ikonu
- Filtrování výsledků pomocí našich syntaxe dotazu (například "t mytype"). Můžete také určit obor vyhledávání právě v aktuálním dokumentu.
- jsou podporovány camelCase odpovídající!

![Přejděte na všechny v sadě Visual Studio](../ide/media/VS2017Guide-go-to-all.png)

## <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>Moje team vynucuje pravidla stylu kódu v našem základu kódu.
Můžete použít soubor .editorconfig kodifikovat konvence psaní kódu a jejich přenášet společně s svůj zdroj.
- Doporučujeme nainstalovat [EditorConfig jazyk služby rozšíření](https://aka.ms/editorconfig) pro přidání a úpravy souboru .editorconfig v sadě Visual Studio. 
- Podívejte se [dokumentace](https://aka.ms/editorconfigDocs) pro všechny .NET kódování konvence možnosti.
- V tématu [tento gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) pro .editorconfig příklad.

![Vynucení styl kódu v sadě Visual Studio](../ide/media/VSGuide_CodeStyle.png)

## <a name="i-need-more-refactorings-and-code-fixes"></a>Potřebuji další Refaktoring a kód opravy.
Visual Studio 2017 se dodává s velkým množstvím refaktoring, kód generování akcí a kód opravy. Podtržení vlnovkou Red představují chyby, zelená podtržení vlnovkou představují upozornění a tři tečky šedé představují návrhy kódu. Přístupový kód opravy můžete kliknutím na ikonu žárovek/šroubovák nebo stisknutím kombinace kláves **Ctrl +.** nebo **Alt + zadejte**. Jednotlivé opravy se dodává s preview okno, které ukazuje ukázku kódu rozdílové toho, jak funguje opravu.

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
- Několik členy komunity vytvořilo *volné* rozšíření, které přidat další kód kontroly: 
  - [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
  - [SonarLint for Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
  - [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)

![Refaktoring v sadě Visual Studio](../ide/media/VSGuide_CodeAnalysis.png "VSGuide_CodeAnalysis")

## <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>Potřebuji použití najít, přejděte k implementaci, přejděte k Decompiled sestavení
Visual Studio 2017 obsahuje mnoho funkcí pro usnadnění hledání a přejděte vaší základu kódu. Další informace o [code vlastnosti navigace](../ide/navigating-code.md)

| Funkce | Zástupce | Podrobnosti nebo vylepšení |
|- | - | -| 
| Najít všechny odkazy | **Shift+F12**| Výsledky jsou obarvené a lze seskupovat podle projektu, definice atd. Je také možné "zamknout" výsledky. |
| Přejít na implementaci | **Ctrl+F12** | Můžete přejít k definici na `override` – klíčové slovo a přejděte do přepsaného člena |
| Přechod na definici | **F12** nebo **Ctrl + kliknutí**| Podržte **Ctrl** při kliknutí na k navgiate na definici | 
| Funkce Náhled definice | **Alt+F12** | Vložené zobrazení definice |
| Struktura Vizualizéru | Šedé, s tečkami čáry mezi složené závorky | Pozastavte ukazatel myši zobrazíte strukturu kódu |
| Navigace na decompiled sestavení | **F12** nebo **Ctrl + kliknutí** | Přejděte na externí zdroj (decompiled s ILSpy) povolením funkce: **nástroje > Možnosti > textový Editor > C# > Upřesnit > povolení navigace na decompiled zdroje**. |

![Přejděte na všechny a najít všechny odkazy](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="i-want-to-run-and-see-my-unit-tests"></a>Chcete spustit a najdete v části Moje testování částí.
V aplikaci Visual Studio 2017 jsme provedli mnoho vylepšení testování prostředí. Použijte některý z našich testování pomocí Mstestu v1, v2 Mstestu, NUnit nebo XUnit částí testování architektury.
- *Testování Explorer* testu zjišťování je rychlé ve verzi 15,6 operací (pro nejlepších výsledků dosáhnete, upgrade na nejnovější verzi adaptéru test).
- Uspořádání testů v Průzkumníka testů pomocí našeho nového *hierarchické řazení* ve verzi 15,6 operací.
- [Live testování částí](../test/live-unit-testing.md) nepřetržitě spustí testy dopad změny kódu a aktualizace vložených editor ikony pokaždé stav testy. Zahrnout nebo vyloučit konkrétní testy nebo testování projektů z vaší *Live testování nastavit*.

![Zobrazení hierarchie pro Explorer Text v sadě Visual Studio](../ide/media/VSGuide_Testing.png)

## <a name="i-want-to-debug-my-code"></a>Chci ladění můj kód.
Přidali jsme tuny nové schopnosti ladění ve Visual Studio 2017. 
- *Spustit a klikněte na tlačítko* umožňuje najeďte vedle řádek kódu, stiskněte tlačítko zelené ikony 'play', který se zobrazí, a spusťte svůj program, dokud nebude dosaženo daného řádku. 
- Nové *pomocníka výjimka* PUT nejdůležitější informace, jako který proměnné je null v výjimky NullReferenceException na nejvyšší úrovni v dialogovém okně.
- [Krok zpět](../debugger/how-to-use-intellitrace-step-back.md) ladění můžete přejít zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti.
- [Pořízení snímku ladění](/azure/application-insights/app-insights-snapshot-debugger) umožňuje prozkoumat stav za provozu webové aplikace se momentálně došlo k výjimce (musí být v Azure).

![Nového pomocníka výjimka v VS2017](../ide/media/VSGuide_Debugging.png "VSGuide_Debugging")

## <a name="i-want-to-use-version-control-with-my-projects"></a>Chci použití správy verzí s projekty.
Git nebo TFVC slouží k ukládání a aktualizujte kód v sadě Visual Studio. 
- Uspořádání místní změny s *Team Explorer* a použít ke sledování čeká na potvrzení a změny stavový řádek. 
- Nastavte průběžnou integraci a doručení pro projekty v sadě Visual Studio s naše [průběžné doručování Tools pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) rozšíření a přijmout, pracovní postup agile developer.

![Správa zdrojového kódu v sadě Visual Studio](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-do-i-need-to-know-about"></a>Jaké další funkce potřebujete vědět o?
Tady je seznam funkcí editoru a produktivitu pro efektivní psaní kódu. Některé funkce možná muset povolit, protože jsou vypnout výchozím (se mohou indexu věci na váš počítač, jsou sporná nebo jsou aktuálně experimentální).

| Funkce | Podrobnosti | Postup povolení |
|-|-|-|
| Vyhledejte soubor v Průzkumníku řešení | Označuje aktivní soubor v Průzkumníku řešení | **Nástroje > Možnosti > projekty a řešení > sledovat Active položky v Průzkumníku řešení** |
| Přidání direktiv using pro typy v referenční sestavení a balíčky NuGet | Zobrazuje žárovek s opravy kódu se nainstalovat balíček NuGet pro typ neregistrované | **Nástroje > Možnosti > textový Editor > C# > Upřesnit > navrhnout direktiv using pro typy v referenční sestavení** a **navrhnout direktiv using pro typy v balíčků NuGet** |
| Povolit úplnou analýzu řešení | Zobrazit všechny chyby ve vašem řešení v seznamu chyb | **Nástroje > Možnosti > textový Editor > C# > Upřesnit > povolit úplnou analýzu řešení** |
| Povolení navigace na decompiled zdroje | Povolit přejít k definici na typy nebo členy z externích zdrojů a ILSpy decompiler znázornit těla – metoda | **Nástroje > Možnosti > textový Editor > C# > Upřesnit > povolení navigace na decompiled zdroje** |
| Režim dokončení/návrhu | Změny chování při dokončování IntelliSense--vývojářům IntelliJ pozadí mají tendenci se měnit nastavení sem z výchozího | **Nabídky > Upravit > IntelliSense > Přepnout režim dokončení** |
| [Codelensu](../ide/find-code-changes-and-other-history-with-codelens.md) | Zobrazí kód referenční informace a změnit historie v editoru | **Nástroje > Možnosti > textový Editor > všechny jazyky > Codelensu** |
| [Fragmenty kódu](../ide/visual-csharp-code-snippets.md) | Nápověda se zakázaným inzerováním na běžné standardní |  Zadejte název fragmentu kódu a dvakrát stiskněte, karta'. |

![Fragmenty kódu v sadě Visual Studio](../ide/media/VSGuide_SmartEditor.png)

## <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>Chybí funkce, která vám umožňuje produktivní nebo právě probíhá nízký výkon?
Chcete nám sdělit svůj názor několika způsoby:
- Žádosti o funkce rozhraní .NET můžete selhala na našem [úložiště GitHub](https://github.com/dotnet/roslyn/issues).
- Žádosti o funkce Visual Studio, chyb a problémů s výkonem můžete podává pomocí **odeslat zpětnou vazbu** ikonu v pravé horní okna aplikace Visual Studio.
