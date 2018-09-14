---
title: 'CA1030: Použijte události, kde je to vhodné'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d1b0bac434ad7a182dc56ac08173646068623bd
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547542"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Použijte události, kde je to vhodné
|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda public, protected nebo private název začíná na jednu z následujících akcí:

- Doplněk

- RemoveOn

- Oheň

- Raise

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo zjišťuje metody, které mají názvy obvykle používané pro události. Události podle návrhový vzor pozorovatel nebo publikování a odběru; používají se při změně stavu do jednoho objektu musí sdělí další objekty. Pokud metoda volána jako odpověď jednoznačně definovanou změnu stavu, by měl vyvolat metodu obslužné rutiny události. Objekty volající tuto metodu by měly místo přímého volání metody vyvolat událost.

 Některé běžné příklady událostí, které se nacházejí v uživatelských rozhraní aplikací, kde způsobí, že akce uživatele, jako je kliknutí na tlačítko segment kódu k provedení. [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Model událostí není omezena pouze na uživatelské rozhraní, měla by se používat kdekoli musí komunikovat, stav se změní na jeden nebo více objektů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud metoda je volána při změně stavu objektu, měli byste zvážit změnu návrhu a použít [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] model událostí.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pokud metoda nefunguje s [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] model událostí.