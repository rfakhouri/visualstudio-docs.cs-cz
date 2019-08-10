---
title: 'CA1901: Deklarace volání nespravovaného kódu by měla být přenosná'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a45b7061ae9d183ec7ee02a3b733ee9340b3689
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921307"
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: Deklarace volání nespravovaného kódu by měla být přenosná

|||
|-|-|
|TypeName|PInvokeDeclarationsShouldBePortable|
|CheckId|CA1901|
|Kategorie|Microsoft. přenositelnost|
|Narušující změna|Přerušení – Pokud je volání nespravovaného modulu mimo sestavení viditelné. Bez přerušení – Pokud není volání nespravovaného volání mimo sestavení viditelné.|

## <a name="cause"></a>příčina
Toto pravidlo vyhodnocuje velikost každého parametru a návratovou hodnotu volání nespravovaného kódu a ověřuje, zda je jejich velikost, je-li zařazování na nespravovaný kód na 32 a 64-bitových platforem správná. Nejběžnějším porušením tohoto pravidla je předávat celé číslo s pevnou velikostí, kde je vyžadována proměnná závislá na platformě a proměnné velikosti ukazatele.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo je v rozporu s některým z následujících scénářů:

- Návratová hodnota nebo parametr je zadán jako celé číslo pevné velikosti, pokud by měl být zadán jako `IntPtr`.

- Návratová hodnota nebo parametr je zadán jako `IntPtr` , když by měl být zadán jako celé číslo s pevnou velikostí.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Toto porušení můžete opravit `IntPtr` pomocí nebo `UIntPtr` `Int32` k reprezentování popisovačů místo nebo `UInt32`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Toto upozornění byste neměli potlačit.

## <a name="example"></a>Příklad
Následující příklad demonstruje porušení tohoto pravidla.

```csharp
internal class NativeMethods
{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, IntPtr nIconIndex);
}
```

V tomto příkladu `nIconIndex` je parametr deklarovaný `IntPtr`jako, což je 4 bajty na platformě 32 a 8 bajtů v celé 64 platformě. V nespravované deklaraci, která následuje, můžete vidět `nIconIndex` , že je na všech platformách unsigned integer o velikosti 4 bajty.

```csharp
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,
    UINT nIconIndex);
```

## <a name="example"></a>Příklad
Chcete-li toto porušení opravit, změňte deklaraci na následující:

```csharp
internal class NativeMethods{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, uint nIconIndex);
}
```

## <a name="see-also"></a>Viz také:
[Upozornění přenositelnosti](../code-quality/portability-warnings.md)