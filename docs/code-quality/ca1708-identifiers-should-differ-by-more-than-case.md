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
ms.openlocfilehash: 32ac2e430abdc068070457dcf362e39dcbc0b398
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797557"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Názvy dva typy, členy, parametry nebo plně kvalifikovaný obory názvů jsou identické, když jste převedený na malá písmena.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, členy a obory názvů, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Identifikátory pro obory názvů, typy, členy a parametry nelze odlišit pouze ve velikosti písmen, protože jazyky cílené na modul CLR (Common Language Runtime) nemusí rozlišovat malá a velká písmena. Například [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] je často používaný jazyk velká a malá písmena.

Toto pravidlo je vyvoláno na veřejně viditelné pouze členy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Vyberte název, který je jedinečný, je porovnání pro jiné identifikátory písmen.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Knihovny nemusí být použitelná ve všech jazycích k dispozici v rozhraní .NET Framework.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1708.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example-of-a-violation"></a>Příkladem porušení

Následující příklad ukazuje porušení tohoto pravidla.

[!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)