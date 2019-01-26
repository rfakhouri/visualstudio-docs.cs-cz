---
title: 'CA2143: Transparentní metody by neměly používat požadavky zabezpečení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 08a7c4d6d7c71954869311b402eed65492391432
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043074"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: Transparentní metody by neměly používat požadavky zabezpečení

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Které má průhledné typ nebo metoda je označena pomocí deklarace s <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` vyžádání nebo volání metody <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> metody.

## <a name="rule-description"></a>Popis pravidla
 Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Kód transparentní z hlediska zabezpečení by měl k učinění rozhodnutí o zabezpečení používat úplné požadavky a bezpečně kritický kód by neměl spoléhat na to, že transparentní kód tyto úplné požadavky provede. Místo toho by měl být bezpečný a kritický veškerý kód, který provádí kontroly zabezpečení, jako jsou požadavky na zabezpečení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Obecně platí, chcete-li opravit porušení tohoto pravidla, označte metody <xref:System.Security.SecuritySafeCriticalAttribute> atribut. Můžete také odebrat vyžádání.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Pravidlo soubory v následujícím kódu, protože transparentní metoda provede požadavek deklarativní zabezpečení.

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>Viz také:
 [CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)