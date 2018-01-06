---
title: "Proměnné Průzkumníku v R Tools pro Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 06/30/2017
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
ms.workload: data-science
ms.openlocfilehash: c75e15def5f9abe98be3f062650c84693716c87e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="variable-explorer"></a>Proměnné Explorer

**Proměnné Explorer** okně Otevřít pomocí **R nástroje > Windows > proměnné Průzkumníka** (nebo kombinace kláves Ctrl + 8, pokud jste použili **R nástroje > Nastavení vědecké účely dat**), znázorňuje všechny proměnné v daném oboru v aktuální relaci R. Například, pokud jste otevřít proměnné Explorer a zadejte následující řádky do [interaktivních okna](interactive-repl.md):

```R
x <- 42
y <- 43
n <- c(1,2,3,5,8,13)
```

Okna proměnných Průzkumník pak vypadat takto:

![Okno Průzkumníka proměnné v sadě Visual Studio](media/variable-explorer-window.png)

Pokud máte složitější rámce R dat definované v relaci, můžete přejít do data. Například po spuštění `cars <- mtcars` datovou sadu můžete procházet rozšířením jiné uzly v Průzkumníku proměnné:

![Rozšířené zobrazení Průzkumníka proměnné](media/variable-explorer-expanded-results.png)

Pokud chcete odstranit proměnné, klikněte pravým tlačítkem a vyberte **odstranit**, nebo vyberte proměnnou a stiskněte klávesu Delete.

Můžete taky vyhledat pozorování v rámci dat pomocí Přírůstkové hledání. Nejprve rozbalte uzly v rámci dat, který chcete hledat, a poté do vyhledávacího pole zadejte hledaný text.

## <a name="details-table-view"></a>Zobrazení podrobností (tabulky)

Protože data jsou často tabulkové, můžete zobrazit všechny komplexního datového typu jako samostatné tabulky vyberete ikonu lupy nebo kliknete pravým tlačítkem a vyberete **zobrazit podrobnosti**.

![Proměnnou tabulky Průzkumník](media/variable-explorer-table-view.png)

Kliknutím na záhlaví sloupce seřadí data podle sloupce (střídavě vzestupně a sestupně). Podržte klávesu Shift a kliknete na další sloupce řazení také přidá tyto sloupce. Kliknutím na sloupec bez posunutí vrátí jeden sloupec řazení.

Pořadí, ve kterém můžete kliknutím na záhlaví sloupce určuje pořadí, ve kterém se provádí toto řazení. Například Shift a kliknutí na **cyl** sloupec a potom kliknutím na Shift **mpg** sloupce seřadí dvakrát v seznamu vzestupně válců a sestupně podle spotřeby paliva:

![Zobrazení tabulky dat řazení podle dvou sloupců.](media/variable-explorer-table-view-sorting.png)

Vzhledem k proměnné Průzkumníka a zobrazení tabulky jsou v systému windows samostatné sady Visual Studio, můžete je uspořádat ale chcete pro pracovní vedle sebe. V tématu [přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md) obecné pokyny.

## <a name="open-in-excel-or-other-csv-capable-application"></a>Otevřete v aplikaci Excel (nebo jiných aplikací podporujících sdílený svazek clusteru)

Pro další zpracování a analýza je často užitečné proměnné relace exportovat do souboru CSV. Export provádí pomocí malé ikony aplikace Excel (![ikonu exportu Excel](media/variable-explorer-excel-icon.png)) vedle každého uzlu v proměnné Průzkumníku nebo kliknutím pravým tlačítkem myši na položku a výběrem **otevřít v aplikaci CSV**. Vyberte ikonu zapisuje data do nového souboru CSV v `%userprofile%\Documents\RTVS_CSV_Exports` složku a potom spustí je přidružen tohoto souboru, který ho otevře v libovolnou aplikaci `.csv` rozšíření.

## <a name="scopes"></a>Obory

Ve výchozím nastavení se otevře v proměnné Exploreru globálním oboru. Obor balíčku můžete přepnout výběrem balíček z rozevíracího seznamu v horní části okna.

![Proměnné Průzkumník zobrazující obor balíčku](media/variable-explorer-package-scopes.png)

Můžete také přepnout obor funkce při zastavení na zarážce v ladicím programu (Všimněte si, že proměnné Explorer nepřepíná automaticky do oboru funkce kódu laděné):

![Proměnné Explorer zobrazující snímek dat během ladění](media/variable-explorer-as-locals-window.png)

Proměnné Explorer automaticky změní rozsah funkce v průběhu kódu v ladicím programu, například zobrazení místních proměnných ve funkci.

## <a name="importing-data-into-variable-explorer"></a>Import dat do proměnné Explorer

Dva příkazy na panelu nástrojů proměnné Explorer, které jsou také k dispozici prostřednictvím **R nástroje > dat** nabídce externích CSV datových import sad do relace prostředí R: **importovat datové sady do relace R z adresy URL webového** a **importovat datové sady do relace R z textového souboru**. 

Jakmile jste zformulovali k importu souboru CSV, sada Visual Studio zobrazí **importovat datovou sadu** dialogové okno, ve kterém máte možnosti řízení, jak analyzovat tohoto datového souboru (to znamená, co je oddělovač polí a určuje způsob zpracování uvozovky). Můžete také zobrazit náhled rámečku importovaných dat a původní soubor dat:

![Dialogové okno importu datové sady](media/variable-explorer-import-dataset-dialog.png)
