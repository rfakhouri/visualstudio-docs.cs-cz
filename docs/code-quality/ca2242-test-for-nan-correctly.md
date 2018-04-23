---
title: 'CA2242: Testujte správně NaN'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3c87b3e3528f12c07f728a5b82b56e75ee6551c1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: Testujte správně NaN
|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Výraz porovnává hodnotu <xref:System.Single.NaN?displayProperty=fullName> nebo <xref:System.Double.NaN?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Double.NaN?displayProperty=fullName>, který představuje not-a-number, výsledky při aritmetické operace není definován. Libovolný výraz, který testuje rovnosti mezi hodnotu a <xref:System.Double.NaN?displayProperty=fullName> vždy vrátí hodnotu `false`. Libovolný výraz, který testuje nerovnosti mezi hodnotu a <xref:System.Double.NaN?displayProperty=fullName> vždy vrátí hodnotu `true`.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Narušení toto pravidlo, a přesně zjistit, zda hodnota představuje <xref:System.Double.NaN?displayProperty=fullName>, použijte <xref:System.Single.IsNaN%2A?displayProperty=fullName> nebo <xref:System.Double.IsNaN%2A?displayProperty=fullName> k testování hodnoty.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dvou výrazů, které nesprávně testovací hodnoty s <xref:System.Double.NaN?displayProperty=fullName> a výraz, který používá správně <xref:System.Double.IsNaN%2A?displayProperty=fullName> k testování hodnoty.

 [!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]