---
title: "Visual Studio 2017 pro vývojáře .NET | Microsoft Docs"
description: "Přehled funkcí Visual Studio 2017 můžete napsat kód lepší .NET rychlejší."
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
ms.openlocfilehash: 7e910c50682d45d209d993cb883ca01d1ea436f2
ms.sourcegitcommit: 236c250bb97abdab99d00c6525d106fc0035d7d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>Visual Studio 2017 produktivitu Příručka pro vývojáře .NET

- [Průvodce produktivitu](#guide)
- [Visual Studio 2017 – přehled](#overview)

## <a name="a-idguide-productivity-guide"></a><a id="guide"/> Průvodce produktivitu
[Visual Studio 2017](https://www.visualstudio.com/downloads/) umožňuje vývojářům zvýšit produktivitu než kdy dřív! Vylepšili výkon a spolehlivost pro spuštění řešení a zatížení, test zjišťování a zadáním latence. Také jsme přidali a pokročilé funkce, které umožňují rychlejší psaní lepší kódu. Mezi tyto funkce patří: navigace na decompiled sestavení, proměnné Název návrhy, jak budete zadávat, zobrazení hierarchie v Průzkumníka testů, přejděte na všechny (**Ctrl + T**) přejděte na soubor nebo typ/člen nebo symbol deklarace inteligentní pomocníka výjimka, konfigurace styl kódu a vynucení a opravy mnoha Refaktoring a kód. 

Postupujte podle tohoto průvodce k optimalizaci produktivitu.

###  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>Používá Moje klávesové zkratky z jiné rozšíření nebo editor/IDE.

Pokud jsou pocházejících z jiného IDE nebo kódování prostředí, může se stát, některou z následujících přípon užitečné instalaci:

- [EMACS emulace](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [HotKeys for Visual Studio (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

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

### <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>Potřebuji způsob, jak rychle přejděte na soubory nebo typy.
Visual Studio 2017 má funkci _přejděte na všechny_ (**Ctrl + T**). Přejděte na všechny umožňuje rychle přejít do souboru, typu, člen nebo symbol deklarace.
- Změňte umístění tohoto panelu Hledat nebo vypnout v za provozu navigační náhledu s **zařízení** ikonu
- Filtrování výsledků pomocí našich syntaxe dotazu (například "t mytype"). Můžete také určit obor vyhledávání právě v aktuálním dokumentu.
- jsou podporovány camelCase odpovídající!

![Přejděte na všechny v sadě Visual Studio](../ide/media/VS2017Guide-go-to-all.png "VS2017Guide přejděte na všechny")

### <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>Moje team vynucuje pravidla stylu kódu v našem základu kódu.
Soubor .editorconfig můžete kodifikovat konvence psaní kódu. Doporučujeme nainstalovat [EditorConfig jazyk služby rozšíření](https://aka.ms/editorconfig) pro přidání a úpravy souboru .editorconfig. Doporučujeme, projděte si [dokumentace](https://aka.ms/editorconfigDocs) pro všechny .NET kódování konvence možnosti.

Chck out [tento gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) pro .editorconfig příklad.

![Styl vynucení v sadě Visual Studio Code](../ide/media/VS2017Guide-code-style.png "VS2017Guide-kódu style")

### <a name="i-need-more-refactorings-and-code-fixes"></a>Potřebuji další Refaktoring a kód opravy.
Visual Studio 2017 se dodává s velkým množstvím refaktoring, kód generování akcí a kód opravy, které se zobrazí v našem [dokumentaci](https://aka.ms/refactorings). Podtržení vlnovkou Red představují chyby, zelená podtržení vlnovkou představují upozornění a tři tečky šedé představují návrhy kódu.

Přístupový kód opravy můžete kliknutím na ikonu žárovek/šroubovák nebo stisknutím kombinace kláves **Ctrl +.** nebo **Alt + zadejte**. Jednotlivé opravy se dodává s preview okno, které ukazuje ukázku kódu rozdílové toho, jak funguje opravu.

Tady jsou některé oblíbených rychlé opravy a refaktoring: přejmenovat, extrahovat metodu, podpis metody změnu, generovat konstruktor, generovat metoda, přesunout typ souboru, přidejte hodnotu Null-zkontrolujte, přidejte parametr, odeberte nepotřebné direktiv Using.

Refaktoring a kód opravy je možné snadno zapsat s [Roslyn analyzátorů](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix). Několik členy komunity vytvořilo *volné* rozšíření, která přidat další kód kontroly: Roslynator a SonarLint pro sadu Visual Studio. 

![Refaktoring v sadě Visual Studio](../ide/media/VS2017Guide-refactoring.png "refaktoring VS2017Guide")

### <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>Potřebuji použití najít, přejděte k implementaci, přejděte k Decompiled sestavení
Visual Studio 2017 obsahuje mnoho funkcí pro usnadnění hledání a přejděte základu kódu – včetně najít všechny odkazy (**Shift + F12**), přejděte na implementaci (**Ctrl + F12**), přejít k definici ( **F12** nebo **Ctrl + kliknutí**). Navigovat Decompiled sestavení se přidal ve verzi 15,6 operací. Chcete-li tuto funkci zapnout, přejděte na **nástroje > Možnosti > textový Editor > C# > Upřesnit > povolení navigace na decompiled zdroje**.

![Přejděte na decompiled zdroje v sadě Visual Studio](../ide/media/VS2017Guide-navigate-to-source.png "VS2017Guide-přejděte na source")

### <a name="i-want-to-run-and-see-my-unit-tests"></a>Chcete spustit a najdete v části Moje testování částí.
Máme dvě nabídky pro testování v aplikaci Visual Studio 2017 částí: Průzkumníka testů a _Live testování částí_. Jsme k výraznému vylepšení rychlosti testu zjišťování v Průzkumníku otestovat ve verzi 15,6 operací. Také jsme přepracovali rozhraní umožňující hierarchické řazení.

Visual Studio také má jednotka testování funkci [Live testování částí](/test/live-unit-testing). Za provozu testování částí nepřetržitě běží na pozadí, spustí testy vliv změny kódu a aktualizace vložených editor ikony pokaždé stav testy.

![Zobrazení hierarchie pro Explorer Text v sadě Visual Studio](../ide/media/VS2017Guide-hiearchy-test-explorer.png "VS2017Guide hiearchy testovací explorer")

### <a name="what-other-features-do-i-need-to-know-about"></a>Jaké další funkce potřebujete vědět o?
Tady je seznam funkcí editoru a produktivitu pro efektivní psaní kódu. Některé funkce možná muset povolit, protože jsou vypnout výchozím (se mohou indexu věci na váš počítač, jsou sporná nebo jsou aktuálně experimentální).
- *Vyhledejte soubor v Průzkumníku řešení* označuje aktivní soubor v Průzkumníku řešení.
  - **Nástroje > Možnosti > projekty a řešení > sledovat Active položky v Průzkumníku řešení**
- *Přidání direktiv using pro typy v referenční sestavení a balíčky NuGet* ukazuje žárovek s opravy kódu se nainstalovat balíček NuGet pro typ neregistrované.
  - **Nástroje > Možnosti > textový Editor > C# > Upřesnit > navrhnout direktiv using pro typy v referenční sestavení** a **navrhnout direktiv using pro typy v balíčků NuGet**
- *Povolit úplnou analýzu řešení* chcete zobrazit všechny chyby ve vašem řešení v seznamu chyb.
  - **Nástroje > Možnosti > textový Editor > C# > Upřesnit > povolit úplnou analýzu řešení**
- *Povolení navigace na decompiled zdroje* povolení přejít k definici na typy nebo členy z externích zdrojů a používání ILSpy decompiler zobrazíte těla metody.
  - **Nástroje > Možnosti > textový Editor > C# > Upřesnit > povolení navigace na decompiled zdroje**
- *Režim dokončení/návrhu* IntelliSense změny chování při dokončování. Vývojářům IntelliJ pozadí mají tendenci se měnit nastavení z výchozího sem.
  - **Nabídky > Upravit > IntelliSense -> Přepnout režim dokončení**
- Máme *výstřižky kódu* pomohou zóny se zakázaným inzerováním na běžné standardní (dvakrát stiskněte, karta'). Najdete v článku [úplný seznam](/ide/visual-csharp-code-snippets).

![Fragmenty kódu v sadě Visual Studio Code](../ide/media/VS2017Guide-code-snippet.png "VS2017Guide fragmentu kódu")

### <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>Chybí funkce, která vám umožňuje produktivní nebo právě probíhá nízký výkon?
Chcete nám sdělit svůj názor několika způsoby:
- Žádosti o funkce rozhraní .NET můžete selhala na našem [úložiště GitHub](https://github.com/dotnet/roslyn/issues).
- Žádosti o funkce Visual Studio, chyb a problémů s výkonem můžete podává pomocí **odeslat zpětnou vazbu** ikona v horní části okna programu sady Visual Studio.


## <a name="a-idoverview-overview-of-visual-studio-2017-for-net-developers"></a><a id="overview"/> Přehled Visual Studio 2017 pro vývojáře .NET

### <a name="smart-code-editor"></a>Editor inteligentní kódu

- [Dokumentace: Pomocí IntelliSense](using-intellisense.md)
- [Dokumentace: Funkce Inteligentní editor](writing-code-in-the-code-and-text-editor.md)

Visual Studio obsahuje hluboké znalosti kódu prostřednictvím kompilátoru .NET ("Roslyn"), kde přinášejí inteligentní úpravy funkcí, jako je zabarvení syntaxe, kód dokončení, kontrola pravopisu chybným proměnné, neimportovaných typu řešení, osnovy, struktura vizualizérech, [Codelensu](find-code-changes-and-other-history-with-codelens.md), volání hierarchie, hover možnost rychlé informace, parametr nápovědy, jakož i nástroje pro refaktoring, použití rychlé akce a generování kódu.

![Visual Studio editor inteligentní kódu](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")

### <a name="navigate-and-search-your-codebase"></a>Přejděte a hledání vaší základu kódu

[Dokumentace: Navigace v kódu](navigating-code.md)

Rychle přechod do souboru, typu, člen nebo symbol deklarace s přejít kódu .NET *přejděte na všechny* zástupce (**Ctrl + T**). Najít všechny odkazy literál nebo symbol v kódu, včetně odkazů mezi jazyky rozhraní .NET (**Shift + F12**). A pomocí našich cílové navigační příkazy můžete přejít přímo na symbol definice (**F12**) nebo implementace (**Ctrl + F12**).

![Přejděte na všechny a najít všechny odkazy](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")

### <a name="live-code-analysis-for-code-quality"></a>Live analýzy kódu pro kvality kódu

[Dokumentaci: Refaktoring a rychlé akce](refactoring-code-generation-quick-actions.md)

Visual Studio má diagnostiky kódu za provozu můžete po zjištění chyby a potenciálně problematické kód zvýšení kvality vašeho kódu. Poskytujeme rychlé akce (**Ctrl**+**.**) k řešení problémů zjištěných napříč dokument, projekt nebo řešení. Povolit *analýzy úplné řešení* najít problémy v celé řešení i v případě, že nemáte ty soubory, otevřete v editoru.

Kromě toho použít kód návrhy další osvědčených postupů, se zakázaným inzerováním nebo vygenerování kódu, refactor kódu a použít nové jazykové funkce s **Ctrl**+**.** Zástupce.

![Použít pro rychlé opravy a refaktoring pomocí žárovek nabídky](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")

### <a name="unit-testing"></a>Testování částí

[Dokumentaci: Testování v sadě Visual Studio částí](../test/improve-code-quality.md)

Spuštění a ladění testů jednotek na základě Mstestu, NUnit nebo XUnit testování architektury pro každou aplikaci cílení na rozhraní .NET Framework, .NET Standard nebo .NET Core. Prozkoumat a zkontrolovat vaše testy *Průzkumníka testů* nebo okamžitě najdete na tom, jak změny kódu ovlivnit testů jednotek v editoru s *Live testování částí* (pouze verzi Enterprise).

![Live testování v sadě Visual Studio částí](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")

### <a name="code-consistency-and-style"></a>Kód konzistence a stylu

- [Dokumentaci: Možnosti přenosné vlastního editoru](create-portable-custom-editor-options.md)
- [Dokumentace: EditorConfig kódu stylu nastavení pro rozhraní .NET](editorconfig-code-style-settings-reference.md)

Visual Studio umožňuje konvence kódování, zjistí kódování porušení stylu a poskytuje rychlé opravy Chcete-li opravit problémy styl s **Ctrl**+**.** Zástupce. Konfigurace a vynutit vašeho týmu, pojmenování, formátování a stylu pravidla vytváření kódu napříč úložiště – povolení potlačení hodnot na úrovni projektu a souborů – pomocí *EditorConfig*.

![Konfigurace a vynutit konvence psaní kódu s EditorConfig](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")

### <a name="debugging"></a>Ladění

[Dokumentace: Ladění v sadě Visual Studio](../debugger/index.md)

Visual Studio obsahuje Bezvadný ladicí program, který umožňuje ladit aplikace .NET cílení na rozhraní .NET Framework, .NET Standard a .NET Core. Přepněte a nastavte podmíněné zarážky (**F9**), krok do volání metod, vyhodnotit výrazy LINQ a lambda, nastavit proměnnou sleduje, připojte k procesy, prozkoumat vaše zásobník volání nebo dokonce vytvořit za provozu úpravy kódu při ladění pomocí  *Upravit a pokračovat*.

Pokud vaše služba běží v Azure, použijte *snímku ladění* žádostí o vyřešení problémů v za provozu, nasazené cloudové aplikace ve Visual Studio 2017 Enterprise.

![Ladění v sadě Visual Studio](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")

### <a name="version-control"></a>Správa verzí

[Dokumentace: Správa verzí v sadě Visual Studio](/vsts/index)

Použití git nebo TFVC k ukládání a aktualizujte kód v sadě Visual Studio. V editoru uspořádání místní změny s Team Explorer a sledovat čeká na potvrzení a změny pomocí stavového řádku. Nastavte průběžnou integraci a doručení v aplikaci Visual Studio s naše [průběžné doručování Tools pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) rozšíření přijmout pracovní postup agile developer.

![Ovládací prvek v sadě Visual Studio zdroje](../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

### <a name="extensibility"></a>Rozšiřitelnost

[Dokumentace: Rozšíření sady Visual Studio](../extensibility/index.md)

Visual Studio obsahuje bohatý ekosystém rozšíření, které můžete nainstalovat nebo vytvořit, protože je budete potřebovat. Instalovat rozšíření z *Galerie rozšíření* nebo *Visual Studio Marketplace*, vytvoření vlastního editoru modulů plug-in s *VS SDK*, nebo vytvořit vlastní analyzátor kódu za provozu nebo refaktoring pomocí *SDK pro platformu .NET kompilátoru*. Stažením můžete najít další kód opravy a návrhy [analýza kódu Microsoft](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) rozšíření.

![Galerie rozšíření sady Visual Studio](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")
