---
title: "CA1711: Identifikátory by neměly mít nesprávnou příponu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1e0701c93146b4cc460a7216d2f4159832389db6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: Identifikátory by neměly mít nesprávnou příponu
|||  
|-|-|  
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|  
|CheckId|CA1711|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Identifikátor nemá správnou příponu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pouze názvy typů, které rozšiřují určité základní typy nebo které implementují určitá rozhraní, nebo typů odvozených z těchto typů by podle konvence měly končit určitými vyhrazenými příponami. Jiné názvy typů by neměly používat tyto vyhrazené přípony.  
  
 Následující tabulka uvádí vyhrazené přípony a základní typy a rozhraní, ke kterým jsou přidruženy.  
  
|Přípona|Základní typ nebo rozhraní|  
|------------|--------------------------|  
|Atribut|<xref:System.Attribute?displayProperty=fullName>|  
|kolekce|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|  
|Slovník|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|  
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|  
|Obslužná rutina události|Delegát obslužné rutiny události|  
|Výjimka|<xref:System.Exception?displayProperty=fullName>|  
|Oprávnění|<xref:System.Security.IPermission?displayProperty=fullName>|  
|Fronta|<xref:System.Collections.Queue?displayProperty=fullName>|  
|Rámec|<xref:System.Collections.Stack?displayProperty=fullName>|  
|Stream|<xref:System.IO.Stream?displayProperty=fullName>|  
  
 Kromě toho by měla následující přípony **není** použít:  
  
-   Delegát  
  
-   Výčet  
  
-   Impl – místo toho použijte „Core“  
  
-   Ex nebo podobná přípona k odlišení starší verze stejného typu  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odeberte příponu z názvu typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla, pokud přípona nemá v doméně aplikace jednoznačný význam.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1710: Identifikátory by měly mít správnou příponu](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)  
  
## <a name="see-also"></a>Viz také  
 [Atributy](/dotnet/standard/design-guidelines/attributes)   
 [Zpracování a generování událostí](/dotnet/standard/events/index)  