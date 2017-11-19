---
title: "CA1035: Implementace ICollection mají členy silného typu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6be0c08efcd1f409bfb69775822e4904372f2511
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035: Implementace ICollection mají členy silného typu
|||  
|-|-|  
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|  
|CheckId|CA1035|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Implementuje typu veřejný nebo chráněného <xref:System.Collections.ICollection?displayProperty=fullName> , ale neposkytuje silného typu metodu pro <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName>. Verzi silného typu <xref:System.Collections.ICollection.CopyTo%2A> musí přijmout dva parametry a nemůže mít <xref:System.Array?displayProperty=fullName> nebo pole <xref:System.Object?displayProperty=fullName> jako svůj první parametr.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo vyžaduje <xref:System.Collections.ICollection> implementace zajistit silně typované členy tak, aby uživatelé nemusí přetypovat argumenty, které mají <xref:System.Object> zadejte při použití funkce, která je k dispozici rozhraní. Toto pravidlo se předpokládá, že typ, který implementuje <xref:System.Collections.ICollection> nepodporuje, takže ke správě kolekci instancí typu, který je vyšší než <xref:System.Object>.  
  
 <xref:System.Collections.ICollection>implementuje <xref:System.Collections.IEnumerable?displayProperty=fullName> rozhraní. Pokud objekty v kolekci rozšířit <xref:System.ValueType?displayProperty=fullName>, je nutné zadat člena silného typu pro <xref:System.Collections.IEnumerable.GetEnumerator%2A> aby se zabránilo snížení výkonu, která je způsobena zabalení. To není potřeba při objekty kolekce jsou odkazového typu.  
  
 K implementaci verzi silného typu člena rozhraní, implementace členů rozhraní explicitně pomocí názvů ve formě `InterfaceName.InterfaceMemberName`, jako například <xref:System.Collections.ICollection.CopyTo%2A>. Členové explicitního rozhraní používat typy dat, které jsou deklarovány rozhraní. Implementace silného typu členů pomocí název člena rozhraní, jako například <xref:System.Collections.ICollection.CopyTo%2A>. Deklarovat silného typu členy jako veřejné a deklarovat parametry a návratové hodnoty být silného typu, který je spravován pomocí kolekce. Silné typy nahradit slabší typy, jako <xref:System.Object> a <xref:System.Array> , které jsou deklarovány jako rozhraní.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, implementace členů rozhraní explicitně (deklarujte ji jako <xref:System.Collections.ICollection.CopyTo%2A>). Přidání veřejné silného typu člena deklarován jako `CopyTo`, a mějte ho trvat silného typu pole jako svůj první parametr.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo, je-li implementovat nový objekt kolekci, například binárního stromu, kde typy, které rozšiřují novou kolekci určit silného typu. Tyto typy by měl splňovat toto pravidlo a vystavit členy silného typu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje správný způsob implementace <xref:System.Collections.ICollection>.  
  
 [!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../code-quality/codesnippet/CSharp/ca1035-icollection-implementations-have-strongly-typed-members_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1038: Enumerátory by měly být silného typu](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)  
  
 [CA1039: Seznamy jsou silného typu.](../code-quality/ca1039-lists-are-strongly-typed.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Array?displayProperty=fullName>   
 <xref:System.Collections.IEnumerable?displayProperty=fullName>   
 <xref:System.Collections.ICollection?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>