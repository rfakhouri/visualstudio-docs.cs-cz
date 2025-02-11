---
title: Nástroje jazyka F#
description: Další informace, které funkce sady Visual Studio jsou podporovány v F#.
ms.date: 07/11/2018
ms.topic: reference
helpviewer_keywords:
- F# features [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: f71e17eae1e728ab755d048daee2c0d156425964
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747589"
---
# <a name="develop-with-visual-f-in-visual-studio"></a>Vývoj s Vizuálem F# v sadě Visual Studio

Tento článek obsahuje informace o funkcích sady Visual Studio pro F# vývoje.

## <a name="install-f-support"></a>Nainstalujte F# podpory

Vývoj pomocí F# v sadě Visual Studio, nejdřív nainstalovat **vývoj desktopových aplikací .NET** pracovního vytížení, pokud jste tak již neučinili. Nainstalovat Visual Studio úloh prostřednictvím instalačního programu Visual Studio, které můžete otevřít tak, že vyberete **nástroje** > **stažení nástrojů a funkcí**.

![Úloha vývoj desktopových aplikací .NET v sadě Visual Studio](media/dotnet-desktop-development-workload.png)

## <a name="f-project-features"></a>F#Funkce projektu

Jsou k dispozici pro různé šablony projektů a položek F# v sadě Visual Studio. Následující obrázek ukazuje některé F# šablony projektů pro .NET Core a .NET Standard:

![F#šablony projektů v sadě Visual Studio](media/fsharp-project-templates.png)

Následující obrázek ukazuje některé F# šablon položek:

![F#šablony položek v sadě Visual Studio](media/fsharp-item-templates.png)

Další informace o šablonách položek pro přístup k datům najdete v tématu [ F# poskytovatelů](/dotnet/fsharp/tutorials/type-providers/index).

Následující tabulka shrnuje funkce ve vlastnostech projektu pro F#:

|Nastavení projektu|Podporované v F#?|Poznámky|
|---------------|----------------|-----|
|Soubory prostředků|Ano||
|Odkaz na nastavení, ladění a sestavení|Ano||
|Cílení na více verzí|Ano||
|Ikona a manifest|Ne|K dispozici prostřednictvím možnosti příkazového řádku kompilátoru.|
|Klienta služby ASP.NET|Ne||
|ClickOnce|Ne|Použijte projekt klienta v jiném jazyce .NET, pokud je k dispozici.|
|Vytváření silných názvů|Ne|K dispozici prostřednictvím možnosti příkazového řádku kompilátoru.|
|Sestavení, publikování a správa verzí|Ne||
|Analýza kódu|Ne|Nástroje pro analýzu kódu můžete spustit ručně nebo jako součást příkazu po sestavení.|
|Zabezpečení (Změna úrovně důvěryhodnosti)|Ne||

## <a name="project-designer"></a>návrhář projektu

**Návrhář projektu** se skládá z několika stránky vlastností projektu seskupeny související funkce. K dispozici stránky F# projekty jsou většinou podmnožinu těchto k dispozici pro ostatní jazyky a jsou popsány v následující tabulce. Jsou uvedeny odkazy na odpovídající jazyka C# **Návrháře projektu** stránky.

|Stránky Návrháře projektu|Související odkazy|Popis|
| - |-------------|-----------|
|Aplikace|[Stránka aplikace, Návrhář projektu](reference/application-page-project-designer-csharp.md)|Umožňuje určit nastavení na úrovni aplikace a vlastnosti, například zda vytváříte knihovnu nebo spustitelný soubor, jakou verzi .NET cíle aplikace a informace o umístění ukládaných souborů prostředků, které aplikace používá.|
|Sestavení|[Vytvořit stránku, Návrhář projektu](reference/build-page-project-designer-csharp.md)|Umožňuje řídit způsob kompilace kódu.|
|Události sestavení|[Stránka události, Návrhář projektu sestavení](reference/build-events-page-project-designer-csharp.md)|Umožňuje určit příkazy se spustí před nebo po kompilaci.|
|Ladění|[Stránka Ladění, Návrhář projektu](reference/debug-page-project-designer.md)|Umožňuje řídit, jak je aplikace spuštěná během ladění. Jedná se o co příkazy mají použít, a co je vaše aplikace spouští, adresář je a jakékoli speciální režimů ladění, které chcete povolit, jako je například nativního kódu a SQL.|
|Balíček (pouze sada .NET SDK)|Není k dispozici|Umožňuje definovat metadata balíčku NuGet při publikování jako balíček NuGet.|
|Cesty odkazů|[Správa odkazů v projektu](managing-references-in-a-project.md)|Umožňuje zadat, kam mají hledat sestavení, na kterém závisí kódu.|
|Prostředky (pouze sada .NET SDK)|Není k dispozici|Umožňuje vytvářet a spravovat výchozí soubor prostředků.|

### <a name="f-specific-settings"></a>F#-konkrétní nastavení

V následující tabulce najdete souhrn nastavení, které jsou specifické pro F#:

|Stránky Návrháře projektu|Nastavení|Popis|
| - |-------|-----------|
|Sestavení|Generovat volání tail|Pokud vybraná, umožňuje použití funkce tail Microsoft Intermediate Language (MSIL) instrukce. To způsobí, že rámec zásobníku znovu použije pro rekurzivní funkce chvostu. Ekvivalentní `--tailcalls` – možnost kompilátoru.|
|Sestavení|Nastavení další příznaky|Umožňuje určit možnosti příkazového řádku kompilátoru Další.|

## <a name="code-and-text-editor-features"></a>Funkce editoru kódu a text

Jsou podporovány následující funkce editory sady Visual Studio code a text v F#:

|Funkce|Popis|Podporované v F#?|
|-------|-----------|----------------|
|Automaticky komentář|Umožňuje komentář nebo zrušte komentář u části kódu.|Ano|
|Automaticky formátovat|Přeformátuje kódu pomocí standardní odsazení a stylu.|Ne|
|Záložky|Umožňuje uložit míst v editoru.|Ano|
|Změna odsazení|Odsazení nebo zruší odsazení vybraných řádků.|Ano|
|Inteligentní odsazení|Automaticky odsadí a zrušení odsazení kurzor podle F# pravidel oboru.|Ano|
|[Vyhledání a nahrazení textu](finding-and-replacing-text.md)|Umožňuje hledat v souboru, projekt nebo řešení a potenciálně změnit text.|Ano|
|Přejít k definici rozhraní API .NET|Když se kurzor na rozhraní API .NET, se zobrazí kód generovaný z .NET metadat.|Ne|
|Přejít k definici pro uživatelské rozhraní API|Pokud je kurzor na entitu program, který jste definovali, přesune kurzor na místo v kódu, kde je definován entity.|Ano|
|Přechod na řádek|Umožňuje přejít na konkrétní řádek v souboru číslem řádku.|Ano|
|Navigační panely v horní části souboru|Umožňuje přejít na umístění v kódu, například název funkce.|Ano|
|Pokyny pro strukturu bloku|Zobrazí pokyny, které označují F# obory, které mohou být myš pro verzi preview.|Ano|
|[Sbalení](outlining.md)|Umožňuje sbalit oddílů kódu vytvoření kompaktnějším zobrazení.|Ano|
|Převést na tabulátory|Převede mezery na tabulátory.|Ano|
|Zabarvení typu|Zobrazí názvy typů definované v speciální barvu.|Ano|
|Rychlé hledání. Podívejte se rychle najít, najít a nahradit okna.|Umožňuje hledat v souboru nebo projektu.|Ano|
|**CTRL**+**klikněte na tlačítko** přejít k definici|Umožňuje uložení **Ctrl** a klikněte na F# symbol, který má být vyvolán přejít k definici.|Ano|
|Přechod na definici z rychlé informace|Po kliknutí symboly uvnitř popisky, které vyvolávají přejít k definici.|Ano|
|Přejít na vše|Povolí globální navigační přibližné shody pro všechny F# vytvoří prostřednictvím **Ctrl**+**T**.|Ano|
|Přejmenování na řádku|Přejmenuje všechny výskyty symbolu vložené.|Ano|
|Najít všechny odkazy|Najde všechny výskyty symbolu v základu kódu.|Ano|
|Zjednodušit název opravu kódu|Odstraní nepotřebné kvalifikátory pro F# symboly.|Ano|
|Odebrat nepoužité `open` opravu kódu – příkaz|Odebere všechny nepotřebné `open` příkazů v dokumentu.|Ano|
|Oprava kódu nepoužívané hodnota|Navrhuje přejmenování nevyužité identifikátor pro podtržítkem.|Ano|

Obecné informace o úpravách kódu v sadě Visual Studio a funkce textového editoru, najdete v části [psaní kódu v editoru](writing-code-in-the-code-and-text-editor.md).

## <a name="intellisense-features"></a>Funkce technologie IntelliSense

Následující tabulka shrnuje funkce IntelliSense podporované a nepodporované ve F#:

|Funkce|Popis|Podporované v F#?|
|-------|-----------|----------------|
|Automaticky implementovat rozhraní|Generuje kód zástupné procedury pro metody rozhraní.|Ano|
|Fragmenty kódu|Vkládá kód z knihovny běžné konstrukce kódování do témat.|Ne|
|Dokončit slovo|Uloží typování tím dokončuje slova a názvy se během psaní.|Ano|
|Automatické dokončování|Pokud povolená, způsobí, že dokončení slova vyberte první shodu, jak budete zadávat, místo abyste čekali, vyberte jednu nebo stisknutím klávesy **Ctrl**+**místo**.|Ano|
|Nabízí dokončování pro symboly v neotevřených oborech názvů|Pomocí automatického dokončování, je určeno odpovídající symbol, který se nachází v neotevřených oboru názvů, nabízí dokončete s odpovídajícím `open` příkaz při výběru.|Ano|
|Generovat prvky kódu|Umožňuje generování kódu zástupné procedury pro různé konstrukce.|Ne|
|Vypsat členy|Při psaní operátor přístupu členů (.) obsahuje členy typu.|Ano|
|Uspořádat direktivy using/Open|Slouží k uspořádání obory názvů odkazované **pomocí** příkazů v C# nebo **otevřete** direktivy v F#.|Ne|
|Informace o parametrech|Při psaní volání funkce, zobrazí se užitečné informace o parametrech.|Ano|
|Rychlé informace|Zobrazí úplnou deklaraci pro libovolný identifikátor ve vašem kódu.|Ano|
|Automatické uzavírání závorek|Automaticky dokončí F# složenou závorku syntaxe konstrukce transakčním způsobem.|Ano|

Obecné informace o technologii IntelliSense, najdete v části [použití IntelliSense](using-intellisense.md).

## <a name="debugging-features"></a>Funkce ladění

Následující tabulka shrnuje funkce, které jsou k dispozici při ladění F# kódu:

|Funkce|Popis|Podporované v F#?|
|-------|-----------|----------------|
|Automatické hodnoty – okno|Ukazuje, automatické nebo dočasné proměnné.|Ne|
|Zarážky|Umožňuje pozastavit provádění kódu v určitých bodech během ladění.|Ano|
|Podmíněné zarážky|Umožňuje zarážky, které testovací podmínku, která určuje, zda by měl pozastavit provádění.|Ano|
|Upravit a pokračovat|Umožňuje kódu se dají upravit a zkompilovat jako ladění programu, spuštěna bez zastavení a restartování ladicího programu.|Ne|
|Chyba při vyhodnocování výrazu|Vyhodnotí a spustí kód v době běhu.|Ne, ale jazyka C# vyhodnocovací filtr výrazů je možné, i když je nutné použít syntaxi jazyka C#.|
|Historické ladění|Můžete krokovat s vnořením dříve spuštěný kód.|Ano|
|Místní hodnoty – okno|Ukazuje místně definované hodnoty a proměnné.|Ano|
|Spustit ke kurzoru|Umožňuje spustit kód, dokud nebude dosaženo řádek obsahující kurzor.|Ano|
|Krokovat s vnořením|Umožňuje provádění záloh a přesunout do každé volání funkce.|Ano|
|Krok přes|Umožňuje předem spouštění v aktuální rámec zásobníku a přesunout za každé volání funkce.|Ano|

Obecné informace o ladicím programu sady Visual Studio najdete v tématu [ladění v sadě Visual Studio](../debugger/index.md).

## <a name="additional-tools"></a>Další nástroje

Následující tabulka shrnuje podporu pro F# v nástrojích Visual Studio.

|Nástroj|Popis|Podporované v F#?|
|----|-----------|----------------|
|Hierarchie volání|Zobrazí vnořené struktury funkce volá ve vašem kódu.|Ne|
|Metriky kódu|Shromažďuje informace o kódu, jako jsou počty řádků.|Ne|
|zobrazení tříd|Poskytuje pohled na základě typu kódu v projektu.|Ne|
|[Okno Seznam chyb](reference/error-list-window.md)|Zobrazí seznam chyb v kódu.|Ano|
|[F# Interactive](/dotnet/fsharp/tutorials/fsharp-interactive/)|Umožňuje zadejte (nebo zkopírujte a vložte) F# kódu a spustit okamžitě, bez ohledu na jejich vytváření projektu. F# Interaktivní okno je pro čtení, vyhodnocení, smyčka tisku (REPL).|Ano|
|prohlížeč objektů|Umožňuje zobrazení typů v sestavení.|F#typy, jak se objeví v kompilovaných sestavení se nezobrazují přesně tak, jak je vytvářet. Můžete procházet pomocí kompilované reprezentace F# typy, ale nelze zobrazit typy, jak se objeví z F#.|
|[Okno výstup](reference/output-window.md)|Zobrazí výstup sestavení.|Ano|
|Analýza výkonu|Poskytuje nástroje pro měření výkonu kódu.|Ano|
|Vlastnosti – okno|Zobrazuje a umožňuje úpravy vlastností objektu ve vývojovém prostředí, který má právě fokus.|Ano|
|Průzkumník serveru|Poskytuje způsoby, jak pracovat s různými prostředky serveru.|Ano|
|Průzkumník řešení|Umožňuje zobrazit a spravovat projekty a soubory.|Ano|
|Seznam úkolů|Umožňuje spravovat pracovní položky týkající se vašeho kódu.|Ne|
|Projekty testů|Poskytuje funkce, které umožňují testování kódu.|Ne|
|Sada nástrojů|Zobrazí karty, které obsahují přetažitelného objekty, jako jsou ovládací prvky a části textu nebo kódu.|Ano|

## <a name="see-also"></a>Viz také:

- [F#Průvodce (.NET Framework)](/dotnet/fsharp/)
- [Začínáme s F# v sadě Visual Studio](/dotnet/fsharp/get-started/get-started-visual-studio)