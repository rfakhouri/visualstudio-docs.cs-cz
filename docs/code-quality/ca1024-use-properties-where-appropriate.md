---
title: 'CA1024: Použijte vlastnosti, kde je to vhodné'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03318241206b812f4ffb57dddfc6b4f021d600f1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024: Použijte vlastnosti, kde je to vhodné
|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda veřejných nebo chráněného má název, který začíná `Get`, nepřijímá žádné parametry a vrátí hodnotu, která není pole.

## <a name="rule-description"></a>Popis pravidla
 Ve většině případů data představují vlastnosti a metody provádět akce. Vlastnosti jsou dostupné jako pole, které usnadňuje jejich použití. Metoda je vhodným kandidátem k vlastnost, pokud se nachází jedna z těchto podmínek:

-   Nezadávaly žádné argumenty a vrátí informace o stavu objektu.

-   Přijme jeden argument nastavit některé části stav objektu.

 Vlastnosti měl chovat, jako by šlo pole; Pokud metoda nelze, neměli byste ji měnit vlastnosti. Metody jsou lepší, než vlastnosti v následujících situacích:

-   Metoda provádí časově náročná operace. Metoda je perceivably nižší než čas, který je potřeba nastavit nebo získat hodnotu pole.

-   Metoda provede převod. Přístup k poli nevrací převedený verzi data, která ukládá.

-   Metoda Get má pozorovatelné vedlejším účinkem. Načítání hodnoty pole nevytváří žádné vedlejší účinky.

-   Je důležité pořadí zpracování. Nastavení hodnoty pole není závislý na výskyt dalších operací.

-   Volání metody dvakrát za sebou vytvoří odlišné výsledky.

-   Metoda je statická, ale vrátí objekt, který může změnit volající. Načítání hodnoty pole neumožňuje volajícího, aby změnit data, která je uložená podle pole.

-   Metoda vrátí pole.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, změňte metodu na vlastnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačíte upozornění na toto pravidlo, pokud metoda splňuje alespoň jedním z výše uvedených kritérií.

## <a name="controlling-property-expansion-in-the-debugger"></a>Řízení vlastnost rozšíření v ladicím programu
 Jeden z důvodu programátory nepoužívejte vlastnost je vzhledem k tomu, že nechtějí ladicího programu auto-rozbalte ho. Například vlastnost mohou zahrnovat přidělování velkého objektu nebo volání P/Invoke, ale nemusí mít ve skutečnosti žádné pozorovatelné vedlejší účinky.

 Ladicí program můžete zabránit samorozbalovací vlastnosti použitím <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>. Následující příklad ukazuje tento atribut bylo použito pro vlastnost instance.

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
```

## <a name="example"></a>Příklad
 Následující příklad obsahuje několik metod, které mají být převedeny na vlastnosti a několik, který má není, protože není chovají jako pole.

 [!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]