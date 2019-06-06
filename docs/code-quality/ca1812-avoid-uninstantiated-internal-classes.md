---
title: 'CA1812: Vyhněte se nevytvořeným instancím interních tříd'
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6946434708e38bde7f6efcfc8404da14f91b41ee
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744705"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: Vyhněte se nevytvořeným instancím interních tříd

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Vnitřní typ (na úrovni sestavení) je nikdy vytvořena instance.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo pokusí vyhledat volání jednoho z konstruktorů typu a oznámí porušení, pokud se nenajde žádný volání.

Následující typy nejsou prozkoumat toto pravidlo:

- Typy hodnot

- Abstraktní typy

- Výčty

- Delegáty

- Typy generované kompilátoru pole

- Typy, které se nedá vytvořit instance, které definují pouze [ `static` ](/dotnet/csharp/language-reference/keywords/static) ([ `Shared` v jazyce Visual Basic](/dotnet/visual-basic/language-reference/modifiers/shared)) metody.

Pokud použijete <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> sestavení, který je analyzován, toto pravidlo nebude příznakem typy, které jsou označeny jako [ `internal` ](/dotnet/csharp/language-reference/keywords/internal) ([ `Friend` v jazyce Visual Basic](/dotnet/visual-basic/language-reference/modifiers/friend)) vzhledem k tomu, že pole může být používané sestavení typu friend.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte typ nebo přidejte kód, který ji používá. Pokud typ obsahuje pouze `static` jednu z následujících metod, přidejte na typ pro zabránění kompilátoru generování výchozí veřejný konstruktor instance:

- `static` Modifikátor pro C# typy, které jsou cíleny na rozhraní .NET Framework 2.0 nebo novější.

- Soukromý konstruktor pro typy, které jsou cíleny na rozhraní .NET Framework verze 1.0 a 1.1.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla. Doporučujeme vám, že je potlačení tohoto upozornění v těchto situacích:

- Třída je vytvořená prostřednictvím reflexe pozdní vazby metod, jako <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.

- Třída je vytvářena automaticky nástrojem runtime nebo technologie ASP.NET. Některé příklady automaticky vytvořené třídy jsou ty, které implementují <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> nebo <xref:System.Web.IHttpHandler?displayProperty=fullName>.

- Třídy je předán jako parametr typu, který má [ `new` omezení](/dotnet/csharp/language-reference/keywords/new-constraint). V následujícím příkladu budou označeny pravidlem CA1812:

    ```csharp
    internal class MyClass
    {
        public DoSomething()
        {
        }
    }
    public class MyGeneric<T> where T : new()
    {
        public T Create()
        {
            return new T();
        }
    }

    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

## <a name="related-rules"></a>Související pravidla

- [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)
- [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)
- [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)