---
title: "CA1003: Použijte instance obslužné rutiny události obecné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cf4f11f3f8fae1130c2cc99468a40ed269c77481
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: Použijte instance obecných obslužných rutin události
|||  
|-|-|  
|TypeName|UseGenericEventHandlerInstances|  
|CheckId|CA1003|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ obsahuje delegáta, který vrátí prázdnou hodnotu, jejíž podpis obsahuje dva parametry (první příslušný objekt a druhá a typ, který je přiřadit k EventArgs) a obsahující sestavení cílů [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].  
  
## <a name="rule-description"></a>Popis pravidla  
 Před [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], aby bylo možné předat vlastních informací do obslužné rutiny události museli nového delegáta deklarovat, zadat třídu, která odvozený z <xref:System.EventArgs?displayProperty=fullName> třídy. To platí už v [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], který zavedl <xref:System.EventHandler%601?displayProperty=fullName> delegovat. Tento obecný delegát umožňuje všechny třídy, která je odvozena z <xref:System.EventArgs> má být použit spolu s obslužné rutiny události.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte delegáta a nahraďte jeho použití pomocí <xref:System.EventHandler%601?displayProperty=fullName> delegovat. Pokud delegát je generován automaticky pomocí [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kompilátoru, změnit syntaxe deklarace události používat <xref:System.EventHandler%601?displayProperty=fullName> delegovat.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje delegáta, který porušuje pravidlo. V [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] například komentáře popisují, jak upravit třeba splňovat pravidla. C# například následuje příklad zobrazující změny kódu.  
  
 [!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
 [!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad odebere předchozí příklad, který splňuje pravidlo a nahradí jeho použití v deklaraci delegáta `ClassThatRaisesEvent` a `ClassThatHandlesEvent` metody pomocí <xref:System.EventHandler%601?displayProperty=fullName> delegovat.  
  
 [!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Nezveřejňují obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Viz také  
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)