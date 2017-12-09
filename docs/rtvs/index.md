---
title: R Tools pro Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: hero-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 1ff32914b523b2b515a3d4175e4b3f76ad7ecefd
ms.sourcegitcommit: ae9450e81c4167b3fbc9ee5d1992fc693628eafa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/04/2017
---
# <a name="working-with-r-in-visual-studio"></a>Práce s R v sadě Visual Studio

R je vysoce rozšiřitelný jazyk a prostředí pro statistické výpočty a grafiky. Je distribuován zdarma v rámci licence GNU General Public License, požívá podpora silné komunity a je známý schopnost vytvářet publikace kvality pozemků včetně matematické symboly a vzorce. Další informace o R na [r project.org](https://www.r-project.org/about.html) a [Úvod do R](https://cran.r-project.org/doc/manuals/r-release/R-intro.html).

R nástrojů pro Visual Studio (RTVS) je bezplatný, [open-source](https://github.com/microsoft/RTVS) rozšíření pro Visual Studio 2017 a Visual Studio 2015 Update 3 (nebo vyšší), vydávaný v rámci licencí MIT. (Druhá součást open source názvem [RHost](https://github.com/microsoft/R-Host), která obsahuje odkazy na binární soubory překladač R je vydávaný v rámci licence V2 veřejné GNU.)

> [!Note]
> RTVS se v současné době podporuje pouze v sadě Visual Studio v systému Windows a ne Visual Studio for Mac.

Chcete-li prostředí R v sadě Visual Studio:

- [Nainstalujte nástroje pro R](installation.md).
- Postupujte podle [Začínáme](getting-started-with-r.md) průvodce, a taky [ukázky](getting-started-samples.md) a [získání pomoci](getting-started-help.md) témata.

Potom postupujte podle níže odkazy, které další informace o funkce související s R a také obecné možnosti sady Visual Studio, sám sebe.

| Funkce | Popis | Dokumentaci obecné Visual Studio | 
| --- | --- | --- |
| [Systém projektu Visual Studio](projects.md) | Uspořádání a správu související soubory ve struktuře pohodlný a využít užitečné šablony pro položky, jako je například kódu jazyka R, dokumentace R, R Markdownu, dotazy SQL a uložených procedur. Získejte také [Správce balíčků](package-manager.md) a [systému SQL Server integration](sql-server.md).  | [Řešení a projekty v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md) |
| [Pracovní prostor](workspaces.md) | RTVS můžete vytvořit vazbu na místní a vzdálené pracovní prostory, což umožňuje vytvořit kód R místně s menší sady dat, pak snadno spustit kód na výkonnější počítače založené na cloudu s mnohem větších datových sad. | není k dispozici |
| [Možnosti nástrojů R](options.md) | Ovládat různé aspekty RTVS. | [Dialogové okno Možnosti](../ide/reference/options-dialog-box-visual-studio.md) |
| [Bohaté úpravy, IntelliSense a fragmenty kódu](code-editing.md) | Zahrnuje zvýrazňování, syntaxe [IntelliSense](code-intellisense.md) ve všech váš kód a knihovny, kód formátování, podpis nápovědy, přechod na definici, najít všechny odkazy [výstřižky kódu](code-snippets.md)a další. | [Psaní kódu v editoru kódu a textovém editoru](../ide/writing-code-in-the-code-and-text-editor.md) |
| [R Markdown](rmarkdown.md) | R Markdownu dokumenty můžete sdílet vaše data výsledky se integrované kódu jazyka R uvnitř bloky kódu markdownu. | není k dispozici |
| [Interaktivní okno](interactive-repl.md) | Nabízí úplné REPL prostředí R a umožňuje snadno spouštění kódu ve zdrojovém souboru v okně interaktivní. | není k dispozici |
| [Vizualizace dat](visualizing-data.md) | Vykreslení je nedílnou součástí prostředí R a RTVS podporuje více nezávislých výkresu windows, každou s vlastní historie a možnost přesunout ukazuje zeměpisný mezi windows. Pozemků můžete uložit do rastrového obrázku a soubory PDF nebo jako rastrový obrázek nebo metafile zkopírován do schránky.  | není k dispozici |
| [Průzkumník proměnných](variable-explorer.md) | Proměnné v globální nebo balíček specifické obory, zkontrolujte možnost Zobrazit řazení tabulky a exportovat do souboru CSV. | není k dispozici |
| [Plnohodnotné ladění](debugging.md) | Zahrnuje integraci se interaktivních okna. | [Ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md) |

Viz také [nejčastější dotazy](faq.md).

Následující video také poskytuje kontrolu brief (5m 48s) R Nástroje možnosti:

> [!VIDEO https://www.youtube.com/embed/RcSDEfMgUvU]

## <a name="send-us-your-feedback"></a>Pošlete nám svůj názor!

1. **Problémy Githubu**: je nejlepší způsob, jak kontaktovat tým RTVS [vyplnění problém na Githubu](https://github.com/Microsoft/RTVS/issues), nebo pomocí **R nástroje > zpětné vazby** nabídky.

1. **Odesílání smajlíka / Oblouček nahoru**: **R nástroje > zpětné vazby** nabídka je rychlý způsob, jak odeslat zpětnou vazbu a připojte soubory protokolu RTVS pomáhá při zjišťování vašeho problému. (Se protokoly zapisují do `%temp%/RTVSlogs.zip` v případě, že se mají posílat je samostatně.) Protokolování je zakázáno, pokud jste se rozhodli mimo telemetrická data sady Visual Studio prostřednictvím **pomoci > zpětnou vazbu > Nastavení** nabídky příkazu, nebo během instalace.

1. **E-mailu**: přímé zpětné vazby můžete odeslat týmu na *rtvsuserfeedback (adrese)*.
