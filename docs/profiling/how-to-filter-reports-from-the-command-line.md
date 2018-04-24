---
title: 'Postupy: filtrování sestav z příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0591b646c8311004d9c08b2fb1a9fcdf2ab1908a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Postupy: Filtrování sestav z příkazového řádku
Pomocí možností **vsperfreport –** příkazů, můžete sestavy segmentu určený čas datového souboru profilování filtrovat nebo omezit data na jeden nebo více procesů nebo vláken. Další informace o tomto příkazu najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**Čas spuštění:**[*hodnotu*]|Zobrazit pouze data shromážděná po hodnotu (v milisekundách).|  
|**Čas ukončení:**[*hodnotu*]|Zobrazit pouze data shromážděná před hodnotu (v milisekundách).|  
|**FilterFile:** `VSPFFile`|Určuje umístění souboru filtru, který byl vytvořen z **Sestava výkonu Visual Studio** okno.|  
|**MsFilter:**[*StartTime, doba trvání*]|Zobrazit pouze data z `StartTime` dokud délka `Duration` (v milisekundách).|  
|**Proces:**[*Pid*]|Zobrazit pouze data ze zadaného procesu.|  
|**Přístup z více vláken:**[*ID podprocesu*]|Zobrazit pouze data ze zadaného vlákno.|  
|**Přístup z více vláken:**[*ID podprocesu, ID procesu*]|Zobrazit pouze data ze zadaného vlákno, které souvisí s určený proces.|