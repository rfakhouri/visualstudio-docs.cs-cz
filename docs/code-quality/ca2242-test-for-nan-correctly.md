---
title: 'CA2242: Testujte správně NaN'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8912cb6eeec8009364936a42d572f4f3d83fae5e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919910"
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: Testujte správně NaN

|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Výraz testuje hodnotu proti <xref:System.Single.NaN?displayProperty=fullName> nebo. <xref:System.Double.NaN?displayProperty=fullName>

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Double.NaN?displayProperty=fullName>, který reprezentuje nečíselný výsledek, je-li aritmetická operace nedefinovaná. Libovolný výraz, který testuje rovnost mezi hodnotou a <xref:System.Double.NaN?displayProperty=fullName> vždy vrátí `false`. Libovolný výraz, který testuje nerovnost mezi hodnotou a <xref:System.Double.NaN?displayProperty=fullName> vždy vrátí. `true`

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla a přesně určit, zda hodnota představuje <xref:System.Double.NaN?displayProperty=fullName>, použijte <xref:System.Single.IsNaN%2A?displayProperty=fullName> nebo <xref:System.Double.IsNaN%2A?displayProperty=fullName> k otestování hodnoty.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad ukazuje dva výrazy, které nesprávně testují hodnotu proti <xref:System.Double.NaN?displayProperty=fullName> a výraz, který je správně použit <xref:System.Double.IsNaN%2A?displayProperty=fullName> k otestování hodnoty.

[!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
[!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]