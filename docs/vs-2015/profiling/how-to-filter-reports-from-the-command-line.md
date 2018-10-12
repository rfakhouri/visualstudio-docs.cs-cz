---
title: 'Postupy: filtrování sestav z příkazového řádku | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
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
ms.openlocfilehash: 5a93e1bb2e1d3a65d82a4a0ac54e903ee20553d4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290144"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Postupy: Filtrování sestav z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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



