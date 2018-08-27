---
title: 'CA1056: Vlastnosti identifikátoru URI by neměly být řetězce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
helpviewer_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 05a6b4e8023bd1966dc007195f405df261b8c436
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42903024"
---
# <a name="ca1056-uri-properties-should-not-be-strings"></a>CA1056: Vlastnosti identifikátoru URI by neměly být řetězce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1056: vlastnosti identifikátoru URI by neměly být řetězce](https://docs.microsoft.com/visualstudio/code-quality/ca1056-uri-properties-should-not-be-strings).

|||
|-|-|
|TypeName|UriPropertiesShouldNotBeStrings|
|CheckId|CA1056|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ deklaruje vlastnosti typu string, jejichž název obsahuje "uri", "Uri", "urn", "Urn", "url" nebo "Url".

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo rozdělí na tokeny, které jsou podle úmluvy malých a velkých písmen Pascal název vlastnosti a zkontroluje, zda každý token se rovná "uri", "Uri", "urn", "Urn", "url" nebo "Url". Pokud se zjistí shoda, toto pravidlo předpokládá, že vlastnost reprezentuje identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri?displayProperty=fullName> Třída poskytuje tyto služby bezpečným a zabezpečeným způsobem.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte vlastnost, která má <xref:System.Uri> typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li vlastnost nepředstavuje identifikátor URI.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, `ErrorProne`, který porušuje tato pravidla a typ, `SaferWay`, který splňuje pravidlo.

 [!code-cpp[FxCop.Design.UriNotString#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cpp/FxCop.Design.UriNotString.cpp#1)]
 [!code-csharp[FxCop.Design.UriNotString#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cs/FxCop.Design.UriNotString.cs#1)]
 [!code-vb[FxCop.Design.UriNotString#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/vb/FxCop.Design.UriNotString.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: Návratové hodnoty identifikátoru URI by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

 [CA2234: Předejte objekty System.Uri namísto řetězců](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: Řetězcové přetížení identifikátoru URI volá přetížení System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)



