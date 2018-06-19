---
title: 'CA2237: Označte typy ISerializable pomocí SerializableAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b7efc13eaee32662688593ff0cb94d9c0cb7a8a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920080"
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237: Označte typy ISerializable pomocí SerializableAttribute
|||
|-|-|
|TypeName|MarkISerializableTypesWithSerializable|
|CheckId|CA2237|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Implementuje externě viditelného typu <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní a typ není označen atributem <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Pravidlo ignoruje odvozené typy, jehož základní typ není serializovatelný.

## <a name="rule-description"></a>Popis pravidla
 Rozpoznala modul common language runtime jako serializable, musí být označen typy <xref:System.SerializableAttribute> atribut i v případě, že typ používá vlastní serializace rutiny prostřednictvím implementace <xref:System.Runtime.Serialization.ISerializable> rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, použít <xref:System.SerializableAttribute> atributu typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Protože musí být serializovatelný ke správnému napříč doménami aplikací není potlačení upozornění od tohoto pravidla pro třídy výjimek.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidlo. Zrušením komentáře u <xref:System.SerializableAttribute> atribut řádku splňovat pravidla.

 [!code-vb[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/VisualBasic/ca2237-mark-iserializable-types-with-serializableattribute_1.vb)]
 [!code-csharp[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/CSharp/ca2237-mark-iserializable-types-with-serializableattribute_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volejte metody třídy Base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)