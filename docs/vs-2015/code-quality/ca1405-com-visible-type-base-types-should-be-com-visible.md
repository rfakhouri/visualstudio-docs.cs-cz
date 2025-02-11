---
title: 'CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f284c0e6e57a2ca359e765992db3f2d599fec328
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705749"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|DependsOnFix|

## <a name="cause"></a>Příčina
 Viditelného typu modelu COM (Component Object) je odvozen z typu, který není viditelné modelu COM.

## <a name="rule-description"></a>Popis pravidla
 Když viditelného typu modelu COM přidá členy v nové verzi, musí dodržovat přísné pokyny, aby se zabránilo přerušení klientům modelu COM, kteří jsou navázáni na aktuální verzi. Typ, který není viditelný pro model COM předpokládá, že že není nutné postupovat podle těchto pravidel správy verzí modelu COM, když přidá nové členy. Pokud ale viditelné modelu COM typ je odvozen z typu neviditelné COM a zpřístupňuje rozhraní třídy z <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ClassInterfaceType> (výchozí), všechny veřejné členy základního typu (pokud nejsou konkrétně označeny jako COM neviditelné, které by bylo nadbytečné) jsou vystaveny objektům modelu COM. Pokud základní typ přidá nové členy v následné verze, může to způsobit narušení jakékoli klientům modelu COM, kteří jsou navázáni na třídy rozhraní odvozeného typu. Viditelné typy modelu COM by měl odvodit jen z viditelných typech modelu COM, abyste snížili riziko rozbíjející klientům modelu COM.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, skrytí základní typy viditelné modelu COM nebo odvozeného typu modelu COM.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComBaseTypes/cs/FxCop.Interoperability.ComBaseTypes.cs#1)]
 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComBaseTypes/vb/FxCop.Interoperability.ComBaseTypes.vb#1)]

## <a name="see-also"></a>Viz také
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName> [Představení rozhraní třídy](https://msdn.microsoft.com/733c0dd2-12e5-46e6-8de1-39d5b25df024) [spolupráce pomocí nespravovaného kódu](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
