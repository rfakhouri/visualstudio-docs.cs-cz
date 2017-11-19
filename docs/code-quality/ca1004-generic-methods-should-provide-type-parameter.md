---
title: "CA1004: Obecné metody by měly poskytnout parametr typu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 01e795c4505b71f337212f85c3946f8800fbc05d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004: Obecné metody by měly poskytnout parametr typu
|||  
|-|-|  
|TypeName|GenericMethodsShouldProvideTypeParameter|  
|CheckId|CA1004|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Parametr podpis externě viditelné obecná metoda neobsahuje typy, které odpovídají k parametrům typ metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Argument typu obecné metody je z argumentu typu předávaného metodě odvozen namísto explicitního určení argumentu typu. Má-li být odvozování povoleno, musí předpis parametrů obecné metody zahrnovat parametr stejného typu jako parametr typu metody. V tomto případě nemusí být argument typu zadán. Pokud používáte odvození pro všechny parametry typu, je stejný jako syntaxi pro volání metod obecné a neobecné instance. Tato funkce zjednodušuje použitelnost obecné metody.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, změňte návrh tak, aby parametr podpis obsahuje stejného typu pro každý typ parametru metody.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Poskytuje obecné typy v syntaxi, který se snadno pochopit a používat zkracuje čas, který je potřeba další a zvyšuje počet přijetí nové knihovny.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje syntaxi pro volání dvě obecné metody. Argument typu pro `InferredTypeArgument` je odvodit a typ argumentu pro `NotInferredTypeArgument` musí být explicitně určena.  
  
 [!code-vb[FxCop.Design.Inference#1](../code-quality/codesnippet/VisualBasic/ca1004-generic-methods-should-provide-type-parameter_1.vb)]
 [!code-csharp[FxCop.Design.Inference#1](../code-quality/codesnippet/CSharp/ca1004-generic-methods-should-provide-type-parameter_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Nezveřejňují obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1003: Použijte obecné události instance obslužné rutiny](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Viz také  
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)