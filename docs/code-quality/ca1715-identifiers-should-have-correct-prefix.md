---
title: 'CA1715: Identifikátory by měly mít správnou předponu'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b794eb7c7a258a843763b2c68902000031c17eb3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807144"
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715: Identifikátory by měly mít správnou předponu

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectPrefix|
|CheckId|CA1715|
|Kategorie|Microsoft.Naming|
|Narušující změna|Zásadní - při vyvolání na rozhraních.<br /><br /> Bez konce – při aktivaci pro parametry obecného typu.|

## <a name="cause"></a>Příčina

Název rozhraní nezačíná velké písmeno "I".

-nebo-

Název [parametr obecného typu](/dotnet/csharp/programming-guide/generics/generic-type-parameters) na typu nebo metody nezačíná velkým 'T'.

Ve výchozím nastavení, toto pravidlo pouze prohledá externě viditelného rozhraní, typy a metody, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Podle úmluvy názvy některé programovací prvky spustit s určitou předponou.

Názvy rozhraní, které by měl začínat velkým, které "I" a další velké písmeno. Toto pravidlo oznámí porušení zásad pro názvy rozhraní, například "MyInterface" a "IsolatedInterface".

Názvy parametrů obecného typu by měl začínat velkým 'T' a volitelně může být následován znakem jiný velké písmeno. Toto pravidlo oznámí porušení zásad pro názvy parametrů obecného typu, jako je například "V" a "Typ".

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), můžete nakonfigurovat, které části kódu toto pravidlo analyzuje. Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

### <a name="single-character-type-parameters"></a>Parametry typu jedním znakem

Můžete nakonfigurovat, jestli se mají vyloučit z tohoto pravidla parametry typu jedním znakem. Například chcete-li určit, že toto pravidlo *by neměla* analyzovat parametry typu jedním znakem, přidejte jeden z následujících páry klíč hodnota do souboru .editorconfig ve vašem projektu:

```
# Package version 2.9.0 and later
dotnet_code_quality.CA1715.exclude_single_letter_type_parameters = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.allow_single_letter_type_parameters = true
```

> [!NOTE]
> Toto pravidlo je vyvoláno nikdy pro parametr typu s názvem `T`, například `Collection<T>`.

### <a name="api-surface"></a>Rozhraní API

Můžete nakonfigurovat, které části vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich dostupnosti. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1715.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Přejmenujte identifikátor tak, že je správně předponou.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="interface-naming-example"></a>Příklad rozhraní pojmenování

Následující fragment kódu ukazuje, nesprávně pojmenované rozhraní:

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]

Následující fragment kódu opravuje předchozí porušení vložením prefixu rozhraní s 'I':

[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]

## <a name="type-parameter-naming-example"></a>Příklad pojmenování parametru typu

Následující fragment kódu ukazuje parametr nesprávně pojmenované obecného typu:

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]

Následující fragment kódu opravuje předchozí porušení vložením prefixu parametr obecného typu s 'T':

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA1722: Identifikátory by neměly mít nesprávnou předponu](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)