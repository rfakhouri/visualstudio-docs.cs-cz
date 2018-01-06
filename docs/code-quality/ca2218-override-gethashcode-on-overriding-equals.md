---
title: "CA2218: Přepište GetHashCode při přepsání Equals | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2218
- OverrideGetHashCodeOnOverridingEquals
helpviewer_keywords:
- OverrideGetHashCodeOnOverridingEquals
- CA2218
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eed9ae032a89eb30785acb71feac47d6c4f8cdc3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2218-override-gethashcode-on-overriding-equals"></a>CA2218: Přepište GetHashCode při přepsání Equals
|||  
|-|-|  
|TypeName|OverrideGetHashCodeOnOverridingEquals|  
|CheckId|CA2218|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Přepsání veřejného typu <xref:System.Object.Equals%2A?displayProperty=fullName> , ale nemůže přepsat <xref:System.Object.GetHashCode%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Object.GetHashCode%2A>Vrátí hodnotu, podle aktuální instance, který je vhodný pro délkami algoritmů hash a datové struktury například zatřiďovací tabulku. Dva objekty, které jsou stejného typu a jsou si rovny musí vrátit stejnou hodnotu hash zajistit správné fungování instancí následujících typů:  
  
-   <xref:System.Collections.Hashtable?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>  
  
-   Typy, které implementují<xref:System.Collections.Generic.IEqualityComparer%601?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, zadejte implementaci <xref:System.Object.GetHashCode%2A>. U pár objekty stejného typu, je nutné zajistit, že implementace vrací stejnou hodnotu, pokud vaši implementaci <xref:System.Object.Equals%2A> vrátí `true` páru.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="class-example"></a>Příklad – třída  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje třídu (odkaz), která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.GetHashCodeErrorClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_1.cs)]  
  
### <a name="comments"></a>Komentáře  
 Následující příklad opraví porušení přepsáním <xref:System.Object.GetHashCode>.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.GetHashCodeFixedClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_2.cs)]  
  
## <a name="structure-example"></a>Příklad struktury  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje strukturu (typ hodnoty), která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.GetHashCodeErrorStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_3.cs)]  
  
### <a name="comments"></a>Komentáře  
 Následující příklad opraví porušení přepsáním <xref:System.Object.GetHashCode>.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Usage.GetHashCodeFixedStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_4.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: Přetížení operátoru mají pojmenované alternativy](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: Přepište Equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Collections.Hashtable?displayProperty=fullName>   
 [Operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators)