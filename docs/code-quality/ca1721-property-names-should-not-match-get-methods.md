---
title: 'CA1721: Názvy vlastností by neměly odpovídat metody get | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59812963f719da4c587d0a59b69619573b0e8a48
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: Názvy vlastností by neměly odpovídat metodám Get
|||  
|-|-|  
|TypeName|PropertyNamesShouldNotMatchGetMethods|  
|CheckId|CA1721|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Název veřejného nebo chráněného člena začíná "Get" a v opačném případě odpovídá názvu vlastnosti veřejného nebo chráněný. Například typu, který obsahuje metodu, která je s názvem "getcolor – a vlastnost, která je s názvem 'Color' v rozporu se toto pravidlo.  
  
## <a name="rule-description"></a>Popis pravidla  
 Get metody a vlastnosti, by měly mít názvy, které jasně odlišit jejich funkce.  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje čas, který je potřeba další nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Změňte název tak, aby neodpovídá název metody, která je s předponou "Get".  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
> [!NOTE]
>  Toto upozornění může být vyloučen, pokud je implementací rozhraní IExtenderProvider způsobená metodu Get.  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje metody a vlastnosti, která porušují toto pravidlo.  
  
 [!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
 [!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)