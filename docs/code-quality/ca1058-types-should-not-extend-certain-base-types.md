---
title: 'CA1058: Typy by neměly rozšiřovat určité základní typy'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5d88f08746035792913601b280a0794a9ff50bf2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62795759"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Typy by neměly rozšiřovat určité základní typy

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ rozšiřuje jednu z následujících základních typů:

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Pro rozhraní .NET Framework verze 1, se doporučuje k odvození nové výjimky z <xref:System.ApplicationException>. Došlo ke změně doporučení a nové výjimky musí být odvozený z: <xref:System.Exception?displayProperty=fullName> nebo jeden z jejích podtříd v <xref:System> oboru názvů.

Nelze vytvořit podtřídu <xref:System.Xml.XmlDocument> Pokud budete chtít vytvořit zobrazení základní objekt model nebo zdroj dat XML.

### <a name="non-generic-collections"></a>Neobecnou kolekce

Použít a/nebo rozšířit obecných kolekcí, kdykoli je to možné. Pokud dříve dodán se netýkají obecné kolekce ve vašem kódu.

**Příklady nesprávné použití**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**Příklady správné použití**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odvodit typ z různých základního typu nebo obecné kolekce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění tohoto pravidla pro porušení o <xref:System.ApplicationException>. Je bezpečné potlačit upozornění tohoto pravidla pro porušení o <xref:System.Xml.XmlDocument>. Je bezpečné pro potlačení varování týkající se obecné kolekce, pokud kód byla vydána dříve.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1058.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).