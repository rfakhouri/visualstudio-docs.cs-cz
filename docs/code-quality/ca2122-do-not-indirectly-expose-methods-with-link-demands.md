---
title: 'CA2122: Nezveřejňujte nepřímo metody s požadavky propojení'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 340d8f0a45506f15cdd9281f7ecda463583c3144
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920830"
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122: Nezveřejňujte nepřímo metody s požadavky propojení

|||
|-|-|
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|
|CheckId|CA2122|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Veřejný nebo chráněný člen má odkaz na [požadavky](/dotnet/framework/misc/link-demands) a je volán členem, který neprovádí žádné kontroly zabezpečení.

## <a name="rule-description"></a>Popis pravidla
Požadavek propojení kontroluje pouze oprávnění bezprostředního volajícího. Pokud člen `X` neprovede žádné požadavky na zabezpečení svých volajících a volá kód chráněný požadavkem propojení, volající bez nezbytných oprávnění může použít `X` pro přístup k chráněnému členu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Přidejte data zabezpečení [a modelování](/dotnet/framework/data/index) nebo přidejte požadavek na člena, aby již neposkytoval nezabezpečený přístup k členovi, který je chráněn požadavkem propojení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Chcete-li bezpečně potlačit upozornění z tohoto pravidla, je nutné zajistit, aby váš kód neudělil volajícím přístup k operacím nebo prostředkům, které lze použít destruktivním způsobem.

## <a name="example-1"></a>Příklad 1
Následující příklady znázorňují knihovnu, která porušuje pravidlo, a aplikaci, která demonstruje slabé stránky knihovny. Ukázková knihovna poskytuje dvě metody, které dohromady narušují pravidlo. `EnvironmentSetting` Metoda je zabezpečena požadavkem propojení pro neomezený přístup k proměnným prostředí. Metoda neprovede žádné požadavky na zabezpečení svých volajících před voláním `EnvironmentSetting`. `DomainInformation`

[!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]

## <a name="example-2"></a>Příklad 2
Následující aplikace volá nezabezpečeného člena knihovny.

[!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]

Tento příklad vytvoří následující výstup:

```txt
*Value from unsecured member: seattle.corp.contoso.com
```

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Požadavky propojení](/dotnet/framework/misc/link-demands)
- [Data a modelování](/dotnet/framework/data/index)