---
title: "CA1308: Normalizujte řetězce na velká písmena | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9064ca9861f609499971b9f5188f5b0006458c15
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: Normalizujte řetězce na velká písmena
|||  
|-|-|  
|TypeName|NormalizeStringsToUppercase|  
|CheckId|CA1308|  
|Kategorie|Microsoft.Globalization|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Operace normalizuje řetězce na malá písmena.  
  
## <a name="rule-description"></a>Popis pravidla  
 Řetězce by měly být normalizovány na velká písmena. Malá skupina znaky, když budou jsou převeden na malá písmena, nelze provádět dobu odezvy. Chcete-li dobu odezvy způsob, jak převést znaky z jednoho národního prostředí na jiné národního prostředí, který představuje data znak jinak a pak na přesně ze převedený znaky načíst původní znaky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Změňte operace, které převod řetězců na malá písmena, tak, aby se převedou řetězce na velká písmena místo. Můžete například změnit `String.ToLower(CultureInfo.InvariantCulture)` k `String.ToUpper(CultureInfo.InvariantCulture)`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné pro potlačení upozornění, nejsou při rozhodnutí zabezpečení na základě výsledku (například když jsou jejich zobrazením v uživatelském rozhraní).  
  
## <a name="see-also"></a>Viz také  
 [Upozornění globalizace](../code-quality/globalization-warnings.md)