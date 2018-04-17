---
title: 'CA1040: Vyhněte se prázdným rozhraním | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 26ba25038baf0d54c1705d4f4dd6c9b0cca9f856
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Vyhněte se prázdným rozhraním
|||  
|-|-|  
|TypeName|AvoidEmptyInterfaces|  
|CheckId|CA1040|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Rozhraní nemá žádné členy deklarovat nebo implementovat dvě nebo více rozhraní.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozhraní definují členy ujednávající jejich chování nebo užití. Funkčnost popsaná rozhraním může být osvojena libovolným typem bez ohledu na to, kde se typ vyskytuje v hierarchii dědičnosti. Typ implementuje rozhraní tím, že poskytuje implementace jeho členů. Prázdný rozhraní nedefinuje žádné členy. Nedefinuje proto kontrakt, který může být implementováno.  
  
 Pokud váš návrh obsahuje prázdný rozhraní, které typy by se měl implementovat, pravděpodobně používáte rozhraní jako značku nebo způsob, jak identifikovat skupiny typů. Pokud tato identifikace dojde za běhu, je správný způsob k tomu použít vlastní atribut. Použijte k identifikaci cílové typy přítomnosti nebo absenci atribut, nebo vlastnosti atribut. Pokud v době kompilace musí dojít k identifikaci, se dá použít rozhraní prázdný.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odeberte rozhraní nebo do ní přidejte členy. Pokud prázdného rozhraní se používají pro označení sadu typů, nahraďte rozhraní vlastní atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné při rozhraní slouží k identifikaci sadu typů v době kompilace potlačit upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje prázdného rozhraní.  
  
 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]