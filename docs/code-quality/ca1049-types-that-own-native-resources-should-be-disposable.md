---
title: 'CA1049: Typy, které vlastní nativní prostředky by měly být uvolnitelné'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 6484d6d6313db543f0e80a1e66c3051839fe0a06
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: Typy, které vlastní nativní prostředky by měly být uvolnitelné
|||
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Odkazuje na typ <xref:System.IntPtr?displayProperty=fullName> pole, <xref:System.UIntPtr?displayProperty=fullName> pole, nebo <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> pole, ale neimplementuje <xref:System.IDisposable?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo předpokládá, že <xref:System.IntPtr>, <xref:System.UIntPtr>, a <xref:System.Runtime.InteropServices.HandleRef> pole úložiště ukazatele na nespravovaných prostředků. Typy, které přidělují nespravované prostředky by měla implementovat <xref:System.IDisposable> umožníte volající k uvolnění těchto prostředků na vyžádání a zkraťte životnosti objektů, které mají prostředky.

 Doporučený návrh vzor vymazání nespravovaných prostředků je poskytnout implicitní i prostředku explicitní k uvolnění těchto prostředků s použitím <xref:System.Object.Finalize%2A?displayProperty=fullName> metoda a <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metoda, v uvedeném pořadí. Volání systém uvolňování paměti <xref:System.Object.Finalize%2A> metoda objektu někdy neurčitém po objekt je určen už být dostupná. Po <xref:System.Object.Finalize%2A> je volána, další uvolňování paměti je potřeba na uvolnění objektu. <xref:System.IDisposable.Dispose%2A> Metoda umožňuje volajícímu explicitně uvolnění prostředků na vyžádání, dříve, než prostředky by vydání, pokud je ponecháno pro uvolňování paměti. Po jeho vyčistí nespravované prostředky <xref:System.IDisposable.Dispose%2A> by měly volat <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> metoda umožníte uvolňování vědět, že <xref:System.Object.Finalize%2A> už má být volána; tím se eliminuje potřeba další uvolnění paměti a zkracuje Doba života objektu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, implementujte <xref:System.IDisposable>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, je-li typ neodkazuje nespravovaných prostředků. Jinak není potlačit upozornění na toto pravidlo protože selhání implementovat <xref:System.IDisposable> může způsobit, že se k dispozici nebo využívané nespravovaných prostředků.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který implementuje <xref:System.IDisposable> vymazání nespravovaných prostředků.

 [!code-csharp[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA2115: Volejte GC.KeepAlive při použití nativních zdrojů](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816: Volejte správně GC.SuppressFinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA1001: Typy vlastních uvolnitelných polí, které by měly být uvolnitelné](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>Viz také
 [Vymazání nespravovaných prostředků](/dotnet/standard/garbage-collection/unmanaged) [Dispose – vzor](/dotnet/standard/design-guidelines/dispose-pattern)