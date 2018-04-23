---
title: 'CA1048: Nedeklarujte virtuální členy v zapečetěných typech'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdd01a1ce610ebd0e2a383ca3eac3a04ffbbdcfb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: Nedeklarujte virtuální členy v zapečetěných typech
|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejného typu je zapečetěná a deklaruje metodu, která se `virtual` (`Overridable` v jazyce Visual Basic) a ne finální. Toto pravidlo nevytváří sestavu porušení pro typy delegáta, které je třeba postupovat podle tohoto vzoru.

## <a name="rule-description"></a>Popis pravidla
 Typy deklarují metody jako virtuální, aby odvozující typy mohly přepsat implementaci virtuální metody. Podle definice nemůže Zdědit z zapečetěné typu, provedení virtuální metoda zapečetěné typu smysl.

 Kompilátory jazyka Visual Basic a C# neumožňují typy porušování toto pravidlo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, metoda bez virtuální nebo typ zděditelné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Ponechat typ v jejím aktuálním stavu může způsobit problémy s údržbou a neposkytuje žádné výhody.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo.

 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]