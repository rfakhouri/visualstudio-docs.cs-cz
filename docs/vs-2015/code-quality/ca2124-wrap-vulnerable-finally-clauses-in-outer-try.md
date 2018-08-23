---
title: 'CA2124: Zabalte ohroženou klauzuli finally do vnějšího bloku try | Dokumentace Microsoftu'
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
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c486c4a6469e1c20b48a953f04201f1dba586d04
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628428"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: Zabalte ohroženou klauzuli finally do vnějšího bloku try
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2124: zabalte ohroženou klauzuli finally do vnějšího bloku try](https://docs.microsoft.com/visualstudio/code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try).  
  
TypeName | WrapVulnerableFinallyClausesInOuterTry |  
| ID kontroly | CA2124 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Bez zásadní |  
  
## <a name="cause"></a>příčina  
 Ve verzích 1.0 a 1.1 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], veřejná nebo chráněná metoda obsahuje `try` / `catch` / `finally` bloku. `finally` Bloku nejspíše obnovuje stav zabezpečení a není uzavřen v `finally` bloku.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo vyhledá `try` / `finally` bloky v kódu, který se zaměřuje na verze 1.0 a 1.1 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] , které by mohly být vystaveny filtry škodlivý výjimek, které jsou k dispozici v zásobníku volání. Pokud dojde k citlivé operace, jako jsou zosobnění v bloku try, a je vyvolána výjimka, filtr můžete spustit před `finally` bloku. Například zosobnění to znamená, že filtr by spuštěň zosobněného uživatele. Filtry jsou aktuálně implementable pouze v jazyce Visual Basic.  
  
> [!WARNING]
>  **Poznámka:** ve verzi 2.0 a novější [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], modul runtime automaticky chrání `try` / `catch` /  `finally` znemožní filtry škodlivý výjimek, pokud dojde k obnovení přímo v rámci metody, která obsahuje bloku výjimky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Umístit nezabalené `try` / `finally` do vnějšího bloku try. Viz druhý příklad, který následuje. To přinutí `finally` předtím, než kód filtru.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
  
### <a name="description"></a>Popis  
 Pseudo následující kód znázorňuje, zjistí toto pravidlo.  
  
### <a name="code"></a>Kód  
  
```  
try {  
   // Do some work.  
   Impersonator imp = new Impersonator("John Doe");  
   imp.AddToCreditCardBalance(100);  
}  
finally {  
   // Reset security state.  
   imp.Revert();  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující kód pseudo zobrazuje vzor, můžete použít k ochraně vašeho kódu a splňovat toto pravidlo.  
  
```  
try {  
     try {  
        // Do some work.  
     }  
     finally {  
        // Reset security state.  
     }  
}  
catch()  
{  
    throw;  
}  
```



