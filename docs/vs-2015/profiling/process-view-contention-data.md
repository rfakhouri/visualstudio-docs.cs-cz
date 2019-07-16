---
title: Zobrazení procesů – Data kolizí | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e43541ddb75b067faa23437d315ce5f239256b1a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180222"
---
# <a name="process-view---contention-data"></a>Zobrazení procesů – data kolizí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Proces zobrazení dat kolizí pro procesy a vlákna, které byly spuštěny během spuštění profilování.  
  
 Když symboly jsou k dispozici, procesy jsou seřazeny podle názvu. Pokud nejsou k dispozici symboly, procesy jsou seřazeny podle jejich adresa paměti v šestnáctkovém formátu. Vlákna jsou uvedené jako podřízené objekty daného procesu, který je vytvořil.  
  
 Následující tabulka vysvětluje hodnot sloupce v tabulce zobrazení procesu.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Čas zahájení**|Počet milisekund nebo cyklů procesoru od začátku profilace do začátku procesu nebo vlákna.|  
|**Čas zablokování**|Celkový čas, během kterého se spuštění zablokoval funkce procesu nebo vlákna.|  
|**% Času zablokování**|Procento doby životnosti procesu nebo vlákna, ve kterém byly blokovat provádění funkce procesu nebo vlákna.|  
|**Tento počet sporů:**|Počet pokusů, které funkce proces nebo vlákno se zablokoval spuštění.|  
|**% Sporů**|Procento všech sporů v profilování, které byly sporů procesu nebo vlákna.|  
|**Koncový čas**|Počet milisekund nebo cyklů procesoru od začátku profilace do konce procesu nebo vlákna.|  
|**ID**|Systémem generovaných identifikátor procesu nebo vlákna.|  
|**Doba životnosti**|Počet milisekund nebo cyklů procesoru od samého začátku procesu nebo vlákna na konci procesu nebo vlákna nebo konce profilace.|  
|**Typ**|Typ řádku, procesu nebo vlákna.<br /><br /> Pouze v **VSReport** příkazového řádku sestavy. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).|  
|**Název**|Název procesu nebo vlákna.|  
|**Jedinečné ID**|Profiler vygenerovat identifikátor, který je jedinečný na příslušný proces nebo vlákno.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení procesů](../profiling/process-view.md)
