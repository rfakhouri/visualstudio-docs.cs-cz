---
title: "Interaktivní REPL Python v sadě Visual Studio | Microsoft Docs"
description: "Jak používat interaktivních okna (REPL) pro kód Python v sadě Visual Studio pro vývoj rychlé kódu."
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 78de05a74fd6626c6bd11e65e01b970c4bc8de34
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="working-with-the-python-interactive-window"></a>Práce s oknem interaktivní Python

Visual Studio poskytuje okno s interaktivní čtení vyhodnotit tiskových smyčky (REPL) pro každé prostředí Python, která vylepšuje REPL dostanete s `python.exe` na příkazovém řádku. Interaktivních okna (otevřít pomocí **zobrazení > ostatní okna > &lt;prostředí&gt; interaktivní** příkazy nabídky) vám umožní zadat libovolný kód Python a zobrazte výsledky okamžitě. Tento způsob kódování pomáhá Další informace a experimentovat s rozhraní API a knihovny a interaktivně vyvíjet funkční kód pro zahrnutí do vašich projektů.

![Okno interaktivní Python](media/interactive-window.png)

Visual Studio má počet Python REPL režimy zvolit:

| REPL | Popis | Úpravy | Ladění | Obrázky |
| --- | --- | --- | --- | --- |
| Standard | Výchozí REPL, rozhovory Python přímo | Standardní úpravy (víceřádkových atd.). | Ano, prostřednictvím`$attach` | Ne |
| Ladit | Výchozí REPL rozhovory vyladěnou procesu Python | Standardní úpravy | Pouze ladění | Ne |
| IPython | REPL komunikuje se IPython back-end | Příkazy IPython, výhody, které Pylab | Ne | Ano, vložené v REPL |
| IPython bez Pylab | REPL komunikuje se IPython back-end | Standardní IPython | Ne | Ano, oddělte okna | 

Toto téma popisuje **standardní** a **ladění** REPL režimy. Informace o režimech IPython v [pomocí IPython REPL](interactive-repl-ipython.md).

Podrobný návod s příklady, včetně interakce s editoru, jako je například Ctrl + Enter, najdete v části [kurzu krok 3: použití okna interaktivní REPL](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md). Video úvod naleznete v tématu [interaktivní okno Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=gJYKY5LWE_4605918567) (Microsoft Virtual Academy, 2m22s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Python-Interactive-Window-gJYKY5LWE_4605918567]

## <a name="opening-an-interactive-window"></a>Otevření interaktivních okna

Existuje několik způsobů otevřete okno interaktivní pro prostředí.

Nejdřív přejít do okna prostředí Python (**zobrazení > ostatní okna > prostředí Python** nebo Ctrl-K, Ctrl-') a vyberte **otevřete okno interaktivní** příkaz nebo tlačítko pro zvolený prostředí .

![Interaktivní okno odkaz v okně prostředí Python](media/interactive-window-opening.png)

Druhý, u dolního okraje **zobrazení > ostatní okna** nabídky, je **interaktivní okno Python** příkaz pro vaše prostředí výchozí, stejně jako příkaz, který má přejít do okna prostředí:

![Položky nabídky interaktivních okna v zobrazení > ostatní okna](media/interactive-window-menu.png)

Třetí, můžete otevřít okno s interaktivní v souboru spuštění ve vašem projektu, nebo pro soubor samostatné výběrem **ladění > spustit [projekt | V interaktivní Python soubor]** příkazu nabídky (Shift + Alt + F5):

![Spustit projekt v nabídce interaktivní Python](media/interactive-execute-project.png)

Nakonec můžete vybrat kód v souboru a použít [kód poslat interaktivního příkazu](#send-code-to-interactive-command) popsané dole.

## <a name="interactive-window-options"></a>Interaktivní okno Možnosti

Můžete ovládat různé aspekty interaktivních okna prostřednictvím **nástroje > Možnosti > Python Tools > Interaktivní Windows** (najdete v části [možnosti](python-support-options-and-settings-in-visual-studio.md)):

![Možnosti interaktivních okna Python](media/options-interactive-windows.png)

## <a name="using-the-interactive-window"></a>Pomocí interaktivních okna

Jakmile je otevřené okno interaktivní, můžete začít zadávání kódu řádek po řádku v `>>>` řádku. Okno interaktivní provádí každý řádek, zadejte ji, která zahrnuje importu modulů, definování proměnných, a tak dále:

![Okno interaktivní Python](media/interactive-window.png)

Výjimkou je, aby dokončení příkazu, jako např. kdy jsou potřeby další řádky kódu `for` příkaz končí v dvojtečkou jako v příkladu nahoře. Příkaz řádku v těchto případech se změní na `...` označující, že je třeba zadat další řádky bloku, jak je znázorněno na řádcích čtvrté a páté v na obrázku výše. Po stisknutí klávesy Enter na prázdný řádek, interaktivní okno zavře bloku a běží v překladač.

> [!Tip]
> Okno interaktivní vylepšuje obvyklé Python prostředí příkazového řádku REPL automaticky odsazením příkazy, které patří do okolního oboru. Historii (třeba připomenout s na šipku nahoru) také poskytuje Víceřádkový položek, zatímco příkazového řádku REPL obsahuje pouze jeden řádky.

<a name="meta-commands"></a>Okno interaktivní také podporuje několik meta příkazy. Všechny příkazy meta začínat `$`, a zadat `$help` získáte seznam příkazů meta a `$help <command>` získat podrobnosti o použití pro konkrétní příkaz.

| Meta-příkazu | Popis |
| --- | --- |
| `$$` | Vloží poznámku, která je vhodné komentář kódu v rámci relace. |
| `$attach` | Připojí ladicí program Visual Studio pro proces REPL okna pro povolení ladění. |
| `$cls`, `$clear` | Vymaže obsah okna editoru a ponechá historie a provádění kontextu. |
| `$help` | Zobrazit seznam příkazů nebo v nápovědě k určitému příkazu. |
| `$load` | Načte příkazy ze souboru a provede až do dokončení. |
| `$mod` | Název zadaného modulu přepínačů aktuálního oboru. |
| `$reset` | Obnoví prostředí pro spuštění na počáteční stav, ale zachová historii. |
| `$wait` | Čeká na alespoň zadanou hodnotu v milisekundách. |

Příkazy jsou také rozšiřitelné rozšířeními sady Visual Studio pomocí implementace a export `IInteractiveWindowCommand` ([příklad](https://github.com/Microsoft/PTVS/blob/master/Python/Product/PythonTools/PythonTools/Repl/InteractiveWindowCommands.cs#L85)).

## <a name="switching-scopes"></a>Přepínání oborů

Ve výchozím nastavení je vymezen interaktivních okna pro projekt do projektu po spuštění souboru jako v případě, že jste spustili z příkazového řádku. Pro soubor samostatné ho je obory na daný soubor. V každém okamžiku ale rozevírací nabídce v horní části okna interaktivní vám umožní změnit obor kdykoli během relace REPL:

![Interaktivní okno oborů](media/interactive-scopes.png)

Po importování modulu, jako je například zadáním `import importlib`, možnosti se zobrazí v rozevíracím seznamu přepnout do kteréhokoliv oboru v tomto modulu. Zprávy v okně interaktivní také označuje nový obor, takže můžete sledovat, jak jste získali do určité stavu během relace.

Zadání `dir()` v oboru zobrazí platné identifikátory v tomto oboru, včetně funkce názvů, třídy a proměnné. Například pomocí `import importlib` následuje `dir()` ukazuje následující:

![Interaktivní okno v oboru importlib –](media/interactive-importlib-scope.png)

<a name="sending-code-to-interactive"</a>

## <a name="send-code-to-interactive-command"></a>Kód poslat interaktivního příkazu

Kromě přímo pracovní interaktivních okna, můžete vybrat kódu v editoru klikněte pravým tlačítkem a zvolte **poslat interaktivní** nebo stiskněte klávesu Ctrl + Enter.

![Odeslat příkaz interaktivní nabídky](media/interactive-send-to.png)

Tento příkaz je užitečné pro vývoj iterativní nebo evolučním kód, včetně testování kódu, když budete vyvíjet ho. Jakmile jste odeslané úsek kódu do okna interaktivní a zobrazit její výstup, stisknutí klávesy na šipku nahoru nezobrazovat kód, upravte ho a otestovat ji rychle stisknutím kláves Ctrl + Enter. (Stisknutím klávesy Enter na konci vstupu provádí, ale stisknutím klávesy Enter uprostřed vstup vloží nový řádek.) Jakmile se kód, který chcete, můžete snadno zkopírovat ji zpět do souboru projektu.

> [!Tip]
> Ve výchozím nastavení, Visual Studio odebere >>> a... REPL zobrazí výzvu, při vkládání do editoru kódu pomocí interaktivních okna. Toto chování lze změnit na **nástroje > Možnosti > textový Editor > Python > Upřesnit** kartě pomocí **vložení odebere REPL výzvy** možnost. V tématu [možnosti - různé možnosti](python-support-options-and-settings-in-visual-studio.md#miscellaneous-options).

<!-- After 15.3 is released, you can also press "Undo" after pasting to restore prompts. Press "Undo" a second time to remove the pasted code entirely. -->

Při použití souboru kódu jako zápisník, často mají malý blok kódu, který chcete odeslat všechny najednou. K seskupení kódu, označit jako kód *buňky kódu* přidáním komentář počínaje `#%%` na začátek buňky, které končí předchozí. Buňky kódu můžete sbalené a rozbalené a uvnitř buňky kódu pomocí kláves Ctrl + Enter odesílá celý buňky do okna interaktivní a přesune na další stránku.

Sada Visual Studio také zjistí buňky kódu počínaje komentáře jako `# In[1]:`, který je formátem, kterou dostanete při exportu poznámkového bloku Jupyter jako soubor Python. Toto zjišťování umožňuje snadné spuštění Poznámkový blok z [poznámkových bloků Azure](https://notebooks.azure.com/) stáhnout jako soubor Python, otevřete v sadě Visual Studio a pomocí kláves Ctrl + Enter ke spuštění jednotlivých buněk.

![Interaktivní kód buněk](media/interactive-code-cells.png)

## <a name="intellisense-behavior"></a>Chování IntelliSense

Okno interaktivní zahrnuje IntelliSense podle živé objekty, na rozdíl od editoru kódu, ve kterém je IntelliSense podle pouze analýza zdrojového kódu. Tyto návrhy jsou více správné v okně interaktivní, zejména s dynamicky generovaného kódu. Nevýhodou je, že funkce s vedlejšími účinky (například protokolování zpráv) může mít vliv na vaše vývojové prostředí.

Pokud toto chování je problém, změňte nastavení v části **nástroje > Možnosti > Python Tools > Interaktivní Windows** v **režim dokončení** skupiny, jak je popsáno na [možnosti - Interaktivní možnosti Windows](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options).
