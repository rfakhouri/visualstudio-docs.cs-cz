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
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: abe689021506ab71953e2d6556db8608c301f528
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="design-time-code-generation-by-using-t4-text-templates"></a>Vytvoření kódu v době návrhu pomocí textových šablon T4
Textové šablony T4 návrhu umožňují generování programovém kódu a další soubory v vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Většinou se tak, aby se liší kód, který generují podle data z zápisu šablony *modelu*. Model je soubor nebo databáze, která obsahuje klíčové informace o požadavcích vaší aplikace.

 Například můžete mít model, který definuje pracovní postup, buď jako tabulku nebo diagram. Z modelu můžete vygenerovat software, který spouští pracovní postup. Při změně požadavků vašich uživatelů, je snadné a proberte nový pracovní postup s uživateli. Opětovné generování kódu z pracovního postupu je spolehlivější než aktualizace kód ručně.

> [!NOTE]
>  A *modelu* je zdroj dat, který popisuje určitý aspekt aplikace. Může být žádný formulář, v libovolného typu souboru nebo databáze. Nemá v jakékoli určité formě, například modelu UML nebo model jazyka domény. Typické modely jsou ve formě tabulky nebo soubory XML.

 Pravděpodobně už jste obeznámeni s generování kódu. Když definujete prostředky v **RESX** ve vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, sada třídy a metody je generován automaticky. Soubor prostředků je mnohem jednodušší a spolehlivější upravit prostředky než by bylo, pokud jste museli upravit třídy a metody. S textové šablony mohou generovat kód stejným způsobem jako ze zdroje vlastní návrh.

 Textové šablony obsahuje směs text, který chcete vygenerovat a kód programu, který generuje proměnné části textu. Kód programu a umožňuje opakovat nebo podmíněně vynechejte části generovaného textu. Vygenerovaný text se může sám sebe být kód programu, který bude součástí vaší aplikace.

## <a name="creating-a-design-time-t4-text-template"></a>Vytváření textové šablony T4 návrhu

#### <a name="to-create-a-design-time-t4-template-in-visual-studio"></a>Vytvoření šablony T4 návrhu v sadě Visual Studio

1.  Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu nebo otevření stávajícího.

     Například **soubor** nabídce zvolte **nový**, **projektu**.

2.  Do projektu přidejte textový soubor šablonu a zadejte jeho název, který má příponu **.tt**.

     Chcete-li to provést, v **Průzkumníku řešení**, na místní nabídky projektu, zvolte **přidat**, **novou položku**. V **přidat novou položku** dialogové okno pole vyberte **textové šablony** v prostředním podokně.

     Všimněte si, že **Custom Tool** vlastnost souboru je **TextTemplatingFileGenerator**.

3.  Otevřete soubor. Již bude obsahovat následující direktivy:

    ```
    <#@ template hostspecific="false" language="C#" #>
    <#@ output extension=".txt" #>
    ```

     Pokud jste přidali šablonu, kterou chcete [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projektu, bude atribut language "`VB`".

4.  Přidejte nějaký text na konci souboru. Příklad:

    ```
    Hello, world!
    ```

5.  Uložte soubor.

     Můžete se setkat **upozornění zabezpečení** okno zprávy, které vás vyzve k potvrzení, že chcete spustit šablonu. Click **OK**.

6.  V **Průzkumníku řešení**, rozbalte uzel šablony soubor a soubor, který má příponu **.txt**. Tento soubor obsahuje textu ze šablony.

    > [!NOTE]
    >  Pokud je váš projekt projektu jazyka Visual Basic, musíte kliknout na **zobrazit všechny soubory** Chcete-li zobrazit výstupní soubor.

### <a name="regenerating-the-code"></a>Opětovné generování kódu
 Šablonu bude proveden, generování souboru jiné v některém z následujících případech:

-   K úpravě šablony a poté změňte fokus na jiný [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno.

-   Uložte šablonu.

-   Klikněte na tlačítko **transformaci všech šablon** v **sestavení** nabídky. To bude proveďte transformaci všech šablon v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení.

-   V **Průzkumníku řešení**, v místní nabídce libovolného souboru, zvolte **spustit nástroj pro vlastní**. Tuto metodu použijte k transformaci podmnožinu vybrané šablony.

 Můžete také nastavit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu tak, aby tyto šablony jsou spouštěny, když datové soubory, které budou přečíst změnily. Další informace najdete v tématu [automaticky znovu vygenerovat kód](#Regenerating).

## <a name="generating-variable-text"></a>Generování textu proměnné
 Textové šablony umožňují používat kód programu k odlišení obsah vygenerovaný soubor.

#### <a name="to-generate-text-by-using-program-code"></a>Pro vygenerování textu s použitím kódu programu

1.  Změnit obsah `.tt` souboru:

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

2.  Uložte soubor .tt a znovu zkontrolujte soubor generovaný .txt. Zobrazí se seznam čtverce čísel od 0 do 10.

 Všimněte si, že příkazy jsou uzavřené v rámci `<#...#>`a jedním výrazy v rámci `<#=...#>`. Další informace najdete v tématu [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).

 Pokud píšete generování kódu [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], `template` by měl obsahovat direktiva `language="VB"`. `"C#"` je výchozí.

## <a name="debugging-a-design-time-t4-text-template"></a>Ladění textové šablony T4 návrhu
 K ladění textové šablony:

-   Vložit `debug="true"` do `template` – direktiva. Příklad:

     `<#@ template debug="true" hostspecific="false" language="C#" #>`

-   Nastavte zarážky v šabloně, stejným způsobem, který by pro běžné kód.

-   Zvolte **ladění šablony T4** z místní nabídky k textovému souboru šablony v Průzkumníku řešení.

 Šablona se spustit a zastavit zarážky. Můžete zkontrolovat proměnné a kód krokovat obvyklým způsobem.

> [!TIP]
>  `debug="true"` Díky generovaný kód přesněji mapovat textové šablony vložením číslování direktivy do generovaný kód více řádků. Pokud je necháte out, může přestat zarážky spustit v chybném stavu.
>
>  Ale můžete nechat v klauzuli v – direktiva šablony i v případě, že nejsou ladění. To způsobí, že pouze velmi malé pokles výkonu.

## <a name="generating-code-or-resources-for-your-solution"></a>Generování kódu nebo prostředky pro vaše řešení
 Můžete vygenerovat programových souborů, které se liší v závislosti na modelu. Model je vstup například databáze, konfigurační soubor, modelu UML, DSL modelu nebo jiný zdroj. Několik obvykle generovat programové soubory jsou ze stejného modelu. Jak toho docílit, můžete vytvořit soubor šablony pro každý soubor generovaný program a přečetli všechny šablony stejného modelu.

#### <a name="to-generate-program-code-or-resources"></a>Generovat kód programu nebo prostředky

1.  Změňte direktivu výstupu můžete vytvořit soubor příslušného typu, jako je například .cs, VB, RESX nebo XML.

2.  Vložení kódu, která bude vytvářet řešení kód, který požadujete. Například, pokud chcete generovat tři pole deklarace celé číslo v třídě:

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

3.  Uložte tento soubor a zkontrolujte vygenerovaný soubor, který teď obsahuje následující kód:

    ```
    class MyGeneratedClass {
      private int P1 = 0;
      private int P2 = 0;
      private int P3 = 0;
    }
    ```

### <a name="generating-code-and-generated-text"></a>Generování kódu a vygenerovaný Text
 Při generování kódu programu, je nejdůležitější, aby se zabránilo složitá generování kódu, který spouští v šabloně a výsledný generovaného kódu, který se stane součástí vašeho řešení. Dva jazyky nemusí být stejné.

 V předchozím příkladu má dvě verze. V jedné verzi je generování kódu v jazyce C#. V jiné verzi je generování kódu jazyka Visual Basic. Ale text vytvořený pomocí obou z nich je stejný, a je třída C#.

 Stejným způsobem, můžete použít [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony pro generování kódu v libovolném jazyce. Vygenerovaný text nemusí být v libovolném jazyce konkrétní a nemá být kód programu.

### <a name="structuring-text-templates"></a>Strukturování textové šablony
 Za věc osvědčených postupů jsme mívají k oddělení kód šablony do dvou částí:

-   Konfigurace nebo část shromažďování dat, která nastavuje hodnoty v seznamu proměnných, ale neobsahuje bloky textu. V předchozím příkladu, tuto část je inicializace `properties`.

     To se někdy nazývá v části "model", protože vytvoří model v úložišti a obvykle přečte soubor modelu.

-   Část textu generace (`foreach(...){...}` v příkladu), který používá hodnoty proměnné.

 Toto není nutné oddělení, ale je styl, takže je jednodušší číst šablonu, protože se sníží složitost část, která obsahuje text.

## <a name="reading-files-or-other-sources"></a>Čtení souborů nebo jiných zdrojů
 K přístupu k souboru modelu nebo databáze, můžete použít šablonu kódu sestavení například System.XML. K získání přístupu k tyto sestavení, je třeba vložit direktivy například tyto:

```
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>
<#@ import namespace="System.IO" #>
```

 `assembly` – Direktiva zpřístupní zadané sestavení do kódu šablony, stejným způsobem jako části odkazy [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Nemusíte obsahovat odkaz na System.dll, kterou se odkazuje automaticky. `import` Umožňuje používat typy bez použití jejich plně kvalifikované názvy stejným způsobem jako `using` direktivy v souboru normální program.

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

### <a name="opening-a-file-with-a-relative-pathname"></a>Otevřete soubor s relativní cestou
 Načtení souboru z umístění relativně k textové šablony, můžete použít `this.Host.ResolvePath()`. Chcete-li použít. Hostitele, musíte nastavit `hostspecific="true"` v `template`:

```
<#@ template debug="false" hostspecific="true" language="C#" #>

```

 Potom můžete napsat, například:

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

 Můžete také použít `this.Host.TemplateFile`, který identifikuje název aktuální soubor šablony.

 Typ `this.Host` (v jazyce Visual Basic, `Me.Host`) je `Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost`.

### <a name="getting-data-from-includevsprvscode-qualityincludesvsprvsmdmd"></a>Získání dat z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]
 Použití služeb, které jsou součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nastavte `hostSpecific` atribut a zatížení `EnvDTE` sestavení. Potom můžete IServiceProvider.GetCOMService() pro přístup k prostředí DTE a dalších služeb. Příklad:

```scr
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetCOMService(typeof(EnvDTE.DTE));
#>

Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>

```

> [!TIP]
>  Textové šablony běží ve vlastní domény aplikace a služby jsou dostupné přes zařazování. V takovém případě je spolehlivější než GetService() GetCOMService().

##  <a name="Regenerating"></a> Automaticky znovu vygenerovat kód
 V obvykle na několik souborů [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení se generují s jeden vstupní model. Každý soubor se generují z vlastní šablony, ale šablony, které všechny odkazovat na stejný model.

 Pokud se změní modelu zdroje, byste měli znovu spustit všechny šablony v řešení. Chcete-li to provést ručně, zvolte **transformaci všech šablon** na **sestavení** nabídky.

 Pokud jste nainstalovali Visual Studio SDK modelování, je třeba všechny šablony transformovat automaticky vždy, když je vytvořit nové sestavení. K tomu, upravte svůj soubor projektu (.csproj nebo .vbproj) v textovém editoru a přidejte následující řádky na konci souboru, po jakékoliv `<import>` příkazy:

> [!NOTE]
> V 2017 Visual Studio sada SDK Text šablony transformaci a Visual Studio SDK modelování instalují automaticky při instalaci konkrétní funkce sady Visual Studio. Další podrobnosti najdete v tématu [tomto příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2016/12/12/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/).

```
<Import Project="$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v15.0\TextTemplating\Microsoft.TextTemplating.targets" />
<PropertyGroup>
   <TransformOnBuild>true</TransformOnBuild>
   <!-- Other properties can be inserted here -->
</PropertyGroup>
```

 Další informace najdete v tématu [generování kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md).

## <a name="error-reporting"></a>Zasílání zpráv o chybách
 Chybové zprávy a upozornění v umístit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno chyb, můžete použít tyto metody:

```
Error("An error message");
Warning("A warning message");
```

##  <a name="Converting"></a> Převádění existující soubor do šablony
 Užitečné funkce šablon je, že hledají hodně podobá soubory, které generují, společně s Některé vložené programovém kódu. To naznačuje užitečné metodu pro vytvoření šablony. Nejprve vytvořte soubor obyčejnou jako prototyp, jako například [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] souboru a postupné zavádění generování kódu, který se liší, bude výsledný soubor.

#### <a name="to-convert-an-existing-file-to-a-design-time-template"></a>Převést existující soubor na šablonu návrhu

1.  Na vaše [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projekt, přidejte soubor typu, kterou chcete vygenerovat, například `.cs`, `.vb`, nebo `.resx` souboru.

2.  Otestujte nový soubor, abyste měli jistotu, že funguje.

3.  V Průzkumníku řešení, změňte příponu názvu souboru do **.tt**.

4.  Ověřte následující vlastnosti **.tt** souboru:

    |||
    |-|-|
    |**Vlastní nástroj =**|**TextTemplatingFileGenerator**|
    |**Akce sestavení =**|**None**|

5.  Na začátek souboru vložte následující řádky:

    ```
    <#@ template debug="false" hostspecific="false" language="C#" #>
    <#@ output extension=".cs" #>
    ```

     Pokud chcete psát kód generování vaše šablony v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], nastavte `language` atribut `"VB"` místo `"C#"`.

     Nastavte `extension` atribut příponu názvu souboru pro typ souboru, kterou chcete vygenerovat, například `.cs`, `.resx`, nebo `.xml`.

6.  Uložte soubor.

     Pomocný soubor je vytvořen, se zadanou příponou. Jeho vlastnosti jsou správné pro typ souboru. Například **akce sestavení** vlastnost .cs souboru by **zkompilovat**.

     Ověřte, že generovaný soubor obsahuje stejný obsah jako původní soubor.

7.  Identifikujte část souboru, který chcete lišit. Například část, která se zobrazí pouze za určitých podmínek nebo součást, která se opakuje, nebo kde konkrétní hodnoty liší. Vložení generování kódu. Uložení souboru a ověřte, že je soubor jiné správně vygenerováno. Tento krok opakujte.

## <a name="guidelines-for-code-generation"></a>Pokyny pro generování kódu
 Najdete v tématu [pokyny pro textové šablony T4 zápis](../modeling/guidelines-for-writing-t4-text-templates.md).

## <a name="next-steps"></a>Další kroky

|Další krok|Téma|
|---------------|-----------|
|Zápis a ladění pokročilejší textové šablony, s kódem, který používá pomocných funkcí, zahrnuté soubory a externí data.|[Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)|
|Generovat dokumenty ze šablon v době běhu.|[Generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md)|
|Spuštění generování textu mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|[Generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md)|
|Transformovat data ve formátu jazyka domény.|[Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)|
|Zápis procesory direktiv k transformaci zdrojům dat.|[Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)|

## <a name="see-also"></a>Viz také

- [Pokyny pro zápis textových šablon T4](../modeling/guidelines-for-writing-t4-text-templates.md)
