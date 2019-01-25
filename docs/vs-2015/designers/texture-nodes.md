---
title: Uzly textury | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: b7df5ef3-dd4f-4964-9d96-34e0e180515e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e43329cb15eaf41ccb8859521bd45eff6f749c10
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54779837"
---
# <a name="texture-nodes"></a>Uzly textury
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V Návrháři shaderu uzly textury ukázkové různé typy textury a geometrie a vytvořit nebo transformovat souřadnice textury. Textury zadat barvu a osvětlení podrobností na objekty.  
  
## <a name="texture-node-reference"></a>Referenční uzel textury  
  
|Uzel|Podrobnosti|Vlastnosti|  
|----------|-------------|----------------|  
|**Vzorek Cubemap**|Získá vzorek barvy z být na zadaných souřadnicích.<br /><br /> Můžete být pro poskytování detailů barvy efektů, nebo použít na kulovité objekty textury s méně deformacemi než 2D textura.<br /><br /> **Vstup:**<br /><br /> `UVW`: `float3`<br /> Vektor, který určuje umístění v texturové krychle, kde je vzorek odebírán. Je vzorek odebírán, ve kterém tento vektoru protíná datové krychle.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Ukázka barvy.|**Texture**<br /> Registr textur, který je spojen se vzorkovačem.|  
|**Vzorek normálové mapy**|Získá vzorek normály z 2D normálové mapy na zadaných souřadnicích<br /><br /> Normálové mapy můžete použít pro simulování vzhledu dodatečných geometrických detailů na povrchu objektu. Map normál obsahuje Sbalená data, která představuje jednotku vektoru místo data o barvách<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice, kde je vzorek odebírán.<br /><br /> **Výstup:**<br /><br /> `Output`: `float3`<br /> Vzorek normály.|**Úprava osy**<br /> Faktor, který slouží k úprava jasu obrazovky z vzorek normálové mapy.<br /><br /> **Texture**<br /> Registr textur, který je spojen se vzorkovačem.|  
|**Pan UV**|Testové koordinuje zadané textury jako funkce času.<br /><br /> To slouží k přesunutí textury nebo normálové mapy po povrchu objektu.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice posun.<br /><br /> `Time`: `float`<br /> Časový interval pro posouvání, během několika sekund.<br /><br /> **Výstup:**<br /><br /> `Output`: `float2`<br /> Panned souřadnice.|**Krok X**<br /> Počet elementů textury, které jsou přesunuty podél osy x za sekundu.<br /><br /> **Krok Y**<br /> Počet elementů textury, které jsou přesunuty podél osy y za sekundu.|  
|**Paralaxovat UV**|Aktivuje souřadnice textury zadané jako funkce výšky a úhel zobrazení.<br /><br /> Efekt, vytvoří se označuje jako *paralaxní mapování*, nebo mapování virtuálních přesunů. Můžete ho použít pro vytváření iluzí hloubky na plochém povrchu.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice odsadit.<br /><br /> `Height`: `float`<br /> Heightmap hodnotu, která je přidružena `UV` souřadnice.<br /><br /> **Výstup:**<br /><br /> `Output`: `float2`<br /> Posunutou souřadnice.|**Rovina hloubky**<br /> Referenční hloubka pro paralaxní efekt. Výchozí hodnota je 0,5. Menší hodnoty texturu; vyzdvihnou vetší ji zanoří do povrchu.<br /><br /> **Měřítko hloubky**<br /> Škálování změní velikost paralaxního efektu. Díky tomu byl dojem hloubky více či méně patrný. Typické hodnoty spadají do rozsahu od 0,02 po 0,1.|  
|**Otočit UV**|Otočí souřadnice textury zadané kolem centrální bod jako funkce času.<br /><br /> Může být využit k otáčení textury nebo normálové mapy povrchu objektu.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice otočí.<br /><br /> `Time`: `float`<br /> Časový interval pro posouvání, během několika sekund.<br /><br /> **Výstup:**<br /><br /> `Output`: `float2`<br /> Otočený souřadnice.|**Center X**<br /> Souřadnice x, která definuje střed otáčení.<br /><br /> **Střed (Y)**<br /> Souřadnice y, která definuje střed otáčení.<br /><br /> **rychlost**<br /> Úhel v radiánech, o který se textura pootočí za sekundu.|  
|**Souřadnice textury**|Souřadnice textury aktuálního pixelu.<br /><br /> Souřadnice textury jsou určeny pomocí interpolace mezi atributů souřadnic textury blízkých vrcholů. To si lze představit jako pozici aktuálního pixelu v prostoru textury.<br /><br /> **Výstup:**<br /><br /> `Output`: `float2`<br /> Souřadnice textury.|Žádná|  
|**Rozměry textury**|Vrací šířku a výšku mapy 2D textury.<br /><br /> Rozměry textury můžete vzít v úvahu šířku a výšku textury v shaderu.<br /><br /> **Výstup:**<br /><br /> `Output`: `float2`<br /> Šířku a výšku textury, vyjádřené jako vektor. Šířka se ukládají v prvním prvku vektoru. Výška se ukládají v druhé elementu.|**Texture**<br /> Registr textur, který je spojen s rozměry textury.|  
|**Texel Delta**|Vrátí rozdíl (vzdálenost) mezi textury mapy 2D textury.<br /><br /> Delta elementů textury můžete použít pro vzorkování v shaderu sousedních hodnot texel.<br /><br /> **Výstup:**<br /><br /> `Output`: `float2`<br /> Rozdíl (vzdálenost) z texel na další texelu (šikmo ve směru pozitivní), vyjádřené jako v prostoru textury normalizovaný vektor. Pozice všech textury sousedních lze odvodit selektivně ignoruje nebo negace U nebo V souřadnice rozdílů.|**Texture**<br /> Registr textur, který je spojen s hodnoty delta elementů textury.|  
|**Vzorek textury**|Získá vzorek barvy z mapy 2D textury na zadaných souřadnicích.<br /><br /> Mapy textury můžete použít pro poskytnutí detailu barvy na povrchu objektu.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice, kde je vzorek odebírán.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Ukázka barvy.|**Texture**<br /> Registr textur, který je spojen se vzorkovačem.|
