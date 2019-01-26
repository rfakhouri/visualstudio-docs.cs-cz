---
title: 'CA2241: Zadejte správné argumenty pro metody formátování'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f723e9c3a6f204b1a19648b121637f42d1fb4017
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920833"
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: Zadejte správné argumenty pro metody formátování

|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 `format` Řetězcový argument předaný metodě například <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, nebo <xref:System.String.Format%2A?displayProperty=fullName> neobsahuje položky formátu, který odpovídá každému argumentu objektu nebo naopak.

## <a name="rule-description"></a>Popis pravidla
 Argumenty pro metody jako <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, a <xref:System.String.Format%2A> obsahovat řetězec formátu, za nímž následuje několik <xref:System.Object?displayProperty=fullName> instancí. Řetězec formátu se skládá z textu a vložené formátu položek formuláře, {index [, zarovnání] [: formatString]}. "index" je založený na nule celého čísla, která označuje, které objekty, které chcete formátovat. Pokud objekt nemá odpovídající index ve formátovacím řetězci, objekt se ignoruje. Pokud objektu určeném "index" buď neexistuje, <xref:System.FormatException?displayProperty=fullName> je vyvolána výjimka za běhu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, poskytují formát položky pro každý objekt argument a argument objektu pro každou položku formátu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva porušení tohoto pravidla.

 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]