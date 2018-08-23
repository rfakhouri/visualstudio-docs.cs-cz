---
title: 'CA2106: Zabezpečte nepodmíněné výrazy | Dokumentace Microsoftu'
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
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5420fa40673eed9f4e8ff4ce9e1b59a5af7d96b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686727"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Zabezpečte nepodmíněné výrazy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2106: Zabezpečte nepodmíněné výrazy](https://docs.microsoft.com/visualstudio/code-quality/ca2106-secure-asserts).  
  
TypeName | SecureAsserts |  
| ID kontroly | CA2106 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Metoda uplatňuje oprávnění a na volajícím nejsou vykonány žádné kontroly zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Uplatnění oprávnění zabezpečení bez provedení jakékoliv kontroly zabezpečení může zanechat ve vašem kódu zneužitelné slabé stránky zabezpečení. Procházení zásobníku zabezpečení zastaví, když je uplatněna oprávnění zabezpečení. Pokud uplatňujete oprávnění bez provedení jakékoli kontroly volajícího, volající mohl nepřímo spustit kód pomocí oprávnění. Nepodmíněné výrazy bez kontroly zabezpečení jsou přípustné, pouze pokud jste si jisti, že kontrolní výraz nelze použít škodlivých způsobem. Assert je neškodný, pokud kód, který voláte je neškodný, nebo uživatelé nemůžou projít libovolné informace pro kód, který voláte.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přidejte do metody nebo její deklarující typ požadavku zabezpečení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačit upozornění tohoto pravidla až po přezkoumání pečlivé ověření zabezpečení.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 [Pokyny pro zabezpečené kódování](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)



