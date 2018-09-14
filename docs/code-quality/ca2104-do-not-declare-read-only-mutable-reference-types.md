---
title: 'CA2104: Nedeklaruje proměnlivé odkazové typy pouze pro čtení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 80d40dd60b0a6b6e507b903fd7a6185c5419422e
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551685"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Nedeklaruje proměnlivé odkazové typy pouze pro čtení

|||
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|Kategorie|Microsoft.Security|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Externě viditelný typ obsahuje externě viditelné pole měnitelného referenčního typu, které je určeno jen pro čtení.

## <a name="rule-description"></a>Popis pravidla
 Měnitelný typ je typ, jehož instanční data lze upravit. <xref:System.Text.StringBuilder?displayProperty=fullName> Je příkladem proměnlivý odkazový typ třídy. Obsahuje členy, které můžete změnit hodnotu vlastnosti instance třídy. Příklad nezměnitelný odkazový typ, který je <xref:System.String?displayProperty=fullName> třídy. Po jeho vytvoření instance, můžete jeho hodnotu nikdy nezmění.

 Modifikátor jen pro čtení ([jen pro čtení](/dotnet/csharp/language-reference/keywords/readonly) v jazyce C#, [jen pro čtení](/dotnet/visual-basic/language-reference/modifiers/readonly) v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], a [const](/cpp/cpp/const-cpp) v jazyce C++) na odkazový typ pole (ukazatele v jazyce C++) brání pole nahrazuje jinou instanci typu odkazu. Modifikátor však nezabraňuje data instance pole nebylo možné měnit pomocí typu odkazu.

 Pole pouze pro čtení se z tohoto pravidla vyjmuty, ale místo toho způsobit narušení [CA2105: pole polí by neměly být pouze pro čtení](../code-quality/ca2105-array-fields-should-not-be-read-only.md) pravidlo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odebrat modifikátor jen pro čtení nebo, pokud k zásadní změně je přijatelné, změňte pole s typem neměnné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud je neměnný typ pole.

## <a name="example"></a>Příklad
 Následující příklad ukazuje deklaraci pole, která způsobí, že porušení tohoto pravidla.

 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]