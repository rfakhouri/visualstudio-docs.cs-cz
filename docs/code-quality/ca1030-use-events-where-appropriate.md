---
title: 'CA1030: Použijte události, kde je to vhodné'
ms.date: 11/04/2016
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
ms.openlocfilehash: 66b9893d6ad0c47dde69fa2cb6d35ee228cff59e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Použijte události, kde je to vhodné
|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Název veřejné, chráněný nebo privátní metoda začíná na jednu z těchto možností:

-   Doplněk

-   RemoveOn

-   Ještě efektivněji

-   Vyvolat

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo zjišťuje metody, které mají názvy obvykle používané pro události. Události podle návrhový vzor pozorovatel nebo publikování a odběru; používají se při změně stavu v jeden objekt musí být oznamovat jiné objekty. Pokud metoda je volána v reakci na změnu stavu jasně definované, by měla být volána metoda obslužnou rutinou události. Objekty volající tuto metodu by měly místo přímého volání metody vyvolat událost.

 Několik běžných příkladů událostí, které se nacházejí v uživatelské rozhraní aplikace, které způsobí, že akce uživatele, jako je například kliknutí na tlačítko segment kódu provést. [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Model událostí není omezeno na uživatelská rozhraní; je určeno odkudkoli musí komunikovat, stav se změní na jeden nebo více objektů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud metoda je volána, když se stav objektu se změní, zvažte změnu návrhu používat [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] událostí modelu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění na toto pravidlo, je-li metoda nefunguje s [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] událostí modelu.