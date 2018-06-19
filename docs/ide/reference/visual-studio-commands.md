---
title: Příkazy sady Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Visual Studio, commands
- commands, Visual Studio
- command syntax
ms.assetid: 76ffa394-ee89-4629-aba9-1a62b72e6cc1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f124ccc0a4eb7af470a9631bc2291dbeb089711e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31951788"
---
# <a name="visual-studio-commands"></a>Příkazy sady Visual Studio
Příkazy sady Visual Studio umožňují vyvolat příkaz z **příkaz** okně **Immediate** okno, nebo **najít/příkaz** pole. V každém případě větší než přihlašovací (`>`) slouží k označení, že příkaz spíše než operace hledání nebo ladění je provést.

 Úplný seznam příkazů a jejich syntaxi můžete najít **klávesnice, prostředí, možnosti** dialogové okno.

 Řídicí znak pro příkazy sady Visual Studio je znak šipka nahoru (^), což znamená, že znak, který ho hned za interpretována oznámena, nikoli jako řídicí znak. To slouží k vložení rovné uvozovky ("), mezery, úvodní lomítka, carets nebo jiných literály hodnotu parametru nebo přepínač, s výjimkou názvy přepínače. Například

```
>Edit.Find ^^t /regex
```

 Šipka nahoru funguje stejně, jestli je uvnitř nebo mimo uvozovky. Pokud šipka nahoru poslední znak v řádku, je ignorován.

 Názvy příkazů v lokalizované verze rozhraní IDE, může být zadán buď v nativním jazyce programovacího rozhraní IDE, nebo v angličtině. Například můžete zadat buď `File.NewFile` nebo `Fichier.NouveauFichier` v integrovaném vývojovém prostředí Francouzština provést stejný příkaz.

 Mnoho příkazy mají aliasy. Seznam aliasy příkazů najdete v tématu [aliasy příkazů Visual Studio](../../ide/reference/visual-studio-command-aliases.md).

 Následující příkazy trvat argumenty nebo přepínače.

|Název příkazu|Popis|
|------------------|-----------------|
|[Přidat existující položku](../../ide/reference/add-existing-item-command.md)|Přidá k aktuálnímu řešení existující soubor a otevře ji.|
|[Přidat existující projekt](../../ide/reference/add-existing-project-command.md)|Přidá k aktuálnímu řešení existujícího projektu.|
|[Přidat novou položku](../../ide/reference/add-new-item-command.md)|Přidá novou položku řešení, například .htm, .css, txt nebo rámců k aktuálnímu řešení a otevře ji.|
|[Alias](../../ide/reference/alias-command.md)|Vytvoří nový alias pro dokončení příkazu, úplný příkaz i jeho argumenty nebo i jiný alias.|
|[Příkaz evaluate](../../ide/reference/evaluate-statement-command.md)|Vyhodnotí a zobrazí daný příkaz.|
|[Najít](../../ide/reference/find-command.md)|Vyhledá soubory pomocí podmnožinu možnosti dostupné na **najít a nahradit** ovládacího prvku.|
|[Najít v souborech](../../ide/reference/find-in-files-command.md)|Vyhledá soubory pomocí podmnožinu možnosti dostupné na [hledání v souborech](../../ide/find-in-files.md).|
|[Přejít na](../../ide/reference/go-to-command.md)|Přesune kurzor na zadaný řádek.|
|[Zásobník volání seznamu](../../ide/reference/list-call-stack-command.md)|Zobrazí aktuální zásobníku volání.|
|[Zpětný překlad seznamu](../../ide/reference/list-disassembly-command.md)|Zahájí proces ladění a umožňuje vám určit způsob zpracování chyb.|
|[Seznam paměti](../../ide/reference/list-memory-command.md)|Zobrazí obsah zadaný rozsah paměti.|
|[Seznam modulů](../../ide/reference/list-modules-command.md)|Seznam modulů pro aktuální proces.|
|[Zaregistruje seznam](../../ide/reference/list-registers-command.md)|Zobrazí seznam registrů.|
|[Zdroj seznamu](../../ide/reference/list-source-command.md)|Zobrazí zadané řádků zdrojového kódu.|
|[Seznam vláken](../../ide/reference/list-threads-command.md)|Zobrazí seznam vláken v aktuálním programem.|
|[Výstup z protokolu příkazového okna](../../ide/reference/log-command-window-output-command.md)|Zkopíruje všechny vstup a výstup z okna příkaz do souboru.|
|[Nový soubor](../../ide/reference/new-file-command.md)|Vytvoří nový soubor a přidá ho na aktuálně vybrané projekt.|
|[Otevření souboru](../../ide/reference/open-file-command.md)|Otevře existující soubor a umožňuje vám určit editoru.|
|[Otevřít projekt](../../ide/reference/open-project-command.md)|Otevře existující projekt a slouží k přidání projektu k aktuálnímu řešení.|
|[Otevřít řešení](../../ide/reference/open-solution-command.md)|Otevře existující řešení.|
|[Tisk](../../ide/reference/print-command.md)|Vyhodnotí výraz a zobrazí výsledky nebo zadaný text.|
|[Příkaz Rychlé kukátko](../../ide/reference/quick-watch-command.md)|Zobrazí vybraný nebo zadaný text v **výraz** pole z **Rychlé kukátko** dialogové okno.|
|[Nahradit](../../ide/reference/replace-command.md)|Nahradí text v souborech pomocí podmnožinu možnosti dostupné na **najít a nahradit** ovládacího prvku.|
|[Nahradit v souborech](../../ide/reference/replace-in-files-command.md)|Nahradí text v souborech pomocí podmnožinu dostupných v možnostech [nahradit v souborech](../../ide/replace-in-files.md).|
|[Nastavit aktuální rámec zásobníku](../../ide/reference/set-current-stack-frame-command.md)|Umožňuje zobrazit konkrétní zásobníku.|
|[Nastavit aktuální vlákno](../../ide/reference/set-current-thread-command.md)|Umožňuje zobrazit konkrétní vlákno.|
|[Nastavit základ –](../../ide/reference/set-radix-command.md)|Určuje počet bajtů, které chcete zobrazit.|
|[prostředí shell](../../ide/reference/shell-command.md)|Spustí programy uvnitř [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jako by byl proveden příkaz z příkazového řádku.|
|[Příkaz ShowWebBrowser (Zobrazit webový prohlížeč)](../../ide/reference/showwebbrowser-command.md)|Zobrazí adresu URL, zadejte v okně webového prohlížeče buď v rámci integrované vývojové prostředí (IDE) nebo externí k prostředí IDE.|
|[Start](../../ide/reference/start-command.md)|Zahájí proces ladění a umožňuje vám určit způsob zpracování chyb.|
|[Cesta](../../ide/reference/symbol-path-command.md)|Nastaví seznam adresářů v ladicím programu pro vyhledávání symbolů.|
|[Přepnout zarážku](../../ide/reference/toggle-breakpoint-command.md)|V závislosti na aktuálním stavu, do aktuálního umístění v souboru se změní zarážek zapnout nebo vypnout.|
|[Příkaz Kukátko](../../ide/reference/watch-command.md)|Vytvoří a otevře zadanou instanci systému **sledovat** okno.|

## <a name="see-also"></a>Viz také

- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)