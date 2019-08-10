---
title: 'CA1821: Odeberte prázdné finalizační metody'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c8c4d4ca04c7a9a21cd1e80e4dc06e8d5a92c2f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921374"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Odeberte prázdné finalizační metody

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Kategorie|Microsoft. Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
Typ implementuje finalizační metodu, která je prázdná, volá pouze finalizační metodu základního typu nebo volá pouze podmíněně emitované metody.

## <a name="rule-description"></a>Popis pravidla
Kdykoli je to možné, vyhněte se použití finalizačních metod kvůli dodatečným nárokům na výkon spojeným se sledováním životního cyklu objektu. Systém uvolňování paměti spustí finalizační metodu před tím, než bude objekt shromažďovat. To znamená, že ke shromáždění objektu budou požadovány dvě kolekce. Prázdná finalizační metoda má tuto přidanou režii bez jakýchkoli výhod.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Odeberte prázdný finalizační metodu. Pokud je pro ladění vyžadován finalizační metoda, vložte celý finalizační metodu do `#if DEBUG / #endif` direktiv.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačit zprávu od tohoto pravidla. Nepovedlo se potlačit konečné snížení výkonu a neposkytuje žádné výhody.

## <a name="example"></a>Příklad
Následující příklad ukazuje prázdný finalizační metodu, která by měla být odebrána, finalizační metoda, která by měla být uzavřena `#if DEBUG / #endif` do direktiv a finalizační metoda, která `#if DEBUG / #endif` používá direktivy správně.

[!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]