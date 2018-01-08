---
title: "CA2224: Přepište equals při přetížení operátoru rovnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2224
- OverrideEqualsOnOverloadingOperatorEquals
- OverrideEqualsOnOverridingOperatorEquals
helpviewer_keywords:
- OverrideEqualsOnOverloadingOperatorEquals
- CA2224
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4d34acafb4f014b91e4c0f707060ce0442a413e3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2224-override-equals-on-overloading-operator-equals"></a>CA2224: Přepište Equals při přetížení operátoru rovnosti
|||  
|-|-|  
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|  
|CheckId|CA2224|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Implementuje operátor rovnosti veřejného typu, ale nemůže přepsat <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Operátor rovnosti má být syntakticky pohodlný způsob, jak přistupovat k funkcím <xref:System.Object.Equals%2A> metoda. Pokud budete implementovat operátor rovnosti, musí být shodná s svou logikou <xref:System.Object.Equals%2A>.  
  
 Kompilátor jazyka C# vydá upozornění, pokud kód porušuje toto pravidlo.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, musí buď odeberte implementace operátor rovnosti nebo přepsat <xref:System.Object.Equals%2A> a mají tyto dvě metody vrátí stejné hodnoty. Pokud operátor rovnosti nezavádí nekonzistentní chování, můžete je vyřešit narušení tím, že poskytuje implementaci pro <xref:System.Object.Equals%2A> , který volá <xref:System.Object.Equals%2A> metodu v základní třídě.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li operátor rovnosti vrací stejnou hodnotu jako zděděné implementace <xref:System.Object.Equals%2A>. V části příklad zahrnuje typ, který může bezpečně potlačit upozornění na toto pravidlo.  
  
## <a name="examples-of-inconsistent-equality-definitions"></a>Příklady definice nekonzistentní rovnosti  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje typ s nekonzistentní definice rovnosti. `BadPoint`Změní význam rovnosti tím, že poskytuje vlastní implementaci operátor rovnosti, ale nemůže přepsat <xref:System.Object.Equals%2A> tak, aby se chová stejně jako.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.OperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující kód testy chování `BadPoint`.  
  
 [!code-csharp[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_2.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **= ([0] 1; 1) a, b = ([1] 2,2) jsou stejné? Ne**  
**== b? Ne**  
**a1 a a jsou stejné? Ano**  
**a1 ==? Ano**  
**b a bcopy jsou stejné? Ne**  
**b == bcopy? Ano**   
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který technicky porušuje toto pravidlo, ale není chovat nekonzistentní způsobem.  
  
 [!code-csharp[FxCop.Usage.ValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_3.cs)]  
  
## <a name="example"></a>Příklad  
 Následující kód testy chování `GoodPoint`.  
  
 [!code-csharp[FxCop.Usage.TestValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_4.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **= (1,1) a, b = (2,2) jsou stejné? Ne**  
**== b? Ne**  
**a1 a a jsou stejné? Ano**  
**a1 ==? Ano**  
**b a bcopy jsou stejné? Ano**  
**b == bcopy? Ano**   
## <a name="class-example"></a>Příklad – třída  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje třídu (odkaz), která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.OverrideEqualsClassViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_5.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad opraví porušení přepsáním <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Usage.OverrideEqualsClassFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_6.cs)]  
  
## <a name="structure-example"></a>Příklad struktury  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje strukturu (typ hodnoty), která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.OverrideEqualsStructViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_7.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad opraví porušení přepsáním <xref:System.ValueType.Equals%2A?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Usage.OverrideEqualsStructFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_8.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: Přetížení operátoru mají pojmenované alternativy](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2218: Přepište GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)