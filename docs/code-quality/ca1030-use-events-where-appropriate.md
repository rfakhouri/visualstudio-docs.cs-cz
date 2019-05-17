---
title: 'CA1030: Použijte události, kde je to vhodné'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ee7e96009d689fec48d242f4db1790e6e0eacafa
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842370"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Použijte události, kde je to vhodné

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Název metody začíná s jedním z následujících akcí:

- Doplněk
- RemoveOn
- Oheň
- Raise

Ve výchozím nastavení, toto pravidlo pouze prohledá externě viditelným metodám, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo zjišťuje metody, které mají názvy obvykle používané pro události. Události podle návrhový vzor pozorovatel nebo publikování a odběru; používají se při změně stavu do jednoho objektu musí sdělí další objekty. Pokud metoda volána jako odpověď jednoznačně definovanou změnu stavu, by měl vyvolat metodu obslužné rutiny události. Objekty volající tuto metodu by měly místo přímého volání metody vyvolat událost.

Některé běžné příklady událostí, které se nacházejí v uživatelských rozhraní aplikací, kde způsobí, že akce uživatele, jako je kliknutí na tlačítko segment kódu k provedení. Model události rozhraní .NET Framework není omezena pouze na uživatelské rozhraní; ji by měl být použít všude, kde musí komunikovat, že se stav změní na jeden nebo více objektů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Pokud metoda je volána při změně stavu objektu, měli byste zvážit změnu návrhu a použít model událostí .NET.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění tohoto pravidla, pokud metoda nefunguje s modelem event .NET.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1030.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).