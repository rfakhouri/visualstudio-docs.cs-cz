---
title: 'CA1720: Identifikátory by neměly obsahovat názvy typů'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8f86037b54b2b7ad5cce1ea683341ca6656c2b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: Identifikátory by neměly obsahovat názvy typů
|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název parametru v externě viditelné člen obsahuje název datového typu.

 -nebo-

 Název člena externě viditelné obsahuje název typu dat pro specifický jazyk.

## <a name="rule-description"></a>Popis pravidla
 Názvy parametrů a členové jsou lépe používá ke komunikaci jejich význam než se popisují jejich typu, který je poskytovaný nástroje pro vývoj. Pro názvy členů Pokud je třeba zadat název typu dat, použijte název nezávislé na jazyku místo jeden konkrétní jazyk. Například místo C# typ název, int', použijte název typu dat nezávislé na jazyku Int32.

 Každý diskrétní token názvu parametru nebo člen je zkontrolován následující názvy typů dat pro specifický jazyk způsobem velká a malá písmena:

-   BOOL

-   WChar

-   int8

-   UInt8

-   krátký

-   Ushort –

-   celá čísla

-   UInt

-   Integer

-   Uinteger –

-   dlouhá

-   Ulong –

-   Bez znaménka

-   Podepsané

-   Plovoucí desetinná čárka

-   Float32

-   Float64

 Kromě toho názvy parametru jsou také zkontrolován následující názvy typů dat nezávislé na jazyku způsobem velká a malá písmena:

-   Objekt

-   Obj

-   Boolean

-   Char

-   String

-   SByte

-   Byte

-   UByte

-   Int16

-   UInt16

-   Int32

-   UInt32

-   Int64

-   UInt64

-   IntPtr

-   PTR

-   Ukazatele

-   UInptr

-   UPtr

-   UPointer

-   Single

-   Double

-   Desetinné číslo

-   Identifikátor GUID

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 **Pokud aktivováno proti parametr:**

 Identifikátor typu dat názvu parametru nahraďte termín, který lépe popisuje její význam nebo více obecný pojem, jako je například 'Hodnota'.

 **Pokud aktivováno proti člen:**

 Identifikátor typu dat pro specifický jazyk názvu člen nahraďte termín, který lépe popisuje její význam, nezávislé na jazyku ekvivalentní nebo více obecný pojem, jako je například 'Hodnota'.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Příležitostné použití názvů založený na typu parametru a člen může být vhodné. Ale pro nový vývoj žádné známé scénáře nastat, kde můžete potlačit upozornění na toto pravidlo. Pro knihovny, které mají předchozí dodaný můžete chtít potlačit upozornění na toto pravidlo.

## <a name="related-rules"></a>Související pravidla
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)

 [CA1719: Názvy parametrů by neměly odpovídat názvům členů](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)