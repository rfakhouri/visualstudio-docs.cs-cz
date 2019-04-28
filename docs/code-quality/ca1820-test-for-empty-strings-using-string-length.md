---
title: 'CA1820: Testujte prázdné řetězce pomocí délky řetězce'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae65ad9c1ad740b3ea39dd97d7430804292df057
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62796754"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: Testujte prázdné řetězce pomocí délky řetězce

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Řetězec je ve srovnání s prázdný řetězec s použitím <xref:System.Object.Equals%2A?displayProperty=nameWithType>.

## <a name="rule-description"></a>Popis pravidla

Porovnání řetězců pomocí <xref:System.String.Length%2A?displayProperty=nameWithType> vlastnost nebo <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> metoda je rychlejší než použití <xref:System.Object.Equals%2A>. Důvodem je, že <xref:System.Object.Equals%2A> provádí výrazně více instrukcí jazyka MSIL než buď <xref:System.String.IsNullOrEmpty%2A> nebo počet instrukcí provést k načtení <xref:System.String.Length%2A> vlastnost hodnotu a porovnat ho na hodnotu nula.

Pro řetězce s hodnotou null <xref:System.Object.Equals%2A> a <xref:System.String.Length%2A> == 0 chovat jinak. Pokud se pokusíte získat hodnotu <xref:System.String.Length%2A> vlastnost na řetězec s hodnotou null, modul common language runtime vyvolá <xref:System.NullReferenceException?displayProperty=fullName>. Pokud provádíte srovnání řetězec s hodnotou null a prázdné řetězce, modul common language runtime nevyvolá výjimku a vrátí `false`. Testování pro null neovlivní výrazně relativní výkon tyto dvě metody. Při cílení na rozhraní .NET Framework 2.0 nebo novější, použijte <xref:System.String.IsNullOrEmpty%2A> metody. Jinak použijte <xref:System.String.Length%2A> == 0 porovnání, kdykoli je to možné.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změňte porovnání pro použití <xref:System.String.Length%2A> vlastnost a testování pro řetězec s hodnotou null. Pokud se zaměřujete na rozhraní .NET Framework 2.0 nebo novější, použijte <xref:System.String.IsNullOrEmpty%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud výkon není problém.

## <a name="example"></a>Příklad

Následující příklad ukazuje různé techniky, které se používají k vyhledání prázdný řetězec.

[!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]