---
title: 'CA2104: Nedeklarujte čtení proměnlivé odkazové typy pouze | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a4c6619bc5803c1b44e1c6b0516987c3110bbd30
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687421"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Nedeklaruje proměnlivé odkazové typy pouze pro čtení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|Kategorie|Microsoft.Security|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Externě viditelný typ obsahuje externě viditelné pole měnitelného referenčního typu, které je určeno jen pro čtení.

## <a name="rule-description"></a>Popis pravidla
 Měnitelný typ je typ, jehož instanční data lze upravit. <xref:System.Text.StringBuilder?displayProperty=fullName> Je příkladem proměnlivý odkazový typ třídy. Obsahuje členy, které můžete změnit hodnotu vlastnosti instance třídy. Příklad nezměnitelný odkazový typ, který je <xref:System.String?displayProperty=fullName> třídy. Po jeho vytvoření instance, můžete jeho hodnotu nikdy nezmění.

 Modifikátor jen pro čtení ([jen pro čtení](https://msdn.microsoft.com/library/2f8081f6-0de2-4903-898d-99696c48d2f4) v jazyce C#, [jen pro čtení](https://msdn.microsoft.com/library/e868185d-6142-4359-a2fd-a7965cadfce8) v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], a [const](https://msdn.microsoft.com/library/b21c0271-1ad0-40a0-b21c-5e812bba0318) v jazyce C++) na odkazový typ pole (ukazatele v jazyce C++) brání pole nahrazuje jinou instanci typu odkazu. Modifikátor však nezabraňuje data instance pole nebylo možné měnit pomocí typu odkazu.

 Pole pouze pro čtení se z tohoto pravidla vyjmuty, ale místo toho způsobit narušení [CA2105: Pole polí by neměly být pouze pro čtení](../code-quality/ca2105-array-fields-should-not-be-read-only.md) pravidlo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odebrat modifikátor jen pro čtení nebo, pokud k zásadní změně je přijatelné, změňte pole s typem neměnné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud je neměnný typ pole.

## <a name="example"></a>Příklad
 Následující příklad ukazuje deklaraci pole, která způsobí, že porušení tohoto pravidla.

 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/cpp/FxCop.Security.MutableReferenceTypes.cpp#1)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/cs/FxCop.Security.MutableReferenceTypes.cs#1)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/vb/FxCop.Security.MutableReferenceTypes.vb#1)]
