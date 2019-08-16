---
title: 'CA1043: Použijte celočíselný nebo řetězcový argument pro indexery'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: aeec6e202ccb7f3075b04d29bdef7d171ae545f7
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547683"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Použijte celočíselný nebo řetězcový argument pro indexery

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Typ obsahuje indexer, který používá jiný typ indexu <xref:System.Int32?displayProperty=fullName>než, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>nebo <xref:System.String?displayProperty=fullName>.

Ve výchozím nastavení toto pravidlo vyhledává pouze veřejné a chráněné typy, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Indexery, tj. indexované vlastnosti, by měly pro index používat celočíselné nebo řetězcové typy. Tyto typy jsou obvykle používány pro indexování datových struktur a zvyšují použitelnost knihovny. <xref:System.Object> Použití typu by mělo být omezeno na ty případy, kde konkrétní celé číslo nebo typ řetězce nelze zadat v době návrhu. Pokud návrh vyžaduje jiné typy pro index, je třeba znovu zvážit, zda typ představuje logické úložiště dat. Pokud nepředstavuje logické úložiště dat, použijte metodu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, změňte index na celé číslo nebo typ řetězce nebo použijte metodu místo indexeru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačí upozornění z tohoto pravidla až po pečlivém zvážení nutnosti nestandardního indexeru.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1043.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje indexer, který používá <xref:System.Int32> index.

[!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
[!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
[!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA1023: Indexery by neměly být multidimenzionální](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)
- [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)