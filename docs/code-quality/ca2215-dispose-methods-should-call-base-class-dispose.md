---
title: 'CA2215: Metody Dispose by měly volat uvolnění třídy Base'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ce7e5de528e8b0c0a6f128fa9f7d68c1b9f385c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Metody Dispose by měly volat uvolnění třídy Base
|||
|-|-|
|TypeName|DisposeMethodsShouldCallBaseClassDispose|
|CheckId|CA2215|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> dědí od typu, který také implementuje <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Metoda dědičných typu nevyvolá <xref:System.IDisposable.Dispose%2A> metoda nadřazeného typu.

## <a name="rule-description"></a>Popis pravidla
 Pokud typ dědí od typu na jedno použití, musí volat <xref:System.IDisposable.Dispose%2A> metoda základní typu v rámci vlastní <xref:System.IDisposable.Dispose%2A> metoda. Volání metody základní typ uvolnění zajišťuje, vydání všechny prostředky vytvořené základního typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, volejte `base`.<xref:System.IDisposable.Dispose%2A> ve vašem <xref:System.IDisposable.Dispose%2A> metoda.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, pokud volání `base`.<xref:System.IDisposable.Dispose%2A> dojde k na podrobnější úrovni volání než pravidla kontroly.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeA` , která implementuje <xref:System.IDisposable>.

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeB` který dědí z typu `TypeA` a správně volá jeho <xref:System.IDisposable.Dispose%2A> metoda.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]

## <a name="see-also"></a>Viz také
 <xref:System.IDisposable?displayProperty=fullName> [Dispose – vzor](/dotnet/standard/design-guidelines/dispose-pattern)