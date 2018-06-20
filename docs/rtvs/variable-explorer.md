---
title: Proměnné Průzkumníka pro R
description: Proměnné Explorer v sadě Visual Studio zobrazí všechny proměnné v daném oboru v aktuální relaci R.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 5af85e8112a4017465329b0284772dd6514ba415
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238379"
---
# <a name="variable-explorer"></a>Průzkumník proměnných

**Proměnné Explorer** okně Otevřít pomocí **R nástroje** > **Windows** > **proměnné Explorer** (nebo **Ctrl**+**8** Pokud jste použili **R nástroje** > **nastavení vědecké účely dat**), znázorňuje všechny proměnné v daném oboru v aktuální relaci R. Například, pokud jste otevřít proměnné Explorer a zadejte následující řádky do [interaktivních okna](interactive-repl-for-r-in-visual-studio.md):

```R
x <- 42
y <- 43
n <- c(1,2,3,5,8,13)
```

Okna proměnných Průzkumník pak vypadat takto:

![Okno Průzkumníka proměnné v sadě Visual Studio](media/variable-explorer-window.png)

Pokud máte složitější rámce R dat definované v relaci, můžete přejít do data. Například po spuštění `cars <- mtcars` datovou sadu můžete procházet rozšířením jiné uzly v Průzkumníku proměnné:

![Rozšířené zobrazení Průzkumníka proměnné](media/variable-explorer-expanded-results.png)

Pokud chcete odstranit proměnné, klikněte pravým tlačítkem a vyberte **odstranit**, nebo vyberte proměnnou a stiskněte klávesu **odstranit** klíč.

Můžete taky vyhledat pozorování v rámci dat pomocí Přírůstkové hledání. Nejprve rozbalte uzly v rámci dat, který chcete hledat, a poté do vyhledávacího pole zadejte hledaný text.

## <a name="details-table-view"></a>Zobrazení podrobností (tabulky)

Protože data jsou často tabulkové, můžete zobrazit všechny komplexního datového typu jako samostatné tabulky vyberete ikonu lupy nebo kliknete pravým tlačítkem a vyberete **zobrazit podrobnosti**.

![Proměnnou tabulky Průzkumník](media/variable-explorer-table-view.png)

Kliknutím na záhlaví sloupce seřadí data podle sloupce (střídavě vzestupně a sestupně). Podržíte stisknutou **Shift** a kliknutím na další sloupce k řazení také přidá tyto sloupce. Kliknutím na sloupec bez **Shift** vrátí jeden sloupec řazení.

Pořadí, ve kterém můžete kliknutím na záhlaví sloupce určuje pořadí, ve kterém se provádí toto řazení. Například **Shift a kliknutí na** **cyl** sloupce, pak **Shift a kliknutí na** **mpg** sloupec dvakrát, seřadí seznam pro vzestupné počet cylindrů a sestupné miles za spotřeby:

![Zobrazení tabulky dat řazení podle dvou sloupců.](media/variable-explorer-table-view-sorting.png)

Vzhledem k proměnné Průzkumníka a zobrazení tabulky jsou v systému windows samostatné sady Visual Studio, můžete je uspořádat ale chcete pro pracovní vedle sebe. V tématu [přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md) obecné pokyny.

## <a name="open-in-excel-or-other-csv-capable-application"></a>Otevřete v aplikaci Excel (nebo jiných aplikací podporujících sdílený svazek clusteru)

Pro další zpracování a analýza je často užitečné proměnné relace exportovat do souboru CSV. Export provádí pomocí malé ikony aplikace Excel (![ikonu exportu Excel](media/variable-explorer-excel-icon.png)) vedle každého uzlu v proměnné Explorer, případně podle **pravým tlačítkem myši na** položku a výběrem **otevřít v aplikaci CSV**. Vyberte ikonu zapisuje data do nového souboru CSV v *%userprofile%\Documents\RTVS_CSV_Exports* složku a potom spustí je přidružen tohoto souboru, který ho otevře v libovolnou aplikaci *.csv*rozšíření.

## <a name="scopes"></a>Obory

Ve výchozím nastavení se otevře v proměnné Exploreru globálním oboru. Obor balíčku můžete přepnout výběrem balíček z rozevíracího seznamu v horní části okna.

![Proměnné Průzkumník zobrazující obor balíčku](media/variable-explorer-package-scopes.png)

Můžete také přepnout obor funkce při zastavení na zarážce v ladicím programu (Všimněte si, že proměnné Explorer nepřepíná automaticky do oboru funkce kódu laděné):

![Proměnné Explorer zobrazující snímek dat během ladění](media/variable-explorer-as-locals-window.png)

Proměnné Explorer automaticky změní rozsah funkce v průběhu kódu v ladicím programu, například zobrazení místních proměnných ve funkci.

## <a name="import-data-into-variable-explorer"></a>Import dat do proměnné Explorer

Dva příkazy na panelu nástrojů proměnné Explorer, které jsou také k dispozici prostřednictvím **R nástroje** > **Data** nabídce externích CSV datových import sad do relace prostředí R: **importovat Datové sady do relace R z adresy URL webového** a **importovat datové sady do relace R z textového souboru**.

Jakmile jste zformulovali k importu souboru CSV, sada Visual Studio zobrazí **importovat datovou sadu** dialogové okno, ve kterém máte možnosti řízení, jak analyzovat tohoto datového souboru (to znamená, co je oddělovač polí a určuje způsob zpracování uvozovky). Můžete také zobrazit náhled rámečku importovaných dat a původní soubor dat:

![Dialogové okno importu datové sady](media/variable-explorer-import-dataset-dialog.png)
