---
title: 'CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2b59e9b0947c6d2b1cbb37cdc850a144976d495
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd
|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Instance typu na úrovni sestavení není vytvořena kódem v sestavení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo se pokusí vyhledat volání jednoho z konstruktorů typu a sestavy narušení, pokud se nenajde žádný volání.

 Následující typy nejsou zkontrolován tímto pravidlem:

-   Typy hodnot

-   Abstraktní typy

-   Výčty

-   Delegáty

-   Typy polí vygenerované kompilátoru

-   Typy, které nelze vytvořit instanci, které definují `static` (`Shared` v jazyce Visual Basic) jenom metody.

 Pokud použijete <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> na sestavení, které je analyzován, nedojde, toto pravidlo na všechny konstruktory, které jsou označeny jako `internal` protože nemůže určit, zda pole je používán jiným `friend` sestavení.

 I když jste nelze toto omezení obejít v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] analýza kódu, externí samostatné FxCop dojde na interní konstruktory Pokud každých `friend` sestavení se nachází v analýzy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, odeberte typ nebo přidejte kód, který používá je. Pokud daný typ obsahuje pouze statické metody, přidejte jednu z následujících typu zabránit generování výchozí veřejný konstruktor instance kompilátoru:

-   Soukromý konstruktor pro typy cílených [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze 1.0 a 1.1.

-   `static` (`Shared` v jazyce Visual Basic) modifikátor pro typy cílených [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné upozornění toto pravidlo potlačit. Doporučujeme vám, že můžete potlačit toto upozornění v následujících situacích:

-   Třída je vytvořena prostřednictvím metody reflexe pozdní vazbou například <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.

-   Třída je vytvářena automaticky nástrojem modulu runtime nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]. Například třídy implementující <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> nebo <xref:System.Web.IHttpHandler?displayProperty=fullName>.

-   Třída je předán jako parametr obecného typu, který obsahuje nové omezení. Například v následujícím příkladu se vyvolají toto pravidlo.

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
    // [...]
    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

 V těchto situacích doporučujeme že potlačit toto upozornění.

## <a name="related-rules"></a>Související pravidla
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)