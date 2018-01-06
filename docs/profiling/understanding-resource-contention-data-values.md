---
title: "Porozumění hodnotám dat kolizí prostředku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: 071c0f0f-1eba-4dc8-ae87-0810e4086dd0
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5c5b108404f8812de8b0a124146fd9270ec2c561
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="understanding-resource-contention-data-values"></a>Porozumění hodnotám dat kolizí prostředku
Profilace kolizí prostředku shromažďuje podrobné zásobníku volání informace pokaždé, když, že konkurenční vláken v aplikaci, vynuceně přesunuty čekání na přístup k sdíleného prostředku.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Sestavy kolizí prostředku zobrazí celkový počet kolizí a celková doba strávená čeká na prostředek pro moduly, funkce, řádků zdrojového kódu a pokyny, ve kterých došlo k čekání.  
  
-   (Včetně) hodnot zobrazí celkový počet kolizí, které vynutit funkce čekání podle kolize prostředku – a celkovou dobu, kterou čekali funkce.  Kolizí, která byla způsobena podřízené funkce, které byly volá funkci jsou součástí (včetně) hodnot.  
  
-   Výhradní hodnoty zobrazit jenom Počet kolizí, vynutit funkce čekat a která byla způsobena kódu v těle funkce. Kolizí způsobené podřízené funkce nejsou zahrnuty. Výhradní čas pro funkci také obsahuje pouze dobu čekání, která byla způsobena příkazy v těle funkce.  
  
 Zobrazení sestav kolizí prostředku také obsahovat časová osa grafy, které se zobrazí jednotlivé kolizní události v čase a zobrazit zásobníky volání, které vytvořili určitá událost. Další informace naleznete v jednom z následujících témat:  
  
-   [Zobrazení podrobností o vláknu](../profiling/thread-details-view-contention-data.md)  
  
-   [Zobrazení podrobností o prostředku](../profiling/resource-details-view-contention-data.md)  
  
 Další informace o druhý režim profilace souběžného zpracování najdete v tématu [vizualizér souběžnosti](../profiling/concurrency-visualizer.md).