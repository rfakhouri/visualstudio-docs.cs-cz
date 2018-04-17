---
title: 'CA1724: Názvy typů by neměly odpovídat oborům názvů | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 39e6b539d0259f83475e3e3a685bed7ffe6a7c87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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