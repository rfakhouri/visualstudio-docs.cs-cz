---
title: 'CA1055: Návratové hodnoty identifikátoru URI by neměly být řetězce'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1055
- UriReturnValuesShouldNotBeStrings
helpviewer_keywords:
- UriReturnValuesShouldNotBeStrings
- CA1055
ms.assetid: 40e39873-7872-4988-8195-9eb0ade9ece0
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c2bbe15cbdd095f4c9c52b2db7614e133301f6ba
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922547"
---
# <a name="ca1055-uri-return-values-should-not-be-strings"></a>CA1055: Návratové hodnoty identifikátoru URI by neměly být řetězce

|||
|-|-|
|TypeName|UriReturnValuesShouldNotBeStrings|
|CheckId|CA1055|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název metody obsahuje "uri", "Uri", "urn", "Urn", "url" nebo "Url" a metoda vrátí hodnotu typu string.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo rozdělí na tokeny, které jsou podle úmluvy malých a velkých písmen Pascal názvu metody a zkontroluje, zda každý token se rovná "uri", "Uri", "urn", "Urn", "url" nebo "Url". Pokud se zjistí shoda, toto pravidlo předpokládá, že metoda vrací identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri?displayProperty=fullName> Třída poskytuje tyto služby bezpečným a zabezpečeným způsobem.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte návratový typ <xref:System.Uri>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud vrácená hodnota nepředstavuje identifikátor URI.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, `ErrorProne`, který porušuje tato pravidla a typ, `SaferWay`, který splňuje pravidlo.

 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1055-uri-return-values-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1055-uri-return-values-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1055-uri-return-values-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>Související pravidla
 [CA1056: Vlastnosti identifikátoru URI by neměly být řetězce](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA2234: Předejte objekty System.Uri namísto řetězců](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: Volání řetězcové přetížení identifikátoru URI volá přetížení System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)