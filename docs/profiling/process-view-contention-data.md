---
title: Zobrazení procesů – Data kolizí | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 41212ffb6b317d7c98a50b074d93c128977a5a82
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="process-view---contention-data"></a>Zobrazení procesů – Data kolizí
Zobrazení procesů zobrazí data kolizí pro procesy a vláken, které byly provedeny během spuštění profilování.  
  
 Když symboly jsou k dispozici, procesy jsou uvedeny podle názvu. Pokud symboly nejsou k dispozici, procesy jsou uvedeny podle jejich adresa paměti v šestnáctkovém formátu. Vlákna jsou uvedeny jako podřízené objekty proces, který je vytvořil.  
  
 Následující tabulka vysvětluje hodnot sloupců v tabulce proces zobrazení.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Počáteční čas**|Počet milisekund nebo cyklů procesoru od začátku profilace na začátek procesu nebo přístup z více vláken.|  
|**Blokované čas**|Celkový čas, během kterého byly funkce proces nebo podproces blokovat spouštění.|  
|**Blokované čas: %**|Procento životnosti procesu nebo vlákno, ve kterém byly blokovat provádění funkcí proces nebo přístup z více vláken.|  
|**Kolizí**|Počet pokusů, které funkce proces nebo podproces měla blokovat spouštění.|  
|**% Kolizí**|Procento všech kolizí v profilaci spuštění, které byly kolizí procesu nebo přístup z více vláken.|  
|**Koncový čas**|Počet milisekund nebo cyklů procesoru od začátku profilace na konci procesu nebo přístup z více vláken.|  
|**ID**|Generované systémem identifikátor procesu nebo přístup z více vláken.|  
|**Doba životnosti**|Počet milisekund nebo cyklů procesoru od začátku procesu nebo na konci procesu nebo vlákna nebo konci profilace podprocesu.|  
|**Typ**|Typ řádek, zpracovat nebo přístup z více vláken.<br /><br /> Pouze v **VSReport** příkazového řádku sestavy. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).|  
|**Jméno**|Název procesu nebo přístup z více vláken.|  
|**Jedinečné ID**|Identifikátor generovaný profileru, které jsou jedinečné pro proces nebo přístup z více vláken.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení procesů](../profiling/process-view.md)