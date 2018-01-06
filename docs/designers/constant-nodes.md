---
title: "Konstantní uzly | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c798a50-a2d7-459b-9879-ad4ad8290c9b
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1edbe90bf9f1002392374a17b8dd85270ec2fef5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="constant-nodes"></a>Uzly konstanty
V Návrháři shaderu konstantní uzly představují literálových hodnot a interpolované vrchol atributy ve výpočtech shaderu pixelů. Protože vrchol atributy interpolace – a tedy se liší pro každý pixelů – každá instance pixelů shaderu obdrží jinou verzi konstanta. To dává jedinečný vzhled každý pixelů.  
  
## <a name="vertex-attribute-interpolation"></a>Vrchol atribut interpolace  
 Bitové kopie 3D scény v hry nebo aplikace se provádí pomocí matematicky transformace počet objektů, které – které jsou definovány vrcholy, vrchol atributy a primitivní definice – do obrazovce pixelů. Všechny informace, které je nutné poskytnout pixel její jedinečné vzhled poskytnutý prostřednictvím vrchol atributy, které jsou společně smíšení podle pixel blízkosti různých vrcholy, které tvoří jeho *primitivní*. Primitivní je element základní vykreslování; To znamená jednoduchou utvářejí jako je například bod, řádku nebo trojúhelník. Pixel, který je velmi blízko právě jeden z vrcholy obdrží konstanty, které jsou téměř stejné tento bod uchycení, ale pixel, který má rovnoměrně rozmístěny mezi všechny vrcholy primitivní obdrží konstanty, které jsou průměr těchto vrcholy. V programování grafiky jsou konstanty, které přijímají pixelů označeny jako *interpolované*. Poskytuje konstantní data na pixelů tímto způsobem vytváří velmi dobré visual kvality a současně snižuje nároky a šířku pásma, požadavky na paměť.  
  
 I když každá instance pixelů shaderu přijímá jen jednu sadu hodnot konstant a tyto hodnoty nedají změnit, přijímat různých pixelů shaderu instancí jiné konstantní datových sad. Tento návrh umožňuje program shaderu k vytvoření výstupu jinou barvu pro každý pixelů v primitivní vlastnost.  
  
## <a name="constant-node-reference"></a>Referenční dokumentace konstantního uzlu  
  
|Uzel|Podrobnosti|Vlastnosti|  
|----------|-------------|----------------|  
|**Vektor fotoaparát**|Vektor, který rozšiřuje z aktuální pixelů ke kameře v prostoru world.<br /><br /> Můžete použít k výpočtu odrazů v prostoru world.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Vektor z aktuální pixelů fotoaparát.|Žádné|  
|**Barva konstanta**|Barva konstantní hodnotu.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Hodnoty barvy.|**Output**<br /> Hodnoty barvy.|  
|**Konstantní**|Konstantní skalární hodnotu.<br /><br /> **Output**<br /><br /> `Output`: `float`<br /> Skalární hodnota.|**Output**<br /> Skalární hodnota.|  
|**2D konstanta**|Toto je konstanta vektoru dvě součásti.<br /><br /> **Output**<br /><br /> `Output`: `float2`<br /> Hodnota vektoru.|**Output**<br /> Hodnota vektoru.|  
|**3D konstanta**|Tři součásti vektoru konstanta.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Hodnota vektoru.|**Output**<br /> Hodnota vektoru.|  
|**Konstanta 4D**|Čtyři součást vektoru konstanta.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Hodnoty barvy.|**Output**<br /> Hodnota vektoru.|  
|**Normalizovaný pozice**|Umístění aktuální pixelů, vyjádřené v souřadnicích normalizovaný zařízení.<br /><br /> Souřadnice x a souřadnici y mají hodnoty v rozsahu [-1, 1],-souřadnice má hodnotu v rozsahu [0, 1], a w součást obsahuje hodnotu hloubky bodu v zobrazení prostoru; w není normalized.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Umístění aktuální pixelů.|Žádné|  
|**Barva bodu**|Rozptýlené barva aktuální pixelů, která jsou tvořena kombinací podstatným rozptýlených barvy a vrchol atributy barvy.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Rozptýlené barva aktuální pixelů.|Žádné|  
|**Hloubka bodů**|Hloubka aktuální pixelů v zobrazení prostoru.<br /><br /> **Output**<br /><br /> `Output`: `float`<br /> Hloubka aktuální pixelů.|Žádné|  
|**Normalizovaný hloubka bodu**|Hloubka aktuální pixelů, vyjádřené v souřadnicích normalizovaný zařízení.<br /><br /> Výsledek obsahuje hodnotu v rozsahu [0, 1].<br /><br /> **Output**<br /><br /> `Output`: `float`<br /> Hloubka aktuální pixelů.|Žádné|  
|**Pozice obrazovky**|Umístění aktuální pixelů, vyjádřené v souřadnice obrazovky.<br /><br /> Souřadnice obrazovky jsou založené na aktuální zobrazení. X a y součásti obsahovat souřadnice obrazovky, součást z obsahuje hloubka normalizovány na rozsah [0, 1], a w součást obsahuje hodnotu hloubky v zobrazení prostoru.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Umístění aktuální pixelů.|Žádné|  
|**Prostor normální**|Prostor normální aktuální pixelů v prostoru objektu.<br /><br /> Můžete použít k výpočtu osvětlení příspěvky a odrazů v prostoru objektu.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Prostor normální aktuální pixelů.|Žádné|  
|**Vektor fotoaparát tečný místa**|Vektor, který rozšiřuje z aktuální pixelů ke kameře v tečný prostoru.<br /><br /> Můžete použít k výpočtu odrazů v tečný prostoru.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Vektor z aktuální pixelů fotoaparát.|Žádné|  
|**Směr světla tečný místa**|Vektor, který definuje směr, ve kterém je lehký přetypovat od zdroje světla ve tečný prostoru aktuální pixelů.<br /><br /> Můžete použít k výpočtu osvětlení a zrcadlová příspěvky v tečný prostoru.<br /><br /> **Výstup:**<br /><br /> `Output`: `float3`<br /> Vektor z aktuální pixelů ke zdroji světla.|Žádné|  
|**Normální World**|Prostor normální aktuální pixelů v prostoru world.<br /><br /> Můžete použít k výpočtu osvětlení příspěvky a odrazů v prostoru world.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Prostor normální aktuální pixelů.|Žádné|  
|**Pozice World**|Umístění aktuální pixelů v prostoru world.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Umístění aktuální pixelů.|Žádné|