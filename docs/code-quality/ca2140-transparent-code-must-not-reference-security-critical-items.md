---
title: 'CA2140: Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c02de86564f6d7754b3c9db86d93577c374a72e0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31918433"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení
|||
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Transparentní metody:

-   zpracovává typ zabezpečení zabezpečení kritické výjimky

-   má parametr, který je označen jako kritické typ zabezpečení

-   má obecný parametr s omezeními kritická zabezpečení

-   má místní proměnné kritické typu zabezpečení

-   odkazuje na typ, který je označený jako zabezpečení kritické

-   volá metodu, která je označena jako zabezpečení kritické

-   odkazuje na pole, která je označena jako zabezpečení kritické

-   Vrátí typ, který je označen jako zabezpečení kritické

## <a name="rule-description"></a>Popis pravidla
 Element kódu, který je označený <xref:System.Security.SecurityCriticalAttribute> atribut je kritické pro zabezpečení. Transparentní metoda nemůže použít prvek kritický pro zabezpečení. Pokud typu transparentní pokusí použít kritické typ zabezpečení <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , nebo <xref:System.FieldAccessException> je vyvolána.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, proveďte jednu z následujících akcí:

-   Označit tento element kódu, která používá kód kritický pro zabezpečení s <xref:System.Security.SecurityCriticalAttribute> atribut

     \- nebo –

-   Odeberte <xref:System.Security.SecurityCriticalAttribute> atribut z elementy kódu, které jsou označeny jako zabezpečení důležité a místo toho označit je pomocí <xref:System.Security.SecuritySafeCriticalAttribute> nebo <xref:System.Security.SecurityTransparentAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujících příkladech transparentní metody pokusí odkazovat kritické obecnou kolekci zabezpečení, kritické položky zabezpečení a důležité metodu zabezpečení.

 [!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Security.SecurityTransparentAttribute> <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecurityTransparentAttribute> <xref:System.Security.SecurityTreatAsSafeAttribute> <xref:System.Security?displayProperty=fullName>