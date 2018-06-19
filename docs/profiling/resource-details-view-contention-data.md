---
title: Podrobnosti prostředku o zobrazení – Data kolizí | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.resourcedetails
helpviewer_keywords:
- Resource Details view
ms.assetid: a4ecfe1c-abbc-4fb3-9ab2-34de50486901
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ac06fa18ee9459d8dc43bd0c536b68f9d027c97d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31584396"
---
# <a name="resource-details-view---contention-data"></a>Zobrazení podrobností o prostředku – Data kolizí
Zobrazení podrobností prostředků uvede časová osa grafu blokování událostí, která byla způsobena kolizí nad vybraného prostředku. Blokování události dojde při vlákno je nucen se pozastavit provádění, protože jiné vlákno zablokuje přístup k prostředku.  
  
 Toto zobrazení představuje časové ose provádění každé vlákno jako vodorovný pruh a představuje všechny blokující události jako svislá čára na časové ose přístup z více vláken. Pokud je to nezbytné, může zvětšit části časové osy a zobrazte jednotlivé události. K zobrazení cesty provádění (zásobník volání) funkcí, které vedly k události, klikněte na panelu událostí. Funkce se zobrazí v **zásobníkem volání** okno. Pokud zdrojový kód pro funkce je k dispozici, můžete kliknout na název funkce upravit zdrojový soubor v rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-magnify-a-timeline-segment"></a>Zvětšit segment časové osy  
  
-   Přetáhněte ukazatel myši nad oblast časovou osu.  
  
     Po uvolnění tlačítka myši se zvětší zobrazení na vybrané časové segmentu. Proces další magnify segmentu, můžete opakovat. Posouvací políčko posuvníku čas představuje relativní velikost segmentu čas, který se zobrazí v zobrazení.  
  
#### <a name="to-zoom-out-on-a-timeline"></a>Zvětšit na časové ose  
  
-   Proveďte jeden z následujících kroků:  
  
    -   Klikněte na tlačítko **Oddálit** se vrátíte do předchozího úroveň přiblížení.  
  
    -   Klikněte na tlačítko **zvětšení resetovat** a zobrazit všechny časové osy v zobrazení.  
  
#### <a name="to-view-the-call-stack-of-an-event"></a>Chcete-li zobrazit zásobníku volání na událost  
  
-   V tomto časová osa grafu klikněte na panelu událostí.  
  
#### <a name="to-view-or-edit-the-source-code-of-a-function-in-the-call-stack"></a>Chcete-li zobrazit nebo upravit zdrojový kód funkce v zásobníku volání  
  
-   V **zásobníkem volání** okně klikněte na název funkce.  
  
 Zdrojový kód funkce musí být součástí aktuálního projektu.  
  
#### <a name="to-view-the-call-tree-of-contention-events-for-the-resource"></a>Zobrazení stromu volání kolizní události pro prostředek  
  
-   V tomto časová osa grafu, klikněte na tlačítko **celkový**.  
  
     Zobrazí se zobrazení kolizí prostředku. Další informace najdete v tématu [zobrazení kolizí prostředku](../profiling/resource-contentions-view-contention-data.md)  
  
#### <a name="to-view-all-the-contention-events-of-a-thread"></a>Chcete-li zobrazit všechny události kolizí vlákna  
  
-   V tomto časová osa grafu klikněte na název nebo ID vlákna.  
  
     Zobrazení podrobností vlákno se zobrazí pro vybrané vlákno. Další informace najdete v tématu [vláken zobrazení podrobností](../profiling/thread-details-view-contention-data.md).