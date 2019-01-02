---
title: 'CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c0221231956c565eb2ce3792d0c88864b0e13e65
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53839320"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|DependsOnFix|

## <a name="cause"></a>příčina
 Viditelného typu modelu COM (Component Object) je odvozen z typu, který není viditelné modelu COM.

## <a name="rule-description"></a>Popis pravidla
 Když viditelného typu modelu COM přidá členy v nové verzi, musí dodržovat přísné pokyny, aby se zabránilo přerušení klientům modelu COM, kteří jsou navázáni na aktuální verzi. Typ, který není viditelný pro model COM předpokládá, že že není nutné postupovat podle těchto pravidel správy verzí modelu COM, když přidá nové členy. Pokud ale viditelné modelu COM typ je odvozen z typu neviditelné COM a zpřístupňuje rozhraní třídy z <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ClassInterfaceType> (výchozí), všechny veřejné členy základního typu (pokud nejsou konkrétně označeny jako COM neviditelné, které by bylo nadbytečné) jsou vystaveny objektům modelu COM. Pokud základní typ přidá nové členy v následné verze, může to způsobit narušení jakékoli klientům modelu COM, kteří jsou navázáni na třídy rozhraní odvozeného typu. Viditelné typy modelu COM by měl odvodit jen z viditelných typech modelu COM, abyste snížili riziko rozbíjející klientům modelu COM.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, skrytí základní typy viditelné modelu COM nebo odvozeného typu modelu COM.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>
- [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)