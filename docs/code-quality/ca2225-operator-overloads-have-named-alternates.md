---
title: 'CA2225: Přetížení operátoru mají pojmenované alternativy'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6a9b03ce2552e50ebfca8f9e6e2823dee794c20
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841766"
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225: Přetížení operátoru mají pojmenované alternativy

|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Bylo zjištěno přetížení operátoru a očekávané pojmenovaný alternativní metoda nebyla nalezena.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Přetížení operátoru umožňuje používat symboly pro vyjádření výpočty typu. Například typ, který přetížení na symbol plus (+) pro přidání by obvykle mít jiný člen s názvem "Přidat". Pojmenovaný alternativní člen poskytuje přístup ke stejným funkcím jako operátor a je k dispozici pro vývojáře, kteří programují v jazycích nepodporujících přetížené operátory.

Toto pravidlo zkontroluje operátorů uvedených v následující tabulce.

|C#|Visual Basic|C++|Alternativní název|
|---------|------------------|-----------|--------------------|
|+ (binární)|+|+ (binární)|Přidejte|
|+=|+=|+=|Přidejte|
|&|A|&|BitwiseAnd|
|&=|A =|&=|BitwiseAnd|
|&#124;|Nebo|&#124;|BitwiseOr|
|&#124;=|Or=|&#124;=|BitwiseOr|
|--|Není k dispozici|--|Snížení|
|/|/|/|Dělení|
|/=|/=|/=|Dělení|
|==|=|==|Je rovno|
|^|XOR|^|XOR|
|^=|XOR =|^=|XOR|
|>|>|>|Porovnat|
|>=|>=|>=|Porovnat|
|++|Není k dispozici|++|Přírůstek|
|<>|!=|Je rovno|
|<<|<<|<<|LeftShift|
|<<=|<<=|<<=|LeftShift|
|<|<|<|Porovnat|
|<=|<=|\<=|Porovnat|
|&&|Není k dispozici|&&|LogicalAnd|
|&#124;&#124;|Není k dispozici|&#124;&#124;|LogicalOr|
|!|Není k dispozici|!|LogicalNot|
|%|Mod|%|Mod nebo zbytku|
|%=|Není k dispozici|%=|Mod|
|* (binární)|*|*|Násobení|
|*=|Není k dispozici|*=|Násobení|
|~|Not|~|OnesComplement|
|>>|>>|>>|RightShift|
=|Není k dispozici|>>=|RightShift|
|-(binární)|-(binární)|-(binární)|Odečíst|
|-=|Není k dispozici|-=|Odečíst|
|true|IsTrue|Není k dispozici|IsTrue (vlastnost)|
|-(unární)|Není k dispozici|-|negate –|
|+ (unární)|Není k dispozici|+|Plus|
|false|IsFalse|False|IsTrue (vlastnost)|

Není k dispozici == nemůže být přetížená ve vybraném jazyce.

Pravidlo zkontroluje také operátory implicitní a explicitní přetypování typu (`SomeType`) tak, že zkontrolujete pro metody s názvem `ToSomeType` a `FromSomeType`.

V jazyce C# Pokud je binární operátor přetížen, odpovídající operátor přiřazení pokud existuje, je také implicitně přetížené.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, implementujte alternativní metoda pro operátor; pojmenujte ho pomocí doporučená alternativní název.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění tohoto pravidla, Pokud implementujete sdílené knihovny. Aplikace můžete ignorovat upozornění tohoto pravidla.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca2225.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (využití). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

V následujícím příkladu definuje strukturu, která poruší toto pravidlo. Chcete-li v příkladu, přidejte veřejnou `Add(int x, int y)` metoda do struktury.

[!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224: Přepište equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Přepište GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)
- [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)