---
title: 'CA2227: Vlastnosti kolekce by měla být jen pro čtení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0884b2fc15a08584052fb69dca9980964b2fd374
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Vlastnosti kolekce by měly být pouze pro čtení
|||  
|-|-|  
|TypeName|CollectionPropertiesShouldBeReadOnly|  
|CheckId|CA2227|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Externě viditelné zapisovatelnou vlastnost je typ, který implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Pole, indexery (vlastnosti s názvem 'Item') a sady oprávnění jsou ignorovány pravidlem.  
  
## <a name="rule-description"></a>Popis pravidla  
 Vlastnost zapisovatelné kolekce umožňuje uživateli kolekce nahradit úplně jinou kolekci. Vlastnost jen pro čtení neumožňuje kolekci nahradit, ale stále umožňuje nastavit jednotlivé členy. Pokud nahrazení kolekce je cílem, vzor upřednostňovanou je způsob odebrání všechny elementy z kolekce a způsob, jak znovu naplňte kolekce. Najdete v článku <xref:System.Collections.ArrayList.Clear%2A> a <xref:System.Collections.ArrayList.AddRange%2A> metody <xref:System.Collections.ArrayList?displayProperty=fullName> třída příklad tohoto vzoru.  
  
 Binární i serializace XML podporují jen pro čtení vlastnosti, které jsou kolekce. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Třída má specifické požadavky pro typy, které implementují <xref:System.Collections.ICollection> a <xref:System.Collections.IEnumerable?displayProperty=fullName> Chcete-li být serializovatelný.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, nastavte vlastnost jen pro čtení a pokud to vyžaduje návrh, přidejte metody zrušte a znovu naplňte kolekce.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ s možností zápisu kolekce vlastností a jak kolekci lze nahradit přímo. Kromě toho upřednostňovaný způsob nahrazení pomocí vlastnosti jen pro čtení kolekce `Clear` a `AddRange` metody se zobrazí.  
  
 [!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1819: Vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md)