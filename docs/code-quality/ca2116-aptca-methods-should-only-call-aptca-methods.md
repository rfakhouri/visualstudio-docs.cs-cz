---
title: 'CA2116: Metody APTCA by měly volat pouze metody APTCA'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f55c48583e47a4602f33d69799d1d86a6c9c3e56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921144"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: Metody APTCA by měly volat pouze metody APTCA

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Metoda v sestavení s <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> atributem volá metodu v sestavení, které nemá atribut.

## <a name="rule-description"></a>Popis pravidla

Ve výchozím nastavení jsou veřejné nebo chráněné metody v sestaveních se silnými názvy implicitně chráněny [požadavky propojení](/dotnet/framework/misc/link-demands) pro úplný vztah důvěryhodnosti; pouze plně důvěryhodní volající mají přístup k sestavení se silným názvem. Sestavení se silným názvem označená <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributem (APTCA) nemají tuto ochranu. Atribut zakáže požadavek propojení, aby bylo sestavení přístupné volajícím, kteří nemají úplný vztah důvěryhodnosti, jako je například spouštění kódu z intranetu nebo z Internetu.

Pokud je atribut APTCA přítomen v plně důvěryhodném sestavení a sestavení spustí kód v jiném sestavení, které nepovoluje částečně důvěryhodné volající, je možné zneužití zabezpečení. Pokud dvě metody `M1` a `M2` splňují následující podmínky, mohou škodlivé volající používat metodu `M1` pro obejít požadavky na odkaz implicitní úplný vztah důvěryhodnosti, který chrání `M2`:

- `M1`je veřejnou metodou deklarovanou v plně důvěryhodném sestavení, které má atribut APTCA.

- `M1`volá metodu `M2` mimo `M1`sestavení.

- `M2`sestavení nemá atribut APTCA a proto by neměl být spuštěn pomocí nebo jménem volajících, které jsou částečně důvěryhodné.

Částečně důvěryhodný volající `X` může volat metodu `M1`, což je `M1` způsob volání `M2`. Vzhledem `M2` k tomu, že nemá atribut APTCA, musí jeho bezprostřední`M1`volající () splňovat požadavek propojení pro úplný vztah důvěryhodnosti; `M1` má úplný vztah důvěryhodnosti a proto splňuje tuto kontrolu. Bezpečnostní riziko je způsobeno `X` tím, že se neúčastní požadavku na propojení, `M2` který je chráněn před nedůvěryhodnými volajícími. Proto metody s atributem APTCA nesmí volat metody, které nemají atribut.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Pokud je vyžadován atribut APCTA, použijte požadavek na ochranu metody, která volá do sestavení s úplným vztahem důvěryhodnosti. Přesná oprávnění budou záviset na funkcích, které vaše metoda zveřejňuje. Pokud je to možné, zabezpečte metodu s požadavkem na úplný vztah důvěryhodnosti, abyste zajistili, že základní funkce nebudou vystaveny částečně důvěryhodným volajícím. Pokud to není možné, vyberte sadu oprávnění, která efektivně chrání vystavené funkce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Chcete-li bezpečně potlačit upozornění z tohoto pravidla, je nutné zajistit, aby funkce vystavené vaší metodou nepřímo ani nepřímo nepovolovaly volajícím přístup k citlivým informacím, operacím nebo prostředkům, které lze použít destruktivním způsobem.

## <a name="example-1"></a>Příklad 1
Následující příklad používá dvě sestavení a testovací aplikaci k ilustraci chyby zabezpečení zjištěné tímto pravidlem. První sestavení nemá atribut APTCA a neměl by být přístupný pro částečně důvěryhodné volající (reprezentované `M2` v předchozí diskuzi).

[!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example-2"></a>Příklad 2
Druhé sestavení je plně důvěryhodné a umožňuje částečně důvěryhodných volajících (reprezentovaných `M1` v předchozí diskuzi).

[!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example-3"></a>Příklad 3
Testovací aplikace (reprezentovaná `X` v předchozí diskusi) je částečně důvěryhodná.

[!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

Tento příklad vytvoří následující výstup:

```txt
Demand for full trust:Request failed.
ClassRequiringFullTrust.DoWork was called.
```

## <a name="related-rules"></a>Související pravidla

- [CA2117: Typy APTCA by měly rozšířily pouze základní typy APTCA](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Používání knihoven z částečně důvěryhodného kódu](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
- [Požadavky propojení](/dotnet/framework/misc/link-demands)
- [Data a modelování](/dotnet/framework/data/index)