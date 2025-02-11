---
title: 'CA2126: Požadavky na propojení typů vyžadují dědičnost požadavků | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8aee10059e9c50e7f572c6fb784da7b97f323905
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687229"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: Požadavky na propojení typů vyžadují požadavky na dědičnost
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejný nezapečetěný typ je chráněn pomocí požadavku propojení, má přepisovatelnou metodu a typ ani metoda nejsou chráněny pomocí vyžádané dědičnosti.

## <a name="rule-description"></a>Popis pravidla
 Požadavek propojení na metody nebo její deklarující typ vyžaduje okamžitou volajícímu metody zadané oprávnění. Požadavek dědičnosti na metodě vyžaduje metodu přepsání zadané oprávnění. Požadavek dědičnosti na typu vyžaduje odvozená třída má zadané oprávnění.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zabezpečte typu nebo metody pomocí vyžádané dědičnosti pro stejné oprávnění jako požadavek propojení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/cpp/FxCop.Security.TypesWithLinkDemands.cpp#1)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/cs/FxCop.Security.TypesWithLinkDemands.cs#1)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/vb/FxCop.Security.TypesWithLinkDemands.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2108: Revize deklarativních zabezpečení na hodnotách](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122: Nezveřejňujte nepřímo metody s požadavky propojení](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123: Požadavky na přepsání odkazu musejí být identické s bází](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>Viz také
 [Pokyny pro zabezpečené kódování](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) [požadavky na dědičnost](https://msdn.microsoft.com/28b9adbb-8f08-4f10-b856-dbf59eb932d9) [požadavky na propojení](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) [požadavky](https://msdn.microsoft.com/e5283e28-2366-4519-b27d-ef5c1ddc1f48)
