---
title: T4 – direktiva Template
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b26f0a6b58a1851e7e348ff367fe81f31eec4a56
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952651"
---
# <a name="t4-template-directive"></a>T4 – direktiva Template

A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] textové šablony T4 obvykle začíná `template` – direktiva, která určuje, jakým způsobem má být zpracován šablony. V textové šabloně a v žádném souboru, který zahrnuje, by neměla existovat více než jedna direktiva šablony.

 Obecné informace o zápisu textové šablony, najdete v části [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).

## <a name="using-the-template-directive"></a>Použití direktivy šablony

```
<#@ template [language="VB"] [compilerOptions="options"] [culture="code"] [debug="true"] [hostspecific="true"] [inherits="templateBaseClass"] [visibility="internal"] [linePragmas="false"] #>
```

 `template` – Direktiva má několik atributů, které umožňují určit různé aspekty transformace. Všechny tyto atributy jsou volitelné.

## <a name="compileroptions-attribute"></a>Atribut compilerOptions
 Příklad: `compilerOptions="optimize+"`

 Platné hodnoty: žádné platné kompilátoru možnosti.

 U šablon běhu (předzpracovaných) se ignoruje.

 Tyto možnosti se použijí, když šablonu byl převeden do [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)], a kompiluje výsledný kód.

## <a name="culture-attribute"></a>Atribut culture
 Příklad: `culture="de-CH"`

 Platné hodnoty: "", neutrální jazykovou verzi, což je výchozí hodnota.

 Jazyková verze vyjádřená jako řetězec ve formátu xx-XX. Příklad: en US, ja-JP, de-CH, de-DE. Další informace naleznete v tématu <xref:System.Globalization.CultureInfo?displayProperty=fullName>.

 Atribut culture určuje jazykovou verzi použitou při převedení bloku výrazu na text.

## <a name="debug-attribute"></a>Atribut debug
 Příklad:
 ```
debug="true"
```

 Platné hodnoty: `true, false`. Výchozí hodnota je false.

 Pokud `debug` atribut je `true`, zprostředkující kód soubor bude obsahovat informace, které umožňují ladicí program k identifikaci přesněji pozici v šabloně, kde došlo k přerušení nebo výjimky.

 Pro návrh šablony budou zapisovat do souboru zprostředkující kódu vaší **% TEMP %** adresáře.

 V ladicím programu spustit šablonu návrhu, uložit textové šablony, pak otevřete v místní nabídce textové šablony v Průzkumníku řešení a zvolte **ladění šablony T4**.

## <a name="hostspecific-attribute"></a>Atribut hostspecific
 Příklad:
 ```
hostspecific="true"
```

 Platné hodnoty: `true, false, trueFromBase`. Výchozí hodnota je false.

 Pokud nastavíte hodnotu tohoto atributu na `true`, vlastnost s názvem `Host` je přidán do třídy generované textové šablony. Vlastnost je odkaz na hostitele transformační modul a je deklarován jako <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Pokud jste definovali vlastního hostitele, lze jej přetypovat na typ vlastního hostitele.

 Protože typ této vlastnosti závisí na typu hostitele, je užitečný pouze při psaní textové šablony, která funguje pouze s konkrétním hostitelem. Používá se pro [návrhu šablony](../modeling/design-time-code-generation-by-using-t4-text-templates.md), ale ne [běhu šablony](../modeling/run-time-text-generation-with-t4-text-templates.md).

 Když `hostspecific` je `true` a používáte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], může odevzdat `this.Host` k IServiceProvider pro přístup k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] funkce. Můžete také použít `Host.ResolvePath(filename)` získat absolutní cestu k souboru v projektu. Příklad:

```csharp
<#@ template debug="false" hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#@ import namespace="System.IO" #>
<# // Get the Visual Studio API as a service:
 DTE dte = ((IServiceProvider)this.Host).GetCOMService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>

<#
 // Find a path within the current project:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>

```

 Pokud použijete `inherits` a `hostspecific` atributy společně, zadejte hostitele = "trueFromBase" v odvozené třídě a hostitele = "true" v základní třídě. Tím je zabráněno dvojité definice `Host` vlastnost generovaného kódu.

## <a name="language-attribute"></a>Atribut language
 Příklad: `language="VB"`

 Platné hodnoty: `C#` (výchozí)

 `VB`

 Atribut language Určuje jazyk ([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]) pro zdrojový kód v blocích prohlášení a výraz. Soubor mezikódu, ze kterého je výstup vygenerován, bude používat tento jazyk. Tento jazyk nesouvisí s jazykem, který generuje šablona, což může být libovolný typ textu.

 Příklad:

```vb
<#@ template language="VB" #>
<#@ output extension=".txt" #>
Squares of numbers:
<#
  Dim number As Integer
  For number = 1 To 4
#>
  Square of <#= number #> is <#= number * number #>
<#
  Next number
#>

```

## <a name="inherits-attribute"></a>Atribut inherits
 Můžete určit, že programový kód šablony může dědit z jiné třídy, která může být rovněž vygenerována z textové šablony.

### <a name="inheritance-in-a-run-time-preprocessed-text-template"></a>Dědičnost v textových šablonách běhu (předzpracovaných)
 Dědičnost lze použít mezi textovými šablonami běhu k vytvoření základní šablony, která má několik odvozených variant. Spuštění šablony jsou ty, které mají **Custom Tool** vlastnost nastavena na hodnotu **texttemplatingfilepreprocessor –**. Šablona běhu generuje kód, který lze v aplikaci volat pro vytvoření textu definovaného v šabloně. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

 Pokud nezadáte `inherits` atribut, základní a odvozené třídy, které se generují z textové šablony. Pokud zadáte `inherits` je generován atribut, odvozené třídy. Základní třídu můžete napsat ručně, ale musí poskytovat metody, které jsou používány odvozenou třídou.

 Obvykleji se jako základní třída určuje jiná předzpracovaná šablona. Základní šablona poskytuje běžné bloky textu, které mohou být proloženy textem z odvozených šablon. Můžete použít třídu funkce bloky `<#+ ... #>` definovat metody, které obsahují fragmenty textu. Do základní šablony lze například umístit rámec výstupního textu a poskytnout tak virtuální metody, které lze v odvozených třídách přepsat:

 Textová šablona běhu (předzpracovaná) BaseTemplate.tt:
 ```scr
This is the common header.
<#
  SpecificFragment1();
#>
A common central text.
<#
  SpecificFragment2();
#>
This is the common footer.
<#+
  // Declare abstract methods
  protected virtual void SpecificFragment1() { }
  protected virtual void SpecificFragment2() { }
#>

```

 Textová šablona běhu (předzpracovaná) DerivedTemplate1.tt:
 ```csharp
<#@ template language="C#" inherits="BaseTemplate" #>
<#
  // Run the base template:
  base.TransformText();
#>
<#+
// Provide fragments specific to this derived template:
protected override void SpecificFragment1()
{
#>
   Fragment 1 for DerivedTemplate1
<#+
}
protected override void SpecificFragment2()
{
#>
   Fragment 2 for DerivedTemplate1
<#+
}
#>

```

 Kód aplikace pro vyvolání DerivedTemplate1:
 ```csharp
Console.WriteLine(new DerivedTemplate().TransformText());
```

 Výsledný výstup:
 ```
This is the common header.
   Fragment 1 for DerivedTemplate1
A common central text.
   Fragment 2 for DerivedTemplate1
This is the common footer.
```

 Základní a odvozené třídy lze sestavit v různých projektech. Nezapomeňte přidat základní projekt nebo sestavení, odkazy na odvozené projektu.

 Jako základní třídu lze také použít běžnou ručně psanou třídu. Základní třída musí poskytovat metody používané v odvozené třídě.

> [!WARNING]
>  Pokud použijete `inherits` a `hostspecific` atributy společně, zadejte hostspecific = "trueFromBase" v odvozené třídě a hostitele = "true" v základní třídě. Tím je zabráněno dvojité definice `Host` vlastnost generovaného kódu.

### <a name="inheritance-in-a-design-time-text-template"></a>Dědičnost v textové šabloně návrhu
 Návrh textové šablony je soubor, pro kterou **Custom Tool** je nastaven na **TextTemplatingFileGenerator**. Šablona generuje soubor výstupní kód nebo textu, který je součástí vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Při vygenerování výstupního souboru je šablona nejdříve přeložena do souboru programového mezikódu, který není obvykle vidět. `inherits` Atribut určuje základní třídu pro tento zprostředkující kód.

 Pro návrh textové šablony, můžete zadat všechny základní třídy, která je odvozena z <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>. Použití `<#@assembly#>` direktiva k načtení sestavení nebo projektu, který obsahuje základní třídy.

 Další informace najdete v tématu ["Dědičnosti v textové šablony" v blogu Gareth Petr](http://go.microsoft.com/fwlink/?LinkId=208373).

## <a name="linepragmas-attribute"></a>Atribut LinePragmas
 Příklad: `linePragmas="false"`

 Platné hodnoty: `true` (výchozí)

 `false`

 Nastavení tohoto atributu na hodnotu false odstraní značky, které identifikují čísla řádků ve vygenerovaném kódu. To znamená, že kompilátor nahlásí jakékoli chyby pomocí čísel řádků generovaného kódu. To vám dává další možnosti ladění, protože se můžete rozhodnout pro ladění textové šablony nebo vygenerovaného kódu.

 Tento atribut může také pomoci, pokud jste hledání, že absolutní názvy souborů v direktivách pragma způsobují rušivě sloučení ve správě zdrojového kódu.

## <a name="visibility-attribute"></a>Atribut visibility
 Příklad: `visibility="internal"`

 Platné hodnoty: `public` (výchozí)

 `internal`

 V textové šabloně běhu se tímto nastavuje atribut visibility vygenerované třídy. Ve výchozím nastavení, třída je součástí veřejné rozhraní API, kód, ale nastavením `visibility="internal"` můžete zkontrolovat, že pouze kódu můžete použít třídu generování textu.
