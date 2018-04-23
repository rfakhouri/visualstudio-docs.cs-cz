---
title: 'CA1901: Deklarace vyvolání P by měla být přenosná'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 45adbedf9318c70b1e73088765cf5487d997d1e3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: Deklarace volání nespravovaného kódu by měla být přenosná
|||
|-|-|
|TypeName|PInvokeDeclarationsShouldBePortable|
|CheckId|CA1901|
|Kategorie|Microsoft.Portability|
|Narušující změna|Ukončování řádků - P/Invoke je zobrazen mimo sestavení. Bez narušující – Pokud P/Invoke není viditelná mimo sestavení.|

## <a name="cause"></a>příčina
 Toto pravidlo vyhodnotí velikost jednotlivých parametrů a vrátí hodnotu, která P/Invoke a ověřuje, že jejich velikost, při zařazen do nespravovaného kódu na 32bitové a 64bitové verze platformy, je správné. Nejběžnější porušení toto pravidlo je předat celé číslo s pevnou velikostí, kdy je potřeba proměnnou závislé na platformě, velikost ukazatele.

## <a name="rule-description"></a>Popis pravidla
 Některý z následujících scénářů porušuje toto pravidlo dojde k:

-   Návratová hodnota nebo parametr je zadán jako celé číslo pevné velikosti při by měl být zadán jako `IntPtr`.

-   Návratová hodnota nebo parametr je zadán jako `IntPtr` při by měl být zadán jako celé číslo pevnou velikostí.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Tato porušení můžete opravit pomocí `IntPtr` nebo `UIntPtr` k reprezentaci obslužné rutiny místo `Int32` nebo `UInt32`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění nesmí potlačit.

## <a name="example"></a>Příklad
 Následující příklad ukazuje narušení tohoto pravidla.

```csharp
internal class NativeMethods
{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, IntPtr nIconIndex);
}
```

 V tomto příkladu `nIconIndex` parametr je deklarován jako `IntPtr`, což je 4 bajtů široké na 32bitové platformě a 8 bajtů široké na 64bitové platformě. V nespravované deklaraci, která následuje, můžete uvidíte, že `nIconIndex` je celé číslo bez znaménka 4bajtový na všech platformách.

```csharp
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,
    UINT nIconIndex);
```

## <a name="example"></a>Příklad
 Opravit porušení zásady, změňte deklaraci na následující:

```csharp
internal class NativeMethods{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)] 
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, uint nIconIndex);
}
```

## <a name="see-also"></a>Viz také
 [Upozornění přenositelnosti](../code-quality/portability-warnings.md)