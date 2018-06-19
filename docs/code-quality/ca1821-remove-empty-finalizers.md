---
title: 'CA1821: Odstraňte prázdné finalizační metody'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f24b0f4c6358da459525288a2812446c1c73f3d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915229"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Odstraňte prázdné finalizační metody
|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ implementuje finalizační metodu, která je prázdný, volá pouze základní typ finalizační metodu nebo volá jen podmíněně vygenerované metody.

## <a name="rule-description"></a>Popis pravidla
 Kdykoli je to možné, vyhněte se použití finalizačních metod kvůli dodatečným nárokům na výkon spojeným se sledováním životního cyklu objektu. Uvolňování paměti spustí finalizační metodu než shromáždí objektu. To znamená, že dvě kolekce se bude vyžadovat ke shromažďování objektu. Prázdné finalizační metodu způsobuje to přidán režie bez nějaké výhody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odstraňte prázdné finalizační metodu. Pokud finalizační metody se vyžaduje pro ladění, uzavřete celý finalizační metodu v `#if DEBUG / #endif` direktivy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Není potlačit zprávu od tohoto pravidla. Selhání potlačit finalizace snižuje výkon a poskytuje žádné výhody.

## <a name="example"></a>Příklad
 Následující příklad ukazuje prázdné finalizační metodu, která má být odebrána, finalizační metodu, která by měla být uzavřená do `#if DEBUG / #endif` direktivy a finalizační metodu, která používá `#if DEBUG / #endif` direktivy správně.

 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]