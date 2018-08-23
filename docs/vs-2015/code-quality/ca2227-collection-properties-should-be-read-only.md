---
title: 'CA2227: Vlastnosti kolekce by měly být jen pro čtení | Dokumentace Microsoftu'
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
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 95085c8b79e49d38bc55aea65b4f9867ce6dfb2a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633799"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Vlastnosti kolekce by měly být pouze pro čtení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2227: vlastnosti kolekce by měly být jen pro čtení](https://docs.microsoft.com/visualstudio/code-quality/ca2227-collection-properties-should-be-read-only).  
  
TypeName | CollectionPropertiesShouldBeReadOnly |  
| ID kontroly | CA2227 |  
| Kategorie | Microsoft.Usage|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Externě viditelný zapisovatelnou vlastnost je typ, který implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Pole, indexery (vlastnosti s názvem "Položka") a sady oprávnění se ignorují pravidlem.  
  
## <a name="rule-description"></a>Popis pravidla  
 Zapisovatelná vlastnost kolekce umožňuje uživateli nahradit kolekci zcela jinou kolekci. Vlastnost jen pro čtení neumožňuje kolekci nahradit, ale stále umožňuje nastavit jednotlivé členy. Pokud nahrazující kolekce je cíl, vzor upřednostňovaný návrh je metoda odebrání všechny elementy z kolekce a způsob, jak znovu naplňte kolekce. Najdete v článku <xref:System.Collections.ArrayList.Clear%2A> a <xref:System.Collections.ArrayList.AddRange%2A> metody <xref:System.Collections.ArrayList?displayProperty=fullName> třídy příklad tohoto modelu.  
  
 Binární soubor a serializace XML podporují jen pro čtení vlastnosti, které jsou kolekce. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Třída má specifické požadavky na typy, které implementují <xref:System.Collections.ICollection> a <xref:System.Collections.IEnumerable?displayProperty=fullName> -li být serializovatelný.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, nastavte vlastnost jen pro čtení a pokud to vyžaduje návrh, přidejte metody, zrušte a znovu naplňte kolekce.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ s zapisovatelná vlastnost kolekce a jak kolekce se dá nahradit přímo. Kromě toho upřednostňovaný způsob nahrazení vlastnost kolekce jenom pro čtení pomocí `Clear` a `AddRange` metody se zobrazí.  
  
 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cpp/FxCop.Usage.PropertiesReturningCollections.cpp#1)]
 [!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cs/FxCop.Usage.PropertiesReturningCollections.cs#1)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/vb/FxCop.Usage.PropertiesReturningCollections.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1819: Vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md)



