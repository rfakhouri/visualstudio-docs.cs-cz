---
title: "CA2106: Zabezpečte vyhodnotí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 321d00f13ebc891070549778239fec60201d03c4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2106-secure-asserts"></a>CA2106: Zabezpečte nepodmíněné výrazy
|||  
|-|-|  
|TypeName|SecureAsserts|  
|CheckId|CA2106|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda uplatňuje oprávnění a na volajícím nejsou vykonány žádné kontroly zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Uplatnění oprávnění zabezpečení bez provedení jakékoliv kontroly zabezpečení může zanechat ve vašem kódu zneužitelné slabé stránky zabezpečení. Procházení zásobníku zabezpečení zastaví, když je uplatněna oprávnění zabezpečení. Pokud uplatňujete oprávnění bez provedení jakýchkoli kontrol na volajícího, může volající nepřímo spouštění kódu pomocí oprávnění. Vyhodnotí bez kontroly zabezpečení jsou přípustné pouze pokud jste si jisti, že assert nelze použít škodlivé způsobem. Assert je neškodné, pokud je kód, který zavoláte neškodné nebo uživatelé nemůžou projít libovolné informace do kódu, které můžete volat.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přidejte metodu nebo jeho deklarující typ požadavek zabezpečení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo až po kontrolu pečlivě zabezpečení.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)