---
title: 'CA1716: Identifikátory by se neměly shodovat s klíčovými slovy'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47bbb39cadb6a092f71ebd7b3907f34fcc2782ce
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842052"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by se neměly shodovat s klíčovými slovy

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Název oboru názvů, typ, nebo virtuální nebo člen rozhraní odpovídá vyhrazenému klíčovému slovu programovacího jazyka.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné obory názvů, typy a členy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Identifikátory pro obory názvů, typy a virtuální a interface členy by neměly odpovídat klíčová slova, která jsou definována jazyky cílenými na modul common language runtime. V závislosti na jazyk, ve kterém se používá a klíčové slovo chyby kompilátoru a nejednoznačnosti můžete nastavit knihovnu obtížně použitelnou.

Toto pravidlo zkontroluje proti klíčových slov v těchto jazycích:

- Visual Basic
- C#
- C++/CLI

Malá a velká písmena malá a velká písmena porovnání se používá pro ostatní jazyky a porovnání slouží pro klíčová slova jazyka Visual Basic.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Vyberte název, který se nezobrazí v seznamu klíčových slov.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud už přesvědčili, že identifikátor nesmí být pro uživatele matoucí rozhraní API a, že je možné použít ve všech jazycích k dispozici v rozhraní .NET knihovnu můžete potlačit upozornění tohoto pravidla.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1716.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).