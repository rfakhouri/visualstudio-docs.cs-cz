---
title: Sledování souborů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 878d4d7e56c51d8a41a0e3cf3e78d6c83ed5d0b5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55027669"
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