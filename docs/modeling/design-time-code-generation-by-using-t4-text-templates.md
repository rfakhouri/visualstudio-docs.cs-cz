---
title: Vytvoření kódu v době návrhu pomocí textových šablon T4
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, guidelines for code generation
- text templates, data source model
- TextTemplatingFileGenerator custom tool
- Transform All Templates
- text templates, getting started
- Text Template project item
- text templates, generating code for your application
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8422b32398c99f33575bb03923e1025207e5956e
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476709"
---
# <a name="design-time-code-generation-by-using-t4-text-templates"></a>Vytvoření kódu v době návrhu pomocí textových šablon T4

Textové šablony T4 návrhu umožňují generování programového kódu a další soubory v projektu sady Visual Studio. Obvykle píšete šablony tak, aby se lišily kód, který se generují podle dat z *modelu*. Model je soubor nebo databázi, která obsahuje základní informace o podle požadavků vaší aplikace.

Například můžete mít modelu, který definuje pracovního postupu, buď jako tabulka nebo diagramu. Z modelu můžete vygenerovat software, který se spustí pracovní postup. Když se změní požadavky uživatelů, je snadné diskutovat o nový pracovní postup s uživateli. Opětovné generování kódu z pracovního postupu je spolehlivější než aktualizace kódu ručně.

> [!NOTE]
> A *modelu* se zdroji dat, který popisuje konkrétní aspekty aplikace. Může být libovolný formulář v nástrojích pro jakýkoli typ souboru nebo databáze. Nemusí být v libovolné formě konkrétní, jako je například modelu UML nebo model jazyka specifického pro doménu. Typické modely jsou ve formě tabulky a soubory XML.

Pravděpodobně již máte zkušenosti s generování kódu. Při definování prostředků v **RESX** soubor v řešení sady Visual Studio, sadu tříd a metod se generuje automaticky. Soubor prostředků je mnohem jednodušší a spolehlivější upravit prostředky než by bylo, pokud jste museli upravovat třídy a metody. Kód lze generovat stejným způsobem ze zdroje vlastní návrhu pomocí textových šablon.

Textová šablona obsahuje kombinaci text, který chcete generovat a programový kód, který generuje proměnné části textu. Kód program umožňuje opakujte nebo podmíněně vynechání části generovaného textu. Generovaný text může, samotné se programový kód, který bude součástí vaší aplikace.

## <a name="create-a-design-time-t4-text-template"></a>Vytvoření textové šablony T4 návrhu

1. Vytvořte nový projekt sady Visual Studio, nebo otevřete existující.

2. Přidejte do projektu soubor textové šablony a přiřaďte jí název, který má příponu **.tt**.

    Chcete-li to provést, v **Průzkumníka řešení**, v místní nabídce projektu zvolte **přidat** > **nová položka**. V **přidat novou položku** dialogové okno Vyberte **textové šablony** v prostředním podokně.

    Všimněte si, že **Custom Tool** vlastnost souboru je **TextTemplatingFileGenerator**.

3. Otevřete soubor. Bude již obsahovat následující direktivy:

   ```
   <#@ template hostspecific="false" language="C#" #>
   <#@ output extension=".txt" #>
   ```

    Pokud jste přidali šablony, která má [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekt, bude atribut language "`VB`".

4. Přidejte nějaký text na konci souboru. Příklad:

   ```
   Hello, world!
   ```

5. Uložte soubor.

    Můžete se setkat **upozornění zabezpečení** okno se zprávou s žádostí o potvrzení, že chcete danou šablonou spustit. Klikněte na **OK**.

6. V **Průzkumníka řešení**, rozbalte uzel soubor šablony a zjistíte, který má příponu souboru **.txt**. Tento soubor obsahuje text vytvořený ze šablony.

   > [!NOTE]
   > Pokud váš projekt je projekt jazyka Visual Basic, musíte kliknout na **zobrazit všechny soubory** Chcete-li zobrazit výstupní soubor.

### <a name="regenerate-the-code"></a>Znovu vygenerovat kód

Šablonu se spustí, generování pomocný soubor v některém z následujících případech:

- Šablonu upravit a potom změňte fokus na jiné okno Visual Studio.

- Uložte šablonu.

- Klikněte na tlačítko **Transformovat všechny šablony** v **sestavení** nabídky. To se transformovat všechny šablony v řešení sady Visual Studio.

- V **Průzkumníka řešení**, v místní nabídce libovolného souboru, zvolte **spustit vlastní nástroj**. Tuto metodu použijte k transformaci podmnožinu vybrané šablony.

Projekt sady Visual Studio můžete také nastavit tak, že šablony jsou spouštěny, když jste změnili datových souborů, které čtou. Další informace najdete v tématu [kód znovu se generuje automaticky](#Regenerating).

## <a name="generate-variable-text"></a>Generování textu proměnlivé

Textové šablony umožňují odlišit obsah generovaný soubor pomocí kódu programu.

1. Změnit obsah `.tt` souboru:

   ```csharp
   <#@ template hostspecific="false" language="C#" #>
   <#@ output extension=".txt" #>
   <#int top = 10;

   for (int i = 0; i<=top; i++)
   { #>
      The square of <#= i #> is <#= i*i #>
   <# } #>
   ```

   ```vb
   <#@ template hostspecific="false" language="VB" #>
   <#@ output extension=".txt" #>
   <#Dim top As Integer = 10

   For i As Integer = 0 To top
   #>
       The square of <#= i #> is <#= i*i #>
   <#
   Next
   #>
   ```

2. Uložte soubor .tt a zkontrolujte soubor .txt generované znovu. Vypíše druhých mocnin čísla od 0 do 10.

   Všimněte si, že příkazy jsou uzavřený do složených závorek `<#...#>`a jedním umístěním pro výrazy `<#=...#>`. Další informace najdete v tématu [vytvoření textové šablony T4](../modeling/writing-a-t4-text-template.md).

   Pokud píšete generování kódu [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], `template` by měl obsahovat směrnice `language="VB"`. `"C#"` je výchozí nastavení.

## <a name="debugging-a-design-time-t4-text-template"></a>Ladění textové šablony T4 návrhu

Ladění textové šablony:

- Vložit `debug="true"` do `template` směrnice. Příklad:

   `<#@ template debug="true" hostspecific="false" language="C#" #>`

- Nastavte zarážky v šabloně v stejně, jako byste to udělali pro běžné kód.

- Zvolte **ladit šablonu T4** z místní nabídky souboru textové šablony v Průzkumníku řešení.

   Šablona spustí a zastaví na zarážce. Můžete prozkoumat proměnné a krokovat kód obvyklým způsobem.

> [!TIP]
> `debug="true"` Díky generovaný kód přesněji namapovat na textové šablony, vložením další řádek číslování direktivy do vygenerovaného kódu. Ponecháte-li vyzkoušet, zarážky může přestat běžet v chybném stavu.
>
> Ale i v případě, že nejsou ladění můžete nechat v klauzuli v direktivě šablony. To způsobí, že jenom velmi malé pokles výkonu.

## <a name="generating-code-or-resources-for-your-solution"></a>Generování kódu nebo prostředky pro vaše řešení

Můžete generovat programové soubory, které se liší v závislosti na modelu. Model je vstup například databáze, konfigurační soubor, modelu UML, modelu DSL nebo jiného zdroje. Ze stejného modelu vygenerujete obvykle několik souborů programu. Za tím účelem vytvořte soubor šablony pro každý soubor generovaného programu a přečetl(a) všechny šablony stejného modelu.

### <a name="to-generate-program-code-or-resources"></a>Ke generování programového kódu nebo prostředkům

1. Změňte – direktiva output vygenerovat soubor příslušného typu, například cs, VB, .resx nebo XML.

2. Vložte kód, který bude generování kódu řešení, která požadujete. Například, pokud chcete generovat tři deklarace pole celé číslo v třídě:

    ```csharp

    <#@ template debug="false" hostspecific="false" language="C#" #>
    <#@ output extension=".cs" #>
    <# var properties = new string [] {"P1", "P2", "P3"}; #>
    // This is generated code:
    class MyGeneratedClass {
    <# // This code runs in the text template:
      foreach (string propertyName in properties)  { #>
      // Generated code:
      private int <#= propertyName #> = 0;
    <# } #>
    }
    ```

    ```vb
    <#@ template debug="false" hostspecific="false" language="VB" #>
    <#@ output extension=".cs" #>
    <# Dim properties = {"P1", "P2", "P3"} #>
    class MyGeneratedClass {
    <#
       For Each propertyName As String In properties
    #>
      private int <#= propertyName #> = 0;
    <#
       Next
    #>
    }

    ```

3. Uložte soubor a zkontrolujte vygenerovaný soubor, který nyní obsahuje následující kód:

    ```csharp
    class MyGeneratedClass {
      private int P1 = 0;
      private int P2 = 0;
      private int P3 = 0;
    }
    ```

### <a name="generating-code-and-generated-text"></a>Generování kódu a vygenerovanému textu

Při generování programového kódu, je nejdůležitější nenastal generování kódu, který se spustí v šabloně a výsledný vygenerovaný kód, který je součástí vašeho řešení. Dva jazyků nemusí být stejné.

V předchozím příkladu má dvě verze. V jedné verzi je generování kódu v jazyce C#. V další verzi je generování kódu jazyka Visual Basic. Ale text vytvořený pomocí obou z nich je stejné, a je třída jazyka C#.

Stejným způsobem, můžete použít [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony pro generování kódu v jakémkoli jazyce. Generovaný text nemusí být v libovolném konkrétním jazyce a nemusí být kód programu.

### <a name="structuring-text-templates"></a>Strukturování textových šablon

Jak dobrým zvykem často Představujeme oddělují kód šablony do dvou částí:

- Konfigurace nebo část shromažďování dat, která nastavuje hodnoty v proměnné, ale nemůže obsahovat textové bloky. V předchozím příkladu, tato část je inicializace `properties`.

   V části "modelu" to se někdy nazývá protože sestaví model v obchodě a obvykle přečte soubor modelu.

- Generování textu část (`foreach(...){...}` v příkladu), který používá hodnoty proměnné.

   To není nezbytné oddělení, ale je styl, což usnadňuje čtení šablony díky snížení složitosti části, který obsahuje text.

## <a name="reading-files-or-other-sources"></a>Čtení souborů nebo jiných zdrojů

Pro přístup k souboru modelu nebo databáze, můžete použít kód šablony sestavení, jako je například System.XML. Pokud chcete získat přístup na tato sestavení, je třeba vložit direktivy takovéto:

```
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>
<#@ import namespace="System.IO" #>
```

`assembly` – Direktiva zpřístupní zadané sestavení kódu šablony, stejně jako část odkazy projektu sady Visual Studio. Nemusíte zahrnovat odkaz na System.dll, který je odkazován automaticky. `import` Umožňuje použít typy bez použití jejich plně kvalifikovaných názvů stejným způsobem jako `using` direktivy v souboru běžné programu.

Například po importu **System.IO**, můžete napsat:

```csharp

<# var properties = File.ReadLines("C:\\propertyList.txt");#>
...
<# foreach (string propertyName in properties) { #>
...
```

```vb
<# For Each propertyName As String In
             File.ReadLines("C:\\propertyList.txt")
#>
```

### <a name="opening-a-file-with-a-relative-pathname"></a>Otevření souboru se relativní cesta

K načtení souboru z umístění vzhledem k textu šablony, můžete použít `this.Host.ResolvePath()`. Chcete-li použít. Hostitele, je nutné nastavit `hostspecific="true"` v `template`:

```
<#@ template debug="false" hostspecific="true" language="C#" #>
```

Můžete napsat, například:

```csharp
<# string fileName = this.Host.ResolvePath("filename.txt");
  string [] properties = File.ReadLines(filename);
#>
...
<#  foreach (string propertyName in properties { #>
...
```

```vb
<# Dim fileName = Me.Host.ResolvePath("propertyList.txt")
   Dim properties = File.ReadLines(filename)
#>
...
<#   For Each propertyName As String In properties
...
#>
```

Můžete také použít `this.Host.TemplateFile`, který identifikuje název aktuálnímu souboru šablony.

Typ `this.Host` (v jazyce Visual Basic, `Me.Host`) je `Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost`.

### <a name="getting-data-from-visual-studio"></a>Získání dat ze sady Visual Studio

Chcete-li použít služby poskytované v sadě Visual Studio, nastavte `hostSpecific` atribut a zatížení `EnvDTE` sestavení. Import `Microsoft.VisualStudio.TextTemplating`, které se nachází `GetCOMService()` – metoda rozšíření.  Potom můžete IServiceProvider.GetCOMService() pro přístup k DTE a dalším službám. Příklad:

```src
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>
<#
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetCOMService(typeof(EnvDTE.DTE));
#>

Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>
```

> [!TIP]
> Textové šablony běží ve vlastní doméně aplikace a služby jsou dostupné přes zařazování. V této situaci je spolehlivější než GetService() GetCOMService().

## <a name="Regenerating"></a> Znova se generuje kód automaticky

Několik souborů v řešení sady Visual Studio se obvykle generují s jeden vstupní model. Každý soubor se generuje z vlastní šablony, ale šablony, které všechny odkazovat do stejného modelu.

Pokud se změní modelu zdroje, byste měli znovu spustit všechny šablony v řešení. Chcete-li to provést ručně, zvolte **Transformovat všechny šablony** na **sestavení** nabídky.

Pokud jste nainstalovali Visual Studio SDK modelování, může mít všechny šablony transformuje automaticky pokaždé, když provádíte sestavení. Provedete to úpravou souboru projektu (.csproj nebo .vbproj) v textovém editoru a přidejte následující řádky na konci souboru, za jakékoli jiné `<import>` příkazy:

> [!NOTE]
> SDK transformace textové šablony a Visual Studio SDK modelování jsou nainstalovány automaticky při instalaci konkrétní funkce sady Visual Studio. Další podrobnosti najdete v tématu [tento příspěvek na blogu](https://devblogs.microsoft.com/devops/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/).

::: moniker range="vs-2017"

```xml
<Import Project="$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v15.0\TextTemplating\Microsoft.TextTemplating.targets" />
<PropertyGroup>
   <TransformOnBuild>true</TransformOnBuild>
   <!-- Other properties can be inserted here -->
</PropertyGroup>
```

::: moniker-end

::: moniker range=">=vs-2019"

```xml
<Import Project="$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v16.0\TextTemplating\Microsoft.TextTemplating.targets" />
<PropertyGroup>
   <TransformOnBuild>true</TransformOnBuild>
   <!-- Other properties can be inserted here -->
</PropertyGroup>
```

::: moniker-end

Další informace najdete v tématu [generování kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md).

## <a name="error-reporting"></a>Odesílání sestav chyb

Umístit chybové zprávy a upozornění v okně chyb sady Visual Studio, můžete použít tyto metody:

```
Error("An error message");
Warning("A warning message");
```

## <a name="Converting"></a> Převod existující soubor do šablony

Užitečné funkce šablon je, že vypadají velmi podobně jako soubory, které generují, společně s Některé vložené programového kódu. To naznačuje užitečný způsob vytváření šablony. Nejprve vytvořit soubor běžné jako prototyp, například [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] souboru a poté postupné zavádění generování kódu, který se liší výsledného souboru.

### <a name="to-convert-an-existing-file-to-a-design-time-template"></a>Chcete-li převést existující soubor do šablony návrhu

1. Do projektu sady Visual Studio, přidejte soubor typu, který chcete vygenerovat, například `.cs`, `.vb`, nebo `.resx` souboru.

2. Vyzkoušejte nový soubor, abyste měli jistotu, že funguje.

3. V Průzkumníku řešení změnit příponu názvu souboru na **.tt**.

4. Ověřte následující vlastnosti **.tt** souboru:

   | | |
   |-|-|
   | **Vlastní nástroj =** | **TextTemplatingFileGenerator** |
   | **Akce sestavení =** | **Žádné** |

5. Na začátek souboru vložte následující řádky:

   ```
   <#@ template debug="false" hostspecific="false" language="C#" #>
   <#@ output extension=".cs" #>
   ```

    Pokud chcete zadat generování kódu šablony v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], nastavte `language` atribut `"VB"` místo `"C#"`.

    Nastavte `extension` atribut příponu názvu souboru pro typ souboru, který chcete vygenerovat, například `.cs`, `.resx`, nebo `.xml`.

6. Uložte soubor.

    Pomocné soubor je vytvořen, se zadanou příponou. Její vlastnosti jsou správné pro typ souboru. Například **akce sestavení** by být vlastnost souboru .cs **kompilaci**.

    Ověřte, že vygenerovaný soubor obsahuje obsah jako původní soubor.

7. Identifikujte část souboru, který chcete měnit. Například na součást, která se zobrazí pouze za určitých podmínek nebo součást, která se opakuje, nebo kde konkrétní hodnoty liší. Vložit generování kódu. Uložte soubor a ověřte, že je správně vygenerován pomocný soubor. Tento krok opakujte.

## <a name="guidelines-for-code-generation"></a>Pokyny pro generování kódu

Podrobnosti najdete na [pokyny pro textové šablony T4 zápis](../modeling/guidelines-for-writing-t4-text-templates.md).

## <a name="next-steps"></a>Další kroky

|Další krok|Téma|
|-|-|
|Programujte a laďte pokročilé textové šablony s kódem, který používá pomocných funkcí, zahrnuté soubory a externí data.|[Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)|
|Generování dokumenty ze šablon v době běhu.|[Generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md)|
|Spuštění generování textu mimo sadu Visual Studio.|[Generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md)|
|Transformujte svá data ve formě jazyka specifického pro doménu.|[Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)|
|Procesory direktiv pro transformaci zdrojích dat zápisu.|[Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)|

## <a name="see-also"></a>Viz také

- [Pokyny pro zápis textových šablon T4](../modeling/guidelines-for-writing-t4-text-templates.md)
