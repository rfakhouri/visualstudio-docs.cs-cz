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
ms.openlocfilehash: 143a094375871bf8073999f89d7fac5d6df01b4f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551857"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: Uvolnitelné pole by mělo být uvolněno

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> deklaruje pole, která jsou typy, které také implementují <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Není volána metoda pole <xref:System.IDisposable.Dispose%2A> metoda deklarujícího typu.

## <a name="rule-description"></a>Popis pravidla
 Typ je zodpovědná za uvolnění všech jeho nespravovaných prostředků; To lze provést prostřednictvím implementace <xref:System.IDisposable>. Toto pravidlo zkontroluje, zda uvolnitelného typu `T` deklaruje pole `F` z uvolnitelného typu, který je instance `FT`. Pro každé pole `F`, pravidlo se pokusí najít volání `FT.Dispose`. Toto pravidlo vyhledá metody volané `T.Dispose`a jednu úroveň níže (volání metody volané metody `FT.Dispose`).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zavolejte <xref:System.IDisposable.Dispose%2A> pro pole, která jsou typy, které implementují <xref:System.IDisposable> Pokud odpovídáte za přidělování a uvolňování nespravovaných prostředků držených pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pokud si nejste zodpovědná pro uvolnění prostředku drží pole, nebo pokud můžete bezpečně volání <xref:System.IDisposable.Dispose%2A> dochází na hlubší úrovni volání než pravidla kontroly.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeA` , který implementuje <xref:System.IDisposable> (`FT` v diskuzi previosu).

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeB` , který porušuje pravidlo deklarací pole `aFieldOfADisposableType` (`F` v předchozím diskusí) jako uvolnitelného typu (`TypeA`) a není volání <xref:System.IDisposable.Dispose%2A> na pole. `TypeB` odpovídá `T` v předchozím diskusí.

 [!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.IDisposable?displayProperty=fullName>
- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)