---
title: 'Postupy: Konfigurace pravidel výkonu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3c6ed583f4ad9db369ed1b05fd23a42c104bad31
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-performance-rules"></a>Postupy: Konfigurace pravidel výkonu
Upozornění výkonu tý Visual Studio profilace nástrojů znamenat problémy v PROFILOVANÉHO aplikace, která může zpomalit spuštění programu. Upozornění taky může znamenat, že možná budete muset změnit metod kolekcí ke shromažďování dat užitečnější. Upozornění výkonu jsou automaticky generovány v relace profilování a zobrazují v **seznam chyb** okno při datového souboru profilování je otevřen v [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Některé upozornění nemusí platit pro scénáře, kdy máte zájem, a některé upozornění může být vyvolána nesprávně. Můžete konfigurovat upozornění výkonu můžete zobrazit nebo skrýt konkrétní varování.  
  
### <a name="to-configure-profiler-performance-warnings"></a>Konfigurace upozornění výkonu profileru  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  Rozbalte položku **nástroje pro sledování výkonu**a potom klikněte na **pravidla**.  
  
3.  Chcete-li povolit nebo zakázat upozornění, vyberte nebo zrušte zaškrtnutí políčka vedle upozornění **ID** a název.  
  
4.  Chcete-li zadat úroveň warring pravidla, klikněte na tlačítko **akce** buňka vedle pravidlo a pak klikněte na úroveň pro upozornění.  
  
    -   **Zakázané** – zakáže pravidlo (je to stejné jako zrušením zaškrtnutí políčka vedle ID pravidla).  
  
    -   **Upozornění** -pravidlo zobrazí jako varování.  
  
    -   **Chyba** – zastaví profilace provádění a zobrazí pravidlo jako chyba.  
  
    -   **Informace o** -pravidlo zobrazí jako pouze informační charakter.