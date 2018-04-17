---
title: 'CA1308: Normalizujte řetězce na velká písmena | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 979b6d0bbd14d6432ea376622ce61f6329f708fa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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