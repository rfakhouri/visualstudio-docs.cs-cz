---
title: "CA1820: Testujte prázdné řetězce pomocí délky řetězce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d044f09ca26b65506bcfb7466f59da73acfad1e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: Testujte prázdné řetězce pomocí délky řetězce
|||  
|-|-|  
|TypeName|TestForEmptyStringsUsingStringLength|  
|CheckId|CA1820|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Řetězec se porovnává se prázdný řetězec pomocí <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Porovnávání řetězců pomocí <xref:System.String.Length%2A?displayProperty=fullName> vlastnost nebo <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> metoda je mnohem rychlejší než použití <xref:System.Object.Equals%2A>. Důvodem je, že <xref:System.Object.Equals%2A> spouští výrazně další instrukce MSIL než buď <xref:System.String.IsNullOrEmpty%2A> nebo počet pokyny provést načíst <xref:System.String.Length%2A> vlastnost hodnota a porovnávají ho na hodnotu nula.  
  
 Je třeba si uvědomit, <xref:System.Object.Equals%2A> a <xref:System.String.Length%2A> == 0 chovat jinak pro řetězce null. Pokud se pokusíte získat hodnotu <xref:System.String.Length%2A> vlastnost na hodnotu null. řetězec, vyvolá modul common language runtime <xref:System.NullReferenceException?displayProperty=fullName>. Pokud provádíte srovnání řetězec null a prázdný řetězec, modul common language runtime nevyvolá výjimku; Porovnání vrátí `false`. Testování pro null neovlivňuje výrazně relativní výkon tyto dva přístupy. Pokud je cílem [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], použijte <xref:System.String.IsNullOrEmpty%2A> metoda. Jinak použijte <xref:System.String.Length%2A> == porovnání kdykoli je to možné.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změňte porovnání používat <xref:System.String.Length%2A> vlastnost a test pro řetězec null. Pokud cílení na [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], použijte <xref:System.String.IsNullOrEmpty%2A> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud výkon není problém.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje různých technik, které se používají k vyhledejte prázdný řetězec.  
  
 [!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]