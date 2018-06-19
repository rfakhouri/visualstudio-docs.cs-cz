---
title: 'CA1400: Vstupní body vyvolání P by měla existovat.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1400
- PInvokeEntryPointsShouldExist
helpviewer_keywords:
- PInvokeEntryPointsShouldExist
- CA1400
ms.assetid: 1d64e470-7b2f-4cca-8fb0-ac92829e6332
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36bd2e74b5abb021b66dda8ddd62260cc58fe181
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901657"
---
# <a name="ca1400-pinvoke-entry-points-should-exist"></a>CA1400: Vstupní body volání nespravovaného kódu by měly existovat
|||
|-|-|
|TypeName|PInvokeEntryPointsShouldExist|
|CheckId|CA1400|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda veřejných nebo chráněné je označena <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Nespravovanou knihovnu nelze nalézt nebo nelze metodu porovnat s funkcí v knihovně. Pokud pravidlo nelze najít název metody, přesně tak, jak je zadán, bude hledat ANSI nebo verze široká charakterová metody pomocí suffixing název metody s "A" nebo "W". Pokud není nalezena žádná shoda, pravidlo se pokusí najít funkci ve formátu názvu __stdcall (_MyMethod@12, kde 12 představuje délku argumentů). Pokud není nalezena žádná shoda, a název metody začíná '#', toto pravidlo vyhledá funkce jako odkaz na pořadovém místě místo odkaz na název.

## <a name="rule-description"></a>Popis pravidla
 Je k dispozici pro Ujistěte se, že žádná kontrola kompilaci metody, které jsou označené <xref:System.Runtime.InteropServices.DllImportAttribute> jsou umístěné v odkazované nespravované knihovny DLL. Pokud žádné funkce, která má zadaný název je v knihovně nebo argumenty pro metodu neodpovídají žádné argumenty funkce, modul common language runtime vyvolá výjimku.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, opravte metodu, která má <xref:System.Runtime.InteropServices.DllImportAttribute> atribut. Ujistěte se, že nespravované knihovny existuje a je ve stejném adresáři jako sestavení, které obsahuje metodu. Pokud je knihovna přítomna a správně odkazované, ověřte, že název metody, návratový typ a argument podpis odpovídají funkce knihovny.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Při nespravované knihovna je ve stejném adresáři jako spravované sestavení, které na ni odkazuje není potlačit upozornění na toto pravidlo. Může to být bezpečné potlačit upozornění na toto pravidlo v případě, kde nespravované knihovny nelze najít.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidlo. Žádná funkce s názvem `DoSomethingUnmanaged` v kernel32.dll dojde.

 [!code-csharp[FxCop.Interoperability.DLLExists#1](../code-quality/codesnippet/CSharp/ca1400-p-invoke-entry-points-should-exist_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>