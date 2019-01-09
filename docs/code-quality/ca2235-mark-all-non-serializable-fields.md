---
title: 'CA2235: Označte všechna neserializovatelná pole'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 484755feac873be04648cfef936b2faa701bba2c
ms.sourcegitcommit: 73861cd0ea92e50a3be1ad2a0ff0a7b07b057a1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2019
ms.locfileid: "54154147"
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
 Serializovatelný typ. je ten, který je označen <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Když je typ serializován, <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> je vyvolána výjimka, pokud typ obsahuje pole instance typu, který není serializovatelný.
 
 Jedinou výjimkou je to je, když typ používá vlastní serializace prostřednictvím <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní. Typy implementující toto rozhraní poskytuje své vlastní logiky serializace, a proto CA2235 neaktivují pro instanci neserializovatelná pole těchto typů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.NonSerializedAttribute?displayProperty=fullName> atributu na pole, který není serializovatelný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pouze v případě potlačit upozornění tohoto pravidla <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> typ je deklarován, která umožňuje instance pole, které chcete serializovat a deserializovat.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla a typ, který splňuje pravidlo.

 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volání metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)
