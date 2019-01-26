---
title: 'CA2123: Požadavky na propojení přepisů by měly být identické s bází'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 31c644beab7a9945832e0bc7fc28162ee680d56e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54939852"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Požadavky na propojení přepisů by měly být identické s bází

|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejná nebo chráněná metoda veřejného typu přepsání metody nebo implementuje rozhraní a nemá stejný [požadavky propojení](/dotnet/framework/misc/link-demands) jako rozhraní nebo virtuální metody.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo přiřazuje metodu své základní metodě, kterou je buď rozhraní, nebo virtuální metoda jiného typu, a poté v obou metodách srovnává požadavky propojení. Porušení bude nahlášena, pokud metodu nebo metodu základní má požadavku propojení a druhá ne.

 Pokud je toto pravidlo porušeno, volající obejít požadavek propojení pouhým voláním nezabezpečené metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte stejný požadavek propojení přepsání metody nebo implementaci. Pokud to není možné, označte metodu se požadavek na úplné nebo úplně odeberte atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje různé porušení tohoto pravidla.

 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Požadavky propojení](/dotnet/framework/misc/link-demands)