---
title: "CA2225: Přetížení operátoru mají pojmenované alternativy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f8c7b71fc964f898aefc5e243c787be71a8a063a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225: Přetížení operátoru mají pojmenované alternativy
|||  
|-|-|  
|TypeName|OperatorOverloadsHaveNamedAlternates|  
|CheckId|CA2225|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Bylo zjištěno přetížení operátoru a alternativní metoda s očekávaným názvem nebyla nalezena.  
  
## <a name="rule-description"></a>Popis pravidla  
 Přetížení operátoru dovoluje symboly představují výpočty typu. Typ, který přetížení symbol plus (+) pro přidání by například obvykle mít jiný člen s názvem "Přidat". Člen s názvem alternativní poskytuje přístup ke stejné funkce jako operátor a je k dispozici pro vývojáře, kteří programu v jazycích, které nepodporují přetížené operátory.  
  
 Toto pravidlo prověří operátory uvedené v následující tabulce.  
  
|C#|Visual Basic|C++|Alternativní název|  
|---------|------------------|-----------|--------------------|  
|+ (binární)|+|+ (binární)|Přidejte|  
|+=|+=|+=|Přidejte|  
|&|A|&|BitwiseAnd|  
|&=|A =|&=|BitwiseAnd|  
|&#124;|Nebo|&#124;|BitwiseOr|  
|&#124;=|Nebo =|&#124;=|BitwiseOr|  
|--|Není k dispozici|--|Snížení|  
|/|/|/|Dělení|  
|/=|/=|/=|Dělení|  
|==|=|==|Rovná se|  
|^|XOR|^|XOR|  
|^=|XOR =|^=|XOR|  
|>|>|>|Porovnání|  
|>=|>=|>=|Porovnání|  
|++|Není k dispozici|++|Přírůstek|  
|<>|!=|Rovná se|  
|<<|<<|<<|LeftShift|  
|<<=|<<=|<<=|LeftShift|  
|<|<|<|Porovnání|  
|<=|<=|\<=|Porovnání|  
|&&|Není k dispozici|&&|LogicalAnd|  
|&#124;&#124;|Není k dispozici|&#124;&#124;|LogicalOr|  
|!|Není k dispozici|!|LogicalNot|  
|%|Mod|%|Mod nebo zbývající|  
|%=|Není k dispozici|%=|Mod|  
|* (binární)|*|*|Násobení|  
|*=|Není k dispozici|*=|Násobení|  
|~|není|~|OnesComplement|  
|>>|>>|>>|RightShift|  
=|Není k dispozici|>>=|RightShift|  
|-(binární)|-(binární)|-(binární)|Odečtena|  
|-=|Není k dispozici|-=|Odečtena|  
|true|IsTrue –|Není k dispozici|IsTrue – (vlastnost)|  
|-(unární)|Není k dispozici|-|Negate –|  
|+ (unární)|Není k dispozici|+|Plus|  
|false|IsFalse –|False|IsTrue – (vlastnost)|  
  
 Není k dispozici == nemohou být přetíženy ve vybraném jazyce.  
  
 Také zkontroluje operátory přetypování implicitní a explicitní v typu, pravidla (`SomeType`) kontrolou metody s názvem `ToSomeType` a `FromSomeType`.  
  
 V jazyce C# při binární operátor je přetížena, odpovídající operátor přiřazení, pokud existuje, je také implicitně přetížené.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, implementujte alternativní metoda pro operátor; Pojmenujte ji pomocí doporučené alternativní název.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud implementujete sdílené knihovny není potlačení upozornění od tohoto pravidla. Aplikace můžete ignorovat upozornění z tohoto pravidla.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu definuje strukturu, která porušuje toto pravidlo. Chcete-li v příkladu, přidejte veřejné `Add(int x, int y)` metoda do struktury.  
  
 [!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: Přepište Equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: Přepište GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)