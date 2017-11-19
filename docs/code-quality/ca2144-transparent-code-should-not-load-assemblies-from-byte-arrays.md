---
title: "CA2144: Transparentní kód nesmí načítat sestavení z bajtových polí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6eb3b2ade52f0870240db1fac24f0ab3f6c6de17
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: Transparentní kód nesmí načítat sestavení z bajtových polí
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|  
|CheckId|CA2144|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Transparentní metody načte sestavení z bajtového pole pomocí jedné z následujících metod:  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
## <a name="rule-description"></a>Popis pravidla  
 Přezkoumání zabezpečení transparentního kódu není tak důsledné jako přezkoumání zabezpečení kritického kódu, protože transparentní kód nemůže provádět akce citlivé na zabezpečení. Sestavení, která jsou načtena z pole bajtů, nemusí být v transparentním kódu zaznamenána a takové pole bajtů může obsahovat kritický nebo důležitější bezpečně kritický kód, který musí být auditován. Proto transparentní kód nesmí načítat sestavení z bajtového pole.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, označit metody, která je načítání sestavení s <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Toto pravidlo aktivuje na následující kód, protože transparentní metody načte sestavení z bajtového pole.  
  
 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../code-quality/codesnippet/CSharp/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays_1.cs)]