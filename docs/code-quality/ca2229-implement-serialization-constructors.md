---
title: "CA2229: Implementovat Serializační konstruktory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f954626a45035aa84633f82ba3a2da0f2a682421
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: Implementovat serializační konstruktory
|||  
|-|-|  
|TypeName|ImplementSerializationConstructors|  
|CheckId|CA2229|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní, není delegáta nebo rozhraní a je splněna jedna z následujících podmínek:  
  
-   Typ nemá konstruktor, který přebírá <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> objektu a <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> objektu (podpis konstruktoru serializace).  
  
-   Typ nezapečetěná a – modifikátor přístupu pro jeho serializace konstruktor není chráněné (rodiny).  
  
-   Typ je zapečetěná a není privátní – modifikátor přístupu pro konstruktor její serializace.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo je relevantní pro typy, které podporují vlastní serializace. Typ podporuje vlastní serializace, pokud se implementuje <xref:System.Runtime.Serialization.ISerializable> rozhraní. Konstruktor serializace je potřeba deserializovat, nebo znovu vytvořit objekty, které byl serializován pomocí <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metoda.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Implementací konstruktoru serializace se vyřeší porušení tohoto pravidla. Pro zapečetěnou třídu musí být konstruktor soukromý. V ostatních případech musí být chráněný.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačit narušení pravidla. Typ nebudou deserializovat a nebude fungovat v mnoha situacích.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který splňuje pravidlo.  
  
 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>