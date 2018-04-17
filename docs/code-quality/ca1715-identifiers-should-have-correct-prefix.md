---
title: 'CA1715: Identifikátory by měly mít správnou předponou. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c6d744022c6be599d0df57f86c0d67b1f6a72dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715: Identifikátory by měly mít správnou předponu
|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectPrefix|  
|CheckId|CA1715|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Pozastavení - při aktivováno u rozhraní.<br /><br /> Non narušující - při parametry obecného typu.|  
  
## <a name="cause"></a>příčina  
 Název rozhraní externě viditelné nezačíná velká písmena "I".  
  
 -nebo-  
  
 Název parametru obecného typu na externě viditelné typ nebo metoda nezačíná velká písmena se '.  
  
## <a name="rule-description"></a>Popis pravidla  
 Podle konvence názvy určitých elementům programování spustit konkrétní předponu.  
  
 Názvy rozhraní, které by měl začínat velkým, které "I" následuje jiný velké písmeno. Toto pravidlo hlásí porušení pro názvy rozhraní, například 'MyInterface' a 'IsolatedInterface'.  
  
 Názvy parametrů obecného typu by měla začínat znakem velká písmena se ' a volitelně může následovat jiné velké písmeno. Toto pravidlo hlásí porušení pro názvy parametrů obecného typu, například "V" a "Typ".  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Přejmenujte identifikátor tak, aby se správně předponu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 **Následující příklad ukazuje správně s názvem rozhraní.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]  
  
## <a name="example"></a>Příklad  
 **Následující příklad opravy předchozí porušení pomocí prefixu rozhraní s "I".**  
  
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]  
  
## <a name="example"></a>Příklad  
 **Následující příklad ukazuje správně pojmenované obecného typu parametru.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]  
  
## <a name="example"></a>Příklad  
 **Následující příklad opravy předchozí porušení pomocí prefixu parametr obecného typu pomocí 'T'.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1722: Identifikátory by neměly mít nesprávnou předponu](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)