---
title: 'CA1724: Názvy typů by neměly odpovídat oborům názvů'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c178558743ca69fb3b62eccaf8164e4b49167ad3
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547565"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Názvy typů by neměly odpovídat oborům názvů
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název typu odpovídal tomu [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] názvy oborů názvů v porovnávání.

## <a name="rule-description"></a>Popis pravidla
 Názvy typů by neměly odpovídat názvům obory názvů, které jsou definovány v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] knihovny tříd. Porušení tohoto pravidla může snížit použitelnost knihovny.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název typu, který se neshoduje s názvem [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] oboru názvů pro knihovny tříd.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pro vývoj nových projektů, žádné známé scénáře nastat, pokud je třeba potlačit upozornění tohoto pravidla. Předtím, než můžete potlačit upozornění, pečlivě zvažte, jak uživatele vaše knihovna může být matoucí odpovídající název. Pro přesouvání knihovny, budete muset potlačit upozornění tohoto pravidla.