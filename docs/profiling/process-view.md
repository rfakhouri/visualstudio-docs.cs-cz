---
title: Zobrazení procesů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a68a2a9f0ca96b943c0b09da5c60268963bc6a7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608237"
---
# <a name="process-view"></a>Zobrazení procesů
Proces zobrazení profilovacích dat pro procesy a vlákna, které byly spuštěny během spuštění profilování.

 Procesy jsou seřazeny podle názvu. Vlákna jsou uvedené jako podřízené uzly procesu, který je vytvořil. Vlákna jsou pojmenovány podle funkce, který spustil vlákno nebo popisek **[ntdll.dll]** Pokud nejsou k dispozici žádné symboly.

 Přidejte nebo odeberte sloupce, klikněte pravým tlačítkem v zobrazení a pak vyberte **Přidat/odebrat sloupce**. Kromě toho můžete seřadit data kliknutím na název sloupce. Další informace najdete v tématu [jak: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md).

 Sloupce zobrazení procesu jsou stejné pro data, která je generována pomocí metody odběru vzorků a instrumentace a pro data, která obsahuje data paměti .NET. Následující tabulka popisuje hodnot sloupců.

|Sloupec|Popis|
|------------|-----------------|
|**Jedinečné ID**|Profiler vygenerovat identifikátor, který je jedinečný na příslušný proces nebo vlákno.|
|**ID**|Systémem generovaných identifikátor procesu nebo vlákna.|
|**Název**|Název procesu nebo vlákna.|
|**Čas zahájení**|Počet milisekund nebo cyklů procesoru od začátku profilace do začátku procesu nebo vlákna.|
|**Koncový čas**|Počet milisekund nebo cyklů procesoru od začátku profilace do konce procesu nebo vlákna.|

## <a name="see-also"></a>Viz také:
- [Zobrazení dat metod vzorkování](../profiling/profiler-sampling-method-data-views.md)
- [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)
- [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)