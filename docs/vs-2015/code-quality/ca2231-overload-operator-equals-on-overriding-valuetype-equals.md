---
title: 'CA2231: Přetižte operátor equals při přepsání ValueType.Equals | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 679df7b916740ad1a45d624f9f50d38c94d64caf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201562"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231: Přetižte operátor rovnosti při přetížení ValueType.Equals
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Hodnotový typ přepisuje <xref:System.Object.Equals%2A?displayProperty=fullName> , ale neimplementuje operátor rovnosti.

## <a name="rule-description"></a>Popis pravidla
 Ve většině programovacích jazyků neexistuje žádný výchozí implementace operátoru rovnosti (==) pro typy hodnot. Pokud svůj oblíbený programovací jazyk podporuje přetížení operátoru, měli byste zvážit, implementoval operátor rovnosti. Musí být shodná s jeho chování <xref:System.Object.Equals%2A>.

 V implementaci přetížení operátoru rovnosti nelze použít výchozí operátor rovnosti. To způsobí přetečení zásobníku. K implementaci operátor rovnosti, použijte metodu Object.Equals v implementaci. Příklad:

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, implementujte operátor rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla; Doporučujeme však, že pokud je to možné zadat operátor rovnosti.

## <a name="example"></a>Příklad
 Následující příklad definuje typ, který porušuje tato pravidla.

 [!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.EqualsGetHashCode/cs/FxCop.Usage.EqualsGetHashCode.cs#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: Přetížení operátoru mají pojmenované alternativy](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224: Přepište equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218: Přepište GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>Viz také
 <xref:System.Object.Equals%2A?displayProperty=fullName>
