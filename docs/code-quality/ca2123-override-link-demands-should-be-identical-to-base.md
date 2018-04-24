---
title: 'CA2123: Požadavky na přepsání odkazu musejí být identické s bází'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7aa696c1d08b71078ff4ae3beed7283d0b0333e2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Požadavky na přepsání odkazu musejí být identické s bází
|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda veřejných nebo chráněné v veřejného typu přepíše metodu nebo implementuje rozhraní a nemá stejný [požadavky propojení](/dotnet/framework/misc/link-demands) jako metodu rozhraní nebo virtuální.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo přiřazuje metodu své základní metodě, kterou je buď rozhraní, nebo virtuální metoda jiného typu, a poté v obou metodách srovnává požadavky propojení. Narušení bude nahlášena, pokud metoda nebo základní metody je požadavek propojení a druhá není.

 Pokud je toto pravidlo došlo k porušení, škodlivý volající obejít požadavek propojení jenom pomocí volání metody zabezpečená.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, platí stejné požadavek propojení pro toto metoda nebo implementace. Pokud to není možné označit metodu s úplný požadavek nebo úplně odeberte atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje různé porušení toto pravidlo.

 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>Viz také
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines) [požadavky na propojení](/dotnet/framework/misc/link-demands)