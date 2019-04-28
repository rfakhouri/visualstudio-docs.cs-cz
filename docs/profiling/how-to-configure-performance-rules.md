---
title: 'Postupy: Konfigurace pravidel výkonu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7387cc54e96aec4deea6a65875f693d704d51859
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62973965"
---
# <a name="how-to-configure-performance-rules"></a>Postupy: Konfigurace pravidel výkonu
Upozornění výkonu th Visual Studio nástrojů pro profilaci sady signalizují potíže v profilované aplikaci, která může zpomalit spuštění programu. Upozornění lze také určit, že může být nutné změnit metody kolekce shromažďovat užitečnější data. Upozornění výkonu jsou automaticky generovány v relaci profilace a zobrazí v **seznam chyb** okno při otevření souboru dat profilování v [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Některé upozornění nemusí platit pro scénáře, že máte zájem, a upozorněním mohla být vyvolána nesprávně vykázán. Můžete nakonfigurovat upozornění výkonu zobrazení nebo skrytí konkrétního upozornění.

### <a name="to-configure-profiler-performance-warnings"></a>Konfigurace upozornění profileru výkonu

1. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.

2. Rozbalte **nástroje pro měření výkonu**a potom klikněte na tlačítko **pravidla**.

3. Pokud chcete povolit nebo zakázat upozornění, zaškrtněte nebo zrušte zaškrtnutí políčka u upozornění **ID** a název.

4. K určení úrovně warring pravidla, klikněte na tlačítko **akce** buňka vedle pravidlo a pak klikněte na úroveň pro upozornění.

    - **Zakázané** – zakáže pravidlo (to je stejný jako zrušením zaškrtnutí políčka vedle ID pravidla).

    - **Upozornění** -pravidlo zobrazí jako varování.

    - **Chyba** – zastaví spuštění profilace a zobrazí pravidlo jako chyba.

    - **Informace o** -zobrazí pravidlo jako pouze informace.