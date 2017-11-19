---
title: "CA1036: Přepište metody srovnatelných typů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d07e63363542a9bf5a1dd756026183349659abe1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: Přepište metody srovnatelných typů
|||  
|-|-|  
|TypeName|OverrideMethodsOnComparableTypes|  
|CheckId|CA1036|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Implementuje typu veřejný nebo chráněné <xref:System.IComparable?displayProperty=fullName> rozhraní a nepřepisuje <xref:System.Object.Equals%2A?displayProperty=fullName> nebo není přetížení pro specifický jazyk operátor rovnosti, nerovnosti, menší nebo větší. Pravidlo nevytváří sestavu narušení, pokud typ dědí pouze implementace rozhraní.  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy, které definují vlastní pořadí řazení implementovat <xref:System.IComparable> rozhraní. <xref:System.IComparable.CompareTo%2A> Metoda vrací celočíselnou hodnotu určující, správné pořadí řazení pro dvě instance typu. Toto pravidlo určuje typy, které nastavit pořadí řazení; To znamená, že obyčejnou význam rovnosti nerovnosti, menší než a je větší než se nevztahují. Když zadáte implementace <xref:System.IComparable>, obvykle musíte také přepsat <xref:System.Object.Equals%2A> tak, aby ho vrátil hodnoty, které jsou konzistentní s <xref:System.IComparable.CompareTo%2A>. Pokud přepíšete <xref:System.Object.Equals%2A> a jsou kódování v jazyce, který podporuje přetížení operátoru, měli byste také poskytnout operátory, které jsou konzistentní s <xref:System.Object.Equals%2A>.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, přepište <xref:System.Object.Equals%2A>. Pokud si programovací jazyk podporuje přetížení operátoru, zadejte následující operátory:  
  
-   op_Equality  
  
-   op_inequality –  
  
-   op_lessthan –  
  
-   op_greaterthan –  
  
 V jazyce C#, tokeny, které se používají k vyjádření tyto operátory jsou následující: ==,! =, \<, a >.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné při porušení je způsobená chybějící operátory a programovací jazyk nepodporuje operátor přetížení, jako je tomu u Visual Basic .NET potlačit upozornění na toto pravidlo. Je také bezpečné potlačení upozornění pro toto pravidlo, když se aktivuje na operátory rovnosti jiného, než op_Equality Pokud zjistíte, že implementace operátory nemá smysl v kontextu vaší aplikace. Nicméně, měli byste vždy přes op_Equality a pokud přepíšete Object.Equals == – operátor.  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje typ, který implementuje správně <xref:System.IComparable>. Komentáře kódu identifikovat metody, které vyhovují různá pravidla, které se vztahují k <xref:System.Object.Equals%2A> a <xref:System.IComparable> rozhraní.  
  
 [!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace testy chování <xref:System.IComparable> implementace, která je uvedena výše.  
  
 [!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IComparable?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators)