---
title: 'CA2123: Požadavky na propojení přepisů by měly být identické s bází'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ecc30f3fe16b283c0eb9cc1f369458bb1d7f952
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920811"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Požadavky na propojení přepisů by měly být identické s bází

|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Veřejná nebo chráněná metoda ve veřejném typu přepisuje metodu nebo implementuje rozhraní a nemá stejné [propojení](/dotnet/framework/misc/link-demands) jako rozhraní nebo virtuální metoda.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo přiřazuje metodu své základní metodě, kterou je buď rozhraní, nebo virtuální metoda jiného typu, a poté v obou metodách srovnává požadavky propojení. Porušení je hlášeno, pokud buď metoda, nebo základní metoda mají požadavek propojení a druhý nikoli.

Pokud je toto pravidlo porušeno, může škodlivý volající obejít požadavek propojení pouze voláním nezabezpečené metody.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, použijte stejnou požadavek propojení na metodu nebo implementaci přepsání. Pokud to není možné, označte metodu úplným požadavkem nebo odeberte atribut úplně.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad ukazuje různá porušení tohoto pravidla.

[!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Požadavky propojení](/dotnet/framework/misc/link-demands)