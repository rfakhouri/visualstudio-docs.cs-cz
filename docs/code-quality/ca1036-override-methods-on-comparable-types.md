---
title: 'CA1036: Přepište metody u srovnatelných typů'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d08644ede6b9b28496cff585624ea37858afd49
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842292"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: Přepište metody u srovnatelných typů

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Typ implementuje <xref:System.IComparable?displayProperty=fullName> rozhraní, nedojde k přepsání <xref:System.Object.Equals%2A?displayProperty=fullName> nebo nepřetěžuje specifické pro jazyk operátor rovnosti, nerovnosti, menší – než, nebo větší-než. Pravidlo nevytváří sestavu porušení, pokud typ dědí pouze implementace rozhraní.

Ve výchozím nastavení, toto pravidlo pouze prohledá veřejné a chráněné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Typy, které definují vlastní řazení implementovat <xref:System.IComparable> rozhraní. <xref:System.IComparable.CompareTo%2A> Metoda vrací celočíselnou hodnotu, která určuje správné pořadí řazení pro dvě instance daného typu. Toto pravidlo určuje typy, které nastaví pořadí řazení. Nastavení pořadí řazení vyplývá, že běžný význam rovnosti, nerovnosti, menší – než a větší-než nevztahují. Když zadáte implementace <xref:System.IComparable>, je obvykle třeba také přepsat <xref:System.Object.Equals%2A> tak, že vrátí hodnoty, které jsou konzistentní s <xref:System.IComparable.CompareTo%2A>. Pokud přepíšete <xref:System.Object.Equals%2A> a psaní kódu v jazyce, který podporuje přetížení operátoru, měli byste také poskytnout operátory, které jsou konzistentní s <xref:System.Object.Equals%2A>.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, přepište <xref:System.Object.Equals%2A>. Pokud svůj oblíbený programovací jazyk podporuje přetížení operátoru, zadejte následující operátory:

- op_Equality
- op_inequality –
- op_LessThan
- op_GreaterThan

Tokeny, které se používají k vyjádření tyto operátory v jazyce C#, jsou následující:

```csharp
==
!=
<
>
```

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění pravidla CA1036 při porušení zásad je způsobena chybějícími operátory a svůj oblíbený programovací jazyk nepodporuje přetěžování, stejně jako v případě s jazykem Visual Basic. Pokud zjistíte, že implementace operátorů nemá smysl v kontextu vaší aplikace, je také bezpečně potlačit upozornění tohoto pravidla, když je vyvoláno na operátory rovnosti než op_Equality. Nicméně byste měli vždy přepsat op_Equality a pokud přepíšete == – operátor <xref:System.Object.Equals%2A?displayProperty=nameWithType>.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1036.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="examples"></a>Příklady

Následující kód obsahuje typ, který implementuje správně <xref:System.IComparable>. Kód poznámky určují metody, které splňují různá pravidla, které se týkají <xref:System.Object.Equals%2A> a <xref:System.IComparable> rozhraní.

[!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

Následující kód aplikace testuje chování <xref:System.IComparable> implementace, které se zobrazilo dříve.

[!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.IComparable?displayProperty=fullName>
- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [Operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators)