---
title: 'CA2149: Transparentní metody nesmí provádět volání nativního kódu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 4811a117220aa154283d97d44d49a8257c4be86e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031796"
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149: Transparentní metody nesmí provádět volání nativního kódu

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallNativeCode|
|CheckId|CA2149|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Metoda volá nativní funkce prostřednictvím pahýl metody, jako je například P/Invoke.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno na jakékoli transparentní metodě, která přímo volá nativní kód, například prostřednictvím P/Invoke. Porušení tohoto pravidla vede k <xref:System.MethodAccessException> v modelu transparentnosti úrovně 2 a k úplnému pro <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> v modelu transparentnosti úrovně 1.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, označte metody, která volá nativní kód <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 [!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../code-quality/codesnippet/CSharp/ca2149-transparent-methods-must-not-call-into-native-code_1.cs)]