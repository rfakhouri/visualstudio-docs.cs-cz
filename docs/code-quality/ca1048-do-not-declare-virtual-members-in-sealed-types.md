---
title: 'CA1048: Nedeklarujte virtuální členy v zapečetěných typech'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 84db1db9061eff1373ee3ad4f0316a1f3dba0474
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55924497"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: Nedeklarujte virtuální členy v zapečetěných typech

|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný typ je zapečetěná a deklaruje metodu, která je oba směry `virtual` (`Overridable` v jazyce Visual Basic) a ne finální. Toto pravidlo nevytváří sestavu porušení pro typy delegátů, které musí postupovat podle tohoto vzoru.

## <a name="rule-description"></a>Popis pravidla
 Typy deklarují metody jako virtuální, aby odvozující typy mohly přepsat implementaci virtuální metody. Dle definice nelze dědit ze zapečetěného typu, že virtuální metoda u zapečetěného typu význam.

 Kompilátory jazyků Visual Basic a C# neumožňují typů pro toto pravidlo porušují.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zkontrolujte nevirtuální metodu nebo změňte typ odvoditelný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Opuštění typu v jejím aktuálním stavu může způsobit problémy s údržbou a nepřináší žádné výhody.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje tato pravidla.

 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]