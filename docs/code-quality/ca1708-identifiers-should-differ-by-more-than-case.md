---
title: 'CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5098e2feadc6d67c466e31ab19d059ac70c7d833
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547395"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Názvy dvou typů, členů, parametrů nebo plně kvalifikovaných oborů názvů jsou identické, když jsou převedeny na malá písmena.

Ve výchozím nastavení toto pravidlo vyhledává pouze externě viditelné typy, členy a obory názvů, ale to je [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Identifikátory pro obory názvů, typy, členy a parametry nelze odlišit pouze ve velikosti písmen, protože jazyky cílené na modul CLR (Common Language Runtime) nemusí rozlišovat malá a velká písmena. Například [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] je široce používaný jazyk bez rozlišení velkých a malých písmen.

Toto pravidlo je vyvoláno pouze u veřejně viditelných členů.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Vyberte název, který je jedinečný, pokud je porovnán s jinými identifikátory při nerozlišování velkých a malých písmen.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Knihovna nemusí být použitelná ve všech dostupných jazycích v rozhraní .NET.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1708.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (pojmenování). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="example-of-a-violation"></a>Příklad porušení

Následující příklad demonstruje porušení tohoto pravidla.

[!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1709: Identifikátory by se měly použita správně.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)