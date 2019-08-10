---
title: 'CA2138: Transparentní metody nesmí volat metody s atributem SuppressUnmanagedCodeSecurity'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 316aef3b0f1f715857fde8eaf2a6e74b1a49e40f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920580"
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: Transparentní metody nesmí volat metody s atributem SuppressUnmanagedCodeSecurity

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|
|CheckId|CA2138|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Transparentní metoda zabezpečení volá metodu, která je označena <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atributem.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo je vyvoláno na jakékoli transparentní metodě, která volá přímo do nativního kódu, například pomocí volání volání nespravovaného kódu (volání platformy). Metody volání nespravovaného volání a modelu COM, které jsou <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> označeny atributem Result, mají za následek, že se v LinkDemand provádí v rámci volající metody. Vzhledem k tomu, že kód transparentní pro zabezpečení nemůže naplnit LinkDemand, kód také nemůže volat metody, které jsou označeny atributem SuppressUnmanagedCodeSecurity, nebo metody třídy, které jsou označeny atributem SuppressUnmanagedCodeSecurity. Metoda se nezdaří nebo se požadavek převede na úplný požadavek.

Porušení tohoto pravidla povedou k <xref:System.MethodAccessException> tomu, že v modelu transparentnosti úrovně 2 a v modelu transparentnosti úrovně 1 máte plnou <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> poptávku.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut a označte metodu <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecuritySafeCriticalAttribute> atributem nebo.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
[!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../code-quality/codesnippet/CSharp/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute_1.cs)]