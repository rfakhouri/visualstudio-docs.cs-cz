---
title: Pokud chcete zvýšit produktivitu pro vývoj v .NET
description: Přehled analýzy kódu, navigace jednotky testování a další funkce, které vám usnadní vytváření kódu .NET lepší rychleji.
author: kuhlenh
ms.author: gewarren
manager: jillfra
ms.date: 04/25/2019
ms.topic: conceptual
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: f623fd040bdd06b4d9de7c2258c6e907e2953edf
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043419"
---
# <a name="visual-studio-productivity-guide-for-c-developers"></a>Produktivita nástroje Visual Studio Příručka pro C# vývojáře

Zjistěte, jak Visual Studio umožňuje vývojáři produktivnější než kdy dřív. Využijte výhod našich vylepšení výkonu a produktivity jako je navigace na dekompilované sestavení, název proměnné návrhy při psaní, hierarchické zobrazení v **Průzkumník testů**, přejít na všechno (**Ctrl** + **T**) přejděte k souboru/typu/členu/symbolu deklarace, inteligentní **pomocníka výjimky**, konfigurace stylu kódu a vynucení a mnoho refaktoringů a kódu opravy.

## <a name="im-used-to-keyboard-shortcuts-from-a-different-editor"></a>Jsem zvyklý / zvyklá klávesových zkratek z jiný editor

::: moniker range="vs-2017"

**Novinka v sadě Visual Studio 2017 verze 15.8**

::: moniker-end

Pokud přecházíte z jiného integrovaného vývojového prostředí nebo prostředí pro psaní kódu, můžete změnit na schéma klávesnice *Visual Studio Code* nebo *ReSharper (Visual Studio)* :

![Schémata klávesnice v sadě Visual Studio](../ide/media/VS2017Guide-Keyboard.png)

Některá rozšíření nabízí také schémata klávesnice:

- [HotKeys for Visual Studio (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [Emulace (emacs)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

Tady jsou oblíbené klávesové zkratky sady Visual Studio:

| Místní (všechny profily) | Příkaz | Popis |
|-|-|-|
| **Ctrl**+**T** | Přejít na vše | Přejděte na soubor, typ, člen nebo deklarace symbolu |
| **F12** (také **Ctrl**+**klikněte na tlačítko**) | Přejít k definici | Přejděte na kterém je definován symbol |
| **Ctrl**+**F12** | Přejít k implementaci | Přejděte do jeho různé implementace ze základní typ nebo člena |
| **Shift**+**F12** | Najít všechny odkazy | Zobrazí všechny symbol nebo literál odkazy |
| **CTRL**+ **.** (také **Alt**+**zadejte** v profil jazyka C#) | Rychlé akce a refaktoringy | Zobrazit, jaký kód opravy, jsou k dispozici na ukazatel pozice nebo kód výběr akce pro generování kódu, refaktoring nebo jiných rychlé akce |
| **Ctrl**+**D** | Duplicitní řádek | Duplikuje řádku kódu, který se kurzor nachází (k dispozici v **Visual Studio 2017 verze 15.6** a novější) |
| **SHIFT**+**Alt**+ **+** / **-** | Rozbalit/Sbalit výběr | Rozbalíte nebo sbalíte aktuální výběr v editoru (k dispozici v **Visual Studio 2017 verze 15.5** a novější) |
| **SHIFT** + **Alt** +  **.** | Vložit další odpovídající blikajícího kurzoru | Přidá výběr a blikající kurzor na dalším místě, která odpovídá aktuální výběr (k dispozici v **Visual Studio 2017 verze 15.8** a novější) |
| **Ctrl**+**Q** | Hledat | Hledat všechna nastavení sady Visual Studio |
| **F5** | Spustit ladění | Spuštění ladění aplikace |
| **Ctrl**+**F5** | Spustit bez ladění | Místní spuštění aplikace bez ladění |
| **CTRL**+**K**,**D** (výchozí profil) nebo **Ctrl**+**E**,**D**  (Profil jazyka C#) | Formátovat dokument | Vyčistí formátování narušení v souboru na základě nového řádku, mezery a nastavení odsazení |
| **CTRL**+ **\\** ,**Ctrl**+**E** (výchozí profil) nebo **Ctrl** + **W**,**E** (profil jazyka C#) | Zobrazení seznamu chyb | Zobrazit všechny chyby v dokumentu, projekt nebo řešení |
| **ALT** + **Page Up nebo PAGE DOWN** | Přejít na další/předchozí problém | Přejít na předchozí nebo další chyba, upozornění, návrh v dokumentu (k dispozici v **Visual Studio 2017 verze 15.8** a novější) |

> [!NOTE]
> Některá rozšíření odpojit klávesové zkratky sady Visual Studio výchozí. Použití výše uvedené příkazy, obnovit vaše klávesové zkratky nastavení sady Visual Studio tak, že přejdete do **nástroje** > **nastavení importu a exportu** > **obnovit všechna nastavení**  nebo **nástroje** > **možnosti** > **klávesnice** > **resetování**.

Další informace o klávesových zkratek a příkazy najdete v tématu [produktivitu zkratky](../ide/productivity-shortcuts.md) a [oblíbených klávesové zkratky](default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md).

## <a name="navigate-quickly-to-files-or-types"></a>Rychle přejít na soubory nebo typy

Visual Studio obsahuje funkci s názvem **přejít na vše** (**Ctrl**+**T**). **Přejít na vše** umožňuje rychle přejít na soubor, typ, člen nebo deklaraci symbolu.

- Změnit umístění tohoto panelu hledání nebo vypnout náhled živého navigace pomocí **ozubené kolečko** ikonu.
- Filtrovat výsledky jako pomocí syntaxe `t mytype`.
- Omezit rozsah hledání pouze na aktuální dokument.
- Stylem camel case odpovídající je podporována.

![Přejít na vše v sadě Visual Studio](../ide/media/VS2017Guide-go-to-all.png)

## <a name="enforce-code-style-rules"></a>Vynucení pravidel stylu kódu

Můžete použít *.editorconfig* souboru kodifikovat konvence kódování a mít je přenášet společně s vaším zdrojem.

::: moniker range="vs-2017"

- Můžete nainstalovat [služba jazyka EditorConfig rozšíření](https://aka.ms/editorconfig), což usnadňuje přidávání a úprava *.editorconfig* souboru v sadě Visual Studio.

::: moniker-end

::: moniker range=">=vs-2019"

- Automaticky vytvořit *.editorconfig* soubor z nastavení stylu kódu v **nástroje** > **možnosti** > **textový Editor**  > **C#** > **Styl kódu**.

   ![Generování souboru .editorconfig z nastavení v VS 2019](media/vs-2019/generate-editorconfig-file.png)

::: moniker-end

- Vyzkoušejte si [IntelliCode rozšíření pro Visual Studio](/visualstudio/intellicode/intellicode-visual-studio). IntelliCode odvodí z něj styl kódu z existujícího kódu a pak vytvoří neprázdný *.editorconfig* soubor s předvolby stylu kódu již definována.

- Podívejte se [možnosti konvence psaní kódu .NET](editorconfig-code-style-settings-reference.md) dokumentaci.

- Zobrazit [tento gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) příklad *.editorconfig* souboru.

![Vynucení stylu kódu v sadě Visual Studio](../ide/media/VSGuide_CodeStyle.png)

::: moniker range="vs-2019"

## <a name="code-cleanup"></a>Kód čištění

Visual Studio poskytuje na vyžádání formátování souboru s kódem, včetně předvoleb stylu kódu prostřednictvím **vyčištění kódu** funkce. Ke spuštění kódu čištění, klikněte na ikonu zarovnání v dolní části editoru nebo stisknutím klávesy **Ctrl**+**K**, **Ctrl**+**E**.

![Kód čištění tlačítko v aplikaci Visual Studio 2019](media/execute-code-cleanup.png)

Kromě formát souboru pro mezery, odsazení, ještě, **vyčištění kódu** také použije stylů vybraného kódu. Předvolby pro každý styl kódu se načítají z [souborů EditorConfig](code-styles-and-code-cleanup.md#code-styles-in-editorconfig-files), pokud máte pro projekt, nebo z [nastavení stylu kódu](code-styles-and-code-cleanup.md#code-styles-in-the-options-dialog-box) v **možnosti** dialogové okno.

::: moniker-end

## <a name="refactorings-and-code-fixes"></a>Refaktoring a kód opravy

Visual Studio se dodává s mnoha refaktoringů, akcí generování kódu a opravy kódu. Chyby představují červenou vlnovkou, zelenou vlnovkou představují upozornění a tři šedé tečky představují návrhy kódu. Přístupový kód opravy můžete kliknutím na ikonu šroubovák nebo návrhy nebo stisknutím klávesy **Ctrl**+ **.** nebo **Alt**+**zadejte**. Jednotlivé opravy se dodává s oknem Náhled, který ukazuje rozdíl živého kódu fungování opravy.

Oblíbené rychlých oprav a refaktoringy patří:

- *Přejmenovat*
- *Extrahování metody*
- *Podpis změny metod*
- *Generování konstruktoru*
- *Generování metody*
- *Přesun typu do souboru*
- *Přidat kontrolu hodnoty Null*
- *Přidat parametr*
- *Odebrat nepotřebné direktivy using*
- *Smyčka foreach dotaz LINQ a LINQ – metoda*
- *Dotyčného členy*
- Další informace najdete v tématu [funkce generování kódu](code-generation-in-visual-studio.md)

Je možné [nainstalovat analyzátory FxCop](../code-quality/install-fxcop-analyzers.md) příznakem potíží s kódem. Nebo vlastní refaktoring nebo kód opravit pomocí zápisu [analyzátory Roslyn](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix).

Několik členů komunity napsali bezplatné rozšíření, které přidávají další kód kontroly:

- [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
- [SonarLint for Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
- [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)
- [CodeCracker](https://www.nuget.org/packages/codecracker.CSharp/)

![Refaktoring v sadě Visual Studio](../ide/media/VSGuide_CodeAnalysis.png)

## <a name="find-usages-go-to-implementation-and-navigate-to-decompiled-assemblies"></a>Najít použití, přejít k implementaci a navigaci na Dekompilované sestavení

Visual Studio obsahuje mnoho funkcí a usnadňuje vyhledávání a [navigace v kódu](../ide/navigating-code.md).

| Funkce | Zástupce | Podrobnosti a vylepšení |
|- | - | -|
| Najít všechny odkazy | **Shift**+**F12**| Výsledky jsou zabarvené a mohou být seskupeny podle projektu, definice a odkaz na typ, například pro čtení nebo zápisu. Je také možné "zamknout" výsledky. |
| Přejít k implementaci | **Ctrl**+**F12** | Chcete-li přejít na přepsaného člena, můžete použít klíčové slovo `override` k přechodu na klíč |
| Přejít k definici | **F12** nebo **Ctrl**+**Klikni**| Stisknutím klávesy **Ctrl** při kliknutí na Přejít k definici |
| Náhled definice | **Alt**+**F12** | Zobrazit vložené definice |
| Vizualizér struktur | Šedé, tečkami čáry mezi složené závorky | Najetím myši zobrazíte struktury kódu |
| Navigace do dekompilovaných sestav | **F12** nebo **Ctrl**+**Klikni** | Přejděte do externího zdroje (decompiled s ILSpy) tím, že tuto funkci: **Nástroje** > **možnosti** > **textový Editor**  >  **C#**  >   **Pokročilé** > **povolit navigaci na dekompilované zdroje**. |

![Přejít na vše a najít všechny odkazy](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="improved-intellisense"></a>Vylepšená technologie IntelliSense

Stáhněte si [IntelliCode pro sadu Visual Studio](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCode) zobrazíte [dokončování kódu podle kontextu](/visualstudio/intellicode/intellicode-visual-studio) místo jenom abecední seznam. Můžete také trénování [vlastního modelu IntelliSense](/visualstudio/intellicode/custom-model-faq) založená na knihovnách vlastní domény.

## <a name="unit-testing"></a>Testování jednotek

Spouští se v sadě Visual Studio 2017, jsou četná vylepšení v testovacím prostředí. Můžete otestovat pomocí MSTest v1, MSTest v2, NUnit nebo XUnit rozhraní pro testování.

- **Průzkumník testů** zjišťování testů je rychlá.

- Uspořádání testů v **Průzkumník testů** s *řazení hierarchických*.

   ![Hierarchické zobrazení pro Text Explorer v sadě Visual Studio](../ide/media/VSGuide_Testing.png)

- [Živé testování částí](../test/live-unit-testing.md) nepřetržitě spouští testy vliv změny kódu a aktualizuje vložené editor ikon s oznámením stav testů. Zahrnout nebo vyloučit určité testy nebo testování projektů ze sady testů za provozu. (Visual Studio Enterprise edition jen.)

## <a name="debugging"></a>Ladění

Některé možnosti ladění sady Visual Studio zahrnují:

::: moniker range=">=vs-2019"

- Schopnost vyhledávat řetězce v rámci **Watch**, **automatické hodnoty**, a **lokální** systému windows.
- *Běžet do kliknutí*, který umožní najedete vedle řádku kódu, přístupů zelená ikona "play", který se zobrazí a spusťte svůj program, dokud nedosáhne tento řádek.
- **Pomocníka výjimky**, která odesílá nejdůležitější informace na nejvyšší úrovni v dialogovém okně, například proměnná, která je `null` v `NullReferenceException`.
- [Krokovat zpět ladění](../debugger/view-historical-application-state.md), která vám umožňuje přejít zpět k předchozím zarážkám nebo krokům a zobrazit stav aplikace, jako v minulosti.
- [Ladění snímků](/azure/application-insights/app-insights-snapshot-debugger), který umožní prozkoumat stav živé webové aplikace v tuto chvíli došlo k výjimce (musí být v Azure).

::: moniker-end

::: moniker range="vs-2017"

- *Běžet do kliknutí*, který umožní najedete vedle řádku kódu, přístupů zelená ikona "play", který se zobrazí a spusťte svůj program, dokud nedosáhne tento řádek.
- **Pomocníka výjimky**, která odesílá nejdůležitější informace na nejvyšší úrovni v dialogovém okně, například proměnná, která je `null` v `NullReferenceException`.
- [Krokovat zpět ladění](../debugger/view-historical-application-state.md), která vám umožňuje přejít zpět k předchozím zarážkám nebo krokům a zobrazit stav aplikace, jako v minulosti.
- [Ladění snímků](/azure/application-insights/app-insights-snapshot-debugger), který umožní prozkoumat stav živé webové aplikace v tuto chvíli došlo k výjimce (musí být v Azure).

::: moniker-end

![Pomocníka výjimky v sadě Visual Studio](../ide/media/VSGuide_Debugging.png)

## <a name="version-control"></a>Správa verzí

Úložiště git nebo TFVC můžete použít k ukládání a aktualizujte svůj kód v sadě Visual Studio.

::: moniker range=">=vs-2019"

- Nainstalujte [pro sadu Visual Studio žádosti o přijetí změn](https://marketplace.visualstudio.com/items?itemName=vsideversioncontrolmsft.pr4vs) vytvořte, zkontrolujte, přečtěte si a spusťte žádosti o přijetí změn bez opuštění sady Visual Studio.

::: moniker-end

- Uspořádání místní změny v [Team Exploreru](reference/team-explorer-reference.md) a sledovat probíhající potvrzení a změny pomocí stavového řádku.

- Nastavte průběžnou integraci a doručování pro projekty ASP.NET v aplikaci Visual Studio s [nástrojů Continuous delivery tools for Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) rozšíření.

![Správa zdrojového kódu v sadě Visual Studio](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-should-i-know-about"></a>Jaké další funkce by měla vědět o?

Tady je seznam editoru a produktivitu funkcí pro zajištění efektivnějšího psaní kódu. Některé funkce možná muset povolit, protože je vypnuto ve výchozím nastavení (může indexování věci na svém počítači, jsou kontroverzním nebo jsou aktuálně experimentální).

| Funkce | Podrobnosti | Jak povolit |
|-|-|-|
| Vyhledejte soubor v Průzkumníku řešení | Zvýrazní aktivní soubor v **Průzkumníka řešení** | **Nástroje** > **možnosti** > **projekty a řešení** > **sledovat aktivní položku v Průzkumníku řešení** |
| Přidání direktivy using pro typy v referenční sestavení a balíčky NuGet | Zobrazí návrhy k chybě s opravu kódu se nainstalovat balíček NuGet pro neodkazovaný typ | **Nástroje** > **možnosti** > **textový Editor** > **jazyka C#**  > **Advanced**   >  **Navrhnout použití typů v sestaveních reference** a **navrhnout použití typů v balíčcích NuGet** |
| Povolení úplné analýzy řešení | Zobrazit všechny chyby ve vašem řešení v **seznam chyb** | **Nástroje** > **možnosti** > **textový Editor** > **jazyka C#**  > **Advanced**   >  **Povolení úplné analýzy řešení** |
| Povolit navigaci na dekompilované zdroje | Povolit přejít k definici pro typy nebo členy z externích zdrojů a ILSpy decompiler znázornit těl metod. | **Nástroje** > **možnosti** > **textový Editor** > **jazyka C#**  > **Advanced**   >  **Povolit navigaci na dekompilované zdroje** |
| Režim dokončování a návrhu | Změny chování při dokončování IntelliSense. Použít jinou než výchozí nastavení tady mají tendenci vývojářům IntelliJ pozadí. | **Nabídka** > **upravit** > **IntelliSense** > **přepnout režim dokončení** |
| [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) | Zobrazí odkaz na informace o kódu a změnit historii v editoru. (Zdrojového CodeLens nejsou k dispozici v aplikaci Visual Studio Community edition, ukazatele.) | **Nástroje** > **možnosti** > **textový Editor** > **všechny jazyky**  >   **Funkce CodeLens** |
| [Fragmenty kódu](../ide/visual-csharp-code-snippets.md) | Nápověda zástupných procedur na společný kód často používaný text | Zadejte název fragmentu kódu a stiskněte klávesu **kartu** dvakrát. |
