---
title: 'CA1815: Přepište rovná se a operátor rovnosti na hodnotových typech'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4d3fbe44347e1d0c453c2db9de1f5deac84ab771
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914803"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: Přepište rovná se a operátor rovnosti na hodnotových typech
|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ veřejné hodnoty nepřepisuje <xref:System.Object.Equals%2A?displayProperty=fullName>, nebo neimplementuje operátor rovnosti (==). Toto pravidlo nekontroluje výčty.

## <a name="rule-description"></a>Popis pravidla
 U typů hodnot, zděděné implementace <xref:System.Object.Equals%2A> reflexe knihovnu používá a porovná obsah všech polí. Reflexe je výpočetně náročná a porovnání rovnosti všech polí může být zbytečné. Pokud budou uživatelé k porovnání nebo řazení instancí nebo používat jako hash klíče tabulky, měli implementovat vaše typ hodnoty <xref:System.Object.Equals%2A>. Pokud si programovací jazyk podporuje přetížení operátoru, měli byste také poskytnout implementaci operátory rovnosti a nerovnosti.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, zadejte implementaci <xref:System.Object.Equals%2A>. Pokud je to možné, implementujte operátor rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné pro potlačení upozornění od tohoto pravidla, pokud instance typu hodnota nebudou porovnány navzájem.

## <a name="example-of-a-violation"></a>Příkladem porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje strukturu (typ hodnoty), která porušuje toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]

## <a name="example-of-how-to-fix"></a>Příklad, jak k opravě

### <a name="description"></a>Popis
 Následující příklad opravy předchozí porušení přepsáním <xref:System.ValueType.Equals%2A?displayProperty=fullName> a implementace operátory rovnosti (==,! =).

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2224: Přepište Equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>Viz také
 <xref:System.Object.Equals%2A?displayProperty=fullName>