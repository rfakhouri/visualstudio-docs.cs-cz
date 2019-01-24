---
title: 'Postupy: Filtrování sestav z příkazového řádku | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: db2c9d845af962fc17da1ebd84e8dd5fe6ffadab
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54802998"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Postupy: Filtr sestavy z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí možností **VSPerfReport** příkazu, můžete filtrovat sestavy k segmentu určený čas souboru dat profilování nebo omezit data na jeden nebo více procesů nebo vláken. Další informace o tomto příkazu najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**StartTime:**[*hodnotu*]|Zobrazit pouze data shromážděná za hodnotou (v milisekundách).|  
|**EndTime:**[*hodnotu*]|Zobrazit pouze data shromážděná před hodnotou (v milisekundách).|  
|**FilterFile:** `VSPFFile`|Určuje umístění souboru filtru, který byl vytvořen **sestavu výkonu Visual Studio** okna.|  
|**MsFilter:**[*StartTime,Duration*]|Zobrazit pouze data od `StartTime` až do délky `Duration` (v milisekundách).|  
|**Proces:**[*Pid*]|Zobrazit pouze data ze zadaného procesu.|  
|**Vlákna:**[*Idvlákna*]|Zobrazit pouze data ze zadaného vlákna.|  
|**Vlákna:**[*Idvlákna, Idprocesu*]|Zobrazit pouze data ze zadaného vlákna, která souvisí se zadaným procesem.|
