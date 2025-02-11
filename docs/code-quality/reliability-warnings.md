---
title: Upozornění spolehlivosti
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 009422eaf9ac81af6e8f9d48732655b2528c85a0
ms.sourcegitcommit: 92a04c57ac0a49f304fa2ea5043436f30068c3cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/21/2019
ms.locfileid: "65976148"
---
# <a name="reliability-warnings"></a>Upozornění spolehlivosti

Upozornění spolehlivosti podporu knihovny a aplikace spolehlivost, jako je například správné využití paměti a podproces. Pravidla spolehlivosti patří:

|Pravidlo|Popis|
|----------|-----------------|
|[CA2000: Uvolňujte objekty před ztrátou oboru](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|Protože může dojít k mimořádné události, která zabrání spuštění destruktoru objektu, měl by být objekt explicitně uvolněn předtím, než se všechny odkazy na něj dostanou mimo rozsah.|
|[CA2001: Vyhněte se volání problematických metod](../code-quality/ca2001-avoid-calling-problematic-methods.md)|Člen volá potencionálně nebezpečnou nebo problematickou metodu.|
|[CA2002: Nepoužívejte zámky na objekty se slabou identitou](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Objekt má slabou identitu, pokud k němu lze přímo přistupovat přes hranice aplikační domény. Vlákno, které se pokouší získat zámek na objekt se slabou identitou, může být blokováno jiným vláknem v jiné aplikační doméně, které má zámek na stejný objekt.|
|[CA2003: Rozlišujte vlákénka od vláken](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|Spravovaným vláknem se zachází jako vlákno Win32.|
|[CA2004: Odeberte volání uvolňování paměti. KeepAlive](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|Pokud převádíte na použití SafeHandle, odeberte veškerá volání uvolňování paměti. KeepAlive (objekt). Třídy v takovém případě by nemělo být volání uvolňování paměti. KeepAlive, za předpokladu, že nemají finalizační metodu, ale spoléhají na SafeHandle operačního systému dokončí zpracování pro ně.|
|[CA2006: Použijte SafeHandle pro zapouzdření nativních prostředků](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Použití IntPtr ve spravovaném kódu může znamenat možný problém zabezpečení a spolehlivosti. Všechna použití IntPtr musí být přezkoumána za účelem určení, zda je použití SafeHandle (nebo podobné technologie) na tomto místě vyžadováno.|
|[CA2007: Není await přímo úkolu](../code-quality/ca2007-do-not-directly-await-task.md)|Asynchronní metoda [čeká](/dotnet/csharp/language-reference/keywords/await) <xref:System.Threading.Tasks.Task> přímo.|