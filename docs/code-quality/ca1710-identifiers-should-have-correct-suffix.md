---
title: 'CA1710: Identifikátory by měly mít správnou příponu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae9af2a4178dd06d9f849adeb1dc42c1c0bffe08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: Identifikátory by měly mít správnou příponu
|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectSuffix|  
|CheckId|CA1710|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Identifikátor nemá správné přípony.  
  
## <a name="rule-description"></a>Popis pravidla  
 Podle konvence, názvy typů, které rozšířit určité základní typy nebo které implementují určité rozhraní, nebo takové typy odvozené od těchto typů máte příponu, která je přidružena k základní typ nebo rozhraní.  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
 Následující tabulka uvádí základní typy a rozhraní, které mají přidružené přípony.  
  
|Základní typ nebo rozhraní|Přípona|  
|--------------------------|------------|  
|<xref:System.Attribute?displayProperty=fullName>|Atribut|  
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|  
|<xref:System.Exception?displayProperty=fullName>|Výjimka|  
|<xref:System.Collections.ICollection?displayProperty=fullName>|kolekce|  
|<xref:System.Collections.IDictionary?displayProperty=fullName>|Slovník|  
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|kolekce|  
|<xref:System.Collections.Queue?displayProperty=fullName>|Kolekce nebo fronty|  
|<xref:System.Collections.Stack?displayProperty=fullName>|Kolekce nebo zásobníku|  
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|kolekce|  
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|Slovník|  
|<xref:System.Data.DataSet?displayProperty=fullName>|DataSet|  
|<xref:System.Data.DataTable?displayProperty=fullName>|Kolekce nebo DataTable|  
|<xref:System.IO.Stream?displayProperty=fullName>|Stream|  
|<xref:System.Security.IPermission?displayProperty=fullName>|Oprávnění|  
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|Podmínka|  
|Delegáta obslužných rutin událostí.|Obslužná rutina události|  
  
 Typy, které implementují <xref:System.Collections.ICollection> a jsou zobecněný typ struktura dat, jako je slovník, zásobník nebo fronty, jsou povolené názvy, které poskytují důležité informace o zamýšlené použití typu.  
  
 Typy, které implementují <xref:System.Collections.ICollection> a jsou kolekce položek konkrétní mít názvy, které končí slovo 'Kolekce'. Například kolekce <xref:System.Collections.Queue> objekty by mít název 'QueueCollection'. Přípona 'Kolekce' znamená, že neexistuje, můžete vytvořit výčet členů kolekce pomocí `foreach` (`For Each` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) příkaz.  
  
 Typy, které implementují <xref:System.Collections.IDictionary> mít názvy, které končí slovo 'slovník, i v případě, že typ také implementuje <xref:System.Collections.IEnumerable> nebo <xref:System.Collections.ICollection>. 'Kolekce' a 'Slovníku' přípon názvů umožnit uživatelům k rozlišení mezi následující dvě výčtu vzory.  
  
 Typy s příponou, kolekce, postupujte podle tohoto vzoru výčtu.  
  
```  
foreach(SomeType x in SomeCollection) { }  
```  
  
 Typy s příponou "slovník, postupujte podle tohoto vzoru výčtu.  
  
```  
foreach(SomeType x in SomeDictionary.Values) { }  
```  
  
 A <xref:System.Data.DataSet> objekt se skládá z kolekce <xref:System.Data.DataTable> objekty, které se skládají z kolekce <xref:System.Data.DataColumn?displayProperty=fullName> a <xref:System.Data.DataRow?displayProperty=fullName> objekty, mimo jiné. Tyto kolekce implementovat <xref:System.Collections.ICollection> prostřednictvím základní <xref:System.Data.InternalDataCollectionBase?displayProperty=fullName> třídy.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Přejmenujte typ tak, aby konci správný výraz.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné pro potlačení upozornění používat příponu, kolekce, pokud je typ zobecněný datová struktura, může dojít ke zpoždění nebo která bude obsahovat libovolnou sadu různé položky. Název, který poskytuje důležité informace o implementaci, výkonem a dalšími charakteristikami datovou strukturu v takovém případě může být vhodné (například BinaryTree). V případech, kde typ reprezentuje kolekci určitého typu (například třída StringCollection), není potlačit upozornění od tohoto pravidla vzhledem k tomu, že přípona označuje, že typ mohou být uvedené pomocí `foreach` příkaz.  
  
 Pro jiné přípony není potlačení upozornění od tohoto pravidla. Přípona umožňuje zamýšlené použití být zřejmé z název typu.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1711: Identifikátory by neměly mít nesprávnou příponu](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
## <a name="see-also"></a>Viz také  
 [Atributy](/dotnet/standard/design-guidelines/attributes)   
 [Zpracování a generování událostí](/dotnet/standard/events/index)  