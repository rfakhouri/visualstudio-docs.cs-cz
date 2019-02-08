---
title: 'CA2215: Metody Dispose by měly volat uvolnění základní třídy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 203fc14097e0c6d2fbdaee1689deffdfe814eb63
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55914315"
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Metody Dispose by měly volat uvolnění základní třídy

|||
|-|-|
|TypeName|DisposeMethodsShouldCallBaseClassDispose|
|CheckId|CA2215|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> je odvozen z typu, který také implementuje <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Nevolá metodu ze dědičné typu <xref:System.IDisposable.Dispose%2A> metoda nadřazeného typu.

## <a name="rule-description"></a>Popis pravidla
 Pokud typ dědí z uvolnitelného typu, musí volat <xref:System.IDisposable.Dispose%2A> metodu základního typu v rámci své vlastní <xref:System.IDisposable.Dispose%2A> metody. Volání metody základní typ Dispose zajistí, že se vydávají všechny prostředky vytvořené v rámci základního typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zavolejte `base`.<xref:System.IDisposable.Dispose%2A> ve vaší <xref:System.IDisposable.Dispose%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud volání `base`.<xref:System.IDisposable.Dispose%2A> nastane na hlubší úrovni volání než pravidla kontroly.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeA` , který implementuje <xref:System.IDisposable>.

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeB` , která dědí z typu `TypeA` a správně volá jeho <xref:System.IDisposable.Dispose%2A> metoda.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]

## <a name="see-also"></a>Viz také:

- <xref:System.IDisposable?displayProperty=fullName>
- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)