---
title: 'CA2138: Transparentní metody nesmějí volat metody s atributem suppressunmanagedcodesecurity | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b78bc348c38f120b5dba904b6e11e4b170fac7e4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49257423"
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: Transparentní metody nesmějí volat metody s atributem SuppressUnmanagedCodeSecurity
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|
|CheckId|CA2138|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Transparentní metoda zabezpečení volá metodu, která je označena <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno na jakékoli transparentní metodě, která přímo volá nativní kód, například pomocí prostřednictvím P/Invoke (nespravovaného) volání. P/Invoke a modelu COM interop metody, které jsou označené <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut výsledkem LinkDemand provádí proti volání metody. Protože transparentního kódu zabezpečení nemůže vyhovovat LinkDemands, kód také nelze volat metody, které jsou označeny atributem SuppressUnmanagedCodeSecurity nebo metody třídy, která je označena atributem SuppressUnmanagedCodeSecurity. Metoda se nezdaří, nebo vyžádání se převedou na úplný požadavek.

 Porušení tohoto pravidla vede k <xref:System.MethodAccessException> v modelu transparentnosti zabezpečení úrovně 2 a k úplnému pro <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> v modelu transparentnosti úrovně 1.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut a označit metody <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 [!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2138.transparentmethodsmustnotcallsuppressunmanagedcodesecuritymethods/cs/ca2138.cs#1)]



