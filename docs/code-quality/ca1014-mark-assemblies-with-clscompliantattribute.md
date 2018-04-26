---
title: 'CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51e5a43a402bb215a939b37354dd30f24e4d5d14
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute
|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Sestavení nemá <xref:System.CLSCompliantAttribute?displayProperty=fullName> byt aplikovaný atribut.

## <a name="rule-description"></a>Popis pravidla
 Specifikace Common Language Specification (CLS) definuje omezení názvů, datové typy a pravidla, která musí sestavení dodržovat, pokud budou použita napříč programovacími jazyky. Dobrý návrh stanoví, že ve všech sestaveních explicitně označovat souladu se specifikací CLS s <xref:System.CLSCompliantAttribute>. Pokud atribut neexistuje na sestavení, není kompatibilní s sestavení.

 Je možné pro kompatibilní se specifikací CLS sestavení a obsahují typy nebo zadejte členy, kteří jsou nekompatibilní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, přidejte atribut sestavení. Místo označení celé sestavení jako nesplňující požadavky, měli byste určit typ nebo členy typu jsou nekompatibilní a označit jako takový tyto prvky. Pokud je to možné by měl poskytovat kompatibilní se specifikací CLS alternativní pro nekompatibilní členy, aby nejširší možnou cílovou skupinou přístup všechny funkce vašeho sestavení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Pokud nechcete, aby sestavení tak, aby vyhovoval, použijte atribut a jeho hodnotu nastavte `false`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, sestavení, který má <xref:System.CLSCompliantAttribute?displayProperty=fullName> použít atribut, který deklaruje kompatibilní se specifikací CLS.

 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>Viz také
 <xref:System.CLSCompliantAttribute?displayProperty=fullName> [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)