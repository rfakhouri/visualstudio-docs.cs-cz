---
title: 'CA2003: Nezacházejte s vlákénky jako s vlákny'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a2b843eb3e4a898006c26d978afb12a147f9745
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54978422"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Nezacházejte s vlákénky jako s vlákny

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Spravovaným vláknem se zachází jako vlákno Win32.

## <a name="rule-description"></a>Popis pravidla

Nepředpokládejte, že se že spravovaným vláknem se vlákno Win32; je vlákno. Modul CLR (CLR) spouští spravovaná vlákna jako jsou vlákna v kontextu reálného vlákna, které jsou vlastněny SQL. Tato vlákna mohou být sdíleny napříč objektů třídy AppDomains a dokonce i databází v procesu serveru SQL Server. Pomocí spravovaného funguje místní úložiště vláken, ale nemusí používat místní úložiště nespravovaného vlákna nebo se předpokládá, že váš kód poběží v aktuálním vlákně operačního systému znovu. Neměňte nastavení, jako je národní prostředí vlákna. Nevolejte CreateCriticalSection nebo CreateMutex – prostřednictvím P/Invoke, protože vyžadují vlákna, která se zadá zámku musí také ukončení uzamčení. Vzhledem k tomu vlákna, která se zadá zámek není zámek ukončit, při použití vlákének, kritické oddíly Win32 a vzájemně vyloučené přístupy jsou zbytečné v SQL. Většina stavu může bezpečně používat na spravované <xref:System.Threading.Thread> objektu, včetně místním úložišti spravované vlákno a aktuální uživatelské rozhraní (UI) jazykovou verzi vlákna. Ale pro programovací model důvody, nebudete moct změnit aktuální jazykovou verzi vlákna, při použití SQL. Toto omezení se vynucují prostřednictvím nové oprávnění.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Zkontrolujte vaše použití vláken a odpovídajícím způsobem měnit kód.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte toto pravidlo.