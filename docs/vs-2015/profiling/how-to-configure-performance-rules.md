---
title: 'Postupy: Konfigurace pravidel výkonu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 71593496613c75485fd30481777d0fcc1102c11c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60117808"
---
# <a name="how-to-configure-performance-rules"></a>Postupy: Konfigurace pravidel výkonu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Upozornění výkonu th Visual Studio nástrojů pro profilaci sady signalizují potíže v profilované aplikaci, která může zpomalit spuštění programu. Upozornění lze také určit, že může být nutné změnit metody kolekce shromažďovat užitečnější data. Upozornění výkonu jsou automaticky generovány v relaci profilace a zobrazí v **seznam chyb** okno při otevření souboru dat profilování v [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]. Některé upozornění nemusí platit pro scénáře, že máte zájem, a upozorněním mohla být vyvolána nesprávně vykázán. Můžete nakonfigurovat upozornění výkonu zobrazení nebo skrytí konkrétního upozornění.  
  
### <a name="to-configure-profiler-performance-warnings"></a>Konfigurace upozornění profileru výkonu  
  
1. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2. Rozbalte **nástroje pro měření výkonu**a potom klikněte na tlačítko **pravidla**.  
  
3. Pokud chcete povolit nebo zakázat upozornění, zaškrtněte nebo zrušte zaškrtnutí políčka u upozornění **ID** a název.  
  
4. K určení úrovně warring pravidla, klikněte na tlačítko **akce** buňka vedle pravidlo a pak klikněte na úroveň pro upozornění.  
  
    - **Zakázané** – zakáže pravidlo (to je stejný jako zrušením zaškrtnutí políčka vedle ID pravidla).  
  
    - **Upozornění** -pravidlo zobrazí jako varování.  
  
    - **Chyba** – zastaví spuštění profilace a zobrazí pravidlo jako chyba.  
  
    - **Informace o** -zobrazí pravidlo jako pouze informace.
