---
title: Zobrazení – Data kolizí podrobností prostředků | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.resourcedetails
helpviewer_keywords:
- Resource Details view
ms.assetid: a4ecfe1c-abbc-4fb3-9ab2-34de50486901
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 27aed07b7e4212502a819ce024b0ce46680df6bf
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759958"
---
# <a name="resource-details-view---contention-data"></a>Zobrazení podrobností o prostředku – data kolizí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení podrobností prostředků zobrazí graf časové osy blokujících událostí, které byly způsobeny kolizí nad vybraný prostředek. Blokování události dojde, když vlákno je nucen k pozastavení provádění, protože jiné vlákno má uzamčený přístup k prostředku.  
  
 Toto zobrazení představuje na časové ose spuštění každého vlákna jako vodorovný pruh a představuje všechny blokující události jako svislá čára na ose vlákna. V případě potřeby můžete zvětšit části časové osy a zobrazte jednotlivé události. Chcete-li zobrazit cesta provedení (zásobník volání) funkcí, které vedly k události, klikněte na panel události. Funkce se zobrazí v **zásobník volání** okna. Pokud zdrojový kód funkce je k dispozici, můžete kliknout na upravit zdrojový soubor v rozhraní pro název funkce [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-magnify-a-timeline-segment"></a>Zvětšit segment časové osy  
  
-   Přetažením ukazatele myši přes oblast na časové ose.  
  
     Po uvolnění tlačítka myši přiblížení zobrazení vybraného časového úseku. Proces další zvětšit segmentu, můžete opakovat. Posuvníku na posuvníku čas představuje relativní velikost časového úseku, který se zobrazí v zobrazení.  
  
#### <a name="to-zoom-out-on-a-timeline"></a>Chcete-li oddálení časové osy  
  
-   Proveďte jeden z následujících kroků:  
  
    -   Klikněte na tlačítko **Oddálit** se vraťte na předchozí úroveň přiblížení.  
  
    -   Klikněte na tlačítko **přiblížení resetování** a zobrazit všechny časové osy v zobrazení.  
  
#### <a name="to-view-the-call-stack-of-an-event"></a>Chcete-li zobrazit zásobník volání události  
  
-   Časová osa grafu klikněte na panel události.  
  
#### <a name="to-view-or-edit-the-source-code-of-a-function-in-the-call-stack"></a>Chcete-li zobrazit nebo upravit zdrojový kód funkce v zásobníku volání  
  
- V **zásobník volání** okna, klikněte na název funkce.  
  
  Zdrojový kód funkce musí být součástí aktuálního projektu.  
  
#### <a name="to-view-the-call-tree-of-contention-events-for-the-resource"></a>Zobrazení stromu volání kolizní události pro prostředek  
  
-   Časová osa grafu, klikněte na tlačítko **celkový**.  
  
     Zobrazení kolizí se zobrazí pro prostředek. Další informace najdete v tématu [zobrazení kolizí prostředku](../profiling/resource-contentions-view-contention-data.md)  
  
#### <a name="to-view-all-the-contention-events-of-a-thread"></a>Chcete-li zobrazit všechny události sporu vlákna  
  
-   Časová osa grafu klikněte na název nebo ID vlákna.  
  
     Zobrazení podrobností vláken se zobrazí pro vybrané vlákno. Další informace najdete v tématu [zobrazení podrobností vláken](../profiling/thread-details-view-contention-data.md).
