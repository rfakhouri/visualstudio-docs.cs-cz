---
title: 'CA2147: Transparentní metody nemusí používat kontrolní příkazy zabezpečení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- SecurityTransparentCodeShouldNotAssert
- CA2147
- CA2128
helpviewer_keywords:
- CA2128
- SecurityTransparentCodeShouldNotAssert
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 057a4eb504a6b8d3eaf559b8ff370712db5e8f91
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932140"
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: Transparentní metody nemusí používat kontrolní příkazy zabezpečení

|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Kód, který je označen jako <xref:System.Security.SecurityTransparentAttribute> není uděleno dostatečné oprávnění k vyhodnocení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo analyzuje všechny metody a typy v sestavení, který je buď 100 % transparentní, nebo smíšené transparentní/kritické a označí všechny deklarativní nebo imperativní použití <xref:System.Security.CodeAccessPermission.Assert%2A>.

 Během spuštění, všechna volání do <xref:System.Security.CodeAccessPermission.Assert%2A> z transparentního kódu způsobí, že <xref:System.InvalidOperationException> vyvolání. Tato situace může nastat, obě 100 % transparentní sestavení a taky na smíšené transparentní/kritické sestavení, ve kterém je deklarována jako transparentní metody nebo typu, ale zahrnuje deklarativní nebo imperativní Assert.

 Rozhraní .NET Framework 2.0 zavedené funkci s názvem *transparentnosti*. Jednotlivé metody, pole, rozhraní, tříd a typů může být transparentní nebo kritické.

 Transparentní kód nesmí zvýšení oprávnění zabezpečení. Proto žádná oprávnění udělit nebo požadováno ho automaticky předávána prostřednictvím kódu volající nebo host domény aplikace. Bezpečnostně příklady nepodmíněné výrazy, pravidla LinkDemand, SuppressUnmanagedCode, a `unsafe` kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li problém vyřešit, buď označit kód, který volá kontrolní výraz s <xref:System.Security.SecurityCriticalAttribute>, nebo odeberte Assert.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte zprávy z tohoto pravidla.

## <a name="example"></a>Příklad
 Tento kód se nezdaří, pokud `SecurityTestClass` je transparentní, když `Assert` vyvolá metoda výjimku <xref:System.InvalidOperationException>.

 [!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>Příklad
 Jednou z možností je k revizi kódu SecurityTransparentMethod metodu v následujícím příkladu a pokud metoda je považován za bezpečný pro zvýšení oprávnění, označit SecurityTransparentMethod zabezpečení – kritické. To vyžaduje, že auditu zabezpečení podrobné, nejúplnější a bez chyb se musí provádět v metodě spolu s všech značek, ke kterým dochází v rámci metody Assert:

 [!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

 Další možností je odebrat Assert z kódu a nechat všechny následné soubory tok na požadavky na oprávnění vstupně-výstupní operace nad rámec SecurityTransparentMethod volajícímu. To umožňuje kontroly zabezpečení. V takovém případě je potřeba žádné auditu zabezpečení, protože oprávnění požadavky se budou přenášet do volajícího a/nebo doménu aplikace. Požadavky na oprávnění jsou úzce ovládaná zásadami zabezpečení, hostování prostředí a udělení oprávnění zdrojového kódu.

## <a name="see-also"></a>Viz také:
 [Upozornění zabezpečení](../code-quality/security-warnings.md)