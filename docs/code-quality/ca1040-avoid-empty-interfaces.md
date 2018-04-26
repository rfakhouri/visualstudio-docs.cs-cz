---
title: 'CA1040: Vyhněte se prázdným rozhraním'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: f0de7459427fae4ea21cf1465167defea6d1d274
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
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