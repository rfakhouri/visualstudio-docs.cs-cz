---
title: 'Postupy: Filtrování sestav z příkazového řádku | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1c90ca0bea8126308b1260258044cece53218fb3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62973783"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Postupy: Filtrování sestav z příkazového řádku
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