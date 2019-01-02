---
title: Vizualizace dat pomocí jazyka R
description: Jak zobrazit data z aplikací jazyka R v sadě Visual Studio pomocí okna diagramů.
ms.date: 06/29/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 8b0c633e3236f537e9f631df12a5af597e67475c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859078"
---
# <a name="create-visual-data-plots-with-r"></a>Vytvoření vykreslení vizuálních dat pomocí jazyka R

Vykreslení je klíčovou součástí pracovního postupu specializují na data. V nástroje jazyka R pro Visual Studio (RTVS) všechny aktivity zobrazování soustředí kolem jeden nebo více okna diagramů, které jsou navržené pro zlepšení produktivity pomocí tohoto klíče aktivity.

![Vykreslení ústřední obrázek](media/plotting-hero-image.png)

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video (webu youtube.com)](https://www.youtube.com/watch?v=ZTbKmz5RSgY) na vykreslení s jazykem R (2 miliony 02s). |

## <a name="the-plot-window"></a>Okno diagramů

Okno diagramů obsahuje řadu graf, ve kterém je každý diagram generován `plot` příkazu. Například použití `plot(1:100)` vytvoří nové okno diagramů, pokud již není k dispozici:

![1 až 100 lineární vykreslení](media/plotting-1-to-100.png)

Technicky vzato R `plot` příkazy vykreslování svůj výstup do zařízení s R graphics; okno diagramů vykreslí obsah grafiky zařízení R, což je důvod, proč každé okno diagramů je zadané číslo zařízení.

Okna diagramů platí bez ohledu na projekty aplikace Visual Studio a zůstanou otevřené a jak načíst a zavřít projekty.

Generuje se graf používá okna diagramů "aktivní", ukládají se všechny předchozí jeho vykreslení historie diagramů (naleznete v tématu [grafu historie](#plot-history)). Zadejte například `plot(100:1)` a první graf je nahrazen klesající řádku.

Stejně jako všechny ostatní okna sady Visual Studio. podporuje vlastní rozložení okna diagramů (viz [přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md). Okna diagramů můžete ukotven na různých místech v rámci sady Visual Studio, v rámci tohoto rámce se změněnou velikostí nebo získaná mimo rámec výhradně pro změnu velikosti nezávislé. 

Změna velikosti okno diagramů vždy znovu vykreslí vykreslení zajistit nejlepší kvalitu obrazu. Obvykle budete chtít změnit velikost vykreslení před exportem vykreslení do souboru nebo do schránky pomocí příkazů popsaných v další části.

## <a name="plot-window-commands"></a>Příkazy okna diagramů

Panel nástrojů okna diagramů obsahuje použitelných příkazů, většina z nich jsou také k dispozici prostřednictvím **nástroje R** > **vykreslení** nabídky.

| Tlačítko | Příkaz | Popis | 
| --- | --- | --- |
| ![Tlačítko Nová okna diagramů](media/plotting-toolbar-01-new-plot-window.png) | Nové okno diagramů | Vytvoří okno samostatné diagramů se svou vlastní historii. Zobrazit [více okna diagramů](#multiple-plot-windows). |
| ![Aktivací tlačítka okna diagramů](media/plotting-toolbar-02-activate-plot-window.png) | Aktivovat okno diagramů | Nastaví aktuální okno diagramů jako aktivní okno, takže to následné `plot` příkazy jsou předány do tohoto okna. Zobrazit [více okna diagramů](#multiple-plot-windows). Zobrazit [více okna diagramů](#multiple-plot-windows). |
| ![Tlačítko okno historie diagramů](media/plotting-toolbar-03-plot-history.png) | Okno historie diagramů | Otevře se okno s všechna vykreslení v historii zobrazené jako miniatury. Zobrazit [grafu historie](#plot-history). |
| ![Tlačítka historie diagramů](media/plotting-toolbar-04-plot-history-arrows.png) | Předchozí nebo další diagram |  Přejde na další nebo předchozí diagram v historii. Můžete také přejít historie pomocí kombinace kláves Ctrl + Alt + F11 (předchozí) a Ctrl + Alt + F12 (Další). Zobrazit [grafu historie](#plot-history). |
| ![Uložit jako obrázek tlačítka](media/plotting-toolbar-05-save-as-image.png)| Uložit jako obrázek | Zobrazí výzvu k zadání názvu souboru a uloží aktuální diagram (okno obsah, na velikost okna) souboru obrázku. Dostupné formáty jsou `.png`, `.jpg`, `.bmp`, a `.tif`. |
| ![Uložit jako PDF tlačítko](media/plotting-toolbar-06-save-as-pdf.png)| Uložit jako PDF | Uloží aktuální diagram do souboru PDF, použijte aktuální velikost okna. Vykreslení se při změně měřítka PDF znovu zpracovat. |
| ![Kopírovat jako rastrový obrázek tlačítka](media/plotting-toolbar-07-copy-as-bitmap.png)| Kopírovat jako rastrový obrázek | Vykreslení zkopíruje do schránky jako rastrový obrázek rastrové, pomocí aktuální velikost okna. | 
| ![Kopírovat jako metasoubor tlačítko](media/plotting-toolbar-08-copy-as-metafile.png)| Kopírovat jako metasoubor | Zkopíruje do schránky jako vykreslení [Windows metafile](https://en.wikipedia.org/wiki/Windows_Metafile) (Wikipedia). | 
| ![Diagram tlačítko Odebrat](media/plotting-toolbar-09-remove-plot.png)| Odebrat diagram | Odstraní aktuální diagram z historie. |
| ![Vykreslení tlačítko pro vymazání výběru](media/plotting-toolbar-10-clear-all-plots.png) | Vymazat všechna vykreslení | Odebere všechna vykreslení z historie (výzvy k potvrzení). |

## <a name="multiple-plot-windows"></a>Více okna diagramů

Protože odborníci přes data často pracují s mnoha vykreslení z mnoha různých datových sad, RTVS umožňuje vytvořit libovolný počet okna diagramů nezávislé. Pak můžete uspořádat okna však chcete zcela v rámci sady Visual Studio nebo mimo rámec. (Viz [přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md) obecné informace o ukotvení a změna velikosti windows.)

Vytvořit nové okno diagramů pomocí tlačítka panelu nástrojů nebo **nástroje R** > **vykreslení** > **nové okno diagramů**. Stane se nové okno diagramů *aktivní* okno, které je, kde jsou vykreslovány nové vykreslení. Chcete-li změnit aktivní okno, přepněte do něj a vyberte **aktivovat okno diagramů** tlačítka panelu nástrojů nebo **nástroje R** > **vykreslí**  >  **Ktivovat okno diagramů**.

Graf, příliš, jsou nezávislé objekty, což znamená, že můžete zkopírovat nebo přesunout mezi použitím obou a přetahování myší, nebo pomocí okna diagramů **kopírování**, **Vyjmout**, a **vložit** příkazy na kontextu, klikněte pravým tlačítkem a **upravit** nabídky.

Výchozí chování pro přetažení myší je kopii. Pokud chcete přesunout, přetáhněte myší při podržení **Shift** klíč.

## <a name="plot-history"></a>Historie diagramů

Diagram příkazy jsou zachována ve historie diagramů pro každé okno, zajištění, že všechny vaše vykreslení v rámci relace je zachovaná. Chcete-li procházet historii, pomocí tlačítek se šipkami na panelu nástrojů okna diagramů nebo **Ctrl**+**Alt**+**F11** a **Ctrl** + **Alt**+**F12**. Můžete také odebrat jeden vykreslení nebo vymazat všechna vykreslení z okna znovu pomocí tlačítka na panelu nástrojů nebo **nástroje R** > **vykreslí** příkazů nabídky.

Chcete-li zobrazit celou kolekci vykreslení, otevřete okno historie diagramů pomocí tlačítka panelu nástrojů nebo **nástroje R** > **vykreslí** > **okno historie diagramů**.
Historie poskytuje seznam miniatury pro vykreslení, které byly zobrazeny v tomto okně, seskupené podle různých vykreslení windows (nebo zařízení). Na panelu nástrojů pomocí tlačítka lupy změní velikost miniatur.

![Okno historie diagramů](media/plotting-plot-history-window.png)

Otevřete vykreslení v jeho přidružené okna, dvakrát klikněte na tento graf, vyberte ho a pak vyberte **zobrazit diagram** tlačítka panelu nástrojů nebo kliknutím pravým tlačítkem a vyberte **zobrazit diagram**. Můžete také vybrat jednotlivý diagram a kopírování, vyjmutí nebo odstranit z kontextu klikněte pravým tlačítkem na nebo **upravit** nabídky.

Doba života napříč všechna okna Historie diagramů je vázán na životnost interaktivní relace R. Pokud resetovat relaci jazyka R nebo ukončete a restartujte aplikaci Visual Studio je resetovat vaše historie diagramů.

## <a name="programmatically-manipulate-plot-windows"></a>Programově manipulovat s okna diagramů

Můžete programově měnit okna diagramů z kódu jazyka R pomocí čísla zařízení k identifikaci okna konkrétní diagramů. 

- `dev.list()`: Seznam všech zařízení grafiky v rámci aktuální relace jazyka R.
- `dev.new()`: Vytvoření nového zařízení grafiky (nové okno diagramů).
- `dev.set(<device number>)`: Nastavte aktivní grafiky zařízení.
- `dev.off()`: Odstraňte aktivních zařízení.
