---
title: 'CA1002: Nezveřejňujte obecné seznamy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotExposeGenericLists
- CA1002
helpviewer_keywords:
- CA1002
- DoNotExposeGenericLists
ms.assetid: 5caac810-1a79-47df-a27b-c46c5040bf34
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2d1b4f67f25db7c0006decc5fc26696c6c5dad01
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65685350"
---
# <a name="ca1002-do-not-expose-generic-lists"></a>CA1002: Nezveřejňujte obecné seznamy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotExposeGenericLists|
|CheckId|CA1002|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Typ obsahuje externě viditelného členu, který je <xref:System.Collections.Generic.List%601?displayProperty=fullName> typ, vrátí <xref:System.Collections.Generic.List%601?displayProperty=fullName> typu nebo jehož signatura obsahuje <xref:System.Collections.Generic.List%601?displayProperty=fullName> parametru.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Collections.Generic.List%601?displayProperty=fullName> je obecná kolekce navržená pro výkon a nikoli dědičnost. <xref:System.Collections.Generic.List%601?displayProperty=fullName> neobsahuje virtuální členy, které chcete změnit chování zděděné třídy. Následující obecné kolekce navržené pro dědičnost a měla by být vystavena místo <xref:System.Collections.Generic.List%601?displayProperty=fullName>.

- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>

- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>

- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte <xref:System.Collections.Generic.List%601?displayProperty=fullName> typ na jednu z obecné kolekce, které je navržené pro dědičnost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla, pokud sestavení, které toto upozornění vyvolá neměl být opakovaně použitelné knihovny. Například je bezpečný pro potlačení tohoto upozornění v aplikaci výkonu, která je vyladěná ve kterém bylo zvýšení výkonu získané z použití obecné seznamy.

## <a name="related-rules"></a>Související pravidla
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Použijte instance obecných události obslužné rutiny](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také
 [Obecné typy](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
