---
title: 'CA1815: Přepište rovná se a operátor rovnosti na hodnotových typech | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 09f9ef7ecb9dce361c2a060501e18fc4b36dd18a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902735"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: Přepište rovná se a operátor rovnosti na hodnotových typech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1815: přepište rovná se a operátor rovnosti na hodnotových typech](https://docs.microsoft.com/visualstudio/code-quality/ca1815-override-equals-and-operator-equals-on-value-types).

|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Veřejné hodnotový typ nemůže přepsat <xref:System.Object.Equals%2A?displayProperty=fullName>, nebo neimplementuje operátor rovnosti (==). Toto pravidlo nekontroluje výčty.

## <a name="rule-description"></a>Popis pravidla
 U typů hodnot, zděděná implementace metody <xref:System.Object.Equals%2A> používá knihovnu reflexe a porovnává obsah všech polí. Reflexe je výpočetně náročná a porovnání rovnosti všech polí může být zbytečné. Pokud budou uživatelé k porovnání nebo řazení instance nebo používají jako klíče zatřiďovací tabulky, typ hodnoty by měly implementovat <xref:System.Object.Equals%2A>. Pokud svůj oblíbený programovací jazyk podporuje přetížení operátoru, měli byste také poskytnout implementaci pro operátory rovnosti a nerovnosti.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zajišťovat implementaci rozhraní <xref:System.Object.Equals%2A>. Pokud je to možné, implementujte operátor rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud instance typu hodnoty nebudou porovnány, k sobě navzájem.

## <a name="example-of-a-violation"></a>Příkladem porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje strukturu (typ hodnoty), který porušuje tato pravidla.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.OverrideEqualsViolation/cs/FxCop.Performance.OverrideEqualsViolation.cs#1)]

## <a name="example-of-how-to-fix"></a>Příklad, jak k opravě

### <a name="description"></a>Popis
 Následující příklad opravuje předchozí porušení tak, že přepíšete <xref:System.ValueType.Equals%2A?displayProperty=fullName> a implementace operátory rovnosti (==,! =).

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.OverrideEqualsFixed/cs/FxCop.Performance.OverrideEqualsFixed.cs#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2224: Přepište Equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>Viz také
 <xref:System.Object.Equals%2A?displayProperty=fullName>



