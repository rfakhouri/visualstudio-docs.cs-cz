---
title: 'CA2003: Rozlišujte vlákénka od vláken | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0a1683c8cb9b9c6dc856f40ddbc7864d773f2101
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189063"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Nezacházejte s vlákénky jako s vlákny
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Spravovaným vláknem se zachází jako vlákno Win32.

## <a name="rule-description"></a>Popis pravidla
 Nepředpokládejte, že se že spravovaným vláknem se vlákno Win32. Je vlákno. Common language runtime (CLR) se spustí spravovaná vlákna, jako jsou vlákna v kontextu reálného vlákna, které jsou vlastněny SQL. Tato vlákna mohou být sdíleny napříč objektů třídy AppDomains a dokonce i databází v procesu serveru SQL Server. Pomocí spravovaného vlákna, místní úložiště bude fungovat, ale nemusí používat místní úložiště nespravovaného vlákna nebo se předpokládá, že váš kód poběží v aktuálním vlákně operačního systému znovu. Neměňte nastavení, jako je národní prostředí vlákna. Nevolejte CreateCriticalSection nebo CreateMutex – prostřednictvím P/Invoke, protože vyžadují vlákna, která se zadá zámku musí také ukončení uzamčení. Vzhledem k tomu, že to nebude tak při použití vlákének, budou mít kritických oddílů Win32 a vzájemně vyloučené přístupy zbytečné v SQL. Většina stavu může bezpečně používat na spravovaný objekt System.Thread. Jedná se o místním úložišti spravované vlákno a aktuální uživatelské rozhraní (UI) jazykovou verzi vlákna. Ale pro programovací model důvody, nebudete moct změnit aktuální jazykovou verzi vlákna, při použití SQL; Tím se vynutí prostřednictvím nové oprávnění.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Zkontrolujte vaše použití vláken a odpovídajícím způsobem měnit kód.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto pravidlo by neměl potlačit.
