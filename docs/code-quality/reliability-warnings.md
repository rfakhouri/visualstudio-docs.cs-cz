---
title: "Upozornění spolehlivosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d3ac06911009a24640031fd3a2306110f289014f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="reliability-warnings"></a>Upozornění spolehlivosti
Upozornění spolehlivosti podporovat spolehlivost knihovny a aplikace, například správné využití paměti a přístup z více vláken.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA2000: Uvolňujte objekty před ztrátou oboru](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|Protože může dojít k mimořádné události, která zabrání spuštění destruktoru objektu, měl by být objekt explicitně uvolněn předtím, než se všechny odkazy na něj dostanou mimo rozsah.|  
|[CA2001: Vyhněte se volání problematických metod](../code-quality/ca2001-avoid-calling-problematic-methods.md)|Člen volá potencionálně nebezpečnou nebo problematickou metodu.|  
|[CA2002: Nepoužívejte zámky na objekty se slabou identitou](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Objekt má slabou identitu, pokud k němu lze přímo přistupovat přes hranice aplikační domény. Vlákno, které se pokouší získat zámek na objekt se slabou identitou, může být blokováno jiným vláknem v jiné aplikační doméně, které má zámek na stejný objekt.|  
|[CA2003: Rozlišujte vlákénka od vláken](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|Spravované vlákno se považuje za Win32 vlákna.|  
|[CA2004: Odeberte volání do globálního katalogu. Funkce KeepAlive](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|Při převodu na hodnotu využití SafeHandle, odeberte všechna volání do globálního katalogu. KeepAlive (objekt). Třídy v tomto případě by nemělo být volání GC. Pro jejich zpracování KeepAlive, za předpokladu, že nemají finalizační metody, ale závisí na SafeHandle pro dokončení operačního systému.|  
|[CA2006: Použijte SafeHandle pro zapouzdření nativních prostředků](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Použití IntPtr ve spravovaném kódu může znamenat možný problém zabezpečení a spolehlivosti. Všechna použití IntPtr musí být přezkoumána za účelem určení, zda je použití SafeHandle (nebo podobné technologie) na tomto místě vyžadováno.|