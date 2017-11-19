---
title: "CA2237: Označte typy ISerializable pomocí SerializableAttribute | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ecb9934ddefe0458f2974af0d73560532a17cc07
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [CA2236: Volejte metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: Vlastnost ISerializable implementujte správně](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)