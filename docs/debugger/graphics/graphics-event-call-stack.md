---
title: Zásobník volání událostí grafiky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3cdaa6cdd3275fa7fda8df33cbdb09a8edae158c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56700234"
---
# <a name="graphics-event-call-stack"></a>Zásobník volání událostí grafiky
Zásobníku volání události grafiky v analyzátoru grafiky sady Visual Studio umožňuje mapovat vztah mezi událostí grafiky problematické a zdrojový kód vaší aplikace.

 Toto je v okně zásobník volání události:

 ![Před událostí DrawIndexed zásobníku volání. ](media/gfx_diag_demo_graphics_event_call_stack_orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")

## <a name="understanding-the-graphics-event-call-stack"></a>Principy zásobník volání událostí grafiky
 Zásobník volání událostí můžete použít k pochopení toku provádění, která vedla k určité události rozhraní Direct3D. Vypadá podobně jako okno zásobníku volání sady Visual Studio, s tím rozdílem, že místo aktuální zásobník volání aktuálního vlákna ve spuštěné aplikaci, se zobrazí zásobník volání podle existovala, když došlo k vybrané události rozhraní Direct3D. Z zásobník volání událostí můžete přejít na lokalitu volání vybrané události rozhraní Direct3D ke kontrole okolním kódem.

 Pomocí zásobník volání událostí k identifikaci do cesty kódu, ze kterého pochází událost problému svoje znalosti v oblasti základu kódu můžete použít k odvození potenciálních zdrojů problému nebo přidat zarážky ve zdrojovém kódu vaší aplikace tak, aby vám tradiční techniky pro zjištění, jak stav parametry aplikace nebo události způsobují událost, abyste misbehave ladění. Při této kontrole můžete najít problémy ve zdrojovém kódu, které jsou pouze označované jako problémů s vykreslováním.

### <a name="graphics-event-call-stack-information"></a>Informace o zásobník volání událostí grafiky
 Zásobník volání událostí nepodporuje události předběžné snímků nebo uživatelem definované události. Zásobník volání událostí grafiky se zobrazí ve formátu tabulky.

|Sloupec|Popis|
|------------|-----------------|
|**Název**|Symbol, který jednoznačně identifikuje funkce, která obsahuje lokalitu volání. Symbol ladění pro funkce se zobrazí, když je k dispozici. v opačném případě se zobrazí funkce Posun.|
|**File**|Název souboru souboru se zdrojovým kódem nebo soubor knihovny, která obsahuje lokalitu volání.|
|**Poloha**|Číslo řádku lokalitu volání.|

### <a name="links-to-graphics-objects"></a>Odkazy na grafických objektů
 Porozumění události vybrané grafiky, budete pravděpodobně potřebovat informace o Direct3D objekty, které jsou k ní přidružena. **Zásobník volání událostí grafiky** okno obsahuje odkazy na tyto informace.

## <a name="see-also"></a>Viz také
- [Návod: Chybějící objekty kvůli vertex shaderu](walkthrough-missing-objects-due-to-vertex-shading.md)