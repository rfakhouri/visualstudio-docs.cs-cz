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
ms.openlocfilehash: ad0659241e75c862b3d82c64a7e8b2ad3ccada21
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547675"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Použijte události, kde je to vhodné

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Název metody začíná jedním z následujících způsobů:

- PhotoDraw
- RemoveOn
- Nebezpečí
- Výkop

Ve výchozím nastavení toto pravidlo vypadá pouze externě viditelnými metodami, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo zjišťuje metody, které mají názvy obvykle používané pro události. Události následují za řídicím vzorem pro pozorovatele nebo publikování a odběr. používají se v případě, že změna stavu v jednom objektu musí být předávána jiným objektům. Pokud je metoda volána v reakci na jasně definovanou změnu stavu, metoda by měla být vyvolána obslužnou rutinou události. Objekty volající tuto metodu by měly místo přímého volání metody vyvolat událost.

Některé běžné příklady událostí jsou k dispozici v aplikacích uživatelského rozhraní, kde akce uživatele, jako je kliknutí na tlačítko, způsobí spuštění segmentu kódu. Model událostí .NET není omezen na uživatelská rozhraní. Měl by se použít všude, kde je nutné sdělit změny stavu jednomu nebo více objektům.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Pokud je metoda volána při změně stavu objektu, zvažte změnu návrhu pro použití modelu události .NET.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačí upozornění z tohoto pravidla, pokud metoda nefunguje s modelem událostí .NET.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1030.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).
