---
title: 'CA2119: Zapečeťte metody, které vyhovují privátním rozhraním | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- SealMethodsThatSatisfyPrivateInterfaces
- CA2119
helpviewer_keywords:
- CA2119
- SealMethodsThatSatisfyPrivateInterfaces
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f54b6c58e30145759881a8a612ad6f7edfd044d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: Zapečeťte metody, které vyhovují privátním rozhraním
|||  
|-|-|  
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|  
|CheckId|CA2119|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Zděditelné veřejného typu poskytuje implementace přepisovatelné metody `internal` (`Friend` v jazyce Visual Basic) rozhraní.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metody rozhraní mají veřejnou dostupnost, který nelze změnit pomocí příkazu implementujícího typu. Vnitřní rozhraní vytvoří kontrakt, který není určeno k implementaci mimo sestavení, které definuje rozhraní. Veřejné typ, který implementuje metoda k interním rozhraní pomocí `virtual` (`Overridable` v jazyce Visual Basic) modifikátor umožňuje metodu k přepsání odvozeným typem, který je mimo sestavení. Pokud druhého typu v sestavení definující volá metodu a očekává jen vnitřní kontrakt, může být narušena chování při, místo toho metodu přepsaného v mimo sestavení. Tím se vytvoří ohrožení zabezpečení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, zabránit metodu přepsání mimo sestavení pomocí jedné z následujících akcí:  
  
-   Ujistěte se, deklarující typ `sealed` (`NotInheritable` v jazyce Visual Basic).  
  
-   Změnit usnadnění deklarující typ má `internal` (`Friend` v jazyce Visual Basic).  
  
-   Odebrání deklarující typ všechny veřejné konstruktory.  
  
-   Implementovat metodu bez použití `virtual` modifikátor.  
  
-   Implementujte metodu explicitně.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění z tohoto pravidla, pokud po pečlivě zkontrolujte žádné problémy se zabezpečením neexistuje, který může být využitelných, pokud je metoda potlačena mimo sestavení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typu, `BaseImplementation`, která porušuje toto pravidlo.  
  
 [!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
 [!code-csharp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
 [!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]  
  
## <a name="example"></a>Příklad  
 Následující příklad zneužije virtuální metoda implementace předchozí příklad.  
  
 [!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
 [!code-csharp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
 [!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní](/dotnet/csharp/programming-guide/interfaces/index)   
 [Rozhraní](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)