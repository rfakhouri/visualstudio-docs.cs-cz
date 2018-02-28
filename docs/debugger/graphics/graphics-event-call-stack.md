---
title: "Zásobník volání událostí grafiky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 89e426c24f1f32161307d573c1ab06cdf459b1d6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-event-call-stack"></a>Zásobník volání událostí grafiky
Zásobník volání událostí grafiky ve Visual Studio Graphics Analyzer umožňuje mapovat vztah mezi problematické grafiky události a zdrojového kódu vaší aplikace.  
  
 Toto je okno zásobník volání událostí:  
  
 ![Předcházející zásobník volání událostí DrawIndexed. ] (media/gfx_diag_demo_graphics_event_call_stack_orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")  
  
## <a name="understanding-the-graphics-event-call-stack"></a>Principy zásobník volání událostí grafiky  
 Zásobník volání událostí můžete lépe pochopit tok provádění, která vedla k určité události Direct3D. Okno zásobník volání Visual Studio se podobá s tím rozdílem, že místo zobrazení aktuální zásobník volání aktuálního vlákna ve spuštěné aplikaci, zobrazí se zásobníkem volání tak, jak byly při vyvolání vybrané události Direct3D –. Z zásobník volání událostí můžete přejít na web volání vybrané události Direct3D – Chcete-li prověřit okolního kódu.  
  
 Pomocí zásobník volání událostí k identifikaci kódu cesta, ze kterého pochází událost problému vašich znalostí základu kódu, můžete odvodit potenciální zdroje problému nebo přidat zarážky ve zdrojovém kódu aplikace tak, aby můžete použít tradiční ladění a zkontrolujte, jak stav parametry aplikace nebo události způsobují událostí k nesprávnému chování techniky. Při této kontrole vám může pomoci najít problémy ve zdrojovém kódu, které jsou pouze označované jako vykreslování problémy.  
  
### <a name="graphics-event-call-stack-information"></a>Informace o zásobník volání událostí grafiky  
 Zásobník volání událostí nepodporuje předběžné rámce události nebo uživatelem definované události. Zásobník volání událostí grafiky se zobrazí ve formátu tabulky.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Symbol, který jednoznačně identifikuje funkce, která obsahuje lokalitu volání. Symbol ladění pro funkci se zobrazí, když je k dispozici. Posun funkce, jinak se zobrazí.|  
|**Soubor**|Název souboru souboru se zdrojovým kódem nebo soubor knihovny, který obsahuje volání lokality.|  
|**Umístění**|Číslo řádku lokality volání.|  
  
### <a name="links-to-graphics-objects"></a>Odkazy na grafických objektů  
 Pochopení událostí vybrané grafiky, budete pravděpodobně potřebovat informace o Direct3D – objekty, které jsou k ní přidružena. **Zásobník volání událostí grafiky** okno obsahuje odkazy na tyto informace.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Chybějící objekty z důvodu použití funkce vertex shading](walkthrough-missing-objects-due-to-vertex-shading.md)