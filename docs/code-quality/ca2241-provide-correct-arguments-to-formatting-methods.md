---
title: 'CA2241: Poskytněte správné argumenty metodě formátování'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02f01df5ac774a22c5a0b9b22c68650f17d3e8c0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: Poskytněte správné argumenty metodě formátování
|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 `format` Argument předána metodě, například řetězce <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, nebo <xref:System.String.Format%2A?displayProperty=fullName> neobsahuje položku formátu, která odpovídá na všechny argumenty objektu a naopak.

## <a name="rule-description"></a>Popis pravidla
 Argumenty, které mají metody, jako <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, a <xref:System.String.Format%2A> obsahovat řetězec formátu, za nímž následuje několik <xref:System.Object?displayProperty=fullName> instance. Řetězec formátu se skládá z textu a formát vložených položek formuláře, {index [, zarovnání] [: formatString]}. 'index' je počítáno od nuly celé číslo, které označuje, které objekty, které chcete formátovat. Pokud objekt nemá odpovídající index ve formátovacím řetězci, objekt je ignorována. Pokud objekt určeného 'index' neexistuje, <xref:System.FormatException?displayProperty=fullName> je vyvolána za běhu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, zadejte položku Formát pro každý objekt argument a zadat argument objekt pro každou položku formátu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva porušení pravidla.

 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]