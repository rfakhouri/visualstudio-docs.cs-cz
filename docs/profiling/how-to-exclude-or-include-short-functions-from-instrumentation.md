---
title: Vyloučení krátkých funkcí z instrumentace nebo jejich zahrnutí do instrumentace
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b8f9601a39e755c1a3886f7049abd592d793fb4b
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66261353"
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>Postupy: Vyloučení krátkých funkcí z instrumentace nebo jejich zahrnutí do instrumentace
Ve výchozím nastavení, nástroje pro profilaci vyloučit *malé funkce* z instrumentace. Malé funkce jsou krátkých funkcí, které Nedovolte, aby byly všechny volání funkce. Kromě těchto malé funkce poskytuje pro menší nároky na instrumentace a proto zlepšit rychlost instrumentace. Vyloučení malé funkce taky snižuje výkon souboru dat profilování (. *Vsp*) velikosti a čas, který je vyžadován pro analýzu. Pokud jsou malé funkce vyloučit, čas, který byl stráven malé funkce počítat celkové a výhradní čas jejich nadřazené funkce. Malé funkce můžete vyloučit nebo součástí instrumentace, jak je popsáno v následujícím postupu.

### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>Vyloučení nebo zahrnutí krátkých funkcí z instrumentace

1. V **prohlížeč výkonu**vyberte **relace výkonu** a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.

     **Stránky vlastností** se zobrazí dialogové okno.

2. V **stránky vlastností**, klikněte na tlačítko **instrumentace** vlastnosti.

3. Chcete-li vyloučení krátkých funkcí z instrumentace, vyberte **vyloučení krátkých funkcí z instrumentace**. Toto je výchozí nastavení.

     -nebo-

     Chcete-li zahrnout krátkých funkcí instrumentace, zrušte **vyloučení krátkých funkcí z instrumentace**.

4. Klikněte na **OK**.

## <a name="see-also"></a>Viz také:
- [Řízení shromažďování dat](../profiling/controlling-data-collection.md)
- [Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)