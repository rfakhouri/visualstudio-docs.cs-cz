---
title: 'CA2140: Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4462bb8ef65fdf593ab0bf64813c19af5d390d97
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916814"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení

|||
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Transparentní metoda:

- zpracovává typ výjimky pro kritické bezpečnostní zabezpečení

- parametr, který je označen jako typ kritický pro zabezpečení

- má obecný parametr důležité omezení zabezpečení

- má místní proměnnou typ kritický pro zabezpečení

- odkazuje na typ, který je označen jako zabezpečení kritická

- volá metodu, která je označena jako zabezpečení kritická

- odkazuje na pole, která je označena jako zabezpečení kritická

- Vrátí typ, který je označen jako zabezpečení kritická

## <a name="rule-description"></a>Popis pravidla

Prvek kódu označeného atributem <xref:System.Security.SecurityCriticalAttribute> atribut je kritický pro zabezpečení. Transparentní metoda nemůže použít prvek kritický pro zabezpečení. Pokud se transparentní typ pokusí použít typ kritický pro zabezpečení <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , nebo <xref:System.FieldAccessException> je vyvolána.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, proveďte jednu z následujících akcí:

- Označení prvku kód, který používá zabezpečení kritického kódu s <xref:System.Security.SecurityCriticalAttribute> atribut

     \- nebo –

- Odeberte <xref:System.Security.SecurityCriticalAttribute> atribut z prvků kódu, které jsou označeny jako zabezpečení důležité a místo toho je s označit <xref:System.Security.SecuritySafeCriticalAttribute> nebo <xref:System.Security.SecurityTransparentAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad

V následujících příkladech transparentní metoda pokusí odkazovat kritické obecnou kolekci zabezpečení, kritické pole zabezpečení a na kritickou metodu zabezpečení.

[!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityCriticalAttribute>
- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityTreatAsSafeAttribute>
- <xref:System.Security?displayProperty=fullName>