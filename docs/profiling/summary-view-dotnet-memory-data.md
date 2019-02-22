---
title: Souhrnné zobrazení – Data paměti .NET | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b11815a709cf91d4e29c8f04dfc2dd9e1fadb75e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56627672"
---
# <a name="summary-view---net-memory-data"></a>Souhrnné zobrazení – data paměti .NET
Souhrnné zobrazení zobrazuje informace o funkcích rozhraní .NET a typy, které nejvíce paměti přidělené a typy, které byly vytvořeny většinu doby v profilování. Další informace, včetně popisu odkazy oznámení a sestavy seznamy, naleznete v tématu [zobrazení se souhrnnými](../profiling/summary-view.md).

## <a name="timeline-graph"></a>Časová osa grafu
 Časová osa grafu v souhrnném zobrazení ukazuje využití procesoru (CPU) profilovaná aplikace v čase, které profilaci došlo k chybě. Časová osa grafu můžete použít k filtrování zobrazení tak, aby ve vybraném časovém rozsahu. Další informace najdete v tématu [jak: Filtrování zobrazení sestav ze časová osa souhrnu](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).

## <a name="functions-allocating-most-memory"></a>Funkce přidělující nejvíce paměti
 Seznam funkcí, které přiděleny nejvyšší počet bajtů paměti během spuštění profilování.

|Sloupec|Popis|
|------------|-----------------|
|**Název**|Název funkce.|
|**% Bajtů**|Procento všech přidělených bajtů při spuštění profilace, které byly přiděleny pomocí této funkce nebo podřízené funkce, která byla volaných touto funkcí.|

## <a name="types-with-most-memory-allocated"></a>Typy s největším množstvím přidělené paměti
 Obsahuje seznam typů, pro které byly přiděleny nejvyšší počet bajtů paměti při spuštění profilace.

|Sloupec|Popis|
|------------|-----------------|
|**Název**|Název typu.|
|**% Bajtů**|Procento všech přidělených bajtů při spuštění profilace, které byly přiděleny u tohoto typu.|

## <a name="types-with-most-instances"></a>Typy s největším množstvím instancí
 Seznam typů, které byly vytvořeny nejvíce času během spuštění profilování. kdyby

|Sloupec|Popis|
|------------|-----------------|
|**Název**|Název typu.|
|**% Instancí**|Procentuální podíl celkového počtu of.NET objektů, které byly vytvořeny v profilování, která byla instance tohoto typu.|

## <a name="see-also"></a>Viz také:
- [Souhrnné zobrazení – vzorkování dat](../profiling/summary-view-sampling-data.md)
- [Souhrnné zobrazení – data instrumentace](../profiling/summary-view-instrumentation-data.md)