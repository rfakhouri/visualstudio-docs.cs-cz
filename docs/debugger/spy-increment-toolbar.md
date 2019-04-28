---
title: Panel nástrojů nástroje Spy ++ | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Spy++ toolbar
ms.assetid: 949c18fb-bb25-42ed-9130-c4a47869f24d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 101b4ad50777f796a3de82127f6ce3253b26ccaa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62930651"
---
# <a name="spy-toolbar"></a>Panel nástrojů nástroje Spy++
V panelu nabídek v nástroji Spy ++ se zobrazí panelu nástrojů. K zobrazení nebo skrytí panelu nástrojů na **zobrazení** nabídky, klikněte na tlačítko **nástrojů**.

 Následující ovládací prvky jsou k dispozici na panelu nástrojů.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

|Tlačítko|Efekt|
|------------|------------|
|![Spy&#43; &#43; Windows tlačítko](../debugger/media/icon_spy--_windows.gif "Icon_Spy ++ systému _Windows")|Zobrazí strom oken a ovládacích prvků v systému. Další informace najdete v tématu [zobrazení Windows](../debugger/windows-view.md).|
|![Spy&#43; &#43; zpracovává tlačítko](../debugger/media/icon_spy--_processes.gif "Icon_Spy ++ _Processes")|Zobrazí strom procesů v systému. Další informace najdete v tématu [zobrazení procesy](../debugger/processes-view.md).|
|![Spy&#43; &#43; vlákna tlačítko](../debugger/media/icon_spy--_threads.gif "Icon_Spy ++ _Threads")|Zobrazí strom vlákna v systému. Další informace najdete v tématu [zobrazení vláken](../debugger/threads-view.md).|
|![Spy&#43; &#43; zprávy tlačítko](../debugger/media/icon_spy--_messages.gif "Icon_Spy ++ _Messages")|Vytvoří okno pro zobrazení oken zpráv a otevře **možnosti zprávy** dialogové okno tak, že vyberete okno, jehož zprávy se zobrazí a také vybrat další možnosti. Další informace najdete v tématu [zobrazení zpráv](../debugger/messages-view.md).|
|![Spy&#43; &#43; protokolu tlačítko Start](../debugger/media/icon_spy--_startlog.gif "Icon_Spy ++ _StartLog")|Spustí protokolování zpráv a zobrazí datové proudy zpráv. Tento ovládací prvek je dostupná jenom v případě **zprávy** okna je aktivní okno. Další informace najdete v tématu [jak: Spuštění a zastavení displeje protokolu zpráv](../debugger/how-to-start-and-stop-the-message-log-display.md).|
|![Spy&#43; &#43; protokolu tlačítko Zastavit](../debugger/media/icon_spy--_stoplog.gif "Icon_Spy ++ _StopLog")|Zastaví zpráv protokolování a zobrazení datového proudu zpráv. Tento ovládací prvek je dostupná jenom v případě **zprávy** okna je aktivní okno. Další informace najdete v tématu [jak: Spuštění a zastavení displeje protokolu zpráv](../debugger/how-to-start-and-stop-the-message-log-display.md).|
|![Spy&#43; &#43; protokolu tlačítko Možnosti](../debugger/media/icon_spy--_logoptions.gif "Icon_Spy ++ _LogOptions")|Zobrazí [možnosti zprávy](../debugger/message-options-dialog-box.md) dialogové okno. Použijte toto dialogové okno Vyberte windows a typy pro zobrazení zpráv. Tento ovládací prvek je dostupná jenom v případě **zprávy** okna je aktivní okno.|
|![Spy&#43; &#43; protokolu tlačítko Vymazat](../debugger/media/spy--_clearlog.gif "nástroje Spy ++ _ClearLog")|Vymaže obsah aktivního **zprávy** okna. Tento ovládací prvek je dostupná jenom v případě **zprávy** okna je aktivní okno.|
|![Spy&#43; &#43; najít okno tlačítko](../debugger/media/icon_spy--_findwindow.gif "Icon_Spy ++ _FindWindow")|Otevře [najít okno](../debugger/find-window-dialog-box.md) dialogové okno, které vám umožní nastavit kritéria vyhledávání oken a zobrazení vlastnosti nebo zprávy. Další informace najdete v tématu [jak: Používání vyhledávacího nástroje](../debugger/how-to-use-the-finder-tool.md).|
|![Spy&#43; &#43; najít první okno tlačítko](../debugger/media/icon_spy--_window.gif "Icon_Spy ++ _Window")|Vyhledá aktuálním zobrazení odpovídající okno, proces, vlákno nebo zprávu.|
|![Spy&#43; &#43; najít tlačítko Další okno](../debugger/media/icon_spy--_nextwindow.gif "Icon_Spy ++ _NextWindow")|Vyhledá další odpovídající okno, proces, vlákno nebo zprávu aktuální zobrazení. Tento ovládací prvek (a související příkaz) je k dispozici pouze v případě, že je výsledek platný hledání, který není jedinečný. Například při použití popisovač okna jako kritérium pro vyhledávání ve stromové struktuře okno vytváří jedinečný výsledky, protože existuje pouze jedno okno ve stromové struktuře okna, která má tento popisovač; v takovém případě **najít další** není k dispozici.|
|![Spy&#43; &#43; najít předchozí okno tlačítko](../debugger/media/icon_spy--_prevwindow.gif "Icon_Spy ++ _PrevWindow")|Vyhledá předchozí odpovídající okno, proces, vlákno nebo zprávu aktuální zobrazení. Tento ovládací prvek (a související příkaz) je k dispozici pouze v případě, že je výsledek platný hledání, který není jedinečný. Například při použití popisovač okna jako kritérium pro vyhledávání ve stromové struktuře okno vytváří jedinečný výsledky, protože existuje pouze jedno okno ve stromové struktuře okna, která má tento popisovač; v takovém případě **najít předchozí** není k dispozici.|
|![Spy&#43; &#43; tlačítko Průzkumníku vlastnost](../debugger/media/icon_spy--_propexp.gif "Icon_Spy ++ _PropExp")|Zobrazí vlastnosti okna, která je vybrána v zobrazení Windows.|
|![Spy&#43; &#43; tlačítko Aktualizovat](../debugger/media/icon_spy--_refresh.gif "Icon_Spy ++ _aktualizovat")|Aktualizuje zobrazení systému.|

## <a name="see-also"></a>Viz také
- [Použití nástroje Spy++](../debugger/using-spy-increment.md)
- [Zobrazení nástroje Spy++](../debugger/spy-increment-views.md)
- [Referenční dokumentace nástroje Spy++](../debugger/spy-increment-reference.md)