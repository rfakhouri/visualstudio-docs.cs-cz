---
title: 'CA2238: Implementujte správně metody serializace'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
helpviewer_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
ms.assetid: 00882cf9-e10d-4d40-9126-3e6753e3c934
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 54a26c2b941289ed7a83e66e1677db172660d270
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920252"
---
# <a name="ca2238-implement-serialization-methods-correctly"></a>CA2238: Implementujte správně metody serializace
|||
|-|-|
|TypeName|ImplementSerializationMethodsCorrectly|
|CheckId|CA2238|
|Kategorie|Microsoft.Usage|
|Narušující změna|Ukončování řádků – Pokud je metoda viditelné mimo sestavení.<br /><br /> Bez narušující – Pokud metoda není viditelná mimo sestavení.|

## <a name="cause"></a>příčina
 Metoda, která zpracovává událost serializace, nemá správný podpis, návratový typ nebo viditelnost.

## <a name="rule-description"></a>Popis pravidla
 Metoda je určen obslužnou rutinu události serializace a to použitím jednoho z následujících atributů serializace událostí:

-   <xref:System.Runtime.Serialization.OnSerializingAttribute?displayProperty=fullName>

-   <xref:System.Runtime.Serialization.OnSerializedAttribute?displayProperty=fullName>

-   <xref:System.Runtime.Serialization.OnDeserializingAttribute?displayProperty=fullName>

-   <xref:System.Runtime.Serialization.OnDeserializedAttribute?displayProperty=fullName>

 Obslužné rutiny událostí serializace trvat jeden parametr typu <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>, vrátí `void`a mít `private` viditelnosti.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, opravte podpis, návratový typ nebo viditelnost obslužné rutiny události serializace.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje správně deklarované serializace obslužné rutiny událostí.

 [!code-vb[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/VisualBasic/ca2238-implement-serialization-methods-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/CSharp/ca2238-implement-serialization-methods-correctly_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volejte metody třídy Base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)