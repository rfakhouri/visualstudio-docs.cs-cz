---
title: "CA1724: Názvy typů by neměly odpovídat oborům názvů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f138958ce2dc83b7d258fbdb16986841e92d3484
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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