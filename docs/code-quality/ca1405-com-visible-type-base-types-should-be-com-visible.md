---
title: 'CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM'
ms.date: 11/04/2016
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
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 56e6e7a53f5f8b07d1afc8b68ef641c576524316
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922054"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|Kategorie|Microsoft. interoperabilita|
|Narušující změna|DependsOnFix|

## <a name="cause"></a>příčina
Viditelný typ objektu součásti modelu COM je odvozen z typu, který není viditelný v modelu COM.

## <a name="rule-description"></a>Popis pravidla
Pokud viditelný typ modelu COM přidá členy v nové verzi, musí dodržovat přísné pokyny, aby nedošlo k narušení klientů modelu COM, které se váže k aktuální verzi. Typ, který není viditelný v modelu COM, se předpokládá, že při přidávání nových členů není nutné dodržovat pravidla správy verzí modelu COM. Pokud je však viditelný typ modelu COM odvozen z neviditelného typu modelu COM a zpřístupňuje rozhraní <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> třídy nebo <xref:System.Runtime.InteropServices.ClassInterfaceType> (výchozí), všechny veřejné členy základního typu (pokud nejsou výslovně označeny jako com neviditelné, což by bylo redundantní). jsou vystavené pro COM. Pokud základní typ přidá nové členy v následné verzi, může dojít k přerušení všech klientů modelu COM, které jsou vázány na rozhraní třídy odvozeného typu. Viditelné typy modelu COM by měly odvozovat pouze z viditelných typů modelu COM, aby se snížila pravděpodobnost poškození klientů modelu COM.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, zajistěte, aby základní typy modelu COM byly viditelné nebo aby byl odvozený typ COM neviditelný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, který je v rozporu s pravidlem.

[!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
[!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>
- [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)