---
title: "CA2235: Označte všechna neserializovatelná pole | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b6489cf400dd2f67c08ff4dba3bf6a1eda4ec46e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Označte všechna neserializovatelná pole
|||  
|-|-|  
|TypeName|MarkAllNonSerializableFields|  
|CheckId|CA2235|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Neserializovatelný typ pole instance je deklarován v serializovatelném typu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Serializovatelné typ je ten, který je označené <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Když je typ serializován, <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> je vyvolána výjimka, pokud typ obsahuje pole instance typu, který není serializovatelný.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, použít <xref:System.NonSerializedAttribute?displayProperty=fullName> atribut pole, které není serializovatelný.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pouze v případě potlačit upozornění na toto pravidlo <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> typ je deklarován umožňuje instancí pole, které chcete serializovat a deserializovat.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo a typ, který splňuje pravidlo.  
  
 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2236: Volejte metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: Vlastnost ISerializable implementujte správně](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)