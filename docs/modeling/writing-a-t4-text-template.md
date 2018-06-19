---
title: Tvorba textové šablony T4
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, syntax
- text templates, guide
- text templates, functions that generate text
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 303e7abfd2ea820de660ed70df915765f11b68a5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975517"
---
# <a name="writing-a-t4-text-template"></a>Tvorba textové šablony T4
Textová šablona obsahuje text, který z ní bude vygenerován. Například bude obsahovat šablonu, která vytvoří webovou stránku "\<html >..." a všechny ostatní standardní části na stránce HTML. Vložit do šablony jsou *řízení bloky*, které jsou fragmenty kódu programu. Řídicí bloky poskytují různé hodnoty a umožňují, aby části textu byly podmíněné a opakované.

 Tato struktura usnadňuje vývoj šablon, protože lze začít s prototypem generovaného souboru a postupně vkládat řídicí bloky, které změní výsledek.

 Textové šablony se skládají z těchto částí:

-   **Direktivy** – elementy, které řídí zpracování šablony.

-   **Text bloky** – obsahu, který se zkopíruje přímo do výstupu.

-   **Řízení bloky** -programu kód, který vloží hodnoty proměnné do textu a ovládací prvky podmíněný nebo opakovaných části textu.

 Pokud chcete vyzkoušet příklady v tomto tématu, zkopírujte je do souboru šablony jak je popsáno v [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md). Po dokončení úprav souboru šablony, uložit jej a poté zkontrolujte výstup **.txt** souboru.

## <a name="directives"></a>Direktivy
 Direktivy textové šablony poskytují obecné pokyny modulu šablon textu o tom, jak generovat kód transformace a výstupní soubor.

 Například následující direktiva určuje, že výstupní soubor má mít příponu .txt:

```

<#@ output extension=".txt" #>
```

 Další informace o direktivy najdete v tématu [direktivy textových šablon T4](../modeling/t4-text-template-directives.md).

## <a name="text-blocks"></a>Bloky textu
 Blok textu vloží text přímo do výstupního souboru. Pro bloky textu neexistuje žádné zvláštní formátování. Například následující textová šablona vytvoří textový soubor, který obsahuje slovo „Hello“:

```
<#@ output extension=".txt" #>
Hello
```

## <a name="control-blocks"></a>Řídicí bloky
 Řídicí bloky jsou části programového kódu, které slouží k transformaci šablon. Výchozí jazyk je C#, ale chcete-li použít jazyk [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], lze tuto direktivu napsat na začátku souboru:

```
<#@ template language="VB" #>
```

 Jazyk, ve kterém píšete kód v řídicích blocích, nesouvisí s jazykem textu, který je generován.

### <a name="standard-control-blocks"></a>Standardní řídicí bloky
 Standardní řídicí blok je část programového kódu, která generuje část výstupního souboru.

 V souboru šablony lze používat libovolný počet textových bloků se standardními řídicími bloky. Nelze však umístit jeden řídicí blok uvnitř jiného. Každý standardní řídicí blok je ohraničen symboly `<# ... #>`.

 Například následující řídicí blok a blok textu způsobí, že výstupní soubor bude obsahovat řádek „0, 1, 2, 3, 4 Hello!“:

```

      <#
    for(int i = 0; i < 4; i++)
    {
        Write(i + ", ");
    }
    Write("4");
#> Hello!
```

 Namísto použití explicitních příkazů `Write()` lze text a kód prokládat. Následující příklad zobrazí "text Hello"! čtyřikrát:

```
<#
    for(int i = 0; i < 4; i++)
    {
#>
Hello!
<#
    }
#>
```

 Blok textu lze vložit všude, kde je v kódu povolen příkaz `Write();`.

> [!NOTE]
>  Když vložíte bloku textu v rámci složený příkaz například smyčku nebo podmíněného, vždy používejte složené závorky {...} tak, aby obsahovala bloku textu.

### <a name="expression-control-blocks"></a>Řídicí bloky výrazu
 Řídicí blok výrazu vyhodnotí výraz a převede jej na řetězec. Ten je vložen do výstupního souboru.

 Řídicí bloky výrazu jsou odděleny symboly `<#= ... #>`.

 Například následující řídicí blok způsobí, že výstupní soubor obsahuje text „5“:

```
<#= 2 + 3 #>
```

 Všimněte si, že počáteční symbol má tři znaky „<#=“.

 Výraz může obsahovat jakoukoli proměnnou, která je v rozsahu. Tento blok například vytiskne řádky s čísly:

```
<#@ output extension=".txt" #>
<#
    for(int i = 0; i < 4; i++)
    {
#>
This is hello number <#= i+1 #>: Hello!
<#
    }
#>
```

### <a name="class-feature-control-blocks"></a>Řídicí bloky s funkcí třídy
 Řídicí blok s funkcí třídy definuje vlastnosti, metody nebo jiný kód, který by neměl být zařazen do hlavní transformace. Bloky s funkcí třídy jsou často používány pro pomocné funkce.  Obvykle bloky funkce třídy jsou umístěny v samostatné soubory tak, aby mohly být [zahrnuté](#Include) více než jeden text šablony.

 Řídicí bloky s funkcí třídy jsou ohraničeny pomocí symbolů `<#+ ... #>`.

 Například následující soubor šablony deklaruje a používá metodu:

```
<#@ output extension=".txt" #>
Squares:
<#
    for(int i = 0; i < 4; i++)
    {
#>
    The square of <#= i #> is <#= Square(i+1) #>.
<#
    }
#>
That is the end of the list.
<#+   // Start of class feature block
private int Square(int i)
{
    return i*i;
}
#>
```

 Funkce třídy musí být umístěny na konci souboru, ve kterém jsou zapsány. Lze však provést `<#@include#>` souboru, který obsahuje funkce třídy, i když je direktiva `include` následována standardními bloky a textem.

 Další informace o řídicí bloky najdete v tématu [řídicí bloky textových šablon](../modeling/text-template-control-blocks.md).

### <a name="class-feature-blocks-can-contain-text-blocks"></a>Bloky s funkcí třídy mohou obsahovat textové bloky.
 Lze zapsat metodu, která generuje text. Příklad:

```
List of Squares:
<#
   for(int i = 0; i < 4; i++)
   {  WriteSquareLine(i); }
#>
End of list.
<#+   // Class feature block
private void WriteSquareLine(int i)
{
#>
   The square of <#= i #> is <#= i*i #>.
<#+
}
#>
```

 Metodu, která generuje text, je vhodné umístit do samostatného souboru, který může obsahovat více než jedna šablona.

## <a name="using-external-definitions"></a>Použití externích definic

### <a name="assemblies"></a>Sestavení
 Bloky kódu šablony mohou používat typy, které jsou definovány nejčastěji používanými sestaveními rozhraní .NET, jako například System.dll. Kromě toho můžete odkazovat na jiné sestavení rozhraní .NET nebo na vlastní sestavení. Lze zadat cestu nebo silný název sestavení:

```
<#@ assembly name="System.Xml" #>
```

 Měli byste používat absolutní názvy cest nebo v názvu cesty použít standardní názvy maker. Příklad:

```
<#@ assembly name="$(SolutionDir)library\MyAssembly.dll" #>
```

 Assembly – direktiva v nemá žádný účinek [předběžně zpracované textové šablony](../modeling/run-time-text-generation-with-t4-text-templates.md).

 Další informace najdete v tématu [T4 – Direktiva Assembly](../modeling/t4-assembly-directive.md).

### <a name="namespaces"></a>Jmenné prostory
 Direktiva import je stejná jako klauzule `using` v jazyce C# nebo klauzule `imports` v jazyce Visual Basic. Umožňuje odkazovat na typy v kódu bez použití plně kvalifikovaného názvu:

```
<#@ import namespace="System.Xml" #>
```

 Můžete použít tolik direktiv `assembly` a `import`, kolik chcete. Je nutné je umístit před textové a řídicí bloky.

 Další informace najdete v tématu [T4 – Direktiva Import](../modeling/t4-import-directive.md).

###  <a name="Include"></a> Včetně kódu a text.
 Direktiva `include` vloží text z jiného souboru šablony. Tato direktiva například vloží obsah souboru `test.txt`.

 `<#@ include file="c:\test.txt" #>`

 Vložený obsah se zpracuje téměř jako kdyby byl součástí textové šablony, která ho vkládá. Můžete však vložit soubor obsahující blok s funkcí třídy `<#+...#>`, i když za direktivou include následuje běžný text a standardní řídicí bloky.

 Další informace najdete v tématu [T4 – direktiva zahrnují](../modeling/t4-include-directive.md).

### <a name="utility-methods"></a>Pomocné metody
 Existuje několik metod, jako je `Write()`, které jsou v řídicím bloku vždy k dispozici. Patří sem metody, které napomáhají odsadit výstup a oznamovat chyby.

 Lze také napsat vlastní sadu pomocných metod.

 Další informace najdete v tématu [pomocné metody textových šablon](../modeling/text-template-utility-methods.md).

## <a name="transforming-data-and-models"></a>Transformace dat a modelů
 Nejužitečnějším použitím textových šablon je generování materiálu na základě obsahu zdroje, jako je model, databáze nebo datový soubor. Šablona extrahuje a přeformátuje data. Pomocí sady šablon lze tyto zdroje transformovat do více souborů.

 Existuje několik způsobů čtení zdrojového souboru.

 **Čtení souboru v textové šablony**. Toto je nejjednodušší způsob, jak vložit data do šablony:

```
<#@ import namespace="System.IO" #>
<# string fileContent = File.ReadAllText(@"C:\myData.txt"); ...
```

 **Načíst soubor jako navigaci model**. Výkonnější metodou je načíst data jako model, kterým kód textové šablony může procházet. Lze například načíst soubor XML a procházet jím pomocí výrazů XPath. Můžete také použít [xsd.exe](http://go.microsoft.com/fwlink/?LinkId=178765) vytvořit sadu tříd, pomocí kterých můžete číst XML data.

 **Upravte soubor modelu v diagramu nebo formuláře.** [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] poskytuje nástroje, které umožňují upravit model jako diagram nebo formuláře Windows. Můžete tak tento model snáze prodiskutovat s uživateli generované aplikace. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] také vytvoří sadu typově silných tříd, které odrážejí strukturu modelu. Další informace najdete v tématu [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md).

### <a name="relative-file-paths-in-design-time-templates"></a>Relativní cesty k souborům v návrhových šablonách
 V [návrhu textové šablony](../modeling/design-time-code-generation-by-using-t4-text-templates.md), pokud chcete odkazovat na soubor v umístění relativně k šabloně text použití `this.Host.ResolvePath()`. Je také nutné nastavit hodnotu `hostspecific="true"` v direktivě `template`:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of MyFile.txt is:
<#= myFile #>

```

Lze také získat další služby, které jsou poskytovány tímto hostitelem. Další informace najdete v tématu [přístup k sadě Visual Studio nebo k jiným hostitelům z šablony](http://msdn.microsoft.com/0556f20c-fef4-41a9-9597-53afab4ab9e4).

### <a name="design-time-text-templates-run-in-a-separate-appdomain"></a>Návrhové textové šablony běží v oddělené doméně AppDomain.

 Je třeba věnovat pozornost, [návrhu textové šablony](../modeling/design-time-code-generation-by-using-t4-text-templates.md) běží v objektu AppDomain, která je oddělená od hlavní aplikace. Ve většině případů to není důležité, ale v některých složitých případech lze narazit na omezení. Pokud například chcete předat data do nebo ze šablony ze samostatné služby, musí tato služba poskytovat serializovatelné rozhraní API.

 (Tato akce není platí [spuštění textové šablony](../modeling/run-time-text-generation-with-t4-text-templates.md), který poskytuje kód, který se zkompiluje spolu s ostatními vašeho kódu.)

## <a name="editing-templates"></a>Úpravy šablon
 Speciální editory textových šablon lze stáhnout z online galerie správce rozšíření. Na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**. Klikněte na tlačítko **Online galerie**a potom pomocí nástroje vyhledávání.

## <a name="related-topics"></a>Související témata

|Úloha|Téma|
|----------|-----------|
|Vytvoření šablony|[Pokyny pro zápis textových šablon T4](../modeling/guidelines-for-writing-t4-text-templates.md)|
|Generování textu pomocí kódu programu|[Struktura textové šablony](../modeling/writing-a-t4-text-template.md)|
|Generování souborů v řešení systému [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|
|Spuštění generování textu mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|[Generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md)|
|Transformovat data ve formátu jazyka domény.|[Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)|
|Zápis procesory direktiv k transformaci zdrojům dat.|[Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)|
