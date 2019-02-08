---
title: 'CA2145: Transparentní metody by neměly být doplněny o SuppressUnmanagedCodeSecurityAttribute'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a9269a0862dacf928cffb31f722f382271d5f0e7
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55953851"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: Transparentní metody by neměly být doplněny o SuppressUnmanagedCodeSecurityAttribute

|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Transparentní metoda, metodu, která je označena <xref:System.Security.SecuritySafeCriticalAttribute> metody nebo typ, který obsahuje metodu je označené <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut.

## <a name="rule-description"></a>Popis pravidla

Metody upravené pomocí <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut mají implicitní LinkDemand umístěn na jakoukoli metodu, která je volá. Tento LinkDemand vyžaduje, aby byl volající kód kritický z hlediska zabezpečení. Označení metody, která používá SuppressUnmanagedCodeSecurity s <xref:System.Security.SecurityCriticalAttribute> atribut zviditelňuje tento požadavek pro volající metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, označte metodu nebo typ s <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

### <a name="code"></a>Kód

[!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]