---
title: Příkazy
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Visual Studio, commands
- commands, Visual Studio
- command syntax
ms.assetid: 76ffa394-ee89-4629-aba9-1a62b72e6cc1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 294ca45123faf1625b6f09a638ddc089a31d85cc
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043594"
---
# <a name="visual-studio-commands"></a>příkazy sady Visual Studio

Můžete zadat příkazy sady Visual Studio v **příkaz** okně **okamžité** okna, nebo **najít/příkaz** pole. V obou případech znak větší (`>`) označuje, že následující příkaz, a ne operace hledání nebo ladění.

Úplný seznam příkazů a jejich syntaxi můžete najít na **klávesnice** stránku **nástroje** > **možnosti**  >   **Prostředí**.

V lokalizovaných verzích rozhraní IDE lze zadat názvy příkazů v původním jazyce rozhraní IDE nebo v angličtině. Například můžete zadat buď `File.NewFile` nebo `Fichier.NouveauFichier` ve francouzském prostředí IDE, chcete-li spustit tak stejný příkaz.

Mnoho příkazů má aliasy. Seznam příkazových aliasů naleznete v tématu [příkaz aliasy](../../ide/reference/visual-studio-command-aliases.md). Příkaz klávesové zkratky, naleznete v tématu [výchozí klávesové zkratky v sadě Visual Studio](../default-keyboard-shortcuts-in-visual-studio.md).

## <a name="escape-character"></a>Řídicí znak

Řídicí znak pro příkazy sady Visual Studio je znak stříšky (^). Řídicí znak znamená, že znak, který bezprostředně následují je interpretován doslovně a ne v jako řídicí znak. To slouží k vložení uvozovek ("), mezer, úvodních lomítek, střížek nebo jakýmikoli literálními znaky parametru nebo hodnotě switch s výjimkou názvů switchů. Příklad:

```
>Edit.Find ^^t /regex
```

Stříška funguje stejně, ať už se jedná o vnitřní nebo vnější uvozovky. Pokud poslední znak na řádku stříška, je ignorován.

## <a name="commands-with-arguments"></a>Příkazy s argumenty

Následující příkazy přijmou argumenty nebo přepínače:

| Název příkazu | Popis |
| - | - |
| [Přidat existující položku](../../ide/reference/add-existing-item-command.md) | Přidá existující soubor do aktuálního řešení a otevře jej. |
| [Přidat existující projekt](../../ide/reference/add-existing-project-command.md) | Přidá existující projekt do aktuálního řešení. |
| [Přidat novou položku](../../ide/reference/add-new-item-command.md) | Přidá novou položku řešení, jako je například htm, CSS, txt nebo sada rámců do aktuálního řešení a otevře jej. |
| [Alias](../../ide/reference/alias-command.md) | Vytvoří nový alias pro úplný příkaz, úplný příkaz a argumenty, nebo dokonce pro jiný alias. |
| [Ohodnotit příkaz](../../ide/reference/evaluate-statement-command.md) | Vyhodnotí a zobrazí daný příkaz. |
| [Najít](../../ide/reference/find-command.md) | Hledá v souborech pomocí některé podsady z možností, které jsou k dispozici na **najít a nahradit** ovládacího prvku. |
| [Najít v souborech](../../ide/reference/find-in-files-command.md) | Hledá v souborech pomocí některé podsady z možností, které jsou k dispozici na [najít v souborech](../../ide/find-in-files.md). |
| [Přejít na](../../ide/reference/go-to-command.md) | Přesune kurzor na zadaný řádek. |
| [Listovat zásobník volání](../../ide/reference/list-call-stack-command.md) | Zobrazí aktuální zásobník volání. |
| [Zobrazit zpětný překlad](../../ide/reference/list-disassembly-command.md) | Spustí proces ladění a umožňuje určit způsob zpracování chyb. |
| [Listovat paměť](../../ide/reference/list-memory-command.md) | Zobrazí obsah určeného rozsahu paměti. |
| [Seznam modulů](../../ide/reference/list-modules-command.md) | Seznam modulů pro aktuální proces. |
| [Listovat registry](../../ide/reference/list-registers-command.md) | Zobrazí seznam registrů. |
| [Zdroj seznamu](../../ide/reference/list-source-command.md) | Zobrazí zadané řádky zdrojového kódu. |
| [Listovat vlákna](../../ide/reference/list-threads-command.md) | Zobrazí seznam vláken v aktuálním programu. |
| [Okno výstupu příkazů protokolu](../../ide/reference/log-command-window-output-command.md) | Zkopíruje všechen vstup a výstup z příkazového okna do souboru. |
| [Nový soubor](../../ide/reference/new-file-command.md) | Vytvoří nový soubor a přidá jej do aktuálně vybraného projektu. |
| [Otevřít soubor](../../ide/reference/open-file-command.md) | Otevře existující soubor a umožňuje určit editor. |
| [Otevřít projekt](../../ide/reference/open-project-command.md) | Otevře existující projekt a umožňuje přidat projekt do aktuálního řešení. |
| [Tisk](../../ide/reference/print-command.md) | Vyhodnotí výraz a zobrazí výsledky nebo zadaný text. |
| [Příkaz Rychlé kukátko](../../ide/reference/quick-watch-command.md) | Zobrazí zadaný nebo vybraný text v **výraz** pole **Rychlé kukátko** dialogové okno. |
| [nahradit](../../ide/reference/replace-command.md) | Nahradí text v souborech pomocí některé podsady z možností, které jsou k dispozici na **najít a nahradit** ovládacího prvku. |
| [Nahradit v souborech](../../ide/reference/replace-in-files-command.md) | Nahradí text v souborech pomocí některé podsady z možností dostupných v [nahradit v souborech](../../ide/replace-in-files.md). |
| [Nastavit aktuální rámec zásobníku](../../ide/reference/set-current-stack-frame-command.md) | Umožňuje zobrazit konkrétní rámec zásobníku. |
| [Nastavit aktuální vlákno](../../ide/reference/set-current-thread-command.md) | Umožňuje zobrazit konkrétní vlákno. |
| [Nastavit základ](../../ide/reference/set-radix-command.md) | Určuje počet bajtů, které mají zobrazit. |
| [Prostředí](../../ide/reference/shell-command.md) | Spouští programy v rámci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jako by byl proveden příkaz z příkazového řádku. |
| [Příkaz ShowWebBrowser (Zobrazit webový prohlížeč)](../../ide/reference/showwebbrowser-command.md) | Zobrazí adresu URL zadanou v okně webového prohlížeče buď v rámci integrovaného vývojového prostředí (IDE) nebo mimo prostředí IDE. |
| [Start](../../ide/reference/start-command.md) | Spustí proces ladění a umožňuje určit způsob zpracování chyb. |
| [Cesta](../../ide/reference/symbol-path-command.md) | Nastaví seznam adresářů pro ladicí program pro hledání symbolů. |
| [Přepnout zarážku](../../ide/reference/toggle-breakpoint-command.md) | V závislosti na jejím aktuálním stavu na aktuální pozici v souboru se změní na zarážku, zapnout nebo vypnout. |
| [Příkaz Kukátko](../../ide/reference/watch-command.md) | Vytvoří a otevře zadanou instanci **Watch** okna. |

## <a name="see-also"></a>Viz také:

- [Okno příkazového řádku](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Visual Studio aliasy příkazů](../../ide/reference/visual-studio-command-aliases.md)