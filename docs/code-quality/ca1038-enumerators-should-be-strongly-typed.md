---
title: "CA1038: Enumerátory by měly být silného typu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 84ddea0bebd5c3811da84abadd207b839ec8be48
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038: Enumerátory by měly být silného typu
|||  
|-|-|  
|TypeName|EnumeratorsShouldBeStronglyTyped|  
|CheckId|CA1038|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Implementuje typu veřejný nebo chráněného <xref:System.Collections.IEnumerator?displayProperty=fullName> neposkytuje verzi silného typu, ale <xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName> vlastnost. Vyloučí z tohoto pravidla jsou typy, které jsou odvozené z následujících typů:  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo vyžaduje <xref:System.Collections.IEnumerator> implementace také zadejte verzi silného typu <xref:System.Collections.IEnumerator.Current%2A> vlastnost tak, aby uživatelé nemusí při použití funkce, která je k dispozici rozhraní přetypovat návratovou hodnotu silného typu. Toto pravidlo se předpokládá, že typ, který implementuje <xref:System.Collections.IEnumerator> obsahuje kolekci instancí typu, který je vyšší než <xref:System.Object>.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, implementovat rozhraní vlastnost explicitně (deklarujte ji jako `IEnumerator.Current`). Přidejte veřejnou verzi silného typu vlastnost deklarován jako `Current`, a mějte ho vrátí objekt silného typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo při implementaci enumerátor na základě objektů pro použití s kolekci na základě objektů jako binárního stromu. Typy, které rozšiřují nová kolekce bude definovat silného typu enumerátor a vystavit vlastnost silného typu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje správný způsob implementace silného typu <xref:System.Collections.IEnumerator> typu.  
  
 [!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1035: Implementace ICollection mají členy silného typu](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)  
  
 [CA1039: Seznamy jsou silného typu](../code-quality/ca1039-lists-are-strongly-typed.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Collections.IEnumerator?displayProperty=fullName>   
 <xref:System.Collections.CollectionBase?displayProperty=fullName>   
 <xref:System.Collections.DictionaryBase?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>