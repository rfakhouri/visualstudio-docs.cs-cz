---
title: 'CA2126: Požadavky propojení typů vyžadují dědičnost požadavků | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4194c216af3ca158d62f040113473c1d64055d49
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: Požadavky propojení typů vyžadují dědičnost požadavků
|||  
|-|-|  
|TypeName|TypeLinkDemandsRequireInheritanceDemands|  
|CheckId|CA2126|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Veřejné nezapečetěných typ je chráněný pomocí požadavků na propojení má metodu přepisovatelné a typ ani metodu chráněné pomocí požadavek dědičnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Požadavek propojení na metodu nebo jeho deklarující typ vyžaduje bezprostředního volajícího metody tak, aby měl zadaný oprávnění. Požadavek dědičnosti na metodu vyžaduje metodu přepsání zadané oprávnění k. Požadavek dědičnosti pro typ vyžaduje odvozující třídě tak, aby měl zadaný oprávnění.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, zabezpečte typ nebo metoda s požadavek dědičnosti pro stejné oprávnění jako požadavek propojení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo.  
  
 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2108: Revize deklarativních zabezpečení na hodnotách](../code-quality/ca2108-review-declarative-security-on-value-types.md)  
  
 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA2122: Nezveřejňujte nepřímo metody s požadavky propojení](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)  
  
 [CA2123: Požadavky na přepsání odkazu musejí být identické s bází](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)   
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)   
