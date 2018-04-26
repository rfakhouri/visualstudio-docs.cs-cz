---
title: Řešení potíží s pokrytí kódu v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: troubleshooting
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e7e939a5acaf89b3013cb5465b8fac6c272dd5d2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshoot-code-coverage"></a>Řešení potíží s pokrytí kódu

Analytické nástroje pokrytí kódu v aplikaci Visual Studio shromažďují data pro nativní a spravovaná sestavení (soubory .dll nebo .exe). Avšak v některých případech se v okně Výsledky pokrytí kódu zobrazí chyba, jako je „Byly generovány prázdné výsledky: ...“. Tady je několik důvodů, proč můžete získat výsledky prázdný. Tento článek pomůže při řešení těchto problémů.

## <a name="what-you-should-see"></a>Co byste měli vidět

Pokud se rozhodnete **analýza pokrytí kódu** příkazu v nabídce testů a pokud sestavení a testů úspěšně spuštěna, pak by měl zobrazit seznam výsledků v okně pokrytí kódu. Pro zobrazení podrobností je možno položky rozbalit.

![Kód pokrytí výsledků s barevné zvýrazňování](../test/media/codecoverage1.png "CodeCoverage1")

Další informace najdete v tématu [pomocí pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

## <a name="possible-reasons-for-seeing-no-results-or-old-results"></a>Možné příčiny zobrazení žádných nebo starých výsledků

### <a name="do-you-have-the-right-edition-of-visual-studio"></a>Máte správnou verzi sady Visual Studio?
 Budete potřebovat Visual Studio Enterprise.

### <a name="no-tests-were-executed"></a>Nebyly provedeny žádné testy

Analýza&mdash;vaše naleznete v okně výstupu. V **zobrazit výstup z** rozevíracího seznamu vyberte **testy**. Zjistěte, zda zde nejsou zaznamenána nějaká varování nebo chyby.

Vysvětlení&mdash;analýzy pokrytí kódu provádí v době spuštění testů. Zahrnuje pouze sestavení, která jsou načtena do paměti v průběhu testů. Pokud jsou proveden žádný z testů, není co pro pokrytí kódu do sestavy.

Řešení&mdash;v Průzkumníka testů, zvolte **spustit všechny** ověřit úspěšné provedení testů. Opravte chyby, před použitím **analýza pokrytí kódu**.

### <a name="youre-looking-at-a-previous-result"></a>Se díváte na předchozí výsledek

Předchozí výsledek pokrytí kódu může být viditelná, včetně kódu zvýrazňování z kterých staré běží při upravit a znovu spusťte testy.

1.  Spusťte analýzu pokrytí kódu.

2.  Ujistěte se, že jste v okně Výsledky pokrytí kódu vybrali nejaktuálnější sadu výsledků.

### <a name="pdb-symbol-files-are-unavailable"></a>Nejsou k dispozici soubory typu .pdb (symbol)

Analýza&mdash;otevřete cílové složky kompilace (obvykle bin\debug) a ověřte, že pro každé sestavení je soubor .pdb ve stejném adresáři jako soubor .dll nebo .exe.

Vysvětlení&mdash;modul pokrytí kódu vyžaduje, aby všechna sestavení jeho přidružené PDB souboru přístupné během spuštění testu. Pokud není dostupný žádný soubor .pdb pro konkrétní sestavení, není analyzovány sestavení.

Soubor typu .pdb je nutné vygenerovat ze stejného sestavení jako soubory typu .dll nebo .exe.

Řešení&mdash;Ujistěte se, že nastavení sestavení generovat soubor .pdb. Pokud soubory PDB nejsou při sestavení projektu, pak otevřete vlastnosti projektu, vyberte **sestavení** vyberte **Upřesnit**a zkontrolovat **ladicí informace**.

Pokud jsou soubory typu .pdb a .dll nebo .exe na různých místech, zkopírujte soubor typu .pdb do stejného adresáře. Je také možné nakonfigurovat nástroj pokrytí kódu tak, aby hledal soubory typu .pdb v jiném umístění. Další informace najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

### <a name="using-an-instrumented-or-optimized-binary"></a>Použití instrumentovaného nebo optimalizovaného binárního souboru

Analýza&mdash;zjistit binárního souboru podstoupila jakoukoli formu pokročilé optimalizace například optimalizace na základě profilu, zda má byly instrumentovány podle profilování nástroje, jako je vsinstr.exe nebo vsperfmon.exe.

Vysvětlení&mdash;Pokud sestavení již byla instrumentována nebo tím, že jiného nástroje pro profilaci, sestavení je vynechaný analýzy pokrytí kódu. Analýza pokrytí kódu nelze provést na takové sestavení.

Řešení&mdash;vypnout optimalizace a použití nového sestavení.

### <a name="code-is-not-managed-net-or-native-c-code"></a>Kód není spravovaný (.NET) nebo nativní (C++) kód

Analýza&mdash;ověřte, zda používáte některé testy na spravované nebo kód jazyka C++.

Vysvětlení&mdash;analýzy pokrytí kódu v sadě Visual Studio je dostupná jen pro spravovaná a nativní kód (C++). Při práci s nástroji třetích stran, může provést některé nebo všechny kódu na jiné platformě.

Řešení&mdash;žádný není k dispozici.

### <a name="assembly-has-been-installed-by-ngen"></a>Sestavení bylo nainstalováno pomocí technologie NGen

Analýza&mdash;ověřte, že sestavení není načten z mezipaměti v nativních bitových kopií.

Vysvětlení&mdash;z důvodů výkonu nejsou analyzovali sestavení nativních bitových kopií. Další informace najdete v tématu [Ngen.exe (Generátor nativních obrázků)](/dotnet/framework/tools/ngen-exe-native-image-generator).

Řešení&mdash;použít MSIL verzi sestavení. Nemáte zpracovat s NGen.

### <a name="custom-runsettings-file-with-bad-syntax"></a>Chybná syntaxe vlastního souboru .runsettings

Analýza&mdash;Pokud používáte vlastní *.runsettings* souboru může obsahovat chybu syntaxe. Pokrytí kódu není spuštěna, a buď okno pokrytí kódu není otevřete na konci testovací běh, nebo původní výsledky.

Vysvětlení&mdash;spuštěním testů jednotek s vlastní .runsettings soubor, který chcete konfigurovat možnosti pokrytí kódu. Možnosti umožňují zahrnout nebo vyloučit soubory. Další informace najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

Řešení&mdash;existují dvě možné typy chyb:

-   **Chyba XML**

     Otevřete soubor .runsettings v editoru jazyka XML sady Visual Studio. Hledejte označení chyb.

-   **Chyba regulární výraz**

     Každý řetězec v souboru je regulární výraz. Zkontrolujte všechny, zda v nich nejsou chyby, a hledejte zejména:

    -   Neshoda závorky (...) nebo neuvozené závorkách \\(... \\). Pokud ve vyhledávacím řetězci chcete najít závorky, musíte je přeskočit. Chcete-li například odpovídat použití funkce: `.*MyFunction\(double\)`

    -   Hvězdička nebo plus na začátku výrazu. Chcete-li shoda s libovolným řetězcem znaků, použijte tečku a hvězdičku: `.*`

### <a name="custom-runsettings-file-with-incorrect-exclusions"></a>Nesprávná vyloučení ve vlastním souboru .runsettings

Analýza&mdash;Pokud používáte vlastní *.runsettings* souboru, ujistěte se, že tento systém obsahuje vaše sestavení.

Vysvětlení&mdash;spuštěním testů jednotek s vlastní .runsettings soubor, který chcete konfigurovat možnosti pokrytí kódu. Možnosti umožňují zahrnout nebo vyloučit soubory. Další informace najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

Řešení&mdash;odebrat všechny `Include` ze souboru .runsettings a potom odebrat všechny uzly `Exclude` uzly. Pokud to vyřeší daný problém, vracejte je zpět ve fázích.

Zkontrolujte, že uzel DataCollectors určuje pokrytí kódu. Porovnání s ukázkou v [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

## <a name="some-code-is-always-shown-as-not-covered"></a>Nějaký kód je vždy zobrazen jako nepokrytý

### <a name="initialization-code-in-native-dlls-is-executed-before-instrumentation"></a>Ještě před instrumentací je provedena inicializace kódu v nativní knihovně DLL

Analýza&mdash;v nativním kódu staticky propojené, součást funkce inicializace **DllMain** a někdy zobrazen kód, který volá nejsou uvedeny, i když byl proveden kód.

Vysvětlení&mdash;nástroj pokrytí kódu funguje tak, že vložení do sestavení instrumentace, těsně před spuštěním aplikace spuštěna. V žádné sestavení načíst předem, inicializace kód v **DllMain** provede také načte sestavení a před spuštěním aplikace. Tento kód je pravděpodobně nebyla zahrnuté. Obvykle to platí pro staticky načtená sestavení.

Řešení&mdash;None.

## <a name="see-also"></a>Viz také

- [Použití pokrytí kódu k určení rozsahu testovaného kódu](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)