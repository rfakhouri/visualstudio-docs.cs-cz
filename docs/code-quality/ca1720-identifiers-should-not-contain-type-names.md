---
title: 'CA1720: Identifikátory by neměly obsahovat názvy typů'
ms.date: 03/11/2019
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0eb7cfeb2271b7ed01f59d4892987fb2ef72808
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546567"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: Identifikátory by neměly obsahovat názvy typů

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Název parametru v člena obsahuje název datového typu.

-nebo-

Název členu obsahuje název typu dat pro konkrétní jazyk.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné členy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Názvy parametrů a členů se lépe používají ke komunikaci jejich význam než se popisují jejich typ, který má být poskytuje nástroje pro vývoj. Pro názvy členů Pokud je třeba zadat název datového typu, použijte název nezávislým na jazyku místo jeden konkrétní jazyk. Například místo nástroje C# název typu `int`, použít název typu nezávislým na jazyku data `Int32`.

Každý samostatný token název parametru nebo člen je porovnávána s následující názvy typů dat pro konkrétní jazyk v podobě velká a malá písmena:

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

Příležitostné použití založené na typ parametru a člen názvů může být vhodné. Ale pro vývoj, žádné známé scénáře nastat, pokud by měla potlačit upozornění tohoto pravidla. Pro knihovny, které byly dříve součástí budete muset potlačit upozornění tohoto pravidla.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1720.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

- [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1719: Názvy parametrů by neměly odpovídat názvům členů](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)