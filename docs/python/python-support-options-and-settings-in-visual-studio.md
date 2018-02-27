---
title: "Možnosti a nastavení pro jazyk Python v sadě Visual Studio | Microsoft Docs"
description: "Referenční dokumentace pro různá nastavení v sadě Visual Studio, které se vztahují na kód Python a projekty."
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Python_Tools
- VS.ToolsOptionsPages.Python_Tools.General
- VS.ToolsOptionsPages.Python_Tools.Debugging
- VS.ToolsOptionsPages.Python_Tools.Diagnostics
- VS.ToolsOptionsPages.Python_Tools.Interactive_Windows
- VS.ToolsOptionsPages.Text_Editor.Python.Advanced
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 25e0540c376017bfc3f3a64d23bbc6963942bb5c
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="options-for-python-in-visual-studio"></a>Možnosti pro jazyk Python v sadě Visual Studio

Chcete-li zobrazit možnosti Python, použijte **nástroje > Možnosti** nabídky příkaz, zkontrolujte, **zobrazit všechna nastavení** je vybrána a pak přejděte do **Python Tools**:

![Dialogové okno Možnosti Python, karta Obecné](media/options-general.png)

Existují také další možnosti specifické pro Python na **textový Editor > Python > Upřesnit** kartě.

> [!Note]
> **Experimentální** skupina obsahuje možnosti pro funkce, které jsou stále ve vývoji a nejsou zde popsány. Že jsou často popsané v příspěvcích na [inženýrství Python v blogu Microsoft](https://blogs.msdn.microsoft.com/pythonengineering/).

## <a name="general-options"></a>Obecné možnosti

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Zobrazí okno výstup, při vytváření virtuálního prostředí| On | Zrušením zabránit zobrazování okně výstupu. |
| Zobrazí okno výstup při instalaci nebo odebrání balíčků | On | Zrušením zabránit zobrazování okně výstupu. |
| Vždy spustit jako správce pip | Off | Vždy zvyšuje `pip install` operací pro všechna prostředí. Při instalaci balíčků, Visual Studio vyzve k zadání oprávnění správce, pokud prostředí je umístěný v oblasti chráněného systému souborů, jako `c:\Program Files`. V této výzvy můžete vždy zvýšení oprávnění `pip install` pro právě jeden prostředí. V tématu [balíčky karta](python-environments-window-tab-reference.md#packages-tab). |
| Automaticky generovat dokončení DB při prvním použití | On | Pro [dokončování IntelliSense](editing-python-code-in-visual-studio.md#intellisense) fungovat pro knihovnu, musíte Visual Studio vygenerovat dokončení databáze pro tuto knihovnu. Vytváření databáze se provádí na pozadí při knihovny je nainstalovaná, ale nemusí být kompletní při spuštění psaní kódu. Tuto možnost Visual Studio upřednostňuje dokončení databáze pro knihovnu při psaní kódu, která jej používá. |
| Ignorovat systémové PYTHONPATH proměnné | On | PYTHONPATH ve výchozím nastavení se ignoruje, protože Visual Studio poskytuje více přímé prostředky ke specifikaci cest hledání v prostředích a projektů. V tématu [cesty hledání](search-paths.md) podrobnosti. |
| Cesty hledání aktualizací při přidání připojené soubory | On | Je-li nastaven, přidání [připojený soubor](managing-python-projects-in-visual-studio.md#linked-files) do projektu aktualizace [cesty hledání](search-paths.md) tak, aby IntelliSense můžete zahrnout obsah složky připojený soubor ve své databázi dokončení. Zrušte zaškrtnutí tohoto políčka vyloučit takový obsah z databáze dokončení. |
| Upozornit, pokud importovat modul nebyl nalezen. | On | Zrušte této volby potlačení upozornění, když víte importovaného modulu není v současné době dostupné, ale neovlivní jinak operaci kódu. |
| Sestava nekonzistentní odsazení jako | Upozornění | Protože překladač Pythonu výraznou závisí na správné odsazení k určení oboru, Visual Studio ve výchozím nastavení vydá upozornění při zjištění nekonzistentní odsazení, které můžou uvádět chyb v kódu. Nastavte na *chyby* být i víc striktní, což vede k ukončení v takových případech. Chcete-li toto chování zcela zakázat, vyberte *není*. |
| Zkontrolujte průzkum nebo zprávy | Jednou za týden | Nastaví frekvenci, ve kterém můžete povolit Visual Studio můžete otevřít okno obsahující webové stránky s související Python průzkumy a položek zpráv, pokud je k dispozici. Možnosti jsou *nikdy*, *jednou denně*, *jednou za týden*, a *jednou za měsíc*. |
| Resetovat všechny trvale skrytá dialogová okna (tlačítko) | není k dispozici | Různá dialogová zadejte možnosti, jako třeba **tento dialog již příště nezobrazovat**. Toto tlačítko slouží k vymazání těchto možností a způsobit, že v dialogových oknech se znovu zobrazí. |

![Dialogové okno Možnosti Python, karta Obecné](media/options-general.png)

## <a name="debugging-options"></a>Možnosti ladění

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Výzvu před spuštěním, pokud existuje chyby | On | Pokud nastavíte, vás vyzve k potvrzení, že chcete spustit kód, který obsahuje chyby. Zrušte zaškrtnutí tohoto políčka Zakázat upozornění. |
| Počkejte, než pro vstup až proces ukončen neobvyklým způsobem<br/><br/>Čekání na vstup při ukončení procesu normálně | Na (pro oba) | Program Python spuštění ze sady Visual Studio se spouští v samostatném okně konzole. Ve výchozím okně čeká na klávesu před jeho zavřením bez ohledu na to, jak program bude ukončen. K odebrání této výzvy a zavřete okno automaticky, zrušte zaškrtnutí jedné nebo obou těchto možností. |
| Typu t výstup programu pro ladění výstup – okno | On | Výstup programu zobrazuje v okně výstupu Visual Studio a okna samostatné konzoly. Zrušte zaškrtnutí tohoto políčka Zobrazit výstup pouze v okně samostatné konzoly. |
| Rozdělit na SystemExit výjimce s ukončovacím kódem 0 | Off | Pokud nastavení, zastaví ladicí program na výjimku. Když jasné, ladicí program se ukončí bez ukončování řádků. |
| Povolit ladění na standardní knihovny jazyka Python | Off | Umožňuje krok do zdrojového kódu standardní knihovna při ladění, ale zvyšuje čas potřebný pro ladicí program spustit.|

![Dialogové okno Možnosti Python, karta ladění](media/options-debugging.png)

## <a name="diagnostics-options"></a>Možnosti diagnostiky

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Zahrnout analýzy protokolů | On | Obsahuje podrobné protokoly týkající se analýza nainstalované prostředí Python při ukládání diagnostiku do souboru nebo jejich kopírování do schránky. pomocí tlačítka. Tato možnost může výrazně zvýšit velikost vygenerovaný soubor, ale je často potřeba diagnostikovat problémy IntelliSense. |
| Uložit diagnostiku do souboru (tlačítko) | není k dispozici | Vyzve k zadání pro název souboru a potom uloží do protokolu do textového souboru. |
| Diagnostika kopírování do schránky (tlačítko) | není k dispozici | Umístí celého protokol do schránky; Tato operace může trvat nějakou dobu v závislosti na velikosti souboru protokolu. |

![Dialogové okno Možnosti Python, karta Diagnostika](media/options-diagnostics.png)

## <a name="interactive-windows-options"></a>Interaktivní možnosti Windows

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Skripty | není k dispozici | Určuje obecné složku pro spouštěcí skripty, které chcete použít pro interaktivní windows pro všechna prostředí. V tématu [spouštěcí skripty](python-environments-window-tab-reference.md#startup-scripts). Upozorňujeme však, že tato funkce momentálně nefunguje. |
| Nahoru/dolů šipky přejděte historie | On | Používá k procházení historie v okně interaktivní klávesy se šipkami. Vymažte toto nastavení použijte klávesy se šipkami místo toho přejděte v rámci interaktivních okna výstupu. |
| Režim dokončení | Pouze vyhodnocení výrazů bez volání funkcí | Určení Dostupní členové na výrazu v okně interaktivní proces může vyžadovat vyhodnocení aktuální nedokončené výrazu, což může vést k vedlejší účinky nebo funkce volané vícekrát. Ve výchozím nastavení je *pouze vyhodnocení výrazů bez volání funkce* vyloučí výrazů, které se zobrazují pro volání funkce, ale vyhodnotí jiné výrazy. Například vyhodnotí `a.b` ale ne `a().b`.  *Nikdy vyhodnocení výrazů* brání všechny vedlejší účinky použití jenom normální IntelliSense modulu pro návrhy. *Vyhodnotit všechny výrazy* vyhodnotí dokončení výraz získat návrhy, bez ohledu na vedlejší účinky. |
| Skrýt návrhy statické analýzy | Off | Pokud nastavíte, zobrazí pouze návrhy, která se získala při vyhodnocování výrazu. Pokud v kombinaci s režim dokončení *nikdy vyhodnocení výrazů*, žádné užitečné dokončených se zobrazí v okně interaktivní. |

![Dialogové okno, karta interaktivních okna Možnosti Python](media/options-interactive-windows.png)

## <a name="advanced-python-editor-options"></a>Rozšířené možnosti editoru Python

### <a name="completion-results"></a>Dokončení výsledky

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Dokončení člen zobrazí průnik členů | Off | Pokud nastavíte, zobrazí jenom dokončených, které jsou podporovány všechny možné typy. |
| Seznam filtrů, které jsou založené na řetězec pro hledání | On | Použije filtry dokončení návrhů při psaní (výchozím nastavení je zaškrtnuto). |
| Automaticky zobrazit dokončených pro všechny identifikátory | On | Zrušte zaškrtnutí tohoto políčka Zakázat dokončených v editoru a interaktivní windows. |

### <a name="selection-in-completion-list"></a>Výběr v seznamu dokončení

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Potvrzené zadáním následujících znaků | {}[]().,:;+-*/%&&#124;^~=<>#@\ | Tyto znaky obvykle podle identifikátor, který jeden může vybrat ze seznamu dokončení, takže je vhodné potvrdit dokončení jednoduše tak, že zadáte znak. Můžete odebrat nebo přidat konkrétní znaků do seznamu podle potřeby.  |
| Zadejte aktuální dokončení potvrzení | On | Pokud nastavíte, klávesy Enter vybere a použije aktuálně vybrané dokončení stejně jako u výše uvedených znaků (ale samozřejmě není k dispozici znak pro Enter tak ho nebylo možné přejít do tohoto seznamu přímo!). |
| Přidejte nový řádek na zadejte na konci plně typu aplikace word | Off | Ve výchozím nastavení Pokud zadáte celá slova, která se zobrazí v automaticky otevřeném okně dokončení a stiskněte klávesu Enter, potvrzení tohoto dokončení. Pomocí této možnosti můžete efektivně potvrdit dokončených po dokončení zápisu identifikátor, tak, aby Enter vloží nový řádek. |

### <a name="miscellaneous-options"></a>Různé možnosti

| Možnost | Výchozí | Popis |
| --- | --- | --- |
| Zadejte popisující režimu při otevírání souborů | On | Automaticky zapněte popisující funkce sady Visual Studio v editoru při otevření souboru kódu Python. |
| Vložení odebrat REPL výzvy | On | Odebere >>> a... z vložený text, povolení nástroje Migrace profilu uživatele kódu pomocí interaktivních okna editoru. Pokud je potřeba zachovat tyto znaky při vkládání z jiných zdrojů, zrušte zaškrtnutí tohoto políčka. |
| Na základě typů názvy barev | On | Umožňuje v kódu jazyka Python zvýrazňování syntaxe. |

![Dialogu Možnosti editoru Python, karta Upřesnit](media/options-editor-advanced.png)