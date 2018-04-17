---
title: 'CA1052: Statický vlastník typů by měl zapečetěná. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6fc3954c4c446ff578790e92bc60dd97e42a0d8c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: Statický vlastník typů by měl být zapečetěný
|||  
|-|-|  
|TypeName|StaticHolderTypesShouldBeSealed|  
|CheckId|CA1052|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ veřejné nebo chráněného obsahuje pouze statické členy a není deklarovaný s [zapečetěné](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) modifikátor.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo se předpokládá, že typ, který obsahuje pouze statické členy není určená k tomu zděděná, protože typ nenabízí žádné funkce, které mohou být přepsána nastaveními v odvozeném typu. Typ, který by neměl být zděděná by měl být označen s `sealed` modifikátor zakázat jeho použití jako základní typ.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, označit jako typ `sealed`. Pokud cílíte [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 nebo novější, je vhodnější je označit jako typ `static`. Tímto způsobem můžete vyhnout se nutnosti soukromý konstruktor zabránit vytváří třídu deklarovat.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo pouze v případě, že typ slouží k zděděná. Neexistence `sealed` modifikátor naznačuje, že je užitečné jako základní typ typu.  
  
## <a name="example-of-a-violation"></a>Příkladem porušení  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje typ, který porušuje pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
 [!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
 [!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]  
  
## <a name="fix-with-the-static-modifier"></a>Oprava se statický modifikátor  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje, jak opravit porušení toto pravidlo na typ s označením `static` modifikátor.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1053: Statický vlastník typů by neměl mít konstruktory](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)
