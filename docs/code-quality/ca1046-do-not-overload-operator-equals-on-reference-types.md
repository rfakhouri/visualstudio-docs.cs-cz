---
title: 'CA1046: Nepřetěžujte operátor rovnosti na odkazových typech | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e78217e2ce8613ca312a96058b4477d1da82a5e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: Nepřetěžujte operátory rovnosti na odkazových typech
|||  
|-|-|  
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|  
|CheckId|CA1046|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Veřejné nebo vnořená veřejné odkazového typu přetížení operátoru rovnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 U referenčních typů je výchozí implementace operátoru rovnosti téměř vždy správná. Ve výchozím nastavení jsou dva odkazy rovny, pouze pokud ukazují na stejný objekt.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte implementace operátor rovnosti.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné při typ odkazu chová jako typ předdefinované hodnoty potlačit upozornění na toto pravidlo. Pokud je smysluplný udělat desetin na instance typu, je pravděpodobně správná implementace operátor rovnosti a potlačit porušení zásady.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje výchozí chování při porovnávání dva odkazy.  
  
 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace porovná některé odkazy.  
  
 [!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **= nové (2,2) a b = nové (2,2) jsou stejné? Ne**  
**c a a jsou stejné? Ano**  
**b a a jsou ==? Ne**  
**c a a jsou ==? Ano**   
## <a name="related-rules"></a>Související pravidla  
 [CA1013: Přetižte operátor rovnosti společně s přetížením operátorů sčítání a odečítání](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators)