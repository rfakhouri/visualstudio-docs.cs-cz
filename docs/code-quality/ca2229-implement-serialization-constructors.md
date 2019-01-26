---
title: 'CA2229: Implementujte serializační konstruktory'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 518a5d4f76d1c26893ae88f45bc74586654ee15c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951973"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: Implementujte serializační konstruktory

|||
|-|-|
|TypeName|ImplementSerializationConstructors|
|CheckId|CA2229|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Tento typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní, delegáta nebo rozhraní a je splněna jedna z následujících podmínek:

- Typ nemá konstruktor, který přijímá <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> objektu a <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> objektu (podpis serializace konstruktoru).

- Typ nezapečetěná a modifikátor přístupu pro jeho Serializační konstruktor není chráněné (řady).

- Typ je zapečetěná a modifikátor přístupu pro jeho Serializační konstruktor není soukromý.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo platí pro typy, které podporují vlastní serializace. Typ podporuje vlastní serializace v případě, že implementuje <xref:System.Runtime.Serialization.ISerializable> rozhraní. Serializační konstruktor je potřeba deserializovat, nebo znovu vytvořit objekty, které byl serializován pomocí <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Implementací konstruktoru serializace se vyřeší porušení tohoto pravidla. Pro zapečetěnou třídu musí být konstruktor soukromý. V ostatních případech musí být chráněný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte porušení tohoto pravidla. Typ nesmí být deserializaci a nebude fungovat v mnoha scénářích.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který splňuje pravidlo.

 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>
- <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
- <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>