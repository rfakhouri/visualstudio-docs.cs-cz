---
title: 'CA1724: Názvy typů by neměly odpovídat oborům názvů'
ms.date: 11/04/2016
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
ms.openlocfilehash: c1f9e13f8e02712ba4d0a0a492a9a6588f7a8a5e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Názvy typů by neměly odpovídat oborům názvů
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název typu odpovídal [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] názvy oborů názvů v porovnání velká a malá písmena.

## <a name="rule-description"></a>Popis pravidla
 Názvy typů by neměly odpovídat názvům oborů názvů, které jsou definovány v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] knihovny tříd. Porušení tohoto pravidla může snížit použitelnost knihovny.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název typu, který neodpovídá názvu [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] obor názvů třídy knihovny.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pro nový vývoj žádné známé scénáře nastat, kde je třeba potlačit upozornění na toto pravidlo. Předtím, než toto upozornění potlačit, pečlivě zvažte, jak může být uživatelé vaše knihovna nerozumíte odpovídající název. Pro přesouvání knihovny, můžete chtít potlačit upozornění na toto pravidlo.