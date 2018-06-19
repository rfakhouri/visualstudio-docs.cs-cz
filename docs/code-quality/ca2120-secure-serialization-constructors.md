---
title: 'CA2120: Zabezpečte serializační konstruktory'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 449258d04b6a47fef42c56637a4de48a4e5d1d12
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915388"
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: Zabezpečte serializační konstruktory
|||
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní, není delegáta nebo rozhraní a je deklarován v sestavení, které umožňuje částečně důvěryhodné volající. Má tento typ konstruktor, který přebírá <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> objektu a <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> objektu (podpis konstruktoru serializace). Tento konstruktor není zabezpečené kontrolu zabezpečení, ale jeden nebo více regulární konstruktory v typu musí být zabezpečená.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je relevantní pro typy, které podporují vlastní serializace. Typ podporuje vlastní serializace, pokud se implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní. Konstruktor serializace je vyžadován a slouží k deserializovat nebo znovu vytvářet objekty, které byl serializován pomocí <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metoda. Protože konstruktor serializace přiděluje a inicializuje objekty, kontrol zabezpečení, které se nacházejí na regulární konstruktory musí být k dispozici také v konstruktoru serializace. Pokud toto pravidlo porušují, může k tomu použít konstruktor serializace volající, které jinak nelze vytvořit instanci.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, Chraňte serializace konstruktor s požadavky na zabezpečení, které jsou stejné jako ochrana další konstruktory.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Není potlačit narušení pravidla.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidlo.

 [!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Viz také
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>