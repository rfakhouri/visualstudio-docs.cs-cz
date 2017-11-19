---
title: "CA1057: Řetězcové přetížení identifikátoru URI Volejte přetížení System.Uri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 094680be86955a47486ec108e779a313b7b0c0fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
  
 [CA1055: Identifikátor URI návratové hodnoty by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)