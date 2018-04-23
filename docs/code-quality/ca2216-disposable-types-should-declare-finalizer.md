---
title: 'CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableTypesShouldDeclareFinalizer
- CA2216
helpviewer_keywords:
- CA2216
- DisposableTypesShouldDeclareFinalizer
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6fbcc8ffe9b81b39734c9b9a4cc6070e584d1183
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu
|||
|-|-|
|TypeName|DisposableTypesShouldDeclareFinalizer|
|CheckId|CA2216|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName>a obsahuje pole, které naznačují použití nespravovaných prostředků, neimplementuje finalizační metody podle <xref:System.Object.Finalize%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Narušení toto pravidlo bude nahlášena, pokud na jedno použití typ obsahuje pole z následujících typů:

-   <xref:System.IntPtr?displayProperty=fullName>

-   <xref:System.UIntPtr?displayProperty=fullName>

-   <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, implementujte finalizační metodu, která volá vaše <xref:System.IDisposable.Dispose%2A> metoda.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, je-li typ neimplementuje <xref:System.IDisposable> za účelem uvolnění nespravovaných prostředků.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo.

 [!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2115: Volejte GC.KeepAlive při použití nativních zdrojů](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816: Volejte správně GC.SuppressFinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA1049: Typy, které vlastní nativní prostředky by měly být uvolnitelné](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)

## <a name="see-also"></a>Viz také
 <xref:System.IDisposable?displayProperty=fullName> <xref:System.IntPtr?displayProperty=fullName> <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> <xref:System.UIntPtr?displayProperty=fullName> <xref:System.Object.Finalize%2A?displayProperty=fullName> [Dispose – vzor](/dotnet/standard/design-guidelines/dispose-pattern)