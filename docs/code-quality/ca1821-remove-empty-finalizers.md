---
title: 'CA1821: Odstraňte prázdné finalizační metody'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: d155d8846828d8806fb4927d39120bfad2b01f33
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53937332"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Odstraňte prázdné finalizační metody

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ implementuje finalizační metodu, která je prázdný, vyžaduje pouze základní typ finalizační metodu nebo volá pouze podmíněně vyslané metody.

## <a name="rule-description"></a>Popis pravidla
 Kdykoli je to možné, vyhněte se použití finalizačních metod kvůli dodatečným nárokům na výkon spojeným se sledováním životního cyklu objektu. Uvolňování paměti spustí finalizační metodu, předtím, než se shromáždí objektů. To znamená, že dvě kolekce se bude vyžadovat ke shromažďování objektu. Prázdná finalizační metoda zvyšuje touto přidanou režie bez žádnou výhodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odstraňte prázdné finalizační metody. Pokud se vyžaduje pro ladění finalizační metodu, uzavřete celý finalizační metodu v `#if DEBUG / #endif` direktivy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte zprávy z tohoto pravidla. Selhání pro potlačení dokončení snižuje výkon a poskytuje žádné výhody.

## <a name="example"></a>Příklad
 Následující příklad ukazuje prázdná finalizační metoda, která by měla být odebrána, finalizační metodu, která by měl být uzavřen v `#if DEBUG / #endif` směrnicemi a finalizační metodu, která používá `#if DEBUG / #endif` direktivy správně.

 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]