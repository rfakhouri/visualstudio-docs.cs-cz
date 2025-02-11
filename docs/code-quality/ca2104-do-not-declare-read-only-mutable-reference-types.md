---
title: 'CA2104: Nedeklarujte jen pro čtení proměnlivé odkazové typy'
ms.date: 11/01/2018
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
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 40fdeefc2d664b80bb6e17c109349cb5912b0516
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545352"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Nedeklaruje proměnlivé odkazové typy pouze pro čtení

|||
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|Kategorie|Microsoft.Security|
|Narušující změna|Nenarušující|

> [!NOTE]
> CA2104 pravidlo je zastaralá a v budoucí verzi systému Visual Studio se odebere. Nebude možné implementovat jako [analyzátor](roslyn-analyzers-overview.md) kvůli složité analýzy, které je nutné určit skutečný neměnnosti typu.

## <a name="cause"></a>Příčina

Externě viditelný typ obsahuje externě viditelné pole měnitelného referenčního typu, které je určeno jen pro čtení.

## <a name="rule-description"></a>Popis pravidla

Měnitelný typ je typ, jehož instanční data lze upravit. <xref:System.Text.StringBuilder?displayProperty=fullName> Je příkladem proměnlivý odkazový typ třídy. Obsahuje členy, které můžete změnit hodnotu vlastnosti instance třídy. Příklad nezměnitelný odkazový typ, který je <xref:System.String?displayProperty=fullName> třídy. Po jeho vytvoření instance, můžete jeho hodnotu nikdy nezmění.

Modifikátor jen pro čtení ([jen pro čtení](/dotnet/csharp/language-reference/keywords/readonly) v C#, [jen pro čtení](/dotnet/visual-basic/language-reference/modifiers/readonly) v jazyce Visual Basic a [const](/cpp/cpp/const-cpp) v jazyce C++) na odkazový typ pole (nebo ukazatele v jazyce C++) brání na pole se nahrazuje jinou instanci typu odkazu. Modifikátor však nezabraňuje data instance pole nebylo možné měnit pomocí typu odkazu.

Toto pravidlo můžou neúmyslně zobrazit porušení pro typ, který se ve skutečnosti neměnné. V takovém případě je bezpečné upozornění můžete potlačit.

Pole pouze pro čtení se z tohoto pravidla vyjmuty, ale místo toho způsobit narušení [CA2105: Pole polí by neměly být pouze pro čtení](../code-quality/ca2105-array-fields-should-not-be-read-only.md) pravidlo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odebrat modifikátor jen pro čtení nebo, pokud k zásadní změně je přijatelné, změňte pole s typem neměnné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud je neměnný typ pole.

## <a name="example"></a>Příklad

Následující příklad ukazuje deklaraci pole, která způsobí, že porušení tohoto pravidla:

[!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
[!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
[!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]