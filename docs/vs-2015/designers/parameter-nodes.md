---
title: Uzly parametru | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: da54db0b-3a3d-48dc-858c-7ac43aa04b13
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110f380f7450d611de5786fb865bdee8e64195f6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54764168"
---
# <a name="parameter-nodes"></a>Uzly parametru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V Návrháři shaderu představují uzly parametru vstupů na shader, které jsou pod kontrolou aplikace na základě za draw, například, vlastností materiálu, směrové světlo, kamery a čas. Vzhledem k tomu, že můžete změnit tyto parametry se každé volání draw, můžete poskytnout objekt rozdílný vzhled dosažený stejné shaderu.  
  
## <a name="parameter-node-reference"></a>Odkaz na parametr uzlu  
  
|Uzel|Podrobnosti|Vlastnosti|  
|----------|-------------|----------------|  
|**Pozice kamery ve světě**|Pozice kamery v prostoru světa.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Pozice kamery.|Žádná|  
|**Směr světla**|Vektor definující směr, ve kterém dopadá světlo ze světelného zdroje v prostoru světa.<br /><br /> To slouží k výpočtu osvětlení a množství odrazů v prostoru světa.<br /><br /> **Výstup:**<br /><br /> `Output`: `float3`<br /> Vektor od aktuálního pixelu ke zdroji světla.|Žádná|  
|**Materiál okolí**|Příspěvek rozptýlení barvy aktuálního pixelu, který má atribut pro nepřímého světla.<br /><br /> Rozptýlení barvy pixel simuluje jak osvětlení komunikuje s hrubý plochy. Parametr materiálu okolí můžete použít k odhadu jak Nepřímé světlo přispívá ke vzhledu objektu v reálném světě.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Rozptýlení barvy aktuálního pixelu, která je z důvodu nepřímé – to znamená, že okolí – osvětlení.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být z editoru modelů jinak **privátní**.<br /><br /> **Hodnota**<br /> Rozptýlení barvy aktuálního pixelu, která je z důvodu nepřímé – to znamená, že okolí – osvětlení.|  
|**Materiál rozptýlení**|Barva, která popisuje, jak aktuální pixel rozptýlí přímé osvětlení.<br /><br /> Rozptýlení barvy pixel simuluje jak osvětlení komunikuje s hrubý plochy. Můžete použít parametr rozptýlit materiál Chcete-li změnit, jak aktuální pixel rozptýlí přímé osvětlení – to znamená, směrové, bod nebo bodové světlo.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Barva, která popisuje, jak aktuální pixel rozptýlí přímé osvětlení.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být z editoru modelů jinak **privátní**.<br /><br /> **Hodnota**<br /> Barva, která popisuje, jak aktuální pixel rozptýlí přímé osvětlení.|  
|**Vyzařující materiál**|Podíl barvy aktuálního pixelu, který je přiřadit osvětlení, poskytující sám na sebe.<br /><br /> To vám umožní simulování zářivých objektů.; To znamená, že objekt, který dodává své vlastní světlo. Toto světlo neovlivňuje ostatní objekty.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Podíl barvy aktuálního pixelu, kterým se vlastním světle.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být z editoru modelů jinak **privátní**.<br /><br /> **Hodnota**<br /> Podíl barvy aktuálního pixelu, kterým se vlastním světle.|  
|**Reflexní materiál**|Barva, která popisuje, jak aktuální pixel odráží přímé osvětlení.<br /><br /> Reflexní barva pixel simuluje interakci světla s hladkého, zrcadlového povrchu. Chcete-li změnit, jak aktuální pixel odráží přímé osvětlení, můžete použít parametr reflexní materiál – to znamená, směrové, bod nebo bodové světlo.<br /><br /> **Výstup:**<br /><br /> `Output`: `float4`<br /> Barva, která popisuje, jak aktuální pixel odráží přímé osvětlení.|**Přístup**<br /> **Veřejné** umožňující vlastnost, která má být z editoru modelů jinak **privátní**.<br /><br /> **Hodnota**<br /> Barva, která popisuje, jak aktuální pixel odráží přímé osvětlení.|  
|**Materiál síla odlesku**|Skalární hodnota, která popisuje intenzitu zrcadlových odlesků.<br /><br /> Čím větší síla odlesku, více velký a dalekosáhlý odlesky stát.<br /><br /> **Výstup:**<br /><br /> `Output`: `float`<br /> Exponenciální termín, který popisuje intenzitu zrcadlových odlesků na aktuální pixel.|**Přístup**<br /> **Veřejné** povolit vlastnost, která má být z editoru modelů jinak **privátní**.<br /><br /> **Hodnota**<br /> Exponent, který udává intenzitu zrcadlových odlesků na aktuální pixel.|  
|**Normalizovaný čas**|Čas v sekundách normalizován do rozsahu [0, 1], tak, že pokud čas dosáhne hodnoty 1, resetuje na hodnotu 0.<br /><br /> Můžete to jako parametr ve výpočtech shaderu, například pro animaci souřadnic textury, barevné hodnoty nebo jiné atributy.<br /><br /> **Výstup:**<br /><br /> `Output`: `float`<br /> Normalizovaný čas v sekundách.|Žádná|  
|**čas**|Čas v sekundách.<br /><br /> Můžete to jako parametr ve výpočtech shaderu, například pro animaci souřadnic textury, barevné hodnoty nebo jiné atributy.<br /><br /> **Výstup:**<br /><br /> `Output`: `float`<br /> Čas v sekundách.|Žádná|
