---
title: "Analýza kódu pro spravovaný kód upozornění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.project.vcfxcoptool.enablefxcop
helpviewer_keywords:
- managed code analyis, warnings
- warnings, managed code analysis
- managed code analysis warnings
- code analysis,managed code
ms.assetid: 3c2741ff-0d3a-42e6-acd5-d42310bd03c4
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 689fe39cfb8a7719efbba15b412800d9dfa78361
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="code-analysis-for-managed-code-warnings"></a>Upozornění Analýzy kódu pro spravovaný kód
Spravovaná analýza kódu nástroj poskytuje upozornění, které indikují porušení pravidel v knihovnách spravovaného kódu. Upozornění jsou uspořádány do oblasti pravidlo například návrhu, lokalizace, výkonu a zabezpečení. Každé upozornění označuje, že je porušení pravidel spravovaná analýza kódu. Tato část obsahuje podrobný diskusí a příklady pro každý upozornění analýzy spravovaného kódu.  
  
 V následující tabulce jsou uvedeny typu informací, který je zadán pro každou upozornění.  
  
|Položka|Popis|  
|----------|-----------------|  
|Typ|TypeName pro pravidlo.|  
|CheckId|Jedinečný identifikátor pro pravidlo. CheckId a kategorie se používají pro-source potlačení upozornění.|  
|Kategorie|Kategorie upozornění.|  
|Narušující změna|Jestli opravu pro porušení pravidlo je narušující změně. Narušující změny znamená, že sestavení, který má závislost na cíli, která způsobila narušení nebude znovu zkompiluje s novým fixed verze nebo může dojít k selhání v době běhu z důvodu změn. Pokud jsou k dispozici více opravy a alespoň jeden oprava k narušující změně a jeden oprava není, lze určit 'Nejnovější' i 'Bez pozastavení'.|  
|příčina|Konkrétní spravovaný kód, který způsobí, že pravidlo generovat upozornění.|  
|Popis|Popisuje problémy, které jsou za upozornění.|  
|Jak vyřešit porušení|Vysvětluje, jak změnit zdrojový kód a splňovat pravidla zabránit generování upozornění.|  
|Kdy potlačit upozornění|Popisuje, když je bezpečné potlačit upozornění z tohoto pravidla.|  
|Příklad kódu|Příklady, které porušují pravidlo a opravit, příklady, které splňují pravidla.|  
|Související upozornění|Související upozornění.|  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|||  
|-|-|  
|[Upozornění podle CheckId](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)|Zobrazí seznam všech upozornění podle CheckId|  
|[Upozornění kryptografie](../code-quality/cryptography-warnings.md)|Upozornění, které podporují bezpečnější knihovny a aplikace prostřednictvím správné použití šifrování.|  
|[Upozornění ohledně návrhu](../code-quality/design-warnings.md)|Upozornění, které podporují správné knihovny návrhu podle specifikace [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pokynů pro návrh.|  
|[Upozornění globalizace](../code-quality/globalization-warnings.md)|Upozornění, které podporují připravených knihovny a aplikace.|  
|[Upozornění interoperability](../code-quality/interoperability-warnings.md)|Upozornění, které podporují interakci s klienty COM.|  
|[Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)|Upozornění, které podporují údržby knihovny a aplikace.|  
|[Upozornění mobility](../code-quality/mobility-warnings.md)|Upozornění, které podporují efektivní spotřeby energie.|  
|[Upozornění na pojmenování](../code-quality/naming-warnings.md)|Upozornění, které podporují dodržování konvencí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pokynů pro návrh.|  
|[Upozornění výkonu](../code-quality/performance-warnings.md)|Upozornění, které podporují aplikace a vysoce výkonné knihovny.|  
|[Upozornění přenositelnosti](../code-quality/portability-warnings.md)|Upozornění, které podporují přenositelnost napříč různými platformami.|  
|[Upozornění spolehlivosti](../code-quality/reliability-warnings.md)|Upozornění, které podporují spolehlivost knihovny a aplikace, například správné využití paměti a přístup z více vláken.|  
|[Upozornění zabezpečení](../code-quality/security-warnings.md)|Upozornění, které podporují bezpečnější knihovny a aplikace.|  
|[Upozornění využití](../code-quality/usage-warnings.md)|Upozornění, která podporují vhodné použití [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|[Chyby zásad Analýzy kódu](../code-quality/code-analysis-policy-errors.md)|Chyby, ke kterým došlo, pokud zásady pro analýzu kódu nesplněno při vrácení se změnami.|