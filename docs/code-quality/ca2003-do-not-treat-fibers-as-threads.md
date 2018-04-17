---
title: 'CA2003: Rozlišujte vlákénka od vláken | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e3873c54b4b0c060f6703102d0429136ed710a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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