---
title: 'CA2205: Použijte spravované ekvivalenty rozhraní Win32 API'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: d964cdbe94822fc6156e25320e723cd10fe7d853
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919961"
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205: Použijte spravované ekvivalenty rozhraní Win32 API
|||
|-|-|
|TypeName|UseManagedEquivalentsOfWin32Api|
|CheckId|CA2205|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Vyvolání platformy metoda je definovaný a metodu s ekvivalentní funkce existuje v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] knihovny tříd.

## <a name="rule-description"></a>Popis pravidla
 Platformu vyvolání metody se používá k volání nespravované funkce DLL a je definován pomocí <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atribut, nebo `Declare` – klíčové slovo v jazyce Visual Basic. Nesprávně definované platformy vyvolání metody může vést k výjimky za běhu kvůli problémům, jako je například misnamed funkce vadný mapování parametru a návratové hodnoty datových typů a specifikace nesprávné pole, jako je znak a konvence volání Sada. Pokud je k dispozici, je obvykle jednodušší a méně náchylný volat metodu ekvivalentní spravované než chcete definovat a volejte metodu nespravované přímo. Volání metody platformu vyvolání metody může vést k další bezpečnostní problémy, které je třeba vzít v úvahu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, nahraďte volání nespravovaného funkce volání na ekvivalentní spravované.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačíte upozornění na toto pravidlo, je-li metoda navrhované nahrazení neposkytuje potřebné funkce.

## <a name="example"></a>Příklad
 Následující příklad ukazuje a platformy vyvolání definici metody, která porušuje pravidlo. Kromě toho volání pro platformu vyvolání metody a metodu ekvivalentní spravované jsou zobrazeny.

 [!code-csharp[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/CSharp/ca2205-use-managed-equivalents-of-win32-api_1.cs)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/VisualBasic/ca2205-use-managed-equivalents-of-win32-api_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1404: Volejte GetLastError ihned po volání P/Invoke](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)

 [CA1060: Přesuňte P/vyvolá do třídy NativeMethods](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

 [CA1400: Vstupní body P/Invoke by měla existovat.](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [CA1401: P/by neměla být viditelné](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101: Určete zařazování pro argumenty řetězce P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)