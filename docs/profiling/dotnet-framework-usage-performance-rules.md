---
title: Pravidla výkonu použití rozhraní .NET framework | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ab573755-6370-48aa-853d-a7321c424c79
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b92ae0ad9d60ac24047b136e67d7659cb680ecc1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55002454"
---
# <a name="net-framework-usage-performance-rules"></a>Pravidla výkonu použití rozhraní .NET Framework
Pravidla výkonu v rozhraní.NET Framework využití kategorii identifikovat konkrétní metody, které se dá optimalizovat a také identifikovat další obecné vzorce používání, jako je například uvolňování paměti a kolize zámků, které můžete prozkoumat pro problémy s výkonem.  
  
|||  
|-|-|  
|[DA0001: Použití třídy StringBuilder ke zřetězení](../profiling/da0001-use-stringbuilder-for-concatenations.md)|Volání <xref:System.String.Concat(System.String,System.String)?displayProperty=fullName> jsou podstatnou část dat profilování. Zvažte použití <xref:System.Text.StringBuilder> třídy k vytvoření řetězce z více segmentů.|  
|[DA0005: Časté shromažďování GC2](../profiling/da0005-frequent-gc2-collections.md)|Relativně velké množství paměti objektů .NET jsou právě uvolněny v procesu uvolnění paměti generace 2. Pokud příliš mnoho krátkodobé objekty byly zachovány při 1. generace kolekce, náklady na správu paměti se snadno můžou stát nadměrné.|  
|[DA0006: Přepis Equals() pro typy hodnot](../profiling/da0006-override-equals-parens-for-value-types.md)|Volání `Equals` metoda nebo operátory rovnosti veřejné hodnotového typu je podstatnou část dat profilování. Zvažte implementaci metodu efektivnější.|  
|[DA0007: Vyhnutí se použití výjimek pro tok řízení](../profiling/da0007-avoid-using-exceptions-for-control-flow.md)|Vysoký počet obslužných rutin výjimek rozhraní .NET Framework byly volány v dat profilování. Zvažte použití další logiku toku řízení k omezení počtu výjimek, které jsou vyvolány.|  
|[DA0010: Náročná funkce GetHashCode](../profiling/da0010-expensive-gethashcode.md)|Volání `GetHashCode` podstatnou část dat profilování jsou metody typu nebo `GetHashCode` metoda přidělí paměť. Zjednodušit metody.|  
|[DA0011: Náročná funkce CompareTo](../profiling/da0011-expensive-compareto.md)|`CompareTo` Metoda typu je nákladné nebo metodu přidělí paměť. Vám pomůže zjednodušit `CompareTo` metody.|  
|[DA0012: Velký počet reflexí](../profiling/da0012-significant-amount-of-reflection.md)|Volání <xref:System.Reflection?displayProperty=fullName> metody jako <xref:System.Reflection.IReflect.InvokeMember%2A> a <xref:System.Reflection.IReflect.GetMember%2A> nebo typ metody jako <xref:System.Type.InvokeMember%2A> jsou podstatnou část dat profilování. Pokud je to možné, zvažte nahrazení tyto metody s časná vazba metod závislá sestavení.|  
|[DA0013: Vysoký výskyt použití String.Split nebo String.Substring](../profiling/da0013-high-usage-of-string-split-or-string-substring.md)|Volání <xref:System.String.Split%2A?displayProperty=fullName> nebo <xref:System.String.Substring%2A> metody jsou podstatnou část dat profilování. Zvažte použití <xref:System.String.IndexOf%2A> nebo <xref:System.String.IndexOfAny%2A> Pokud testujete existenci podřetězce v řetězci.|  
|[DA0018: 32bitová aplikace spuštěná v limitech paměti spravovaného procesu](../profiling/da0018-32-bit-application-running-at-process-managed-memory-limits.md)|Data systému, které jsou shromažďovány během profilování označuje, že rozhraní .NET Framework paměti haldy dosaženy maximální velikost, se kterým dosáhnete spravované haldy v 32bitový proces. Vezměte v úvahu profilaci znovu pomocí metody profilování paměti .NET a optimalizaci aplikací pomocí spravované prostředky.|  
|[DA0021: Vysoká míra 1. generace uvolňování paměti](../profiling/da0021-high-rate-of-gen-1-garbage-collections.md)|Relativně velké množství paměti objektů .NET jsou právě uvolněny v procesu uvolnění paměti generace 1. Pokud příliš mnoho krátkodobé objekty byly zachovány při shromažďování generace 0, náklady na správu paměti se snadno můžou stát nadměrné.|  
|[DA0022: Vysoká míra 2. generace uvolňování paměti](../profiling/da0022-high-rate-of-gen-2-garbage-collections.md)|Velké množství paměti objektů .NET jsou právě uvolněny v procesu uvolnění paměti generace 2. Pokud příliš mnoho krátkodobé objekty byly zachovány při 1. generace kolekce, náklady na správu paměti se snadno můžou stát nadměrné. Toto pravidlo je vyvoláno, když překročí vyšší prahová hodnota pravidla DA0005 míře sporů zámků.|  
|[DA0023: Vysoký čas procesoru uvolňování paměti](../profiling/da0023-high-gc-cpu-time.md)|Údaje o výkonu systému, který je shromážděných během profilace označuje, že množství času, který byl stráven uvolňování paměti je důležité ve srovnání s časem zpracování celkový počet aplikací.|  
|[DA0024: Nadměrný čas procesoru uvolňování paměti](../profiling/da0024-excessive-gc-cpu-time.md)|Údaje o výkonu systému, který je shromážděných během profilace označuje, že množství času, který byl stráven uvolňování paměti je příliš vysoká ve srovnání s časem zpracování celkový počet aplikací. Toto pravidlo je vyvoláno, když vyšší prahová hodnota pravidla DA0023 přesahuje množství času stráveného při uvolňování paměti.|  
|[DA0038: Vysoká míra konfliktů zámků](../profiling/da0038-high-rate-of-lock-contentions.md)|Systém údaje o výkonu, která se shromažďují se data profilace označuje, že výrazně vysoké míře sporů zámků došlo k chybě při spuštění aplikace. Vezměte v úvahu profilaci znovu pomocí metody profilace souběžného zpracování najít příčinu sporů.|  
|[DA0039: Velmi vysoké míře sporů zámků platformy](../profiling/da0039-very-high-rate-of-lock-contentions.md)|Systém údaje o výkonu, která se shromažďují se data profilace označuje, že došlo k příliš vysoké míře sporů zámků při spuštění aplikace. Vezměte v úvahu profilaci znovu pomocí metody profilace souběžného zpracování najít příčinu sporů. Toto pravidlo je vyvoláno, když překročí vyšší prahová hodnota pravidla DA0038 míře sporů zámků.|