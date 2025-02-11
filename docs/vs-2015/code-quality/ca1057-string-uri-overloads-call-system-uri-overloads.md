---
title: 'CA1057: Volání řetězcové přetížení identifikátoru URI volá přetížení System.Uri | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4cf50ca225544b06409415320c73e7824a10843a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62552726"
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: Přetížení řetězce identifikátoru URI volají přetížení System.Uri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|StringUriOverloadsCallSystemUriOverloads|
|CheckId|CA1057|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Typ deklaruje přetížení metod, které se liší pouze nahrazením řetězcového parametru s <xref:System.Uri?displayProperty=fullName> parametr a přetížení přijímající řetězcový parametr nevolá přetížení přebírající <xref:System.Uri> parametru.

## <a name="rule-description"></a>Popis pravidla
 Protože přetížení se liší pouze v řetězci /<xref:System.Uri> parametr, řetězec je předpokládá, že představují identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri> Třída poskytuje tyto služby bezpečným a zabezpečeným způsobem. K těžit z výhod <xref:System.Uri> třídy, řetězcová přetížení měla volat <xref:System.Uri> přetížit pomocí řetězcový argument.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Znovu implementovat metodu, která využívá řetězcovou reprezentaci identifikátoru URI vytvoří instanci <xref:System.Uri> pomocí řetězcový argument a pak předá <xref:System.Uri> objekt, který má přetížení <xref:System.Uri> parametru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li parametr řetězec nepředstavuje identifikátor URI.

## <a name="example"></a>Příklad
 Následující příklad ukazuje správně implementované řetězcová přetížení.

 [!code-cpp[FxCop.Design.CallUriOverload#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/cpp/FxCop.Design.CallUriOverload.cpp#1)]
 [!code-csharp[FxCop.Design.CallUriOverload#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/cs/FxCop.Design.CallUriOverload.cs#1)]
 [!code-vb[FxCop.Design.CallUriOverload#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/vb/FxCop.Design.CallUriOverload.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2234: Předejte objekty System.Uri namísto řetězců](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1056: Vlastnosti identifikátoru URI by neměly být řetězce](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: Identifikátor URI návratové hodnoty by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
