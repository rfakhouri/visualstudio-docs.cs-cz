---
title: 'CA2126: Požadavky propojení typů vyžadují dědičnost požadavků'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
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
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 834f120994070e055fe5ac417d1fb39830c7bcef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53904137"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: Požadavky propojení typů vyžadují dědičnost požadavků

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nezapečetěný typ je chráněn pomocí požadavku propojení, má přepisovatelnou metodu a typ ani metoda nejsou chráněny pomocí vyžádané dědičnosti.

## <a name="rule-description"></a>Popis pravidla
 Požadavek propojení na metody nebo její deklarující typ vyžaduje okamžitou volajícímu metody zadané oprávnění. Požadavek dědičnosti na metodě vyžaduje metodu přepsání zadané oprávnění. Požadavek dědičnosti na typu vyžaduje odvozená třída má zadané oprávnění.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zabezpečte typu nebo metody pomocí vyžádané dědičnosti pro stejné oprávnění jako požadavek propojení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2108: Revize deklarativních zabezpečení na hodnotách](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122: Nezveřejňujte nepřímo metody s požadavky propojení](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123: Požadavky na přepsání odkazu musejí být identické s bází](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Požadavky propojení](/dotnet/framework/misc/link-demands)