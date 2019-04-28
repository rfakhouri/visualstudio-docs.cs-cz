---
title: 'CA1415: Deklarujte správně volání nespravovaných kódů'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da6448a414437a07b545a999b35031f82e9a8689
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546183"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: Deklarujte správně volání nespravovaných kódů

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Bez konce – Pokud P/Invoke, který deklaruje parametr je nemohou vidět mimo sestavení. Rozdělení - P/Invoke, který deklaruje parametr viditelné mimo sestavení.|

## <a name="cause"></a>Příčina
 Metoda vyvolání platformy je deklarován nesprávně.

## <a name="rule-description"></a>Popis pravidla
 Platforma vyvolat metodu přístupy do nespravovaného kódu a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. V současné době toto pravidlo hledá deklarace metod, které se zaměřují na funkce Win32, které mají ukazatel na parametr struktury OVERLAPPED vyvolání platformy a odpovídající spravovaný parametr není ukazatel <xref:System.Threading.NativeOverlapped?displayProperty=fullName> struktury.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, deklarujte správně platformu vyvolání metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metody, které porušují pravidlo a splňovat pravidla vyvolání platformy.

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>Viz také:
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)