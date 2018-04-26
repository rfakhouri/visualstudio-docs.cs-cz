---
title: 'CA2239: Poskytujte metody deserializace pro nepovinné pole'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04d3e40c73a02c43ecfb13eda0abcfabcb0d3ad5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239: Poskytujte metody deserializace pro nepovinné pole
|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Typ obsahuje pole, která je označena pomocí <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> atribut a typ neposkytuje zpracování metody deaktivace serializace událostí.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Runtime.Serialization.OptionalFieldAttribute> Atribut nemá žádný vliv na serializace; pole s atributem serializován. Pole však je na deaktivace serializace ignorována a zachová výchozí hodnotu přidruženou k jeho typu. Obslužné rutiny událostí deaktivace serializace by měl být deklarován nastavit pole během procesu deaktivace serializace.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přidejte zpracování metody pro typ deaktivace serializace událostí.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, je-li pole třeba ji ignorovat během procesu deaktivace serializace.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ s volitelné pole a deaktivace serializace událostí obslužné metody.

 [!code-csharp[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/CSharp/ca2239-provide-deserialization-methods-for-optional-fields_1.cs)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/VisualBasic/ca2239-provide-deserialization-methods-for-optional-fields_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volejte metody třídy Base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)