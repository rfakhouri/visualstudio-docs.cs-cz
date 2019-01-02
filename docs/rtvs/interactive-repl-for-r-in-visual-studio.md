---
title: Interaktivní okno REPL pro R
description: Jak používat interaktivní prostředí REPL pro inVisual Studio R, který je součástí pomocí okna editoru.
ms.date: 06/28/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 7df300a57120bec2fc93ec7433a7ea9fdd3a2fc8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947072"
---
# <a name="work-with-the-r-interactive-window"></a>Práce s interaktivním okně jazyka r.

Nástroje R pro Visual Studio (RTVS) poskytuje interaktivní okno R, označované také jako **REPL** (čtení-vyhodnocení-Print-Loop) okno, ve kterém můžete zadat kód R a hned vidět výsledky. Všechny moduly, syntaxi a proměnné, jakož i technologii IntelliSense, je k dispozici v interaktivním okně.

Interaktivní okno je integrovaná taky s regulární systému windows R editoru. Můžete vybrat kód a stiskněte klávesu **Ctrl**+**Enter**, nebo klikněte pravým tlačítkem a vyberte **provést v Interactive**, a spuštění kódu řádek po řádku v interaktivní okno jako kdyby jste ho zadali přímo. Když je ukazatel myši na jeden řádek v okně editoru **Ctrl**+**Enter** odešle tento řádek do interaktivního okna a pak přesune kurzor na další řádek. Tímto způsobem můžete stačí stisknout **Ctrl**+**Enter** opakovaně ke krokování kódu.

Pokud chcete vyzkoušet tyto funkce, postupujte [Začínáme s jazykem R](getting-started-with-r.md) návod a také části v tomto článku. [Fragmenty kódu](code-snippets-for-r.md) fungovat i v interaktivním okně, jako je tomu v oknech editoru jazyka R.

## <a name="overview-of-the-interactive-window"></a>Přehled interaktivní okno

Zadáním platné kód R a stisknutím klávesy **Enter** na konci řádku spustí kód, který na tomto řádku:

```repl
> 3 + 3
[1] 6
```

Stisknutím klávesy **Enter** kdekoli na jeden řádek vstupu poběží i v daném řádku.

Všechny předchozí vstupů a výstupů v REPL je jen pro čtení a nedá se změnit. Můžete ale vybrat a kopírovat text z okna v okamžiku, stejně jako vložený. Vložený kód se spustí jako by byl zadán řádek po řádku.

To znamená, když začnete psát příkaz a stiskněte klávesu **Enter**, RTVS pozná, pokud příkaz musí pokračovat a přejde do víceřádkového režimu s + výzvy na levé straně a odpovídající odsazení. RTVS také dokončí závorky, hranaté závorky a složených závorek:

![Příkaz Víceřádkový vstupní v interaktivním okně](media/repl-multiline-entry.png)

V tomto režimu více řádky **Enter** klíč spouští blok kódu, pouze když umístěný na konci bloku, jinak vloží nový řádek. Však můžete stisknout **Ctrl**+**Enter** v jakékoliv pozici pro spuštění tohoto kódu blokovat okamžitě.

### <a name="toolbar-commands"></a>Příkazy panelu nástrojů

Tady je interaktivní okno s jeho nástrojů:

![Interaktivní okno s panelem nástrojů](media/repl-window.png)

Příkazy nástrojů jsou následující, z nichž většina ekvivalenty klávesnice a jsou také k dispozici na **nástroje R** > **relace** a **nástroje R**  >  **Pracovní adresář** nabídek (nebo jak je uvedeno):

| Tlačítko | Příkaz | Kombinace kláves | Popis | 
| --- | --- | --- | --- |
| ![Tlačítko Obnovit.](media/repl-toolbar-01-reset.png) | Resetovat | **CTRL**+**Shift**+**F10** | Interaktivní okno relace, zrušíte všechny proměnné a historii obnoví. |
| ![Tlačítko Vymazat](media/repl-toolbar-02-clear.png) | Vymazat | **CTRL**+**L** | Vymaže výstupu v interaktivním okně; nemá vliv na relace proměnné nebo historie. |
| ![Historie tlačítka](media/repl-toolbar-03-history.png) | Předchozí příkaz historie<br/>Další příkaz historie | **Až**, **dolů**<br/>**ALT**+**nahoru**, **Alt**+**dolů** | Posune historii, pomocí určitého chování kódu víceřádkových bloků. Zobrazit [historie](#history). |
| ![Tlačítko Načíst pracovní prostor](media/repl-toolbar-04-load-workspace.png) | Načíst pracovní prostor | není k dispozici | Načte předchozí uložit pracovní prostor (viz [pracovních prostorů a relace](#workspaces-and-sessions). |
| ![Uložit pracovní prostor jako tlačítko](media/repl-toolbar-05-save-workspace-as.png)| Uložit pracovní prostor jako | není k dispozici | Uloží aktuální stav relace jako pracovní prostor (viz [pracovních prostorů a relace](#workspaces-and-sessions). |
| ![Tlačítko skript r.](media/repl-toolbar-06-source-r-script.png) | Source skript R | **CTRL**+**Shift**+**S** | Volání `source` s aktuálně aktivních skriptů R v editoru sady Visual Studio, která se spouští kód.  Toto tlačítko se zobrazí pouze v případě, že soubor R je otevřen v editoru sady Visual Studio. | 
| ![Source skript R s echo tlačítko](media/repl-toolbar-07-source-r-script-with-echo.png) | Source skript R s Echo | **CTRL**+**Shift**+**zadejte** | Stejné jako Source skript R se ale zobrazí obsah skriptu v interaktivním okně. |
| ![Přerušit R tlačítko](media/repl-toolbar-08-interrupt-r.png)| Přerušit R | **ESC** | Zastaví všechny spuštěním kódu v interaktivním okně, jako `while` smyčky na snímku obrazovky se zobrazí na začátku této části. |
| ![Připojit ladicí program tlačítko](media/repl-toolbar-09b-attach-debugger.png)| Připojit ladicí program | není k dispozici | Rovněž k dispozici na **ladění** > **připojit k interaktivní R** příkazu. | 
| ![Nastavte pracovní adresář pro tlačítko umístění zdrojového souboru](media/repl-toolbar-10-set-working-directory-source.png)| Nastavit pracovní adresář na umístění zdrojových souborů | **CTRL**+**Shift**+**E** | Nastaví pracovní adresář, který naposledy Source soubor načíst do interaktivního okna (pomocí `source`). Zobrazit [pracovní adresář](#working-directory). |
| ![Nastavte pracovní adresář pro tlačítko umístění projektu](media/repl-toolbar-11-set-working-directory-to-project.png) | Nastavit pracovní adresář na umístění projektu | **CTRL**+**Shift**+**P** | Nastaví pracovní adresář kořenového adresáře aktuálně načtený projekt v sadě Visual Studio. Zobrazit [pracovní adresář](#working-directory). |
| (Textové pole) | Vybrat pracovní adresář | není k dispozici | Přímé vstupní pole pro pracovní adresář. Zobrazit [pracovní adresář](#working-directory). |

## <a name="workspaces-and-sessions"></a>Pracovní prostory a relace

Spouštění kódu v interaktivním okně vytvoří kontext v aktuální relaci. Kontext se skládá z globálních proměnných, definic funkcí, načtení knihovny a tak dále. Tento kontext se nazývají *pracovní prostor*, a můžete uložit a načíst pracovní prostory v každém okamžiku. 

Výběr **uložit pracovní prostor jako** tlačítko nebo pomocí **nástroje R** > **relace** > **uložit pracovní prostor jako**příkaz vás vyzve k zadání umístění a název souboru (výchozí příponou je *. RData*).

K uložení pracovního prostoru pomocí konkrétní název souboru (výchozí hodnota je *. RData*), klikněte na **uložit pracovní prostor** tlačítko v REPL:

Chcete-li znovu načíst dříve uložený pracovního prostoru, vyberte **načtení pracovního prostoru** tlačítko, nebo použijte **nástroje R** > **relace** > **zatížení Pracovní prostor** a přejděte na soubor pracovního prostoru.

**Resetování** tlačítko nebo **nástroje R** > **relace** > **resetování** vymaže kontextu relace. Pokud používáte vzdálenou relaci, resetuje se také odstraní profilu uživatele na vzdáleném počítači zrušte vypnout všechny soubory uložené. (Viz [pracovní prostory](r-workspaces-in-visual-studio.md#directories-on-local-and-remote-computers).)

## <a name="working-directory"></a>Pracovní adresář

Vývojáři obvykle chcete změnit svoje pracovní adresář v interaktivní relaci. Různé příkazy, které jsou k dispozici na panelu nástrojů **nástroje R** > **pracovní adresář** nabídky a místní nabídky projektu umožňuje snadno nastavit pracovní adresář na umístění zdrojového souboru , umístění nebo projektu nebo v jiném libovolného umístění. To umožňuje vyhnout se zadáním úplné názvy cest nebo delší relativní cesty k odkazování na soubory.

## <a name="history"></a>Historie

Každého řádku, který zadáte v interaktivním okně, obsahuje řádky odeslané z editoru, jsou zachovány REPL historie. Pak můžete Navigovat pomocí historie s nahoru a dolů šipkami, jak jste zvyklí pravděpodobně na příkazovém řádku.

Jedním rozdílem je, že pokud začněte psát na aktuálním řádku a stisknutím klávesy, že aktuální řádek je zachováno v historii klidně i prostřednictvím nespustily tento řádek ještě.

Historie v interaktivním okně funguje taky inteligentně s příkazy další blok kódu, které jsou rozmístěny řádky. Při procházením historie s nahoru a dolů šipkami, bloky kódu více řádků se načte jako celé jednotky a zobrazí jako aktuální položku. V tomto okamžiku se šipkami procházet daný blok kódu řádek po řádku, dokud nebude dosaženo horní nebo dolní. V horní části bloku kódu na šipku nahoru načte předchozí položka historie; na řádku dolního načte šipku dolů na další položku.

Toto chování obsáhne typický případ znovu spustit poslední položka v historii s šipkou nahoru a **Enter** stisknutí kláves kombinaci, přičemž přirozeně pro úpravy bloku kódu více řádky stisknutím kombinace kláves Šipka nahoru na Přejděte do něj.

Pokud chcete vyhnout, přejdete do bloků kódu více řádků, použijte tlačítka panelu nástrojů nebo **Alt**+**nahoru** a **Alt**-**dolů**, a tyto bloky jsou považovány za jeden řádek.

Nejjednodušší způsob, jak některé funkce historie je chcete vyzkoušet sami v interaktivním okně. Následující kód obsahuje několik vhodný řádku jeden a více příkazů. Pomocí kopírování a vkládání každý příkaz samostatně, ale k vytvoření odpovídající historie. (Můžete také vložit kód v samostatném souboru kódu a potom odeslat řádků do interaktivního okna s **Ctrl**+**Enter**.)

```R
3 + 3

4 + 4

5 + 5

add <- function (x, y) {
  return (x + y)
}

sub <- function (x, y) {
  return (x - y)
}
```