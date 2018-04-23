---
title: 'CA2145: Transparentní metody nesmějí být doplněny pomocí SuppressUnmanagedCodeSecurityAttribute'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 072aa9a7b77441fbd2d742209e6221cd74fd6bf1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: Transparentní metody nesmějí být doplněny pomocí SuppressUnmanagedCodeSecurityAttribute
|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Transparentní metody, metodu, která je označena <xref:System.Security.SecuritySafeCriticalAttribute> metody nebo typu, který obsahuje metodu označena <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut.

## <a name="rule-description"></a>Popis pravidla
 Metody označených pomocí <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> atribut mít implicitní LinkDemand umístit na libovolné metody, která se volá. Tento LinkDemand vyžaduje, aby byl volající kód kritický z hlediska zabezpečení. Označení metody, která používá SuppressUnmanagedCodeSecurity s <xref:System.Security.SecurityCriticalAttribute> atribut usnadňuje tento požadavek zřejmější volající metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, označte metodu nebo zadejte s <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]

### <a name="comments"></a>Komentáře