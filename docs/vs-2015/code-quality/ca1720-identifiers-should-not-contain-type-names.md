---
title: 'CA1720: Identifikátory by neměly obsahovat názvy typů | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 504c985bd276a891b76e8c9b2a7c0ef51c3a490a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62576715"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: Identifikátory by neměly obsahovat názvy typů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Název parametru v externě viditelném členu obsahuje název datového typu.

 -nebo-

 Název externě viditelného členu obsahuje název typu dat pro konkrétní jazyk.

## <a name="rule-description"></a>Popis pravidla
 Názvy parametrů a členů se lépe používají ke komunikaci jejich význam než se popisují jejich typ, který má být poskytuje nástroje pro vývoj. Pro názvy členů Pokud je třeba zadat název datového typu, použijte název nezávislým na jazyku místo jeden konkrétní jazyk. Například místo C# typu název "int", použijte název typu nezávislým na jazyku dat datový typ Int32.

 Každý samostatný token název parametru nebo člen je porovnávána s následující názvy typů dat pro konkrétní jazyk, v podobě velká a malá písmena:

- Bool

- WChar

- Int8

- UInt8

- Krátké

- UShort

- Int

- UInt

- Integer

- UInteger

- Dlouhé

- ULong

- bez znaménka

- podepsané

- Float

- Float32

- Float64

  Kromě toho názvy parametru jsou zkontrolovány také proti následující názvy typů dat nezávislým na jazyku písmen:

- Objekt

- Obj

- Boolean

- Char

- String

- SByte

- Byte

- UByte

- Int16

- UInt16

- Int32

- UInt32

- Int64

- UInt64

- IntPtr

- Ptr

- Ukazatel

- UInptr

- UPtr

- UPointer

- Single

- Double

- Desetinné číslo

- Guid

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 **Pokud je aktivována před parametr:**

 Nahraďte datového typu identifikátoru názvu parametru termín, který lépe popisuje jeho význam nebo obecnějším pojmem, jako například 'value'.

 **Pokud je aktivována před členem:**

 Nahraďte konkrétní jazyk datového typu identifikátoru název člena termín, který lépe popisuje jeho význam, jazykově nezávislým ekvivalentem nebo obecnějším pojmem, jako například 'value'.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Příležitostné použití založené na typ parametru a člen názvů může být vhodné. Ale pro vývoj, žádné známé scénáře nastat, pokud by měla potlačit upozornění tohoto pravidla. Pro knihovny, které mají předchozí dodán budete muset potlačit upozornění tohoto pravidla.

## <a name="related-rules"></a>Související pravidla
 [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)

 [CA1719: Názvy parametrů by neměly odpovídat názvům členů](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)
