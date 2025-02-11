---
title: Správa kanálů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.tools.managechannels
helpviewer_keywords:
- Concurrency Visualizer, Manage Channels
ms.assetid: 507b06e9-bb56-4a72-8fd5-f91f958da6fc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0b1480bab2f52383a8ca3a5b0ac22fd56acb5e01
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435633"
---
# <a name="manage-channels"></a>Správa kanálů
V **zobrazení vláken** ve vizualizátoru souběžnosti můžete uspořádat kanály pro proces, takže můžete zkoumat konkrétní vzory. Můžete řadit kanály, je přesunout nahoru a dolů a skrýt nebo zobrazit jejich.

## <a name="sort-by"></a>Seřadit podle:
 Ovládací prvek řadit podle můžete řadit vlákna podle různých kritérií založených na aktuální úroveň přiblížení. To je užitečné, když hledáte určitému vzoru. Můžete řadit podle těchto kritérií:

|Kritéria|Definice|
|--------------|----------------|
|Čas spuštění|Seřadí podle jejich časy spuštění vlákna. Toto je výchozí pořadí řazení.|
|Koncový čas|Vlákna jsou řazeny podle jejich koncovým časem.|
|Spuštění|Seřadí podle procent času stráveného při provádění vlákna.|
|Synchronizace|Seřadí podle procent času stráveného v synchronizaci vláken.|
|I/O|Vlákna seřadí podle procent času stráveného ve vstupně-výstupních operací (čtení a zápis dat).|
|Přejít do režimu spánku|Vlákna seřadí podle procent času stráveného v režimu spánku.|
|Stránkování|Vlákna jsou řazeny podle procentuální hodnotu času, který byl stráven stránkování.|
|Přerušení|Seřadí podle procentuální hodnotu času, který byl stráven přerušování vláken.|
|Zpracování uživatelského rozhraní|Vlákna seřadí podle procent času stráveného ve zpracování uživatelského rozhraní.|

## <a name="move-selected-channel-up-or-down"></a>Přesunout vybraný kanál nahoru nebo dolů
 Tyto ovládací prvky můžete použít k přesunutí kanál směrem nahoru nebo dolů v seznamu. Například může umístit související kanály vedle sebe můžete prozkoumat určitému vzoru nebo vztah mezi vlákny.

## <a name="move-selected-channel-to-top-or-bottom"></a>Přesunout vybraný kanál na horní nebo dolní
 Vybrané kanály můžete přesunout na začátek nebo konec seznamu tak, aby si projdete určitému vzoru, nebo přesunout některé kanály eliminuje při zkoumání ostatní.

## <a name="hide-selected-channels"></a>Skrýt vybrané kanály
 Zvolte tento ovládací prvek, pokud chcete skrýt kanály. Například pokud vlákno je synchronizace 100 procent po celou dobu životnosti vašeho spravovaného procesu, ji může skrýt jak analyzovat jiných vláken.

> [!NOTE]
> Skrytí vlákno také odebere ho z čas výpočtu, která se zobrazí v legendě aktivní a v sestavách profilu.

## <a name="show-all-channels"></a>Zobrazit všechny kanály
 Tento ovládací prvek je aktivní, když jsou skryté jednoho nebo několika kanálů. Pokud jste ji zvolili, jsou uvedeny všechny prvky skrytý a jsou vráceny ve výpočtech čas.

## <a name="move-markers-to-top"></a>Přesunout značky na začátek
 Pokud trasování neobsahuje značky události, můžete použít tento příkaz pro přesun kanály značky do horní části na časové ose. Jejich relativního pořadí je zachováno.

## <a name="group-markers-by-thread"></a>Seskupit značky podle vlákna
 Pokud trasování neobsahuje značky události, můžete použít tento příkaz na kanály skupiny značky podle vlákna, která se vygenerované značky události.  Kanály disku přesunou do horní části seznamu kanálů a kanály GPU přesunou do dolní části.

## <a name="see-also"></a>Viz také:
- [Ovládací prvek Lupa (zobrazení vláken)](../profiling/zoom-control-threads-view.md)
- [Zapnout nebo vypnout režim míry](../profiling/measure-mode-on-off.md)
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)