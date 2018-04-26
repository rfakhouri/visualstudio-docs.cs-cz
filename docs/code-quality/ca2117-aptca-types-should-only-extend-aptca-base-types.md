---
title: 'CA2117: Typy APTCA by měl rozšířit pouze základní typy APTCA'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2117
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
helpviewer_keywords:
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
- CA2117
ms.assetid: c505b586-2f1e-47cb-98ee-a5afcbeda70f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2d295ef0a0cc2723634ad6f32c9bb91c4f7524b2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2117-aptca-types-should-only-extend-aptca-base-types"></a>CA2117: Typy APTCA by měl rozšířit pouze základní typy APTCA

|||
|-|-|
|TypeName|AptcaTypesShouldOnlyExtendAptcaBaseTypes|
|CheckId|CA2117|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Veřejné nebo chráněného typ v sestavení s <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> atribut dědí z typu v sestavení, které nemá atribut deklarován.

## <a name="rule-description"></a>Popis pravidla

Ve výchozím nastavení, jsou veřejných nebo chráněného typy v sestavení se silnými názvy implicitně chráněny [InheritanceDemand](xref:System.Security.Permissions.SecurityAction#System_Security_Permissions_SecurityAction_InheritanceDemand) pro úplný vztah důvěryhodnosti. Sestavení se silným názvem označené jako <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atribut (APTCA) nemají tato ochrana. Atribut zakáže požadavek dědičnosti. Jsou zveřejněné typy v sestavení bez vyžádání dědičnosti deklarována zděditelné typy, které nemají úplný vztah důvěryhodnosti.

Když je atribut APTCA na plně důvěryhodný pro sestavení a typ v sestavení dědí od typu, který neumožňuje částečně důvěryhodné volající, je možné zneužití zabezpečení. Pokud dva typy `T1` a `T2` splňovat následující podmínky, škodlivými úmysly použít typ `T1` obejít požadavek dědičnosti implicitní úplný vztah důvěryhodnosti, který chrání `T2`:

- `T1` je v plně důvěryhodný pro sestavení, které má atribut APTCA deklarována veřejného typu.

- `T1` dědí z typu `T2` mimo jeho sestavení.

- `T2`pro sestavení nemá atribut APTCA a proto by nemělo být zděditelné typy v sestavení částečně důvěryhodné.

Částečně důvěryhodný typ `X` může dědit vlastnosti z `T1`, které poskytuje, je přístup k zděděné členy deklarované v `T2`. Protože `T2` nemá atribut APTCA jeho okamžitou odvozený typ (`T1`) musí splňovat požadavek dědičnosti pro úplný vztah důvěryhodnosti; `T1` má úplný vztah důvěryhodnosti a proto splňuje této kontroly. Je bezpečnostní riziko, protože `X` neúčastní neodpovídajících vyžádání dědičnosti, který chrání `T2` z nedůvěryhodné vytváření podtříd. Z tohoto důvodu nesmí typy atributem APTCA rozšířit typy, které nemají atribut.

Jiného problému se zabezpečením a případně častější jeden, který je odvozený typ (`T1`) můžou prostřednictvím programátory chyba vystavit chráněné členy z typu, který vyžaduje úplný vztah důvěryhodnosti (`T2`). Dojde-li se tato ohrožení, nedůvěryhodné volající získat přístup na informace, které by měla být k dispozici pouze plně důvěryhodný pro typy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Pokud je v sestavení, které nevyžaduje žádný atribut APTCA typ hlášené porušení zásady, odeberte ji.

Pokud atribut APTCA je povinný, přidejte na typ požadavek dědičnosti pro úplný vztah důvěryhodnosti. Požadavek dědičnosti chrání před dědičnosti nedůvěryhodné typy.

Je možné opravit porušení přidáním atribut APTCA do sestavení základní typy hlášených porušení zásady. Neprovádějte tuto akci bez první provádění náročné zabezpečení kontrolu všech kód v sestavení a všechen kód, který závisí na sestavení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Chcete-li bezpečně potlačit upozornění na toto pravidlo, je nutné zajistit, že chráněné členy zveřejněné podle typu vašeho přímo nebo nepřímo neumožňují nedůvěryhodné volajícím přístup k citlivým informacím, provoz nebo prostředky, které můžete použít destruktivní způsobem.

## <a name="example"></a>Příklad

Následující příklad používá dvě sestavení a testovací aplikaci pro ilustraci ohrožení zabezpečení zjistil tímto pravidlem. První sestavení nemá atribut APTCA a neměla by být zděditelné částečně důvěryhodné typy (reprezentována `T2` v předchozí diskuse).

[!code-csharp[FxCop.Security.NoAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_1.cs)]

Druhý sestavení, reprezentována `T1` v předchozí výkladu je plně důvěryhodná a umožňuje částečně důvěryhodné volající.

[!code-csharp[FxCop.Security.YesAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_2.cs)]

Typ testu, reprezentována `X` v předchozí výkladu je v částečně důvěryhodné sestavení.

[!code-csharp[FxCop.Security.TestAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_3.cs)]

Tento příklad vytvoří následující výstup:

**Plnění v shady glen 2/22/2003 12:00:00 AM!**

**Z testu: Slunečného pastviny**

**Plnění v slunečného pastviny 2/22/2003 12:00:00 AM!**

## <a name="related-rules"></a>Související pravidla

[CA2116: Metody APTCA by měly volat pouze metody APTCA](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)

## <a name="see-also"></a>Viz také

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Používání knihoven z částečně důvěryhodného kódu](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
