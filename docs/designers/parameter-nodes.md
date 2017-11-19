---
title: Parametr uzly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da54db0b-3a3d-48dc-858c-7ac43aa04b13
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6c93a889ca1bfa911a9f0934302450f6c1ec5413
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="parameter-nodes"></a>Uzly parametru
V Návrháři shaderu parametr uzly představují vstupy shaderu, které jsou pod kontrolou aplikace na základě za kreslení, například, vlastnosti materiálu, směrová světla, fotoaparát pozice a čas. Protože tyto parametry s každou volání kreslení můžete změnit, můžete poskytnout objekt různé vzhledy stejné shaderu.  
  
## <a name="parameter-node-reference"></a>Odkaz na parametr uzlu  
  
|Uzel|Podrobnosti|Vlastnosti|  
|----------|-------------|----------------|  
|**Pozice World fotoaparát**|Pozice fotoaparátu v prostoru world.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Pozice fotoaparát.|Žádné|  
|**Světla směr**|Vektor, který definuje směr, ve kterém je lehký přetypovat od zdroje světla v prostoru world.<br /><br /> Můžete použít k výpočtu osvětlení a zrcadlová příspěvky v prostoru world.<br /><br /> **Výstup:**<br /><br /> `Output`: `float3`<br /> Vektor z aktuální pixelů ke zdroji světla.|Žádné|  
|**Materiály vedlejším**|Příspěvek rozptýlených barva aktuální pixelů, který vyplývá z nepřímého osvětlení.<br /><br /> Rozptýlené barev pixelů simuluje, jak osvětlení komunikuje s hrubý ploch. Parametr materiálu vedlejším můžete Přibližná jak nepřímého osvětlení přispívá k vzhled objektu v reálném světě.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Rozptýlené barva aktuální pixelů, který je z důvodu nepřímých – to znamená, vedlejším – osvětlení.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**<br /> Rozptýlené barva aktuální pixelů, který je z důvodu nepřímých – to znamená, vedlejším – osvětlení.|  
|**Rozptýlené materiály**|Barva, která popisuje, jak aktuální pixelů rozptýlí přímé osvětlení.<br /><br /> Rozptýlené barev pixelů simuluje, jak osvětlení komunikuje s hrubý ploch. Parametr materiálu rozptýlené můžete změnit, jak aktuální pixelů rozptýlí přímé osvětlení – to znamená, směrové, bod a přímé indikátory.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Barva, která popisuje, jak aktuální pixelů rozptýlí přímé osvětlení.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**<br /> Barva, která popisuje, jak aktuální pixelů rozptýlí přímé osvětlení.|  
|**Materiály Emissive**|Barva podíl aktuální pixelů, který vyplývá z osvětlení poskytující na sebe sama.<br /><br /> Můžete použít k simulaci objekt Zářící; To znamená, objekt, který poskytuje vlastní light. Tento lehký nemá vliv jiné objekty.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Barva podíl aktuální pixelů, která je kvůli samoobslužné zadat osvětlení.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**<br /> Barva podíl aktuální pixelů, která je kvůli samoobslužné zadat osvětlení.|  
|**Zrcadlová materiály**|Barva, která popisuje, jak aktuální pixelů odráží přímé osvětlení.<br /><br /> Zrcadlová barev pixelů simuluje, jak osvětlení komunikuje s povrchy smooth, jako zrcadlení. Parametr materiálu zrcadlová můžete změnit, jak aktuální pixelů odráží přímé osvětlení – to znamená, směrové, bod a přímé indikátory.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Barva, která popisuje, jak aktuální pixelů odráží přímé osvětlení.|**Přístup**<br /> **Veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**<br /> Barva, která popisuje, jak aktuální pixelů odráží přímé osvětlení.|  
|**Podstatným zrcadlová napájení**|Skalární hodnota, která popisuje intenzitou zrcadlová světla.<br /><br /> Čím větší zrcadlová napájení více velký a dalekosáhlou stát zrcadlová světla.<br /><br /> **Výstup:**<br /><br /> `Output`: `float`<br /> Exponenciální termín, který popisuje intenzitou zrcadlová světla na aktuální pixelů.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**<br /> Exponent, která definuje intenzitou zrcadlová světla na aktuální pixelů.|  
|**Normalizovaný čas**|Doba v sekundách, normalizovány na rozsahu [0, 1], tak, aby se při čas dosáhne 1, resetuje na hodnotu 0.<br /><br /> Můžete to jako parametr v shaderu výpočty, například animace texture souřadnice, – hodnoty barev nebo dalších atributů.<br /><br /> **Výstup:**<br /><br /> `Output`: `float`<br /> Normalizovaný čas v sekundách.|Žádné|  
|**Čas**|Čas v sekundách.<br /><br /> Můžete to jako parametr v shaderu výpočty, například animace texture souřadnice, – hodnoty barev nebo dalších atributů.<br /><br /> **Výstup:**<br /><br /> `Output`: `float`<br /> Čas v sekundách.|Žádné|