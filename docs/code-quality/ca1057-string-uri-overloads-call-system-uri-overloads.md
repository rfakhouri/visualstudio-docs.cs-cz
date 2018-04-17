---
title: 'CA1057: Řetězcové přetížení identifikátoru URI Volejte přetížení System.Uri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 18b38dab9ad7a2a3065b78a1d73bbadee2c28f28
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: Řetězcové přetížení identifikátoru URI volá přetížení System.Uri
|||  
|-|-|  
|TypeName|StringUriOverloadsCallSystemUriOverloads|  
|CheckId|CA1057|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ deklaruje přetížení metody, které se liší pouze nahrazení parametru řetězce s <xref:System.Uri?displayProperty=fullName> parametr a přetížení, která použije parametr řetězce nevyvolá přetížení, které přijímá <xref:System.Uri> parametr.  
  
## <a name="rule-description"></a>Popis pravidla  
 Protože přetížení liší pouze řetězec nebo<xref:System.Uri> parametr řetězec předpokládá se, že představují identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri> Třída poskytuje tyto služby v bezpečném režimu. Využití výhod z <xref:System.Uri> třída, by měly volat přetížení řetězec <xref:System.Uri> přetížení pomocí argument řetězce.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Znovu implementovat metodu, která použije řetězcová reprezentace identifikátoru URI, takže se vytvoří instance <xref:System.Uri> pomocí argument řetězce a pak předá <xref:System.Uri> objekt, který má přetížení, které má <xref:System.Uri> parametr.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li parametr řetězce nepředstavuje identifikátoru URI.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje správně implementovaná řetězec přetížení.  
  
 [!code-csharp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CSharp/ca1057-string-uri-overloads-call-system-uri-overloads_1.cs)]
 [!code-cpp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CPP/ca1057-string-uri-overloads-call-system-uri-overloads_1.cpp)]
 [!code-vb[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/VisualBasic/ca1057-string-uri-overloads-call-system-uri-overloads_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2234: Předejte objekty System.Uri namísto řetězců](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)  
  
 [CA1056: Vlastnosti identifikátoru URI by neměly být řetězce](../code-quality/ca1056-uri-properties-should-not-be-strings.md)  
  
 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: Návratové hodnoty identifikátoru URI by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)