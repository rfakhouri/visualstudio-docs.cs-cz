---
title: 'CA2120: Zabezpečte Serializační konstruktory | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ea70b7f9462e3195a78b915691a5069ebd6fe6aa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68154355"
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: Zabezpečte serializační konstruktory
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Tento typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní, není delegát nebo rozhraní a je deklarována v sestavení, které povoluje částečně důvěryhodné volající. Typ má konstruktor, který přijímá <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> objektu a <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> objektu (podpis serializace konstruktoru). Tento konstruktor není zabezpečen pomocí kontroly zabezpečení, ale jeden nebo více běžných konstruktorů typ je zabezpečen.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo platí pro typy, které podporují vlastní serializace. Typ podporuje vlastní serializace v případě, že implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní. Serializační konstruktor je povinný a slouží k deserializovat, nebo znovu vytvořit objekty, které byl serializován pomocí <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metody. Protože Serializační konstruktor přiděluje a inicializuje objekty, kontroly zabezpečení, které se nacházejí na běžných konstruktorů musí být k dispozici také u konstruktoru serializace. Pokud toto pravidlo porušují, může k tomu použít Serializační konstruktor volajícím, které jinak nelze vytvořit instanci.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, Chraňte Serializační konstruktor s požadavky na zabezpečení, které jsou stejné jako ty chrání ostatní konstruktory.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte porušení tohoto pravidla.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-csharp[FxCop.Security.SerialCtors#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.SerialCtors/cs/FxCop.Security.SerialCtors.cs#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Viz také
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName><xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>
