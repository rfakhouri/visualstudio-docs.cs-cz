---
title: 'Postupy: filtrování sestav z příkazového řádku | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14be02ecf293cfb141b671917a715c8013009d2e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668742"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Postupy: Filtrování sestav z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: filtrování sestav z příkazového řádku](https://docs.microsoft.com/visualstudio/profiling/how-to-filter-reports-from-the-command-line).  
  
Pomocí možností **VSPerfReport** příkazu, můžete filtrovat sestavy k segmentu určený čas souboru dat profilování nebo omezit data na jeden nebo více procesů nebo vláken. Další informace o tomto příkazu najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**StartTime:**[*hodnotu*]|Zobrazit pouze data shromážděná za hodnotou (v milisekundách).|  
|**EndTime:**[*hodnotu*]|Zobrazit pouze data shromážděná před hodnotou (v milisekundách).|  
|**FilterFile:** `VSPFFile`|Určuje umístění souboru filtru, který byl vytvořen **sestavu výkonu Visual Studio** okna.|  
|**MsFilter:**[*StartTime, doba trvání*]|Zobrazit pouze data od `StartTime` až do délky `Duration` (v milisekundách).|  
|**Proces:**[*Pid*]|Zobrazit pouze data ze zadaného procesu.|  
|**Vlákna:**[*Idvlákna*]|Zobrazit pouze data ze zadaného vlákna.|  
|**Vlákna:**[*Idvlákna, Idprocesu*]|Zobrazit pouze data ze zadaného vlákna, která souvisí se zadaným procesem.|



