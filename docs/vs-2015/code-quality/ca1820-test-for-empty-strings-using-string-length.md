---
title: 'CA1820: Testujte prázdné řetězce pomocí délky řetězce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 17def2bda544a188d6144affc9d7fccb24c3b079
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902535"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: Testujte prázdné řetězce pomocí délky řetězce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1820: Test prázdné řetězce pomocí délky řetězce](https://docs.microsoft.com/visualstudio/code-quality/ca1820-test-for-empty-strings-using-string-length).

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Řetězec je ve srovnání s prázdný řetězec s použitím <xref:System.Object.Equals%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Porovnání řetězců pomocí <xref:System.String.Length%2A?displayProperty=fullName> vlastnost nebo <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> metoda je mnohem rychlejší než použití <xref:System.Object.Equals%2A>. Důvodem je, že <xref:System.Object.Equals%2A> provádí výrazně více instrukcí jazyka MSIL než buď <xref:System.String.IsNullOrEmpty%2A> nebo počet instrukcí provést k načtení <xref:System.String.Length%2A> vlastnost hodnotu a porovnat ho na hodnotu nula.

 Byste měli vědět, který <xref:System.Object.Equals%2A> a <xref:System.String.Length%2A> == 0 chovat jinak pro řetězce s hodnotou null. Pokud se pokusíte získat hodnotu <xref:System.String.Length%2A> vlastnost na řetězec s hodnotou null, modul common language runtime vyvolá <xref:System.NullReferenceException?displayProperty=fullName>. Pokud provádíte srovnání řetězec s hodnotou null a prázdné řetězce, modul common language runtime nevyvolá výjimku. Porovnání vrátí `false`. Testování pro null neovlivní výrazně relativní výkon tyto dvě metody. Při cílení na [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], použijte <xref:System.String.IsNullOrEmpty%2A> metody. Jinak použijte <xref:System.String.Length%2A> == porovnání, kdykoli je to možné.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte porovnání pro použití <xref:System.String.Length%2A> vlastnost a testování pro řetězec s hodnotou null. Pokud je zaměřen na [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], použijte <xref:System.String.IsNullOrEmpty%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud výkon není problém.

## <a name="example"></a>Příklad
 Následující příklad ukazuje různé techniky, které se používají k vyhledání prázdný řetězec.

 [!code-csharp[FxCop.Performance.StringTest#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.StringTest/cs/FxCop.Performance.StringTest.cs#1)]



