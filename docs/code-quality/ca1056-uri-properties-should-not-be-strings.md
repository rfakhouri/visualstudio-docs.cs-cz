---
title: 'CA1056: Vlastnosti identifikátoru URI by neměly být řetězce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
helpviewer_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cda8af664b6ad71ce90aa7d0bf3bbe06aefc3ab0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1056-uri-properties-should-not-be-strings"></a>CA1056: Vlastnosti identifikátoru URI by neměly být řetězce
|||  
|-|-|  
|TypeName|UriPropertiesShouldNotBeStrings|  
|CheckId|CA1056|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ deklaruje ve vlastnosti string, jejichž název obsahuje "uri", "Uri", "urn", "Urn", "url" nebo "Url".  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo rozdělí název vlastnosti do tokenů podle konvence Pascal velká a malá písmena a zkontroluje, zda každý token rovná "uri", "Uri", "urn", "Urn", "url" nebo "Url". Pokud je nalezena shoda, pravidlo předpokládá, že vlastnost představuje identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri?displayProperty=fullName> Třída poskytuje tyto služby v bezpečném režimu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změňte vlastnost, která má <xref:System.Uri> typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li vlastnost nepředstavuje identifikátoru URI.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typu, `ErrorProne`, která porušuje toto pravidlo a typu, `SaferWay`, která by splnila pravidlo.  
  
 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1056-uri-properties-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1056-uri-properties-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1056-uri-properties-should-not-be-strings_1.cpp)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: Návratové hodnoty identifikátoru URI by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)  
  
 [CA2234: Předejte objekty System.Uri namísto řetězců](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)  
  
 [CA1057: Řetězcové přetížení identifikátoru URI volá přetížení System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)