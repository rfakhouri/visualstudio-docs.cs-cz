---
title: Filtrování uzlů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7cae2dc-e9a7-49d4-8be5-58b79868624e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2789676505588c2041abfd876a228fc456ee3607
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668350"
---
# <a name="filter-nodes"></a>Uzly filtru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [uzly filtrů](https://docs.microsoft.com/visualstudio/designers/filter-nodes).  
  
V Návrháři shaderu uzly filtrů transformují vstupní – například vzorek barvy nebo textury – na hodnotu názorné barvu. Tyto hodnoty názorné barva se běžně používají v jiných fotorealistické vykreslování nebo komponenty v jiných vizuálních efektů.  
  
## <a name="filter-node-reference"></a>Referenční uzel filtru  
  
|Uzel|Podrobnosti|Vlastnosti|  
|----------|-------------|----------------|  
|**Rozostření**|Rozostří pixelů texturu pomocí Gaussovy funkce.<br /><br /> To můžete použít ke snížení detailu barvy nebo šumu v textuře.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice texel k testování.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Hodnota rozmazaný barvy.|**Textury**<br /> Registr textur, který je spojen s vzorkovači používanému při rozostření.|  
|**Snížit sytost**|Snižuje počet barev v určené barvy.<br /><br /> Když je barva odebrána, barva se Zamění šedi ekvivalentní.<br /><br /> **Vstup:**<br /><br /> `RGB`: `float3`<br /> Barva pro zmenšení sytosti.<br /><br /> `Percent`: `float`<br /> Procento barev, které chcete odebrat, vyjádřené jako normalizované hodnoty v rozsahu [0, 1].<br /><br /> **Výstup:**<br /><br /> `Output`: `float3`<br /> Odbarvený barvu.|**Světlosti**<br /> Váhy, které jsou uvedeny na komponenty červené, zelené a modré barvu.|  
|**Detekce okraje**|Detekuje hrany v textuře pomocí cannyho detektoru. Pixely hrany, které jsou výstupem jako prázdné; bez okrajů pixelů se výstup jako černá.<br /><br /> Může být využit k identifikaci hran textury, aby mohli používat další efekty přistupovat ke všem pixely hrany.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice texel k testování.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Prázdné, pokud je texel na okraj; v opačném případě černá.|**Textury**<br /> Registr textur, který je spojen se vzorkovačem, který je použit během detekce hran.|  
|**Zdokonalení**|Zaostří texturu.<br /><br /> Může být využit zvýrazněte podrobné detaily v textuře.<br /><br /> **Vstup:**<br /><br /> `UV`: `float2`<br /> Souřadnice texel k testování.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Hodnota rozmazaný barvy.|**Textury**<br /> Registr textur, který je spojen se vzorkovačem, který se používá během zostření.|



