---
title: 'CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e4455373338cda463623c75ff099a1c706f589dc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897630"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6
|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ, který je specificky označen jako viditelný na modelu COM (Component Object) člena deklaruje, že trvá <xref:System.Int64?displayProperty=fullName> argument.

## <a name="rule-description"></a>Popis pravidla
 Visual Basic 6 COM klienti nemají přístup k 64bitových celých čísel.

 Ve výchozím nastavení, jsou viditelné pro COM následující: sestavení, veřejné typy, členy veřejné instance ve veřejné typy a všichni členové typů veřejné hodnot. Však snížil počet falešných poplachů, toto pravidlo vyžaduje COM viditelnost typ, který má být explicitně uvedena; musí být označen obsahující sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> nastavena na `false` a typ musí být označené jako <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `true`.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení tohoto pravidla pro parametr, jehož hodnota může být vždy vyjádřený jako integrální 32-bit, změnit typ parametru na <xref:System.Int32?displayProperty=fullName>. Pokud hodnota parametru může být větší, než může být vyjádřený jako integrální 32-bit, změňte typ parametru pro <xref:System.Decimal?displayProperty=fullName>. Všimněte si, že oba <xref:System.Single?displayProperty=fullName> a <xref:System.Double?displayProperty=fullName> ztratit přesnost v horní Rozsahy <xref:System.Int64> datového typu. Pokud člen by neměl být viditelné modelu COM, označte jej pomocí <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `false`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, jestliže je zajištěno, že klienti COM Visual Basic 6 nebude přístup k typu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidlo.

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/CSharp/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.cs)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/VisualBasic/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Viz také
 [Spolupráce pomocí nespravovaného kódu](/dotnet/framework/interop/index) [Long – datový typ](/dotnet/visual-basic/language-reference/data-types/long-data-type)