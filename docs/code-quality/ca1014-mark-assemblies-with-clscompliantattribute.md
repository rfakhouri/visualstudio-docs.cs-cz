---
title: 'CA1014: Označte sestavení pomocí CLSCompliantAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3c97d7731cc3bbad98ce5b62346bab1b7d5029ea
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986641"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Označte sestavení pomocí CLSCompliantAttribute

|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Sestavení nemá <xref:System.CLSCompliantAttribute?displayProperty=fullName> byt aplikovaný atribut.

## <a name="rule-description"></a>Popis pravidla
 Specifikace Common Language Specification (CLS) definuje omezení názvů, datové typy a pravidla, která musí sestavení dodržovat, pokud budou použita napříč programovacími jazyky. Dobrý návrh přikazuje, aby všechna sestavení explicitně uvedla dodržování specifikace CLS <xref:System.CLSCompliantAttribute>. Pokud atribut není v sestavení přítomen, nedodržuje sestavení předpisy.

 Je možné, kompatibilní se Specifikací CLS sestavení obsahují typy nebo členy, které nejsou kompatibilní s typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte atribut do sestavení. Namísto označení celé sestavení jako nesplňující požadavky, měli byste určit, které typ nebo členy typu jsou nekompatibilní a označte tyto prvky jako takové. Pokud je to možné by měl poskytovat alternativy CLS pro členy nesplňující požadavky, aby na nejširší možné cílovou skupinu dostanete všechny funkce, které jsou součástí vašeho sestavení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Pokud nechcete, aby sestavení, aby vyhovoval předpisům, použijte atribut a nastavte jej na hodnotu `false`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje sestavení, který má <xref:System.CLSCompliantAttribute?displayProperty=fullName> atribut, který deklaruje kompatibilní se Specifikací CLS.

 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>Viz také:

- <xref:System.CLSCompliantAttribute?displayProperty=fullName>
- [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)