---
title: 'CA2119: Zapečeťte metody, které vyhovují privátním rozhraním | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SealMethodsThatSatisfyPrivateInterfaces
- CA2119
helpviewer_keywords:
- CA2119
- SealMethodsThatSatisfyPrivateInterfaces
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6768bb0100b3bb0052898efc6a57017fca3702b9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754764"
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: Zapečeťte metody, které vyhovují privátním rozhraním
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|
|CheckId|CA2119|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Odvoditelný veřejný typ poskytuje implementaci přepisovatelné metody `internal` (`Friend` v jazyce Visual Basic) rozhraní.

## <a name="rule-description"></a>Popis pravidla
 Metody rozhraní mít přístupnost public, což není možné změnit implementujícího typu. Vnitřní rozhraní vytvoří kontrakt, který není zamýšlena k implementaci mimo sestavení, který definuje rozhraní. Veřejný typ, který implementuje metodu pomocí interní rozhraní `virtual` (`Overridable` v jazyce Visual Basic) umožňuje Modifikátor metody, která se dá přepsat odvozený typ, který se nachází mimo sestavení. Pokud druhý typ v sestavení volá metodu a očekává, že pouze interní smlouvy, chování může být ohrožené, když místo toho se zpracovává přepsané metody v mimo sestavení. Tím se vytvoří ohrožení zabezpečení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zabránit metody přepsání mimo sestavení pomocí jedné z následujících akcí:

-   Ujistěte se, že deklarující typ `sealed` (`NotInheritable` v jazyce Visual Basic).

-   Změňte přístupnost deklarující typ, který má `internal` (`Friend` v jazyce Visual Basic).

-   Odebrání všech veřejných konstruktorů deklarujícího typu.

-   Implementace metody bez použití `virtual` modifikátor.

-   Explicitně implementujte metodu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění z tohoto pravidla, pokud po pečlivou revizi, neexistují žádné problémy se zabezpečením, která může být zneužitelné, pokud je přepsána metoda mimo sestavení.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, `BaseImplementation`, který porušuje tato pravidla.

 [!code-cpp[FxCop.Security.SealMethods1#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.SealMethods1/cpp/FxCop.Security.SealMethods1.cpp#1)]
 [!code-csharp[FxCop.Security.SealMethods1#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.SealMethods1/cs/FxCop.Security.SealMethods1.cs#1)]
 [!code-vb[FxCop.Security.SealMethods1#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.SealMethods1/vb/FxCop.Security.SealMethods1.vb#1)]

## <a name="example"></a>Příklad
 Následující příklad využívá virtuální metoda provádění předchozího příkladu.

 [!code-cpp[FxCop.Security.SealMethods2#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.SealMethods2/cpp/FxCop.Security.SealMethods2.cpp#1)]
 [!code-csharp[FxCop.Security.SealMethods2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.SealMethods2/cs/FxCop.Security.SealMethods2.cs#1)]
 [!code-vb[FxCop.Security.SealMethods2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.SealMethods2/vb/FxCop.Security.SealMethods2.vb#1)]

## <a name="see-also"></a>Viz také
 [Rozhraní](http://msdn.microsoft.com/library/2feda177-ce11-432d-81b4-d50f5f35fd37) [rozhraní](http://msdn.microsoft.com/library/61b06674-12c9-430b-be68-cc67ecee1f5b)
