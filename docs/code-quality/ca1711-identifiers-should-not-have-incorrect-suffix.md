---
title: 'CA1711: Identifikátory by neměly mít nesprávnou příponu'
ms.date: 03/11/2019
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9377dcf03bcbb8087d152ef98986f31c12c94c45
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841931"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: Identifikátory by neměly mít nesprávnou příponu

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Identifikátor nemá správnou příponu.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné identifikátory, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Pouze názvy typů, které rozšiřují určité základní typy nebo které implementují určitá rozhraní, nebo typů odvozených z těchto typů by podle konvence měly končit určitými vyhrazenými příponami. Jiné názvy typů by neměly používat tyto vyhrazené přípony.

Následující tabulka uvádí vyhrazené přípony a základní typy a rozhraní, ke kterým jsou přidruženy.

|Přípona|Základní typ nebo rozhraní|
|------------|--------------------------|
|Atribut|<xref:System.Attribute?displayProperty=fullName>|
|Shromažďování|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Slovník|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|EventHandler|Delegát obslužné rutiny události|
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

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1711.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

- [CA1710: Identifikátory by měly mít správnou příponu](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>Viz také:

- [Atributy](/dotnet/standard/design-guidelines/attributes)
- [Zpracování a generování událostí](/dotnet/standard/events/index)