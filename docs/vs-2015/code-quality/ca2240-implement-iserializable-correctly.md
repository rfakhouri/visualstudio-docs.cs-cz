---
title: 'CA2240: Implementujte správně ISerializable | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 37f84bff4802c703bb61b36e9c1933a31cd6c5e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68142369"
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: Implementujte správně ISerializable
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ImplementISerializableCorrectly|
|CheckId|CA2240|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Externě viditelný typ je přiřadit k <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> platí rozhraní a jeden z následujících podmínek:

- Typ dědí, ale nepřepisuje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metoda a typ deklaruje pole instancí, které nejsou označené <xref:System.NonSerializedAttribute?displayProperty=fullName> atribut.

- Typ není zapečetěná a tento typ implementuje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metodu, která není externě viditelnou a přepisovatelnou.

## <a name="rule-description"></a>Popis pravidla
 Instance pole, které jsou deklarovány v typu, který dědí <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní nejsou automaticky součástí procesu serializace. Chcete-li zahrnují pole, musí implementovat typ <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metody a konstruktoru serializace. Pokud pole nesmí být serializován, použije <xref:System.NonSerializedAttribute> atributu na pole explicitně určit rozhodnutí.

 Typy, které nejsou uzavřeny, implementace <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda by měla být externě viditelné. Proto metodu je možné vyvolat v odvozených typech a je přepsatelný.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, ujistěte se, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda viditelnou a přepisovatelnou a ujistěte se, že všechna pole instancí jsou součástí procesu serializace nebo výslovně označena <xref:System.NonSerializedAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva Serializovatelné typy, které pravidlo porušují.

 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.ImplementISerializableCorrectly/cpp/FxCop.Usage.ImplementISerializableCorrectly.cpp#1)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ImplementISerializableCorrectly/cs/FxCop.Usage.ImplementISerializableCorrectly.cs#1)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.ImplementISerializableCorrectly/vb/FxCop.Usage.ImplementISerializableCorrectly.vb#1)]

## <a name="example"></a>Příklad
 V následujícím příkladu řeší tím, že poskytuje přepisovatelný provádění [ISerializable.GetObjectData] (dvě předchozí porušení<!-- TODO: review code entity reference <xref:assetId:///ISerializable.GetObjectData?qualifyHint=False&amp;autoUpgrade=False>  -->) ve třídě knihy a tím, že poskytuje implementace <!-- TODO: review code entity reference <xref:assetId:///ISerializable.GetObjectData?qualifyHint=False&amp;autoUpgrade=False>  --> v knihovně tříd.

 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.ImplementISerializableCorrectly2/cpp/FxCop.Usage.ImplementISerializableCorrectly2.cpp#1)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ImplementISerializableCorrectly2/cs/FxCop.Usage.ImplementISerializableCorrectly2.cs#1)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.ImplementISerializableCorrectly2/vb/FxCop.Usage.ImplementISerializableCorrectly2.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volání metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)
