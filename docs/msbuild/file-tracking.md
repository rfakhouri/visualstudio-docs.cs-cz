---
title: Sledování souborů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b99934091ed617aa6c6bf2163391aa0d79c5414
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53861663"
---
# <a name="file-tracking"></a>Sledování souborů
Volání do systému souborů Windows pro proces a podřízené procesy protokolů sledování souborů. Voláním funkcí uvedených níže programy řídí, kdy zapnout a vypnout protokolování a určit soubor protokolu, který chcete použít.  
  
 [EndTrackingContext](../msbuild/endtrackingcontext.md)  
 Zastavte sledování aktuálního kontextu.  
  
 [ResumeTracking](../msbuild/resumetracking.md)  
 Obnovte sledování po volání [SuspendTracking](../msbuild/suspendtracking.md).  
  
 [SetThreadCount](../msbuild/setthreadcount.md)  
 Nastavte počet vláken pro sledování.  
  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)  
 Začněte nový kontext sledování.  
  
 [StartTrackingContextWithRoot](../msbuild/starttrackingcontextwithroot.md)  
 Začněte nový kontext sledování se zadaným kořenem.  
  
 [StopTrackingAndCleanup](../msbuild/stoptrackingandcleanup.md)  
 Ukončit sledování a uvolnit použité prostředky.  
  
 [SuspendTracking](../msbuild/suspendtracking.md)  
 Dočasně pozastavíte sledování.  
  
 [WriteAllTLogs](../msbuild/writealltlogs.md)  
 Vypsat protokoly sledování pro všechny kontexty.  
  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)  
 Vypsat protokol sledování pro aktuální kontext.