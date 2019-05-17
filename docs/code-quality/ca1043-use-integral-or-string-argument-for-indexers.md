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
ms.openlocfilehash: ca381d88524535ad042b5bd3efda25f8cc350fa4
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842128"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Použijte celočíselný nebo řetězcový argument pro indexery

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ obsahuje indexer, který používá typ indexu jiné než <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, nebo <xref:System.String?displayProperty=fullName>.

Ve výchozím nastavení, toto pravidlo pouze prohledá veřejné a chráněné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Indexery, tj. indexované vlastnosti, by měly používat celočíselné typy nebo typy řetězců pro index. Tyto typy se obvykle používají pro indexování datových struktur a zlepšit tak použitelnost knihovny. Použití <xref:System.Object> typ by měl být omezeno na ty případy, ve kterém nejde zadat konkrétní typ celé číslo nebo řetězec v době návrhu. Pokud návrhu vyžaduje další typy pro index, zvažte, zda typ představuje logické datové úložiště. Pokud to nepředstavuje logické datové úložiště, použijte metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změnit index typu celé číslo nebo řetězec nebo používat metodu místo indexeru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění tohoto pravidla až po pečlivého zvážení potřebu nestandardní indexeru.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1043.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje, indexer, který se používá <xref:System.Int32> indexu.

[!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
[!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
[!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA1023: Indexery by neměly být multidimenzionální](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)
- [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)