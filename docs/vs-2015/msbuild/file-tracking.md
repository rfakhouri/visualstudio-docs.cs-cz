---
title: Sledování souborů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c5afc245bd16954ba348b4ec581238bf17e5d994
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758710"
---
# <a name="file-tracking"></a>Sledování souborů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Volání do systému souborů Windows pro proces a podřízené procesy protokolů sledování souborů. Voláním funkcí uvedených níže programy řídí, kdy zapnout a vypnout protokolování a určit soubor protokolu, který chcete použít.  
  
## <a name="in-this-section"></a>V tomto oddílu  
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
