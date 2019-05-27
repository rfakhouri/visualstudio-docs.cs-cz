---
title: 'CA2235: Označte všechna neserializovatelná pole'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5ebfa5e9b90951acf59c8214941b93adae76d06e
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177385"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Označte všechna neserializovatelná pole

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Neserializovatelný typ pole instance je deklarován v serializovatelném typu.

## <a name="rule-description"></a>Popis pravidla

Serializovatelný typ. je ten, který je označen <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Když je typ serializován, <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> je vyvolána výjimka, pokud typ obsahuje pole instance typu, který není serializovatelný *a* neimplementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní.

> [!TIP]
> CA2235 neaktivuje pro instanci pole typů, které implementují <xref:System.Runtime.Serialization.ISerializable> protože poskytují své vlastní logiky serializace.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.NonSerializedAttribute?displayProperty=fullName> atributu na pole, který není serializovatelný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pouze v případě potlačit upozornění tohoto pravidla <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> typ je deklarován, která umožňuje instance pole, které chcete serializovat a deserializovat.

## <a name="example"></a>Příklad

Následující příklad ukazuje dva typy: ten, který porušuje pravidla a ten, který splňuje pravidlo.

[!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
[!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]

## <a name="remarks"></a>Poznámky

Pravidlo CA2235 nebudou analyzované typy, které implementují <xref:System.Runtime.Serialization.ISerializable> rozhraní (pokud jsou také označena <xref:System.SerializableAttribute> atributu). Důvodem je, že [pravidlo CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md) již doporučuje označit typy, které implementují <xref:System.Runtime.Serialization.ISerializable> rozhraní se službou <xref:System.SerializableAttribute> atribut.

## <a name="related-rules"></a>Související pravidla

- [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2236: Volání metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)
- [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)