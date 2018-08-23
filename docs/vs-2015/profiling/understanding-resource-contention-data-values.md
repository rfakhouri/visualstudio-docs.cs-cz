---
title: Porozumění hodnotám dat kolizí prostředku | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: 071c0f0f-1eba-4dc8-ae87-0810e4086dd0
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10c06805db7ef817421f7c9f85e316af8d4b5b35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669254"
---
# <a name="understanding-resource-contention-data-values"></a>Porozumění hodnotám dat kolizí prostředku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [porozumění hodnotám dat kolizí prostředku](https://docs.microsoft.com/visualstudio/profiling/understanding-resource-contention-data-values).  
  
Profilace kolize prostředků shromažďuje podrobné informace v zásobníku volání pokaždé, když, že jsou konkurenční vlákna v aplikaci musí počkat na přístup ke sdíleným prostředkům.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
 Sestavy kolize prostředků zobrazují celkový počet kolizí a celkový čas, který byl vynaložen na čekání na prostředek pro moduly, funkce, řádky zdrojového kódu a instrukce, ve kterých došlo k čekání.  
  
-   Celkové hodnoty se zobrazí celkový počet sporů, které vynutit funkci čekat ve sporty prostředků a celková doba čekání funkce.  Spory, které byly způsobeny podřízené funkce, které byly volány funkce jsou součástí (včetně) hodnot.  
  
-   Výhradní hodnoty se zobrazí pouze počet sporů, který vynucené funkci čekat a, které byly způsobeny kódu v těle funkce. Tento počet sporů: způsobené podřízené funkce nejsou zahrnuty. Výhradní čas pro funkci také zahrnuje pouze dobu čekání, které byly způsobeny příkazy v těle funkce.  
  
 Zobrazení sestav kolize prostředků také zahrnovat grafech časové osy, které ukazují jednotlivých kolizní události v čase a zobrazit zásobníky volání, které vytvořeny určitá událost. Další informace naleznete v jednom z následujících témat:  
  
-   [Zobrazení podrobností o vláknu](../profiling/thread-details-view-contention-data.md)  
  
-   [Zobrazení podrobností o prostředku](../profiling/resource-details-view-contention-data.md)  
  
 Další informace o druhý režim profilace souběžnosti, naleznete v tématu [Vizualizátor souběžnosti](../profiling/concurrency-visualizer.md).



