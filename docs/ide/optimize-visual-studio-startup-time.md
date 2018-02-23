---
title: "Optimalizace výkonu v sadě Visual Studio | Microsoft Docs"
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing performance [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: d1508121-8499-4084-8eb5-fa89fa7b17d3
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.performancecenter
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 403bbfff74cfe969a26e12aeb1f4b54ef0473195
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="optimize-visual-studio-performance"></a>Optimalizace výkonu v sadě Visual Studio

Visual Studio slouží ke spuštění jako rychle a efektivně míře. Však určitá rozšíření Visual Studia a nástroje systému windows může nepříznivě ovlivnit čas spuštění, když jsou načteny. Můžete řídit chování pomalé rozšíření a nástroje systému windows v **Správa výkonu Visual Studio** dialogové okno. Další Obecné tipy pro zlepšení výkonu, najdete v části [Rady a tipy pro zvýšení výkonu sady Visual Studio](../ide/visual-studio-performance-tips-and-tricks.md).

## <a name="startup-behavior"></a>Chování při spuštění

Abyste se vyhnuli rozšíření čas spuštění, načte Visual Studio 2017 rozšířením s využitím _na vyžádání_ přístup. Toto chování znamená, že rozšíření neotevřou okamžitě po spuštění sady Visual Studio, ale na podle potřeby. Protože nástroj windows ponechány otevřené v předchozí relaci sady Visual Studio může zpomalit spuštění, Visual Studio otevře nástroj windows inteligentnější způsobem, aby se zabránilo čas spuštění, které mají vliv.

Pokud Visual Studio zjistí pomalé spuštění, zobrazí se místní zpráva výstrahy upozorňující na okno rozšíření nebo nástroj, který je příčinou zpomalení. Zpráva obsahuje odkaz **Správa výkonu Visual Studio** dialogové okno. Tohoto dialogového okna můžete také přejít pomocí výběr **pomoci**, **Správa výkonu Visual Studio** z řádku nabídek.

![Správa výkonu Visual Studio – místní čtení ' zaznamenali jsme rozšíření... je zpomalení Visual Studio.](../ide/media/vside_perfdialog_popup.png)

Dialogové okno obsahuje seznam rozšíření a nástroje systému windows, které mají vliv na výkon při spouštění. Můžete změnit nastavení okno rozšíření a nástroj pro zlepšení výkonu při spuštění.

## <a name="to-change-extension-settings-to-improve-startup-solution-load-and-typing-performance"></a>Chcete-li změnit nastavení rozšíření ke zlepšení spuštění, řešení zatížení a zadáním výkonu

1. Otevřete **Správa výkonu Visual Studio** dialogové okno a vybrat **pomoci**, **Správa výkonu Visual Studio** z řádku nabídek.

    Pokud je rozšíření zpomalení spuštění sady Visual Studio, řešení načítání, nebo zadáním, rozšíření se zobrazí v **Správa výkonu Visual Studio** dialogové okno pod **rozšíření**,  **Spuštění** (nebo **řešení zatížení** nebo **zadáním**).

    ![Správa výkonu sady Visual Studio – rozšíření zobrazení](../ide/media/vside_perfdialog_extensions.png)

2. Zvolte rozšíření, které chcete zakázat, a potom vyberte **zakázat** tlačítko.

Můžete vždy znovu povolit rozšíření pro budoucí relace pomocí Správce rozšíření nebo dialogové okno Správa výkonu Visual Studio.

## <a name="to-change-tool-window-settings-to-improve-startup-time"></a>Chcete-li změnit nastavení okna nástroj ke zlepšení spuštění

1. Otevřete **Správa výkonu Visual Studio** dialogové okno a vybrat **pomoci**, **Správa výkonu Visual Studio** z řádku nabídek.

    Pokud okno nástroje je zpomalení spuštění sady Visual Studio, zobrazí se okno nástroje v **Správa výkonu Visual Studio** dialogové okno pod **nástroj Windows**, **spuštění**.

2. Zvolte panel nástrojů, kterou chcete změnit chování.

3. Vyberte jednu z následujících tří možností:

    - **Použít výchozí chování:** výchozí chování pro panel nástrojů. Zachování vybrána tato možnost nebude zvýšit výkon při spouštění.

    - **Nezobrazovat okno při spuštění:** zadaný nástroj zavření okna je vždy při otevření Visual Studio, i když je ponechán otevřít v předchozí relace. Panel nástrojů můžete otevřít z nabídky vhodné v případě potřeby.

    - **Skrýt okna automaticky při spuštění:** Pokud okno nástroje byla otevřená v předchozí relace, tato možnost sbalí okno nástroje skupiny při spuštění předejdete inicializace okno nástroje. Tato možnost je vhodná, pokud často používáte okno nástroje. Panel nástrojů je stále k dispozici, ale už negativně ovlivní čas spuštění sady Visual Studio.

    ![Správa výkonu sady Visual Studio – zobrazení okna nástrojů](../ide/media/vside_perfdialog_toolwindows.png)

> [!NOTE]
> Některé starší verze Visual Studio 2017 měl funkci **lightweight řešení zatížení**. Tato funkce již není k dispozici ve verzi Visual Studio 2017 15,5 a novějším. V aplikaci Visual Studio 2017 verze 15,5 a novější velkých řešení, které obsahují spravované kód zatížení mnohem rychleji než dřív, i bez zatížení lightweight řešení.

## <a name="see-also"></a>Viz také

- [Rady a tipy pro zvýšení výkonu Visual Studio](../ide/visual-studio-performance-tips-and-tricks.md)
