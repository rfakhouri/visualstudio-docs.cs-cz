---
title: Přístup k modelům z textových šablon
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, accessing models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 54bd5c4989f23b1de64a17bdf8d88ccebeb65a38
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952323"
---
# <a name="accessing-models-from-text-templates"></a>Přístup k modelům z textových šablon
Pomocí textových šablon můžete vytvořit sestavu soubory, soubory zdrojového kódu a další textové soubory, které jsou založeny na modely jazyka domény. Základní informace o textové šablony najdete v tématu [generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md). Textové šablony budou fungovat v režimu experimentální při ladění vaší DSL a bude fungovat i v počítači, na kterém jste nasadili DSL.

> [!NOTE]
>  Při vytváření řešení DSL, ukázkový text šablony  **\*.tt** soubory jsou generovány v ladění projektu. Když změníte názvy třídy domény, tyto šablony přestane fungovat. Nicméně tyto základní direktivy, které musíte zahrnout a příklady, které můžete aktualizovat tak, aby odpovídaly vaší DSL.

 Pro přístup modelu z textové šablony:

-   Nastaví vlastnost inherit – direktiva šablony k <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation>. To poskytuje přístup k úložišti.

-   Zadejte procesory direktiv DSL, který chcete získat přístup. Tento kód načte sestavení pro vaše DSL tak, aby jeho domény třídy, vlastnosti a vztahy můžete použít v kódu textové šablony. Načte také soubor modelu, který určíte.

 A `.tt` soubor podobně jako v následujícím příkladu se vytvoří v ladění projektu, když vytvoříte novou [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení z DSL minimální jazyka šablony.

```
<#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
<#@ output extension=".txt" #>
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>

This text will be output directly.

This is the name of the model: <#= this.ModelRoot.Name #>

Here is a list of elements in the model:
<#
  // When you change the DSL Definition, some of the code below may not work.
  foreach (ExampleElement element in this.ExampleModel.Elements)
  {#>
<#= element.Name #>
<#
  }
#>

```

 Všimněte si následujících bodů o tuto šablonu:

-   Domény třídy, vlastnosti a vztahy, které jste definovali v definici DSL, můžete použít šablonu.

-   Načte soubor modelu, který určíte v šabloně `requires` vlastnost.

-   Vlastnost v `this` obsahuje kořenový element. Odtud můžete kódu přejít na další prvky modelu. Název vlastnosti je obvykle stejné jako vaše DSL třídu kořenové domény. V tomto příkladu je `this.ExampleModel`.

-   I když je jazyk, ve kterém jsou zapsány fragmenty kódu C#, můžete vygenerovat text jakéhokoli druhu. Případně můžete napsat kód [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] přidáním vlastnost `language="VB"` k `template` – direktiva.

-   Chcete-li ladit šablony, přidejte `debug="true"` k `template` – direktiva. Tato šablona se otevře v jiné instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Pokud dojde k výjimce. Pokud chcete přejít k ladicímu v určitém bodě v kódu, vložte příkaz `System.Diagnostics.Debugger.Break();`

     Další informace najdete v tématu [ladění textové šablony T4](../modeling/debugging-a-t4-text-template.md).

## <a name="about-the-dsl-directive-processor"></a>O procesoru direktiv DSL
 Šablonu můžete použít třídy domény, které jste definovali ve vaší DSL definice. To je způsobené direktiva, která obvykle se zobrazí u počáteční šablony. V předchozím příkladu je následující.

```
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>
```

 Název direktiva ( `MyLanguage`, v tomto příkladu) je odvozený od názvu vaší DSL. Vyvolá *procesoru direktiv* generovanou jako součást vaší DSL. Můžete najít jeho zdrojový kód v **Dsl\GeneratedCode\DirectiveProcessor.cs**.

 Procesor direktiv DSL provádí dvě hlavní úlohy:

-   Vloží efektivně direktivy sestavení a importovat do šablony, která odkazuje na vaše DSL. To umožňuje používat třídy domény v kódu šablony.

-   Načte soubor, který určíte v `requires` parametr a nastaví vlastnost `this` který odkazuje na kořenový element načíst modelu.

## <a name="validating-the-model-before-running-the-template"></a>Ověřování modelu před spuštěním šablony
 Může způsobit modelu, který má být ověřen před provedením šablony.

```
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1';validation='open|load|save|menu'" #>

```

 Všimněte si, že:

1.  `filename` a `validation` parametry jsou odděleny znakem ";" a musí být bez oddělovačů nebo mezery.

2.  Seznam kategorií ověřování určuje, které metody ověření bude proveden. Více kategorií by měl být oddělený s "&#124;" a musí být bez oddělovačů nebo mezery.

 Pokud je nalezena chyba, se ohlásí v okně chyby a bude výsledný soubor obsahovat chybovou zprávu.

##  <a name="Multiple"></a> Přístup k více modelů z textové šablony

> [!NOTE]
>  Tato metoda umožňuje číst více modelů do stejné šablony, ale nepodporuje ModelBus odkazy. Modely, které jsou vzájemně propojena podle ModelBus odkazů najdete v tématu [pomocí Visual Studio ModelBus v textové šablony](../modeling/using-visual-studio-modelbus-in-a-text-template.md).

 Pokud chcete pro přístup k více než jeden model ze stejné textové šablony, je třeba zavolat generovaného procesoru direktiv jednou pro každý model. Musíte zadat název souboru každý model v `requires` parametr. Je nutné zadat názvy, které chcete použít pro třídu kořenové domény v `provides` parametr. Musíte zadat různé hodnoty pro `provides` parametry v každé direktivy volání. Předpokládejme například, že máte tři soubory modelu s názvem Library.xyz, School.xyz a Work.xyz. Chcete-li přistupovat k nim z stejné textové šablony, musíte napsat tři direktivy volání podobné těm, které jsou následující.

```
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Library.xyz'" provides="ExampleModel=LibraryModel" #>
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='School.xyz'" provides="ExampleModel=SchoolModel" #>
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Work.xyz'" provides="ExampleModel=WorkModel" #>
```

> [!NOTE]
>  Tento ukázkový kód je pro jazyk, který je založený na šabloně řešení minimální jazyk.

 Pro přístup k modely v textové šablony, můžete nyní můžete napsat kód, podobně jako kód v následujícím příkladu.

```csharp
<#
foreach (ExampleElement element in this.LibraryModel.Elements)
...
foreach (ExampleElement element in this.SchoolModel.Elements)
...
foreach (ExampleElement element in this.WorkModel.Elements)
...
#>
```

```vb
<#
For Each element As ExampleElement In Me.LibraryModel.Elements
...
For Each element As ExampleElement In Me.SchoolModel.Elements
...
For Each element As ExampleElement In Me.WorkModel.Elements
...
#>
```

## <a name="loading-models-dynamically"></a>Dynamické načítání modelů
 Pokud chcete určit za běhu, které modely načíst, můžete načíst soubor modelu dynamicky v programovém kódu, místo použití direktiva DSL specifické.

 Jednou z funkcí DSL specifické – direktiva je však k importu DSL oboru názvů, tak, aby kód šablony můžete používat domény tříd definovaných v této DSL. Vzhledem k tomu, že nepoužíváte direktiva, je nutné přidat  **\<sestavení >** a  **\<import >** direktivy pro všechny modely, které může načíst. Toto je snadno, pokud jsou všechny instance stejné DSL odlišnými modely, které může načíst.

 Načíst soubor, je nejúčinnější pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus. Typický scénář použije textové šablony direktivu DSL konkrétní načíst první model obvyklým způsobem. Tento model by obsahovat ModelBus odkazy na jiný model. ModelBus můžete použít k otevření odkazovaný model a přístup konkrétní elementu. Další informace najdete v tématu [pomocí Visual Studio ModelBus v textové šablony](../modeling/using-visual-studio-modelbus-in-a-text-template.md).

 V případě méně obvykle můžete chtít otevřete soubor modelu, pro které máte pouze název souboru, a které nemusí být v aktuální [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. V takovém případě můžete otevřít soubor pomocí podle postupu popsaného v [postupy: otevření modelu ze souboru v programovém kódu](../modeling/how-to-open-a-model-from-file-in-program-code.md).

## <a name="generating-multiple-files-from-a-template"></a>Generování více souborů ze šablony
 Pokud chcete generovat několik souborů – například můžete vytvořit samostatný soubor pro každý prvek v modelu, existuje několik možných přístupů. Ve výchozím nastavení je vytvořit pouze jeden soubor z každého souboru šablony.

### <a name="splitting-a-long-file"></a>Rozdělení dlouho souboru
 Tato metoda použijte šablonu pro generování jeden soubor, oddělených oddělovač. Pak můžete rozdělit na jednotlivé části. Existují dvě šablony, jednu pro generování jeden soubor a druhým k rozdělení ho.

 **LoopTemplate.t4** generuje dlouho jeden soubor. Všimněte si, že jeho přípona souboru je ".t4", protože by neměl být zpracována přímo po kliknutí **transformaci všech šablon**. Tato šablona přebírá parametr, který určuje oddělovač řetězec, který odděluje segmentů:

```
<#@ template ninherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
<#@ parameter name="delimiter" type="System.String" #>
<#@ output extension=".txt" #>
<#@ MyDSL processor="MyDSLDirectiveProcessor" requires="fileName='SampleModel.mydsl1';validation='open|load|save|menu'" #>
<#
  // Create a file segment for each element:
  foreach (ExampleElement element in this.ExampleModel.Elements)
  {
    // First item is the delimiter:
#>
<#= string.Format(delimiter, element.Id) #>

   Element: <#= element.Name #>
<#
   // Here you generate more content derived from the element.
  }
#>

```

 `LoopSplitter.tt` Vyvolá `LoopTemplate.t4`a následně rozdělí výsledný soubor na jeho segmenty. Všimněte si, protože není pro čtení model nemá tato šablona jako šablonu modelování.

```
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>
<#@ import namespace="System.Runtime.Remoting.Messaging" #>
<#@ import namespace="System.IO" #>

<#
  // Get the local path:
  string itemTemplatePath = this.Host.ResolvePath("LoopTemplate.t4");
  string dir = Path.GetDirectoryName(itemTemplatePath);

  // Get the template for generating each file:
  string loopTemplate = File.ReadAllText(itemTemplatePath);

  Engine engine = new Engine();

  // Pass parameter to new template:
  string delimiterGuid = Guid.NewGuid().ToString();
  string delimiter = "::::" + delimiterGuid + ":::";
  CallContext.LogicalSetData("delimiter", delimiter + "{0}:::");
  string joinedFiles = engine.ProcessTemplate(loopTemplate, this.Host);

  string [] separateFiles = joinedFiles.Split(new string [] {delimiter}, StringSplitOptions.None);

  foreach (string nameAndFile in separateFiles)
  {
     if (string.IsNullOrWhiteSpace(nameAndFile)) continue;
     string[] parts = nameAndFile.Split(new string[]{":::"}, 2, StringSplitOptions.None);
     if (parts.Length < 2) continue;
#>
 Generate: [<#= dir #>] [<#= parts[0] #>]
<#
     // Generate a file from this item:
     File.WriteAllText(Path.Combine(dir, parts[0] + ".txt"), parts[1]);
  }
#>

```