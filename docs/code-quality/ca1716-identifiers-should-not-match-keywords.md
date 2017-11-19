---
title: "CA1716: Identifikátory by neměly odpovídat klíčová slova | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 619fc7867d14a26f2c3b674b4b8ac8b2d8fba114
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by neměly odpovídat klíčovým slovům
|||  
|-|-|  
|TypeName|IdentifiersShouldNotMatchKeywords|  
|CheckId|CA1716|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Název oboru názvů, typ nebo člen viritual nebo rozhraní odpovídá rezervované klíčové slovo v programovacím jazyce.  
  
## <a name="rule-description"></a>Popis pravidla  
 Identifikátory pro obory názvů, typy a virtuální a členové rozhraní by neměly odpovídat klíčová slova, která jsou definovaná sadou jazyky, které cílí modul common language runtime. V závislosti na jazyk, který se používá a klíčové slovo chyby kompilátoru a nejednoznačnosti můžete nastavit knihovny obtížně použitelný.  
  
 Toto pravidlo zkontroluje proti klíčová slova v těchto jazycích:  
  
-   Visual Basic  
  
-   C#  
  
-   C++/CLI  
  
 Porovnávání se používá pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] klíčová slova a porovnání malá a velká písmena se používá pro jiné jazyky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vyberte název, který se nenachází v seznamu klíčová slova.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Upozornění od tohoto pravidla můžete potlačit, pokud jste přesvědčeni, že identifikátor nesmí být pro uživatele matoucí rozhraní API, a že je použitelná ve všech jazycích k dispozici v knihovně [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].