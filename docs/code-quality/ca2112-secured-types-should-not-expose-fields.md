---
title: 'CA2112: Zabezpečené typy by neměly vystavovat pole'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 43ef4165823f59045dda8c05b5679fdd3b795114
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921085"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Zabezpečené typy by neměly vystavovat pole

|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Veřejný nebo chráněný typ obsahuje veřejná pole a je zabezpečený [požadavky propojení](/dotnet/framework/misc/link-demands).

## <a name="rule-description"></a>Popis pravidla
Pokud má kód přístup k instanci typu, která je zabezpečena pomocí požadavku na propojení, nemusí kód vyhovět požadavku na propojení pro přístup k polím tohoto typu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, nastavte pole NonPublic a přidejte veřejné vlastnosti nebo metody, které vrátí data pole. Kontroly zabezpečení LinkDemand u typů chrání přístup k vlastnostem a metodám typu. Zabezpečení přístupu kódu však nelze použít u polí.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Pro problémy se zabezpečením a dobrým návrhem byste měli opravit porušení tím, že zveřejníte veřejná pole NonPublic. Můžete potlačit upozornění z tohoto pravidla, pokud pole neobsahuje informace, které by měly zůstat zabezpečené, a Nespoléháte se na obsah pole.

## <a name="example"></a>Příklad
Následující příklad se skládá z typu knihovny (`SecuredTypeWithFields`) s nezabezpečenými poli, typ (`Distributor`), který může vytvořit instance typu knihovny a chybné předávání instancí na typy nemají oprávnění k jejich vytvoření, a kód aplikace, který může číst pole instance, i když nemá oprávnění zabezpečující typ.

Následující kód knihovny je v rozporu s pravidlem.

[!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example-1"></a>Příklad 1
Aplikace nemůže vytvořit instanci z důvodu požadavku na propojení, který chrání zabezpečený typ. Následující třída umožňuje aplikaci získat instanci zabezpečeného typu.

[!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example-2"></a>Příklad 2
Následující aplikace ukazuje, jak bez oprávnění k přístupu k metodám zabezpečeného typu, kód má přístup k jeho polím.

[!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

Tento příklad vytvoří následující výstup:

```txt
Creating an instance of SecuredTypeWithFields.
Secured type fields: 22, 33
Changing secured type's field...
Cached Object fields: 99, 33
```

## <a name="related-rules"></a>Související pravidla

- [CA1051: Nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>Viz také:

- [Požadavky propojení](/dotnet/framework/misc/link-demands)
- [Data a modelování](/dotnet/framework/data/index)