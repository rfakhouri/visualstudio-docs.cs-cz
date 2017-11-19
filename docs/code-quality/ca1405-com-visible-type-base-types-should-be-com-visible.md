---
title: "CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 91634d5d46d63165874deded9c5ac67e7d4afa07
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM
|||  
|-|-|  
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|  
|CheckId|CA1405|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|DependsOnFix|  
  
## <a name="cause"></a>příčina  
 Viditelného typu modelu COM (Component Object) je odvozen od typu, který není viditelné modelu COM.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud viditelného typu modelu COM přidá členy v nové verzi, musíte dodržet striktní pokyny, abyste předešli porušení klientů modelu COM, které vazby na aktuální verzi. Typ, který je pro COM skrytá předpokládá, že nemá postupujte podle těchto pravidel verze modelu COM, když přidá nové členy. Ale pokud viditelné modelu COM typ je odvozen od typu neviditelná COM a zveřejňuje třídy rozhraní <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ClassInterfaceType> (výchozí), všechny veřejné členy základní typ (pokud nejsou konkrétně označeny jako COM neviditelná, které by bylo nadbytečné) jsou viditelné na modelu COM. Základní typ přidá nové členy v další verzi, může porušit všechny COM klienty, kteří vytvořit vazbu na rozhraní třída odvozeného typu. Viditelné typy modelu COM by měl být odvozen pouze z viditelné typy modelu COM, abyste snížili riziko nejnovější klienti COM.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, nastavit základní typy viditelné modelu COM nebo odvozený typ modelu COM neviditelná.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo.  
  
 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>   
 [Představení rozhraní – třída](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)