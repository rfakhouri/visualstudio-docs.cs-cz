---
title: "CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d68fa549775b3e3a4a6831e3fb82188367725d0b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute
|||  
|-|-|  
|TypeName|MarkAssembliesWithClsCompliant|  
|CheckId|CA1014|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Sestavení nemá <xref:System.CLSCompliantAttribute?displayProperty=fullName> byt aplikovaný atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Specifikace Common Language Specification (CLS) definuje omezení názvů, datové typy a pravidla, která musí sestavení dodržovat, pokud budou použita napříč programovacími jazyky. Dobrý návrh stanoví, že ve všech sestaveních explicitně označovat souladu se specifikací CLS s <xref:System.CLSCompliantAttribute>. Pokud atribut neexistuje na sestavení, není kompatibilní s sestavení.  
  
 Je možné pro kompatibilní se specifikací CLS sestavení a obsahují typy nebo zadejte členy, kteří jsou nekompatibilní.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přidejte atribut sestavení. Místo označení celé sestavení jako nesplňující požadavky, měli byste určit typ nebo členy typu jsou nekompatibilní a označit jako takový tyto prvky. Pokud je to možné by měl poskytovat kompatibilní se specifikací CLS alternativní pro nekompatibilní členy, aby nejširší možnou cílovou skupinou přístup všechny funkce vašeho sestavení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Pokud nechcete, aby sestavení tak, aby vyhovoval, použijte atribut a jeho hodnotu nastavte `false`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, sestavení, který má <xref:System.CLSCompliantAttribute?displayProperty=fullName> použít atribut, který deklaruje kompatibilní se specifikací CLS.  
  
 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.CLSCompliantAttribute?displayProperty=fullName>   
 [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)