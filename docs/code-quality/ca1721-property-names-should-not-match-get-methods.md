---
title: 'CA1721: Názvy vlastností by se neměly shodovat s metodami Get'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bf16a9edf25132aa8b58702f01563b8d7ccf109a
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841495"
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: Názvy vlastností by se neměly shodovat s metodami Get

|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Název členu začíná na "Get" a shoduje s názvem vlastnosti. Například typ, který obsahuje metodu s názvem 'Getcolor –' a vlastnost s názvem 'Color' způsobit porušení pravidla.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné členy a vlastnosti, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Metody „Get“ a vlastnosti by měly mít názvy, které zřetelně rozliší jejich funkce.

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. Taková konzistence snižuje čas, který vyžaduje další nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Změňte název tak, aby neodpovídá názvu metody, která je s předponou "Get".

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

> [!NOTE]
> Toto upozornění může vyloučit, je-li metody "Get" implementací rozhraní IExtenderProvider.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1721.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad obsahuje metody a vlastnosti, která toto pravidlo porušují.

[!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
[!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)