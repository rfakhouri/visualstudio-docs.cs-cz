---
title: 'CA2147: Transparentní metody nemusejí podporovat použití nepodmíněných výrazů zabezpečení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f732e22d53b4d469f73c4ef3efc753240fa6841f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: Transparentní metody nemusejí podporovat použití nepodmíněných výrazů zabezpečení
|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Kód, který je označen jako <xref:System.Security.SecurityTransparentAttribute> není dostatečná oprávnění k vyhodnocení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo analyzuje všechny metody a typy v sestavení, která je buď 100 % transparentní nebo smíšeném transparentní a důležitých a flags žádné deklarativní nebo imperativní využití <xref:System.Security.CodeAccessPermission.Assert%2A>.

 V době, volání spuštění <xref:System.Security.CodeAccessPermission.Assert%2A> z transparentní kód způsobí <xref:System.InvalidOperationException> vyvolání. Tato situace může nastat v obou 100 % transparentní sestavení a taky v smíšená transparentní a důležitých sestavení, kde je deklarovaná transparentní metody nebo typu, ale zahrnuje deklarativní nebo imperativní Assert.

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 zavedená funkci s názvem *průhlednost*. Jednotlivé metody, pole, rozhraní, třídy a typů může být průhledná nebo kritické.

 Transparentní kód nesmí zvýšení oprávnění zabezpečení. Proto všechna oprávnění udělená nebo který je od něj jsou automaticky předána kód do domény aplikace volající nebo hostitele. Příklady – zvýšení úrovní oprávnění jsou nepodmíněné výrazy, LinkDemands, SuppressUnmanagedCode, a `unsafe` kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li problém vyřešit, buď označit kód, který volá Assert s <xref:System.Security.SecurityCriticalAttribute>, nebo odeberte Assert.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Není potlačit zprávu od tohoto pravidla.

## <a name="example"></a>Příklad
 Tento kód se nezdaří, pokud `SecurityTestClass` je transparentní, když `Assert` metoda vrátí <xref:System.InvalidOperationException>.

 [!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>Příklad
 Jednou z možností je revize kódu metodu SecurityTransparentMethod v následujícím příkladu a pokud metoda považuje za bezpečné pro zvýšení oprávnění, označit SecurityTransparentMethod s zabezpečit důležité to vyžaduje, aby podrobné, úplné a bez chyb zabezpečení auditování je potřeba provést na metodu společně s všech značek, ke kterým došlo v rámci metody pod Assert:

 [!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

 Další možností je odebrat Assert z kódu a nechat všechny následné soubory vstupně-výstupních operací toku oprávnění požadavky nad rámec SecurityTransparentMethod volajícímu. To umožňuje kontroly zabezpečení. V takovém případě žádné auditu zabezpečení je obecně potřeba, protože požadavky oprávnění bude procházet volající nebo doménu aplikace. Požadavky na oprávnění jsou úzce ovládaná zásadami zabezpečení, hostování prostředí a udělení oprávnění zdrojového kódu.

## <a name="see-also"></a>Viz také
 [Upozornění zabezpečení](../code-quality/security-warnings.md)