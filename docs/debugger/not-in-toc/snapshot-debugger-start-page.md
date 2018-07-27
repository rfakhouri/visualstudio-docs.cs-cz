---
title: Úvodní stránky pro Snapshot Debugger
ms.date: 07/14/2018
robots: noindex, nofollow
ms.technology: vs-ide-debug
ms.topic: reference
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c7b5b48aeeb0cfcaeed72a06bfb6709892c58de7
ms.sourcegitcommit: e6ef03cc415ca67f75fd1f26e0e7b8846857166d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2018
ms.locfileid: "39310125"
---
# Začínáme s Snapshot Debugger

Visual Studio Snapshot Debugger je teď připojený k vaší službě a můžete spustit shromažďování snímků pomoci s laděním.

Použití ladicího programu snímků, nastavit některé snímkovací body ve vašem kódu, klikněte na tlačítko a začněte shromažďovat snímky a spusťte váš scénář. Při spuštění kódu v které jste nastavili snímkovacího bodu, se pořídí snímek vaší aplikace. Otevřete v sadě Visual Studio v okně diagnostické nástroje kliknutím na snímek. Teď můžete ladit snímek služby stejným způsobem, jako je místní. Podrobné pokyny pokračujte ve čtení.

## Umožňuje shromáždit a zobrazit snímky

Snapshot Debugger shromažďuje snímky z vaší aplikace. Snímky jsou podobné obrázky z vašich aplikací v bodě v čase. Visual Studio říct, kdy a kde získá snímek nastavením snímkovacího bodu v kódu. V snímkovacích bodů nastavte všechny podmínky, které potřebujete, abyste měli jistotu, že získat snímek problém, který hledáte.

### Nastavte snímkovacího bodu

1. V editoru kódu klikněte na levém hřbetu vedle řádku kódu, které vás zajímají nastavení snímkovacího bodu. Ujistěte se, že je kód, o kterém víte, že se spustí. 

    ![Nastavení snímkovacího bodu v editoru](../media/snapshot-startpage-set-snappoint.png)

    Fialový šestiúhelník se zobrazí, pokud kliknete na levé straně.

2. Klikněte na tlačítko **spustit shromažďování** zapnout snímkovacího bodu.

### Otevření snímku

1. Při dosažení snímkovacího bodu, se zobrazí v okně diagnostické nástroje na pravé straně snímku. Pokud se okno se neotevře, které můžete otevřít výběrem **ladění** > **Windows** > **zobrazit diagnostické nástroje**. 

    ![Snímek v okně diagnostické nástroje](../media/snapshot-startpage-diagsession-window.png)

2. Dvakrát klikněte na snímek můžete otevřít.

### Kontrolovat data snímku

V tomto zobrazení můžete najedete myší proměnné k zobrazení datových tipech, pomocí místních hodnot, kukátek a volání zásobníku systému windows a také vyhodnocujte výrazy.

Je webem jako takovým stále aktivní a nejsou to vliv na koncové uživatele. Ve výchozím nastavení je pouze jeden snímek zachycena na snímkovacího bodu. To znamená, že po zachytávání snímku snímkovací bod vypne. Pokud chcete zaznamenat další snímek na snímkovacího bodu, můžete zapnout snímkovací bod zpět kliknutím **aktualizovat shromažďování**.

### Nastavte protokolovacích bodů:

1. Klikněte pravým tlačítkem na ikonu snímkovací bod (fialová šestiúhelník) a zvolte **nastavení**.

2. V **snímkovací bod nastavení** okně **akce**.

    ![Snímkovací bod podmínky](../media/snapshot-startpage-logpoint.png)

3. V **zpráva** zadejte zprávu protokolu, který chcete zaznamenat. Můžete také vyhodnotit proměnné ve zprávě protokolu je umístit uvnitř složených závorek.

    Pokud se rozhodnete **odeslat do okna výstup**, zpráva se zobrazí v okně diagnostické nástroje, když protokolovacích bodů: dosažení. 

    Pokud se rozhodnete **odeslat do protokolu aplikace**, zobrazí se zpráva kdekoli, zobrazí se zprávy z `System.Diagnostics.Trace` (nebo `ILogger` v .NET Core), jako jsou App Insights, při dosažení protokolovacích bodů:.

## Víc se uč

Další informace o ladicím programu snímků můžete najít na [stránky dokumentace](../debug-live-azure-applications.md). Další informace o nastavení podmínky, aby bylo snazší najít chyby.

## Není "zprávu již nezobrazovat

Chcete-li již nezobrazovat úvodní stránku ladicího programu snímků při připojování ladicího programu snímků, změňte **Show "Začínáme" stránku při spuštění relace** možnost **nástroje**  >   **Možnosti** > **Snapshot Debugger**. 

![Stránka – možnost nástroje ladicího programu snímků](../media/snapshot-startpage-tools-options.png)
