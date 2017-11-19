---
title: "CA1005: Vyhněte se nadbytečným parametrům na obecných typů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b5fad132dfdda0ef12e6d74c503c5d27024a8382
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: Vyhněte se nadbytečným parametrům na obecných typech
|||  
|-|-|  
|TypeName|AvoidExcessiveParametersOnGenericTypes|  
|CheckId|CA1005|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Externě viditelné obecného typu má více než dva parametry typu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Čím více parametrů typu obecný typ obsahuje, tím obtížnější je vědět a zapamatovat si, co každý z parametrů typu představuje. Je obvykle zřejmé se jeden typ parametru, jako v `List<T>`a v některých případech se dva parametry typu, jako v `Dictionary<TKey, TValue>`. Pokud existuje víc než dva parametry typu, je obtížné stane příliš velký pro většinu uživatelů (například `TooManyTypeParameters<T, K, V>` v jazyce C# nebo `TooManyTypeParameters(Of T, K, V)` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, změňte návrh používat více než dva parametry typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud návrh absolutně vyžaduje více než dva parametry typu není potlačení upozornění od tohoto pravidla. Poskytuje obecné typy v syntaxi, který se snadno pochopit a používat zkracuje čas, který je potřeba další a zvyšuje počet přijetí nové knihovny.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Nezveřejňují obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Použijte obecné události instance obslužné rutiny](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Viz také  
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)