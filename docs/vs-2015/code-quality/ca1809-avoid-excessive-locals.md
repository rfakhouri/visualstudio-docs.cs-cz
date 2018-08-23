---
title: 'CA1809: Vyhněte se nadměrným místním hodnotám | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e5dbd1ffc9a427994d923fda695a8dab0c37dda0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670681"
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809: Vyhněte se nadměrným místním hodnotám
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1809: Vyhněte se nadměrným místním hodnotám](https://docs.microsoft.com/visualstudio/code-quality/ca1809-avoid-excessive-locals).  
  
TypeName | AvoidExcessiveLocals |  
| ID kontroly | CA1809 |  
| Kategorie | Microsoft.Performance|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Člen obsahuje více než 64 místních proměnných, z nichž některé mohou být vygenerovaný kompilátorem.  
  
## <a name="rule-description"></a>Popis pravidla  
 Běžnou optimalizací výkonu je uložení hodnoty v registru procesoru místo v paměti, což se označuje jako *enregistering* hodnotu. Modul common language runtime bere v úvahu pro enregistration až 64 místních proměnných. Proměnné, které nejsou uloženy v registrech procesoru jsou vloženy do zásobníku a musí přesunout do registru před manipulaci. Chcete-li možnost povolit, že všechny místní proměnné získat uloženy v registrech procesoru, omezte počet lokálních proměnných na 64.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, Refaktorujte implementace používat více než 64 místních proměnných.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné, můžete potlačit upozornění tohoto pravidla nebo zakážete pravidlo, pokud výkon není problém.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)



