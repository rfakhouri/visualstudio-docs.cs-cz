---
title: "Interaktivní REPL s R Tools pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 06/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: da77078bfd0d6e2195169d40dfdbfdb484b68655
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="working-with-the-r-interactive-window"></a>Práce s interaktivních okna R

R Tools pro Visual Studio (RTVS) poskytuje interaktivní okno s R, také známé jako **REPL** (čtení-vyhodnotit-tisk-smyčky) okno, ve kterém můžete zadat kód R a okamžitě zobrazit výsledky. Všechny moduly, syntaxe a proměnné, jakož i technologii IntelliSense, je k dispozici v okně interaktivní.

Okno interaktivní integrována se regulární R editor windows. Vyberte kód a stiskněte klávesu Ctrl + Enter nebo klikněte pravým tlačítkem a vyberte **spouštět v interaktivní**, a spouští se kód řádek po řádku v okně interaktivní jako v případě, že jste ji zadali přímo. Pokud se ukazatel na jeden řádek v okně editor, Ctrl + Enter odešle daného řádku interaktivního okna a pak se posouvá kurzor na další řádek. Tímto způsobem lze pouze stisknutím Ctrl + Enter opakovaně pro jednotlivé kód kroky.

Chcete-li zaznamenat tyto funkce, postupujte podle [Začínáme s R](getting-started-with-r.md) návod a také v následujících částech:

- [Přehled interaktivních okna](#overview-of-the-interactive-window)
- [Pracovní prostory a relace](#workspaces-and-sessions)
- [Pracovní adresář](#working-directory)
- [Historie](#history)

[Fragmenty kódu](code-snippets.md) také pracovat v okně interaktivní jako v R editor windows.

## <a name="overview-of-the-interactive-window"></a>Přehled interaktivních okna

Zadejte platný kód R a stisknutí klávesy Enter na konci řádku spuštěním kódu na tento řádek:

```
> 3 + 3
[1] 6
```

Stisknutím klávesy Enter kdekoli na jednom řádku vstup spouští daného řádku.

Všechny předchozí vstupní a výstupní v REPL je jen pro čtení a nelze změnit. Můžete ale vybrat a zkopírujte text z okna kdykoli, a také vložit. Vložený kód běží, jako kdyby byl zadán řádek po řádku.

To znamená, když začněte psát příkaz a stiskněte klávesu Enter, RTVS zná, když musí být příkaz dál a přejde do režimu Víceřádkový s + výzvy na levé straně a příslušné odsazení. RTVS také dokončení závorky, závorky a složené závorky:

![Položka Víceřádkový příkaz v okně interaktivní](media/repl-multiline-entry.png)

V tomto režimu Víceřádkový klávesy Enter spouští blok kódu jenom v případě, že je umístěný na konci bloku, jinak se vloží nový řádek. Lze však stisknutím Ctrl + Enter na všechny pozici pro okamžité spuštění této blok kódu.

### <a name="toolbar-commands"></a>Příkazy panelu nástrojů

Tady je interaktivní okno s jeho nástrojů:

![Interaktivní okno s panelu nástrojů](media/repl-window.png)

Příkazy nástrojů je následujícím způsobem, většina z nich ekvivalenty klávesnice a jsou k dispozici na také **R nástroje > relace** a **R nástroje > pracovní adresář** nabídky (nebo jak jsme uvedli):

| Tlačítko | Příkaz | Kombinace klíče | Popis | 
| --- | --- | --- | --- |
| ![Tlačítko Obnovit](media/repl-toolbar-01-reset.png) | Resetování | Ctrl+Shift+F10 | Obnoví interaktivních okna relace, vymazání všech proměnných a historie. |
| ![Nezaškrtnuté políčko](media/repl-toolbar-02-clear.png) | Zrušte zaškrtnutí | Ctrl+L | Vymaže výstup zobrazený v okně interaktivní; neovlivňuje proměnné relace nebo historie. |
| ![Historie tlačítka](media/repl-toolbar-03-history.png) | Předchozí příkaz historie<br/>Další příkaz historie | Tlačítka nahoru, dolů<br/>ALT + Šipka nahoru, dolů Alt | Posunutí historie, pomocí určitého chování pro bloky kódu víceřádkový. V tématu [historie](#history). |
| ![Tlačítka pracovního prostoru zatížení](media/repl-toolbar-04-load-workspace.png) | Načtení pracovního prostoru | není k dispozici | Načte předchozí uložit prostoru (viz [pracovních prostorů a relace](#workspaces-and-sessions). |
| ![Pracovní prostor tlačítko Uložit jako](media/repl-toolbar-05-save-workspace-as.png)| Uložit pracovní prostor jako | není k dispozici | Uloží aktuální stav relace jako pracovní prostor (viz [pracovních prostorů a relace](#workspaces-and-sessions). |
| ![Tlačítko zdroj R skript](media/repl-toolbar-06-source-r-script.png) | Zdroj R skript | Ctrl+Shift+S | Volání `source` s aktuálně aktivní R skript v editoru Visual Studio, která se spouští kód.  Toto tlačítko se zobrazí jenom v případě, že soubor R je otevřen v editoru Visual Studio. | 
| ![Zdroj R skript s tlačítkem echo](media/repl-toolbar-07-source-r-script-with-echo.png) | Zdroj R skript s Echo | Ctrl+Shift+Enter | V okně interaktivní stejný jako zdroj R skript ale zobrazí obsah ke skriptu. | 
| ![Přerušení tlačítko R](media/repl-toolbar-08-interrupt-r.png)| Přerušení R | Esc | Zastaví všechny spuštěním kódu v okně interaktivní, jako `while` smyčky na snímku obrazovky zobrazuje na začátku této části. |
| ![Připojit ladicí program tlačítko](media/repl-toolbar-09b-attach-debugger.png)| Připojit ladicí program | není k dispozici | Také k dispozici pomocí **ladění > připojit k R interaktivní** příkaz. | 
| ![Nastavit pracovní adresář na umístění souboru zdroje – tlačítko](media/repl-toolbar-10-set-working-directory-source.png)| Nastavit pracovní adresář pro umístění zdrojových souborů | Ctrl+Shift+E | Nastaví pracovní adresář, který má nejvíce nedávno z domácích zdrojů soubor načíst do okna interaktivní (pomocí `source`). V tématu [pracovní adresář](#working-directory). |
| ![Nastavit pracovní adresář pro tlačítko umístění projektu](media/repl-toolbar-11-set-working-directory-to-project.png) | Nastavit pracovní adresář na umístění projektu | Ctrl+Shift+P | Nastaví pracovní adresář na kořenovém aktuálně načtených projektu v sadě Visual Studio. V tématu [pracovní adresář](#working-directory). |
| (Textové pole) | Vyberte pracovní adresář | není k dispozici | Přímé vstupní pole pro pracovní adresář. V tématu [pracovní adresář](#working-directory). |

## <a name="workspaces-and-sessions"></a>Pracovní prostory a relace

Spuštění kódu v okně interaktivní vytvoří kontextu v aktuální relaci. Kontext se skládá z globální proměnné, definice funkcí, načítání knihovny a tak dále. Tento kontext se nazývají *prostoru*, a můžete uložit a načíst pracovní prostory kdykoli. 

Výběr **uložit prostoru jako** tlačítko nebo pomocí **R nástroje > relace > Uložit prostoru jako...**  příkaz vás vyzve k zadání umístění a název souboru (výchozí rozšíření je `.RData`).

Pro uložení pracovního prostoru pomocí konkrétní název souboru (výchozí hodnota je `.RData`), klikněte na tlačítko Uložit prostor v REPL:

Chcete-li znovu načíst dříve uložené pracovního prostoru, vyberte **zatížení prostoru** tlačítko nebo použijte **R nástroje > relace > zatížení prostoru...**  a přejděte k souboru pracovního prostoru.

**Resetovat** tlačítko nebo **R nástroje > relace > resetovat** vymaže kontextu relace. Pokud používáte vzdálenou relaci, resetování dojde také k odstranění profilu uživatele na vzdáleném počítači zrušte vypnout všechny soubory, které jsou v ní uloženy. (Viz [pracovních prostorů](workspaces.md#directories-on-local-and-remote-computers).)

## <a name="working-directory"></a>Pracovní adresář

Vývojáři se běžně chcete změnit své pracovní adresář v interaktivní relace. Různé příkazů, které jsou k dispozici na panelu nástrojů **R nástroje > pracovní adresář** nabídce a místní nabídky projektu umožňuje snadno nastavit pracovní adresář na umístění zdrojového souboru, umístění nebo projektu nebo libovolný jiný libovolného umístění. To pomůže nemuseli zadávat na úplné názvy cest nebo dlouhé názvy cest relativní k odkazování na soubory.

## <a name="history"></a>Historie

Každého řádku, který zadáte do okna interaktivní obsahuje řádky odeslaných z editoru, se zachovají v REPL na historii. Pak můžete přejít pomocí historie nahoru a dolů klávesy se šipkami, jak jste zvyklí pravděpodobně na příkazovém řádku.

Jedním rozdílem je, že pokud začněte psát na aktuálním řádku a stisknutím klávesy, že aktuálního řádku se zachová historii i prostřednictvím nebyly daného řádku ještě.

Historie v okně interaktivní funguje taky inteligentně s příkazy další blok kódu, které jsou rozmístěny řádky. Když cyklického seznamu historie nahoru a dolů klávesy se šipkami, jsou bloky kódu Víceřádkový načíst jako celou jednotku a zobrazené jako s aktuální položkou. Nyní přejděte klávesy se šipkami prostřednictvím tohoto bloku kódu řádek po řádku, dokud nebude dosaženo horní nebo dolní. V horní části blok kódu na šipku nahoru načte předchozí položce v historii; v řádku dolní načte na šipku dolů na další položku.

Toto chování může vyrovnávat typické malá opětným spuštěním poslední položky v historii se stoupajícím šipku a zadejte stisknutí kláves kombinaci, zatímco přirozeně pro úpravy bloku kódu Víceřádkový stisknutím klávesy šipka nahoru a přejděte do ní.

Aby nedošlo přejdete do bloků více řádků kódu, pomocí tohoto panelu nástrojů tlačítka nebo Alt + šipka nahoru a dolů Alt a všechny takové bloky jsou považovány za jeden řádek.

Nejjednodušší způsob, jak se některé funkce historie je v okně interaktivní je vyzkoušet sami. Následující kód obsahuje několik vhodný řádku jeden a více příkazů. Způsobené kopírováním a vkládáním každý příkaz samostatně, ale k vytvoření použijte s příslušnou historie. (Můžete také vložte kód na samostatném souboru kódu a pak poslat řádky do okna interaktivní s Ctrl + Enter.)

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