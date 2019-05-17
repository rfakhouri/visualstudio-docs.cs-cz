---
title: 'CA1024: Použijte vlastnosti, kde je to vhodné'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UsePropertiesWhereAppropriate
- CA1024
helpviewer_keywords:
- CA1024
- UsePropertiesWhereAppropriate
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bfedb55c0dcdb1077faea03bca56488ab3da1525
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842458"
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024: Použijte vlastnosti, kde je to vhodné

|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Metoda má název, který začíná `Get`, nepřijímá žádné parametry a vrátí hodnotu, která není pole.

Ve výchozím nastavení, toto pravidlo pouze prohledá veřejné a chráněné metody, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Ve většině případů vlastnosti představují data a provedení metody akce. Vlastnosti jsou dostupné jako pole, které usnadňují jejich použití. Metoda je vhodným kandidátem pro stala vlastností, pokud se nachází jedna z těchto podmínek:

- Nepřijímá žádné argumenty a vrátí informace o stavu objektu.

- Přijímá jeden argument nastavit některá část stav objektu.

Vlastnosti by měla chovat, jako by šlo polí. Pokud nelze metodu by neměla změnit na vlastnost. Metody jsou lepší než vlastnosti v následujících situacích:

- Metoda provádí časově náročná operace. Metoda je perceivably pomalejší než čas, který je potřeba nastavit nebo získat hodnotu pole.

- Metoda provádí převod. Přístup k poli nevrací převedená verze tohoto data, která ukládá.

- Metoda Get má pozorovatelný vedlejší efekt. Načítání hodnoty pole nevytváří žádné vedlejší účinky.

- Je důležité pořadí provádění. Nastaví hodnotu pole není závislý na výskyt jiné operace.

- Volání metody dvakrát za sebou vytvoří jiné výsledky.

- Metoda je statická, ale vrátí objekt, který můžete změnit tak, volající. Načítání hodnoty pole neumožňuje volajícího, aby změna dat uložených v poli.

- Metoda vrátí pole.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změňte metodu na vlastnost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění tohoto pravidla, pokud metoda splňuje splnit aspoň jednu z výše uvedených kritérií.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1024.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="control-property-expansion-in-the-debugger"></a>Ovládací prvek vlastnosti rozšíření v ladicím programu

Jedním z důvodů programátoři Vyhněte se použití vlastnosti je vzhledem k tomu, že nechcete, aby ladicí program automaticky doplnit jej. Například vlastnost může zahrnovat přidělování velkého objektu nebo volání P/Invoke, ale nemusí mít ve skutečnosti všechny pozorovatelný vedlejší účinky.

Ladicí program z vlastností autoexpanding můžete zabránit použitím <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>. Následující příklad ukazuje tento atribut použity pro vlastnost instance.

```vb
Imports System
Imports System.Diagnostics

Namespace Microsoft.Samples

    Public Class TestClass

        ' [...]

        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _
        Public ReadOnly Property LargeObject() As LargeObject
            Get
                ' Allocate large object
                ' [...]
            End Get
        End Property

    End Class

End Namespace
```

```csharp
using System;
using System.Diagnostics;

namespace Microsoft.Samples
{
    publicclass TestClass
    {
        // [...]

        [DebuggerBrowsable(DebuggerBrowsableState.Never)]
        public LargeObject LargeObject
        {
            get
            {
                // Allocate large object
                // [...]
            }
        }
    }
}
```

## <a name="example"></a>Příklad

Následující příklad obsahuje několik metod, které mají být převedeny do vlastností a několik, který by nebyl, protože není chovají jako pole.

[!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]