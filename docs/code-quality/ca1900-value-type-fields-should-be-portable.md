---
title: 'CA1900: Pole hodnot typu by měla být přenosná | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 669f52b3255559dec2ac90eea90356c2bb886c9d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Pole hodnot by měla být přenosná
|||  
|-|-|  
|TypeName|ValueTypeFieldsShouldBePortable|  
|CheckId|CA1900|  
|Kategorie|Microsoft.Portability|  
|Narušující změna|Ukončování řádků - li pole si můžete prohlédnout mimo sestavení.<br /><br /> Non narušující – Pokud pole není viditelná mimo sestavení.|  
  
## <a name="cause"></a>příčina  
 Toto pravidlo zkontroluje, že struktury, které jsou deklarovány s explicitní rozložení zarovnané správně při zařazen do nespravovaného kódu v 64bitových operačních systémech. IA-64 neumožňuje přistupuje k nezarovnané paměti a proces bude selhat, pokud není tato porušení pevný.  
  
## <a name="rule-description"></a>Popis pravidla  
 Struktury, které mají explicitní rozložení, který obsahuje chybně zarovnaných pole příčina havárií na 64bitové operační systémy.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Všechna pole, které jsou menší než 8 bajtů musí mít posuny, které je násobkem jejich velikost a pole, které jsou 8 bajtů nebo více musí mít posuny, které je násobkem 8. Jiným řešením je použití `LayoutKind.Sequential` místo `LayoutKind.Explicit`, pokud je možné logicky.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto upozornění má být potlačeno pouze v případě, že se vyskytuje v chybě.