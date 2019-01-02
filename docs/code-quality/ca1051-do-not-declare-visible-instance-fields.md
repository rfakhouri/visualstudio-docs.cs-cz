---
title: 'CA1051: Nedeklarujte viditelná pole instance'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b85fe5458dc4395ab7f1e119c3da90b685c96410
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53944467"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Nedeklarujte viditelná pole instance

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Externě viditelný typ obsahuje pole instance externě viditelné.

## <a name="rule-description"></a>Popis pravidla
 Hlavní použití pole by mělo být jako podrobnost implementace. Pole by měla být `private` nebo `internal` a měla by být vystavena s použitím vlastností. Je snadné přístup k vlastnosti, jako je přístup k poli a kód v přistupující objekty vlastnosti můžete změnit, protože funkce typu rozbalte bez vnášení rozbíjející změny. Vlastnosti, které právě vracejí hodnotu privátní nebo interní pole jsou optimalizována pro provedení ji přístup k poli. velmi malé zvýšení výkonu je spojené s použitím externě viditelné pole prostřednictvím vlastností.

 Externě viditelný odkazuje na `public`, `protected`, a `protected internal` (`Public`, `Protected`, a `Protected Friend` v jazyce Visual Basic) úrovní přístupu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, ujistěte se, pole `private` nebo `internal` a zpřístupnit ji pomocí externě viditelné vlastnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Externě viditelné pole neposkytují žádné výhody, které nejsou k dispozici pro vlastnosti. Kromě toho veřejné polí se nedají chránit pomocí [požadavky propojení](/dotnet/framework/misc/link-demands). Zobrazit [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ (`BadPublicInstanceFields`), který porušuje tato pravidla. `GoodPublicInstanceFields` zobrazuje opravený kód.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Viz také:
 [Požadavky propojení](/dotnet/framework/misc/link-demands)