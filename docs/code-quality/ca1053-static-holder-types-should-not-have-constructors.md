---
title: 'CA1053: Statický vlastník typů by neměl mít konstruktory'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b490fb4a6ad5ffe510f7a443758bc53f5f8f0d99
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: Statický vlastník typů by neměl mít konstruktory
|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo vnořený veřejný typ deklaruje pouze statické členy a má veřejný nebo chráněný výchozí konstruktor.

## <a name="rule-description"></a>Popis pravidla
 Konstruktor není nutný, protože volání statických členů nevyžaduje instanci typu. Navíc vzhledem k tomu, že typ nemá nestatické členy, vytvoření instance neposkytuje přístup k jakémukoli typu členů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, odeberte výchozí konstruktor nebo nastavit jako soukromé.

> [!NOTE]
>  Některé kompilátory automaticky vytvoří výchozí veřejný konstruktor, pokud typ nedefinuje žádné konstruktory. Pokud je tomu u vašeho typu, přidejte privátní výchozí konstruktor eliminovat porušení zásady.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Přítomnost konstruktoru naznačuje, že typ není typu statické.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo. Všimněte si, že neexistuje žádný výchozí konstruktor ve zdrojovém kódu. Když tento kód se zkompiluje do sestavení, kompilátor jazyka C# vloží výchozí konstruktor, který bude toto pravidlo porušují. Chcete-li vyřešit tento problém, deklarujte soukromý konstruktor.

 [!code-csharp[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]