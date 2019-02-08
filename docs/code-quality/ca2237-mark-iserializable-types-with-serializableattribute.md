---
title: 'CA2237: Označte typy ISerializable pomocí SerializableAttribute'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7ccc7819de8e79cae86a60fd015e6b8268c2456c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55944543"
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237: Označte typy ISerializable pomocí SerializableAttribute

|||
|-|-|
|TypeName|MarkISerializableTypesWithSerializable|
|CheckId|CA2237|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Externě viditelný typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní a typ není označen atributem <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Pravidlo ignoruje odvozené typy, jehož základní typ není serializovatelný.

## <a name="rule-description"></a>Popis pravidla
 Chcete-li rozpoznán modulem common language runtime jako serializovatelný, musí být označen pomocí <xref:System.SerializableAttribute> atribut i v případě, že typ používá vlastní rutinu serializace prostřednictvím implementace <xref:System.Runtime.Serialization.ISerializable> rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.SerializableAttribute> atribut typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla pro třídy výjimek, protože musí být serializovatelný fungování napříč doménami aplikace.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla. Zrušením komentáře u <xref:System.SerializableAttribute> atribut řádku splňovat pravidla.

 [!code-vb[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/VisualBasic/ca2237-mark-iserializable-types-with-serializableattribute_1.vb)]
 [!code-csharp[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/CSharp/ca2237-mark-iserializable-types-with-serializableattribute_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volání metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)