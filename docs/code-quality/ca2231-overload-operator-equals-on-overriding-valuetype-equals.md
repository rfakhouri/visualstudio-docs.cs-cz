---
title: 'CA2231: Přetižte operátor rovnosti při přetížení ValueType.Equals'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 81c9a94e318638837fb4ab8fe1a822dc0cfec46a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806576"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231: Přetižte operátor rovnosti při přetížení ValueType.Equals

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Hodnotový typ přepisuje <xref:System.Object.Equals%2A?displayProperty=fullName> , ale neimplementuje operátor rovnosti.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

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

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca2231.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (využití). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad definuje typ, který porušuje tato pravidla:

[!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225: Přetížení operátoru mají pojmenované alternativy](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224: Přepište equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Přepište GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Object.Equals%2A?displayProperty=fullName>