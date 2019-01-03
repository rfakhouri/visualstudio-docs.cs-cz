---
title: Karta soubor stránky, dialogové okno vlastností procesu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ded332b68ee4ae4d628bc272b563e973da6154e5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913330"
---
# <a name="page-file-tab-process-properties-dialog-box"></a>Karta Soubor stránky, dialogové okno vlastností procesu
Použití **stránkovací soubor** kartu prozkoumat stránkovacího souboru procesu. Pro zobrazení [dialogové okno vlastností procesu](../debugger/process-properties-dialog-box.md), přesunout fokus [zobrazení procesů](../debugger/processes-view.md) okno. Vyberte libovolný uzel procesu ve stromové struktuře a pak zvolte **vlastnosti** z **zobrazení** nabídky.  
  
 Následující nastavení jsou k dispozici na **stránkovací soubor** kartu:  
  
|Položka|Popis|  
|-----------|-----------------|  
|**Bajty stránkovacího souboru**|Aktuální číslo stránky, které tento proces používá ve stránkovacím souboru. Stránkovací soubor uloží stránek využívané procesem, ale nejsou obsažené v jiných souborech. Stránkovací soubor je používán všechny procesy a nedostatečné místo ve stránkovacím souboru mohou způsobit chyby, zatímco jiné procesy jsou spuštěny.|  
|**Bajty stránkovacího souboru – Špička**|Maximální počet stránek, které tento proces se má použít ve stránkovacím souboru.|  
|**Chyby stránek**|Počet chyb stránek podle vlákna provádění v tomto procesu. Stránkování nastane, pokud vlákno odkazuje na stránku virtuální paměti, která není v jeho pracovního sadě v hlavní paměti. Díky tomu se na stránce nebudou načteny z disku Pokud je na seznamu a proto již do paměti, nebo pokud jej používá jiný proces se na stránce se sdílí.|