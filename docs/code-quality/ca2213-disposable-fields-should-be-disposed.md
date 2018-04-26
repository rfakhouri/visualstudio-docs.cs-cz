---
title: 'CA2213: Uvolnitelné pole by mělo být uvolněno'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be4efbd197a8146789b9646f6b5c467cc42815b1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: Uvolnitelné pole by mělo být uvolněno
|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> deklaruje pole, které jsou typy, které taky implementovat <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Nevolá metoda pole <xref:System.IDisposable.Dispose%2A> metoda deklarující typ.

## <a name="rule-description"></a>Popis pravidla
 Typ je zodpovědná za uvolnění všechny jeho nespravovaných prostředků; toho dosahuje tím, že implementujete <xref:System.IDisposable>. Toto pravidlo zkontroluje, jestli na jedno použití typu `T` deklaruje pole `F` tedy instanci na jedno použití typu `FT`. Pro každé pole `F`, pravidlo se pokusí najít volání `FT.Dispose`. Toto pravidlo vyhledá volá metody `T.Dispose`a o jednu úroveň níže (volají metody volá metody `FT.Dispose`).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, volejte <xref:System.IDisposable.Dispose%2A> na pole, které jsou z typů, které implementují <xref:System.IDisposable> Pokud jste zodpovědní za přidělování a uvolněním nespravované prostředky držené pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, pokud si nejste zodpovědná pro uvolnění prostředku uchovávat podle pole, nebo pokud volání <xref:System.IDisposable.Dispose%2A> dojde na podrobnější úrovni volání než pravidla kontroly.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeA` , která implementuje <xref:System.IDisposable> (`FT` v diskusi previosu).

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeB` která porušuje toto pravidlo deklarace pole `aFieldOfADisposableType` (`F` v předchozí diskuse) jako na jedno použití typ (`TypeA`) a není volání <xref:System.IDisposable.Dispose%2A> na pole. `TypeB` odpovídá `T` v předchozí diskuse.

 [!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.IDisposable?displayProperty=fullName> [Dispose – vzor](/dotnet/standard/design-guidelines/dispose-pattern)