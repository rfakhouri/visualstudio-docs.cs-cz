---
title: 'CA1711: Identifikátory by neměly mít nesprávnou příponu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86bcd9373fda82c1f650da88a87d905a7ba1e6a7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53920430"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: Identifikátory by neměly mít nesprávnou příponu

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Identifikátor nemá správnou příponu.

## <a name="rule-description"></a>Popis pravidla

Pouze názvy typů, které rozšiřují určité základní typy nebo které implementují určitá rozhraní, nebo typů odvozených z těchto typů by podle konvence měly končit určitými vyhrazenými příponami. Jiné názvy typů by neměly používat tyto vyhrazené přípony.

Následující tabulka uvádí vyhrazené přípony a základní typy a rozhraní, ke kterým jsou přidruženy.

|Přípona|Základní typ nebo rozhraní|
|------------|--------------------------|
|Atribut|<xref:System.Attribute?displayProperty=fullName>|
|Kolekce|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Slovník|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|Obslužná rutina události|Delegát obslužné rutiny události|
|Výjimka|<xref:System.Exception?displayProperty=fullName>|
|Oprávnění|<xref:System.Security.IPermission?displayProperty=fullName>|
|Fronta|<xref:System.Collections.Queue?displayProperty=fullName>|
|Rámec|<xref:System.Collections.Stack?displayProperty=fullName>|
|Stream|<xref:System.IO.Stream?displayProperty=fullName>|

Kromě toho by měl následující přípony **není** použít:

- `Delegate`

- `Enum`

- `Impl` (použít `Core` místo)

- `Ex` nebo podobná přípona k odlišení starší verze stejného typu

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Odeberte příponu z názvu typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění tohoto pravidla, pokud přípona nemá v doméně aplikace jednoznačný význam.

## <a name="related-rules"></a>Související pravidla

- [CA1710: Identifikátory by měly mít správnou příponu](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>Viz také:

- [Atributy](/dotnet/standard/design-guidelines/attributes)
- [Zpracování a generování událostí](/dotnet/standard/events/index)