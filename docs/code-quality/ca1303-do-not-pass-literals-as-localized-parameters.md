---
title: 'CA1303: Nepředávejte literály jako lokalizované parametry'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5bdae3d0ee17624a2b168e5ce944ba10ab37fc8a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907695"
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303: Nepředávejte literály jako lokalizované parametry

|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Metoda předává řetězcový literál jako parametr do konstruktoru nebo metody v knihovně tříd rozhraní .NET Framework a tento řetězec by měl být lokalizovatelný.

 Toto upozornění je vyvoláno, když řetězcový literál je předán jako hodnotu parametru nebo vlastnost a nejméně jednu z následujících případech má hodnotu true:

- <xref:System.ComponentModel.LocalizableAttribute> Atribut parametru nebo vlastnosti je nastaven na hodnotu true.

- Název parametru nebo vlastnosti obsahuje "Text", "Zpráva" nebo "Popisu".

- Název parametru řetězce, který se předá metodě Console.Write nebo Console.WriteLine je "value" nebo "format".

## <a name="rule-description"></a>Popis pravidla
 Řetězcové literály, které jsou vloženy do zdrojového kódu se obtížně lokalizují.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, nahraďte řetězcový literál řetězce načíst prostřednictvím instance <xref:System.Resources.ResourceManager> třídy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud knihovny kódu nesmí být lokalizována, nebo pokud řetězec není vystavený koncovému uživateli nebo vývojáři pomocí knihovny kódu.

 Uživatelům můžete eliminovat šumu proti metody, které by neměly být předány lokalizované řetězce přejmenování parametru nebo vlastnost s názvem nebo označením tyto položky jako podmíněný.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která vyvolá výjimku, pokud některý z jeho dva argumenty jsou mimo rozsah. Pro první argument je předán konstruktoru výjimka řetězcový literál, který porušuje tato pravidla. Pro druhý argument je předán konstruktoru správně načtené pomocí řetězce <xref:System.Resources.ResourceManager>.

 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]

## <a name="see-also"></a>Viz také:
 [Prostředky v desktopových aplikacích](/dotnet/framework/resources/index)