---
title: "CA1039: Seznamy jsou silného typu. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1039
- ListsAreStronglyTyped
helpviewer_keywords:
- CA1039
- ListsAreStronglyTyped
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 358ae06a2913f7b89338027c79f81c298253d23b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1039-lists-are-strongly-typed"></a>CA1039: Seznamy jsou silného typu
|||  
|-|-|  
|TypeName|ListsAreStronglyTyped|  
|CheckId|CA1039|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Veřejné nebo chráněného typu implementuje <xref:System.Collections.IList?displayProperty=fullName> , ale neposkytuje silného typu metodu pro jednu nebo více následujících akcí:  
  
-   IList.Item  
  
-   IList.Add  
  
-   IList.Contains  
  
-   IList.IndexOf  
  
-   IList.Insert  
  
-   IList.Remove  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo vyžaduje <xref:System.Collections.IList> implementace zajistit silně typované členy tak, aby uživatelé nemusí přetypovat argumenty, které mají <xref:System.Object?displayProperty=fullName> zadejte při použití funkce, která je k dispozici rozhraní. <xref:System.Collections.IList> Rozhraní je implementováno modulem kolekce objektů, kterým lze přistupovat pomocí indexu. Toto pravidlo se předpokládá, že typ, který implementuje <xref:System.Collections.IList> tomu spravovat kolekci instancí typu, který je vyšší než <xref:System.Object>.  
  
 <xref:System.Collections.IList>implementuje <xref:System.Collections.ICollection?displayProperty=fullName> a <xref:System.Collections.IEnumerable?displayProperty=fullName> rozhraní. Pokud implementujete <xref:System.Collections.IList>, je nutné zadat požadované členy silného typu pro <xref:System.Collections.ICollection>. Pokud objekty v kolekci rozšířit <xref:System.ValueType?displayProperty=fullName>, je nutné zadat člena silného typu pro <xref:System.Collections.IEnumerable.GetEnumerator%2A> aby se zabránilo snížení výkonu je příčinou zabalení; to není potřeba po objekty kolekce odkazového typu.  
  
 Abyste dosáhli souladu s tímto pravidlem, implementace členů rozhraní explicitně pomocí názvů v podobě InterfaceName.InterfaceMemberName, jako například <xref:System.Collections.IList.Add%2A>. Členové explicitního rozhraní používat typy dat, které jsou deklarovány rozhraní. Implementace silného typu členů pomocí název člena rozhraní, jako například `Add`. Deklarovat silného typu členy jako veřejné a deklarovat parametry a návratové hodnoty být silného typu, který je spravován pomocí kolekce. Silné typy nahradit slabší typy, jako <xref:System.Object> a <xref:System.Array> , které jsou deklarovány jako rozhraní.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, explicitní implementace <xref:System.Collections.IList> členy a zadejte silného typu alternativy pro členy, které jste si poznamenali dříve. Pro kód, který implementuje správně <xref:System.Collections.IList> rozhraní a obsahuje požadované členy silného typu, najdete v následujícím příkladu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo při implementaci nového objektu kolekci, například odkazovaného seznamu, kde typy, které rozšiřují novou kolekci určit silného typu. Tyto typy by měl splňovat toto pravidlo a vystavit členy silného typu.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu, typ `YourType` rozšiřuje <xref:System.Collections.CollectionBase?displayProperty=fullName>, jako by všechny silného typu kolekce. Všimněte si, že <xref:System.Collections.CollectionBase> poskytuje explicitní implementace <xref:System.Collections.IList> rozhraní pro vás. Proto je nutné pouze zadat členy silného typu pro <xref:System.Collections.IList> a <xref:System.Collections.ICollection>.  
  
 [!code-csharp[FxCop.Design.IListStrongTypes#1](../code-quality/codesnippet/CSharp/ca1039-lists-are-strongly-typed_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1035: Implementace ICollection mají členy silného typu](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)  
  
 [CA1038: Enumerátory by měly být silného typu](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Collections.CollectionBase?displayProperty=fullName>   
 <xref:System.Collections.ICollection?displayProperty=fullName>   
 <xref:System.Collections.IEnumerable?displayProperty=fullName>   
 <xref:System.Collections.IList?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>