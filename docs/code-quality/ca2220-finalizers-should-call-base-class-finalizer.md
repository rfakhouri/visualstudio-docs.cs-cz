---
title: 'CA2220: Finalizační metody by měly volat finalizační metodu třídy Base'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 874f0d744f00808d038cdf2bc0343ae7438b76db
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: Finalizační metody by měly volat finalizační metodu třídy Base
|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Typ, který přepíše <xref:System.Object.Finalize%2A?displayProperty=fullName> nevyvolá <xref:System.Object.Finalize%2A> metoda v její základní třída.

## <a name="rule-description"></a>Popis pravidla
 Finalizační metoda musí být šířena přes hierarchii dědičnosti. Aby, musí volat typy jejich základní třídy <xref:System.Object.Finalize%2A> metoda z v rámci své vlastní <xref:System.Object.Finalize%2A> metoda. Kompilátor jazyka C# automaticky přidá volání finalizační metodu třídy base.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, volejte základní typ <xref:System.Object.Finalize%2A> metoda z vaší <xref:System.Object.Finalize%2A> metoda.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Některé kompilátory, které cílí modul common language runtime vložit volání finalizační metodu základní typ do Microsoft (MSIL intermediate language). Pokud upozornění na toto pravidlo se použije v hlášení, vaše kompilátoru nevkládá volání a je třeba přidat ji do vašeho kódu.

## <a name="example"></a>Příklad
 Následující příklad jazyka Visual Basic ukazuje typ `TypeB` , správně volá <xref:System.Object.Finalize%2A> metoda v její základní třída.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]

## <a name="see-also"></a>Viz také
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)