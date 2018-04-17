---
title: 'CA2138: Transparentní metody nesmějí volat metody s atributem suppressunmanagedcodesecurity | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: dd12cf43425c863b72c7a77b8ccd8884c0ad7d2d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: Transparentní metody nesmějí volat metody s atributem SuppressUnmanagedCodeSecurity
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|  
|CheckId|CA2138|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Transparentní metody zabezpečení volá metodu, která je označena <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo aktivuje na libovolné transparentní metody, která volá přímo do nativního kódu, například pomocí prostřednictvím P/Invoke (vyvolání platformy) volání. P/Invoke a COM spolupráce metody, které jsou označené <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut vést LinkDemand prováděná před voláním metody. Protože kód transparentní pro zabezpečení nemůže vyhovovat LinkDemands, kód také nelze volat metody, které jsou označené atributem suppressunmanagedcodesecurity nebo metody třídy, která je označena atributem SuppressUnmanagedCodeSecurity. Metoda se nezdaří, nebo vyžádání text bude převeden na úplný požadavek.  
  
 Toto pravidlo porušení vést k <xref:System.MethodAccessException> v modelu zabezpečení průhlednost úrovně 2 a úplný požadavek pro <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> v modelu průhlednost úrovně 1.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut a označit metodu s <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../code-quality/codesnippet/CSharp/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute_1.cs)]