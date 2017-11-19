---
title: "CA2003: Rozlišujte vlákénka od vláken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4ca9b0649950be50dcff5103258d60f6f924f12a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Rozlišujte vlákénka od vláken
|||  
|-|-|  
|TypeName|DoNotTreatFibersAsThreads|  
|CheckId|CA2003|  
|Kategorie|Microsoft.Reliability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Spravované vlákno se považuje za Win32 vlákna.  
  
## <a name="rule-description"></a>Popis pravidla  
 Není předpokládají, že spravované vlákno je Win32 vlákna. Je vlákno. Modul CLR (CLR) se spustí spravovaných vláknech, jako jsou vlákna v kontextu skutečné vláken, které jsou vlastněny SQL. Tyto vláken může sdílet víc domén a i databáze v procesu systému SQL Server. Pomocí spravovaného přístup z více vláken, který bude fungovat místní úložiště, ale nemusí použít místní úložiště vláken nespravované nebo Předpokládejme, že váš kód bude spuštěna znovu v aktuální vlákno operačního systému. Neměňte nastavení, jako například národní prostředí vlákna. Nevolejte CreateCriticalSection nebo funkce CreateMutex prostřednictvím P/Invoke, protože vyžadují podproces, který zadá zámek musí ukončit také zámek. Protože to nebude tak při použití jsou vlákna, kritické oddíly Win32 a mutex – třídy budou nemá v systému SQL. Většina stavu můžete bezpečně používat na spravovaném objektu System.Thread. To zahrnuje lokální úložiště vláken spravované a aktuální prostředí uživatelského rozhraní (UI) vlákna. Ale pro programování modelu důvodů, nebudete moct změnit jazykové verze aktuálního vlákna při použití SQL; Tím se vynutí prostřednictvím nové oprávnění.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zkontrolujte vaše použití vláken a odpovídajícím způsobem upravit svůj kód.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto pravidlo by nemělo potlačit.