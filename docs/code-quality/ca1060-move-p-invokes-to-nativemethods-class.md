---
title: 'CA1060: Přesuňte P-vyvolá do třídy NativeMethods'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
helpviewer_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 806721f5d2d02752be539675571fbcef16696ebf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060: Přesuňte volání nespravovaných kódů do třídy NativeMethods
|||
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda služby volání nespravovaného používá pro přístup k nespravovaného kódu a není členem jedné z **NativeMethods** třídy.

## <a name="rule-description"></a>Popis pravidla
 Volání metody platformy, jako jsou ty, které jsou označené pomocí <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atribut nebo metody, které jsou definované za použití `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], přístup k nespravovanému kódu. Tyto metody by měla být v jednom z následujících tříd:

-   **NativeMethods** -Tato třída nepotlačuje zásobníku pro oprávnění nespravovaného kódu. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> nesmí použít pro tuto třídu.) Tato třída je pro metody, které lze použít kdekoli, protože se provede procházení zásobníku.

-   **SafeNativeMethods** -Tato třída potlačí zásobníku pro oprávnění nespravovaného kódu. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> se použije pro tuto třídu.) Tato třída je pro metody, které jsou bezpečné pro přístup každý, kdo k volání. Volající z těchto metod není nutné provádět úplnou kontrolu, abyste měli jistotu, že využití je bezpečná, protože se neškodné pro všechny volající metody.

-   **UnsafeNativeMethods** -Tato třída potlačí zásobníku pro oprávnění nespravovaného kódu. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> se použije pro tuto třídu.) Tato třída je pro metody, které jsou potenciálně nebezpečné. Všechny volající z těchto metod, musíte provést úplnou kontrolu, abyste měli jistotu, že využití je bezpečná, protože se provede žádné procházení zásobníku.

 Tyto třídy jsou deklarovány jako `internal` (`Friend`, v jazyce Visual Basic) a deklarovat soukromý konstruktor zabránit vytváří nové instance. Metody v těchto tříd by měla být `static` a `internal` (`Shared` a `Friend` v jazyce Visual Basic).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přesunout do odpovídající metodu **NativeMethods** třídy. Pro většinu aplikací přesunutí P/vyvolá novou třídu s názvem **NativeMethods** je dost.

 Ale pokud vyvíjíte knihovny pro použití v ostatních aplikacích, měli byste zvážit definování dvě třídy, které se nazývají **SafeNativeMethods** a **UnsafeNativeMethods**. Tyto třídy vypadat **NativeMethods** třídy; ale jsou označené pomocí speciálním názvem atributu **SuppressUnmanagedCodeSecurityAttribute**. Když tento atribut se používá, modul runtime neprovádí úplné zásobníku a ujistěte se, že všechny volající mají **UnmanagedCode** oprávnění. Modul runtime normálně zkontroluje toto oprávnění při spuštění. Protože ověřování se neprovádí, může výrazně zlepšit výkon volání těchto metod, nespravované, taky umožňuje kód, který má omezená oprávnění k volání těchto metod.

 Tento atribut by měl však použít velmi obezřetně. Pokud je nesprávně implementovaný může mít vliv na závažnou zabezpečení...

 Informace o tom, jak implementovat metodu, najdete v článku **NativeMethods** například **SafeNativeMethods** příklad, a **UnsafeNativeMethods** příklad.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad deklaruje metodu, která porušuje toto pravidlo. Chcete-li opravit porušení, **RemoveDirectory** P/Invoke přesunout do příslušné třídy, která je určená k uložení pouze P/vyvolá.

 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_1.vb)]
 [!code-csharp[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_1.cs)]

## <a name="nativemethods-example"></a>Příklad NativeMethods

### <a name="description"></a>Popis
 Protože **NativeMethods** třída by neměl být označena pomocí **SuppressUnmanagedCodeSecurityAttribute**, bude vyžadovat P/vyvolá, která jsou chápat **UnmanagedCode** oprávnění. Protože spouštět většinu aplikací z místního počítače a spustit společně s úplným vztahem důvěryhodnosti, to je obvykle není problém. Ale pokud vyvíjíte opakovaně použitelné knihovny, měli byste zvážit definování **SafeNativeMethods** nebo **UnsafeNativeMethods** třídy.

 Následující příklad ukazuje **Interaction.Beep** metoda, která zabalí **MessageBeep** funkce z user32.dll. **MessageBeep** P/Invoke uveden **NativeMethods** třídy.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_2.cs)]
 [!code-vb[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_2.vb)]

## <a name="safenativemethods-example"></a>Příklad SafeNativeMethods

### <a name="description"></a>Popis
 P/Invoke metody, které mohou být bezpečně zpřístupněny všechny aplikace a které nemají žádné vedlejší účinky měly být umístěny na třídu, která je s názvem **SafeNativeMethods**. Nemáte oprávnění k vyžádání a není nutné věnovat pozornost mnohem kdy jsou volány z.

 Následující příklad ukazuje **Environment.TickCount** vlastnost, která zabalí **GetTickCount** funkce z kernel32.dll.

### <a name="code"></a>Kód
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_3.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_3.cs)]

## <a name="unsafenativemethods-example"></a>Příklad UnsafeNativeMethods

### <a name="description"></a>Popis
 P/Invoke metody, které nelze bezpečně volat a které by mohly způsobit vedlejší účinky měly být umístěny na třídu, která je s názvem **UnsafeNativeMethods**. Tyto metody pečlivě zkontrolovat a ujistěte se, že nejsou uživateli neúmyslnému zveřejnění. Pravidlo [CA2118: revize použití SuppressUnmanagedCodeSecurityAttribute](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) můžou pomoct se to. Alternativně metody by měl mít jiné oprávnění, které je požadováno místo **UnmanagedCode** při jejich použití.

 Následující příklad ukazuje **Cursor.Hide** metoda, která zabalí **ShowCursor** funkce z user32.dll.

### <a name="code"></a>Kód
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_4.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_4.cs)]

## <a name="see-also"></a>Viz také
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)