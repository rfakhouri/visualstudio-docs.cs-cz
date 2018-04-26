---
title: 'CA2115: Volejte GC.KeepAlive při použití nativních zdrojů'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CallGCKeepAliveWhenUsingNativeResources
- CA2115
helpviewer_keywords:
- CA2115
- CallGCKeepAliveWhenUsingNativeResources
ms.assetid: f00a59a7-2c6a-4bbe-a1b3-7bf77d366f34
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 66621bec3316dfcee92a1e5b1d1d1a8d97ae5c54
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2115-call-gckeepalive-when-using-native-resources"></a>CA2115: Volejte GC.KeepAlive při použití nativních zdrojů
|||
|-|-|
|TypeName|CallGCKeepAliveWhenUsingNativeResources|
|CheckId|CA2115|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Metoda deklarovaného v typu s finalizační metody odkazuje <xref:System.IntPtr?displayProperty=fullName> nebo <xref:System.UIntPtr?displayProperty=fullName> pole, ale nevyvolá <xref:System.GC.KeepAlive%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Uvolňování paměti dokončí objekt, pokud nejsou žádné další odkazy na ni ve spravovaném kódu. Nespravované odkazy na objekty nebudou bránit uvolňování paměti. Toto pravidlo zjistí chyby, které mohou nastat, protože nespravovaný prostředek je finalizován v době, kdy je stále používán nespravovaným kódem.

 Toto pravidlo předpokládá, že <xref:System.IntPtr> a <xref:System.UIntPtr> pole úložiště ukazatele na nespravovaných prostředků. Protože účelem finalizační metody je uvolnění nespravovaných prostředků, pravidlo předpokládá, že finalizační metodu uvolní nespravovaný prostředek ukazující na pole ukazatel. Toto pravidlo také předpokládá, že metoda odkazuje na pole ukazatel předat nespravovaných prostředků na nespravovaný kód.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přidejte volání <xref:System.GC.KeepAlive%2A> metodu, předávání aktuální instance (`this` v C# a C++) jako argument. Pozice volání za posledním řádkem kódu, kde objekt musí být chráněný proti uvolňování paměti. Ihned po volání <xref:System.GC.KeepAlive%2A>, objekt je znovu považovat za připravené pro uvolňování paměti za předpokladu, že neexistují žádné spravované odkazy na ni.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto pravidlo vytváří některé předpoklady, které můžou vést k falešně pozitivních zjištění. Upozornění od tohoto pravidla můžete bezpečně potlačit, pokud:

-   Finalizační metodu neuvolní obsah <xref:System.IntPtr> nebo <xref:System.UIntPtr> pole odkazuje metodu.

-   Metoda nepředává <xref:System.IntPtr> nebo <xref:System.UIntPtr> pole na nespravovaný kód.

 Než je vyloučíte, pečlivě projděte další zprávy. Toto pravidlo zjistí chyby, které je obtížné reprodukujte a ladění.

## <a name="example"></a>Příklad
 V následujícím příkladu `BadMethod` nezahrnuje volání `GC.KeepAlive` a proto porušuje pravidlo. `GoodMethod` obsahuje kód opravené.

> [!NOTE]
>  V tomto příkladu je pseudo kód, i když kód zkompiluje a spustí, upozornění není aktivováno, protože není vytvořen nebo vydání nespravovaných prostředků.

 [!code-csharp[FxCop.Security.IntptrAndFinalize#1](../code-quality/codesnippet/CSharp/ca2115-call-gc-keepalive-when-using-native-resources_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.GC.KeepAlive%2A?displayProperty=fullName> <xref:System.IntPtr?displayProperty=fullName> <xref:System.Object.Finalize%2A?displayProperty=fullName> <xref:System.UIntPtr?displayProperty=fullName> [Dispose – vzor](/dotnet/standard/design-guidelines/dispose-pattern)