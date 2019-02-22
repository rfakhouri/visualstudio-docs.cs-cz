---
title: Souhrnné zobrazení – Data instrumentace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91d53eef12c1c2dc59d8c442a040f721af75e7b3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56595943"
---
# <a name="summary-view---instrumentation-data"></a>Souhrnné zobrazení – data instrumentace
Souhrnné zobrazení zobrazuje informace o výkonu – nejdražší funkce v profilování. Další informace, včetně popisu odkazy oznámení a sestavy seznamy, naleznete v tématu [zobrazení se souhrnnými](../profiling/summary-view.md).

## <a name="timeline-graph"></a>Časová osa grafu
 Časová osa grafu v souhrnném zobrazení ukazuje využití procesoru (CPU) profilovaná aplikace v čase, které profilaci došlo k chybě. Časová osa grafu můžete použít k filtrování zobrazení tak, aby ve vybraném časovém rozsahu. Další informace najdete v tématu [jak: Filtrování zobrazení sestav ze časová osa souhrnu](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).

## <a name="hot-path"></a>Kritická cesta
 **Kritickou cestu** cesta spuštění, které nejvíce času. Můžete kliknout na funkci, kterou chcete zobrazit podrobnosti o funkci pro funkci. Další zobrazení, pro funkce, klikněte pravým tlačítkem na funkci a potom klikněte na zobrazit ze seznamu.

 **Kritickou cestu** zahrnuje následující data pro každou funkci:

|Sloupec|Popis|
|------------|-----------------|
|**Název**|Název funkce.|
|**% Uplynulého celkového času**|Procento celou dobu profilování dat, které funkce strávený prováděním kódu v těle jeho funkce a funkce, které ji volaly.|
|**% Uplynulého výhradního času**|Procento všech času v profilaci dat, který funkce stráví prováděním kódu v těle jeho funkce. Času stráveného ve funkcích, které volá se, funkce není součástí.|

## <a name="functions-with-most-individual-work"></a>Funkce s většinou jednotlivé práce
 Seznam funkcí, které spotřebovávají nejvíce času prováděním kódu v těle funkce a ne v funkce, které ji volaly.

 **Funkce s nejvíce individuální práce** zahrnuje následující data pro každou funkci:

|Sloupec|Popis|
|------------|-----------------|
|**Název**|Název funkce.|
|**% Výhradního času**|Procento všech času v profilaci dat, který funkce stráví prováděním kódu v těle jeho funkce. Času stráveného ve funkcích, které volá se, funkce není součástí.|

## <a name="see-also"></a>Viz také:
- [Souhrnné zobrazení – vzorkování dat](../profiling/summary-view-sampling-data.md)
- [Souhrnné zobrazení – data paměti .NET](../profiling/summary-view-dotnet-memory-data.md)