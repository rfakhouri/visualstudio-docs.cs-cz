---
title: 'CA2236: Volejte metody třídy base na typech ISerializable | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1679772ea95fbaf0a13a91572ad81f0b987a2e31
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236: Volejte metody třídy Base na typech ISerializable
|||  
|-|-|  
|TypeName|CallBaseClassMethodsOnISerializableTypes|  
|CheckId|CA2236|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ je odvozen od typu, který implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> platí rozhraní a jedno z následujících podmínek:  
  
-   Typ implementuje serializace konstruktor, který je konstruktor s <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> parametr podpis, ale není volat konstruktor serializace základního typu.  
  
-   Typ implementuje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metoda nevyvolá, ale <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda základního typu.  
  
## <a name="rule-description"></a>Popis pravidla  
 V procesu vlastní serializace typu implementuje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda k serializaci jeho polí a serializace konstruktor deserializovat pole. Pokud typ je odvozen od typu, který implementuje <xref:System.Runtime.Serialization.ISerializable> základní typ rozhraní <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda a serializace konstruktor by měla být volána k serializaci nebo deaktivuje-serialize pole základního typu. Typ, jinak nebude serializovat a deserializovaný správně. Všimněte si, že pokud odvozený typ není přidat nová pole, typ není nutné implementovat <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda ani konstruktor serializace nebo volat základní typ ekvivalenty.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, volejte základní typ <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda nebo serializace konstruktor z odpovídající odvozený typ metoda nebo konstruktor.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje odvozený typ splňující pravidlo při volání konstruktoru serializace a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda základní třídy.  
  
 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)