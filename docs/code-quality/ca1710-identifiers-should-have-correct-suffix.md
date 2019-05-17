---
title: 'CA1710: Identifikátory by měly mít správnou příponu'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 154d7d36c949ac361f938aa7d8608251c2a9adee
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841914"
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: Identifikátory by měly mít správnou příponu

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectSuffix|
|CheckId|CA1710|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Identifikátor nemá správnou příponu.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné identifikátory, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Podle úmluvy názvy typů, které rozšiřují určité základní typy nebo které implementují určitá rozhraní, nebo typů odvozených z těchto typů máte příponu, která je přidružena k základní typ nebo rozhraní.

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

V následující tabulce jsou uvedeny základní typy a rozhraní, které mají přidružené přípony.

|Základní typ nebo rozhraní|Přípona|
|--------------------------|------------|
|<xref:System.Attribute?displayProperty=fullName>|Atribut|
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|
|<xref:System.Exception?displayProperty=fullName>|Výjimka|
|<xref:System.Collections.ICollection?displayProperty=fullName>|Shromažďování|
|<xref:System.Collections.IDictionary?displayProperty=fullName>|Slovník|
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|Shromažďování|
|<xref:System.Collections.Queue?displayProperty=fullName>|Kolekce nebo fronty|
|<xref:System.Collections.Stack?displayProperty=fullName>|Kolekce nebo zásobníku|
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|Shromažďování|
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|Slovník|
|<xref:System.Data.DataSet?displayProperty=fullName>|DataSet|
|<xref:System.Data.DataTable?displayProperty=fullName>|Kolekci nebo tento objekt DataTable|
|<xref:System.IO.Stream?displayProperty=fullName>|Stream|
|<xref:System.Security.IPermission?displayProperty=fullName>|Oprávnění|
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|Podmínka|
|Delegát obslužné rutiny události.|EventHandler|

Typy, které implementují <xref:System.Collections.ICollection> a jsou zobecněného typu datové struktury, jako například slovníku, zásobníku nebo fronty, jsou povolené názvy, které poskytují smysluplné informace o zamýšlené použití typu.

Typy, které implementují <xref:System.Collections.ICollection> a jsou kolekce konkrétní položky mají názvy, které končí slovem "Kolekce". Například kolekce <xref:System.Collections.Queue> objektů bude mít název "QueueCollection". Přípona "Kolekce" znamená, že členové kolekce jsou uvedené s použitím `foreach` (`For Each` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) příkaz.

Typy, které implementují <xref:System.Collections.IDictionary> mít názvy, které končí slovem "Slovník" i v případě, že typ implementuje rovněž <xref:System.Collections.IEnumerable> nebo <xref:System.Collections.ICollection>. Konvence pojmenování příponu "Kolekce" a "Slovník" umožnit uživatelům si rozlišovat mezi následujících vzorů dvě výčtu.

Typy s příponou "Kolekce" postupovat podle tohoto vzoru výčtu.

```
foreach(SomeType x in SomeCollection) { }
```

Typy s příponou "Slovník" postupovat podle tohoto vzoru výčtu.

```
foreach(SomeType x in SomeDictionary.Values) { }
```

A <xref:System.Data.DataSet> objekt se skládá z kolekce <xref:System.Data.DataTable> objekty, které se skládají z kolekce <xref:System.Data.DataColumn?displayProperty=fullName> a <xref:System.Data.DataRow?displayProperty=fullName> objekty, mimo jiné. Implementace těchto kolekcí <xref:System.Collections.ICollection> prostřednictvím základní třídy <xref:System.Data.InternalDataCollectionBase?displayProperty=fullName> třídy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Přejmenujte typ tak, aby příponu správný výraz.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění použít příponu "Kolekce", pokud typ je zobecněný datová struktura, která může rozšířit nebo, který bude obsahovat libovolné sadu různých položek. Název, který poskytuje důležité informace o implementaci, výkon nebo dalších vlastností datové struktury v takovém případě může mít smysl (například BinaryTree). V případech, kde typ představuje kolekci určitého typu (například třída StringCollection), nepotlačujte upozornění tohoto pravidla vzhledem k tomu, že přípona označuje, že můžete vytvořit výčet typu pomocí `foreach` příkazu.

Pro další přípony nepotlačujte upozornění tohoto pravidla. Přípona umožňuje zamýšlené použití bude zřejmé z názvu typu.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1710.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

[CA1711: Identifikátory by neměly mít nesprávnou příponu](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

## <a name="see-also"></a>Viz také:

- [Atributy](/dotnet/standard/design-guidelines/attributes)
- [Zpracování a generování událostí](/dotnet/standard/events/index)