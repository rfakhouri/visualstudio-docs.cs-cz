---
title: "CA2234: Předejte objekty System.Uri namísto řetězců | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 99001a5406ce4e70e0e76670eba250073ce030b2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: Předejte objekty System.Uri namísto řetězců
|||  
|-|-|  
|TypeName|PassSystemUriObjectsInsteadOfStrings|  
|CheckId|CA2234|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Přišla žádost na metodu, která má parametr řetězce, jejichž název obsahuje "uri", "Uri", "urn", "Urn", "url" nebo "Url"; a deklarující typ metody obsahuje odpovídající přetížení metody, který má <xref:System.Uri?displayProperty=fullName> parametr.  
  
## <a name="rule-description"></a>Popis pravidla  
 Název parametru je rozdělená do tokenů založené na konvenci camelCase, a poté zkontroluje každý token se zda rovná "uri", "Uri", "urn", "Urn", "url" nebo "Url". Pokud je nalezena shoda, předpokládá se, že parametr je představují identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri> Třída poskytuje tyto služby v bezpečném režimu. Pokud je mezi dvěma přetížení, které se liší pouze ohledně reprezentace identifikátoru URI volbou, uživatel by měl vybrat přetížení, které přijímá <xref:System.Uri> argument.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, volejte přetížení, které přijímá <xref:System.Uri> argument.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li parametr řetězce nepředstavuje identifikátoru URI.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, `ErrorProne`, která porušuje pravidlo a metodu, `SaferWay`, která správně volá <xref:System.Uri> přetížení.  
  
 [!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
 [!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
 [!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1057: Řetězcové přetížení identifikátoru URI Volejte přetížení System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)  
  
 [CA1056: Vlastnosti identifikátoru URI by neměly být řetězce](../code-quality/ca1056-uri-properties-should-not-be-strings.md)  
  
 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: Identifikátor URI návratové hodnoty by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)