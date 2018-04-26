---
title: 'CA2240: Implementujte správně ISerializable'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bfd13bb09e8e9e3338ed37723f74ca42b09fdeb3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: Implementujte správně ISerializable
|||
|-|-|
|TypeName|ImplementISerializableCorrectly|
|CheckId|CA2240|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Typ externě viditelné je přiřadit k <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> platí rozhraní a jedno z následujících podmínek:

-   Typ dědí ale nemůže přepsat <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metoda a typ deklaruje pole instance, které nejsou označené jako <xref:System.NonSerializedAttribute?displayProperty=fullName> atribut.

-   Typ, není zapečetěná a typ implementuje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda, která není externě viditelné a přepisovatelné.

## <a name="rule-description"></a>Popis pravidla
 Instance pole, které jsou deklarované v typ, který dědí <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní nejsou automaticky součástí procesu serializace. Vyberte pole, musí typ implementovat <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda a konstruktor serializace. Pokud pole nesmí být serializován, budou použity <xref:System.NonSerializedAttribute> atribut pole explicitně udávajících rozhodnutí.

 Typy, které nejsou zapečetěná implementace <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda by měla být externě viditelné. Proto metodu lze volat odvozené typy a je přepisovatelné.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, ujistěte se, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda viditelné a přepisovatelné a zajistěte, aby všechny instance pole jsou součástí procesu serializace nebo explicitně označené jako <xref:System.NonSerializedAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva Serializovatelné typy, které porušují pravidlo.

 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]

## <a name="example"></a>Příklad
 Následující příklad opravy dva předchozí porušení tím, že poskytuje přepisovatelné implementace <xref:System.Runtime.Serialization.ISerializable.GetObjectData> na třídě adresáře a tím, že poskytuje implementaci pro `GetObjectData` na třídy knihovny.

 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volejte metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md) [CA2229: implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md) [CA2238: implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md) [ CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md) [CA2237: typy označit ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md) [CA2239: Zadejte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md) [CA2120: zabezpečené Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)
