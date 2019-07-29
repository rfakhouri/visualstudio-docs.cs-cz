---
title: 'CA1053: Statické typy vlastníků by neměly mít konstruktory'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fec59e1d683c7867eb1cad9ae4e796a0815200d4
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68604783"
---
# <a name="ca1053-static-holder-types-should-not-have-default-constructors"></a>CA1053: Typy statických držitelů by neměly mít výchozí konstruktory.

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

> [!NOTE]
> Pravidlo CA1053 je kombinované do [CA1052: Statické typy držitelů by měly](ca1052-static-holder-types-should-be-sealed.md) být zapečetěné v [analyzátorech FxCop](fxcop-analyzers.yml).

## <a name="cause"></a>příčina

Veřejný nebo vnořený veřejný typ deklaruje pouze statické členy a má výchozí konstruktor.

## <a name="rule-description"></a>Popis pravidla

Výchozí konstruktor není potřebný, protože volání statických členů nevyžaduje instanci typu. Vzhledem k tomu, že typ nemá nestatické členy, vytvoření instance neposkytuje přístup k žádnému z členů typu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte výchozí konstruktor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Přítomnost výchozího konstruktoru naznačuje, že typ není statický typ.