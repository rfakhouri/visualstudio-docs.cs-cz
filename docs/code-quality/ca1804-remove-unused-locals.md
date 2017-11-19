---
title: "CA1804: Odeberte nepoužívané místní hodnoty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9217f3109c6ef03de33e444e723caa585d065efb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: Odeberte nepoužívané místní hodnoty
|||  
|-|-|  
|TypeName|RemoveUnusedLocals|  
|CheckId|CA1804|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Metoda deklaruje, místní proměnné, ale nepoužívá proměnnou s výjimkou pravděpodobně jako příjemce příkazu přiřazení. Pro analýzu tímto pravidlem otestované sestavení musí být vytvořená s ladicími informacemi a přidružené programového souboru databáze (.pdb) musí být k dispozici.  
  
## <a name="rule-description"></a>Popis pravidla  
 Nepoužívané místní proměnné a zbytečná přiřazení zvětšují velikost sestavení a snižují výkon.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte, nebo použijte místní proměnné. Všimněte si, že kompilátor jazyka C#, který je součástí s [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] odebere nepoužívané místní proměnné při `optimize` je povolena možnost.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo, je-li proměnná byla kompilátoru vygenerované. Je také bezpečné upozornění toto pravidlo potlačit nebo zakážete pravidlo, pokud výkon a údržba kódu nejsou primární otázky.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje několik nepoužívané místní proměnné.  
  
 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1809: Vyhněte se nadměrným](../code-quality/ca1809-avoid-excessive-locals.md)  
  
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: Vyhněte se nevytvořeným interní třídy](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)