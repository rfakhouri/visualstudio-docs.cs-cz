---
title: "Generování textu běhu pomocí textových šablon T4 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- Preprocessed Text Template project item
- TextTemplatingFilePreprocessor custom tool
- text templates, TransformText() method
- text templates, generating files at run time
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: f3900a9f42791f4b71ef221bbeb1f010d1785917
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="run-time-text-generation-with-t4-text-templates"></a>Generování textu za běhu pomocí textových šablon T4

Můžete vygenerovat textové řetězce ve vaší aplikaci v době běhu pomocí textových šablon modulu runtime Visual Studio. Počítače, kde se spouští aplikace nemá mít Visual Studio. Modul runtime šablony se někdy označuje jako "zpracované textové šablony" vzhledem k tomu, že v době kompilace Šablona generuje kód, který se spustí v době běhu.

Každá šablona je kombinaci textu, jak se zobrazí v generované řetězec a fragmenty kódu programu. Program fragmenty zadat hodnoty pro proměnné části řetězce a také řízení podmíněného a opakované částí.

Například následující šablony může v aplikaci, která vytvoří sestavu ve formátu HTML.

```html
<#@ template language="C#" #>
<html><body>
<h1>Sales for Previous Month</h2>
<table>
    <# for (int i = 1; i <= 10; i++)
       { #>
         <tr><td>Test name <#= i #> </td>
             <td>Test value <#= i * i #> </td> </tr>
    <# } #>
 </table>
This report is Company Confidential.
</body></html>
```

Všimněte si, že šablona je stránku HTML, ve kterém se nahradily proměnné částí kódu programu. Návrh taková stránka může začněte tím, že zápis prototyp statické stránky HTML. Můžete pak nahradit tabulky a dalšími částmi proměnné kódu programu, který generuje obsah, který se liší od jednou na další.

Použití šablony v díky vaše aplikace je snazší zjistit konečné formu výstupu, než ve, například dlouho řada zápisu příkazů. Provádění změn formu výstupu je jednodušší a spolehlivější.

## <a name="creating-a-run-time-text-template-in-any-application"></a>Vytváření v jakékoli aplikaci Run-Time textové šablony

### <a name="to-create-a-run-time-text-template"></a>Chcete-li vytvořit spuštění textové šablony

1. V Průzkumníku řešení, vyberte v místní nabídce projektu **přidat**, **novou položku**.

2. V **přidat novou položku** dialogové okno, vyberte **Runtime textové šablony**. (V jazyce Visual Basic podívejte se do části **společné položky** > **Obecné**.)

3. Zadejte název souboru šablony.

    > [!NOTE]
    > Název souboru šablony se použije jako název třídy generovaného kódu. Proto by neměl mít mezery nebo interpunkční znaménko.

4. Zvolte **přidat**.

    Je vytvořen nový soubor, který má příponu **.tt**. Jeho **Custom Tool** je nastavena na **texttemplatingfilepreprocessor –**. Obsahuje následující řádky:

    ```
    <#@ template language="C#" #>
    <#@ assembly name="System.Core" #>
    <#@ import namespace="System.Linq" #>
    <#@ import namespace="System.Text" #>
    <#@ import namespace="System.Collections.Generic" #>
    ```

## <a name="converting-an-existing-file-to-a-run-time-template"></a>Převádění existující soubor na šablonu běhu

Převést stávající příklad výstupu je dobrý způsob, jak vytvořit šablonu. Například pokud aplikace vygeneruje soubory HTML, můžete spustit tak, že vytvoříte prostý soubor HTML. Ujistěte se, že funguje správně a zda je správný její vzhled. Potom ho zahrňte do projektu sady Visual Studio a ho převést na šablonu.

### <a name="to-convert-an-existing-text-file-to-a-run-time-template"></a>Převést na šablonu spuštění existující textový soubor

1. Přidání souboru do projektu sady Visual Studio. V Průzkumníku řešení klikněte na místní nabídky projektu, zvolte **přidat** > **existující položka**.

2. Nastavte v souboru **vlastní nástroje** vlastnost **texttemplatingfilepreprocessor –**. V Průzkumníku řešení v místní nabídce souboru, zvolte **vlastnosti**.

    > [!NOTE]
    > Pokud už je vlastnost nastavena, ujistěte se, že je **texttemplatingfilepreprocessor –** a není **TextTemplatingFileGenerator**. K tomu může dojít, pokud zahrnete soubor, který již má příponu **.tt**.

3. Změňte příponu názvu souboru do **.tt**. Přestože tento krok je volitelný, pomáhá se vyhnete otevření souboru v editoru nesprávné.

4. Odeberte všechny mezery nebo interpunkční znaménka z hlavní část názvu souboru. Například "Moje webové Page.tt" by být nesprávný, ale "MyWebPage.tt" je správný. Název souboru se použije jako název třídy generovaného kódu.

5. Na začátek souboru vložte následující řádek. Pokud pracujete v projektu jazyka Visual Basic, nahraďte "C" s "VB".

    `<#@ template language="C#" #>`

## <a name="the-content-of-the-run-time-template"></a>Obsah šablony běhu

### <a name="template-directive"></a>– Direktiva šablony

První řádek šablony zachovat, stejně jako tomu bylo při vytváření souboru:

`<#@ template language="C#" #>`

Parametr language, bude záviset na jazyk projektu.

### <a name="plain-content"></a>Nešifrovaná obsahu

Upravit **.tt** souboru tak, aby obsahovala text, který má aplikace vygenerovat. Příklad:

```html
<html><body>
<h1>Sales for January</h2>
<!-- table to be inserted here -->
This report is Company Confidential.
</body></html>
```

### <a name="embedded-program-code"></a>Vložené programovém kódu

Můžete vložit kód programu mezi `<#` a `#>`. Příklad:

```csharp
<table>
    <# for (int i = 1; i <= 10; i++)
       { #>
         <tr><td>Test name <#= i #> </td>
             <td>Test value <#= i * i #> </td> </tr>
    <# } #>
 </table>
```

```vb
<table>
<#
    For i As Integer = 1 To 10
#>
    <tr><td>Test name <#= i #> </td>
      <td>Test value <#= i*i #> </td></tr>
<#
    Next
#>
</table>
```

Všimněte si, že jsou příkazy vložen mezi `<# ... #>` a výrazy jsou vloženy mezi `<#= ... #>`. Další informace najdete v tématu [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).

## <a name="using-the-template"></a>Pomocí šablony

### <a name="the-code-built-from-the-template"></a>Kód vytvořené ze šablony

Při ukládání **.tt** souboru, dceřiné společnosti **.cs** nebo **VB** se vygeneruje soubor. Chcete-li zobrazit tento soubor v Průzkumníku řešení, rozbalte **.tt** uzel souboru. V projektu jazyka Visual Basic, nejprve vyberte **zobrazit všechny soubory** na panelu nástrojů v Průzkumníku řešení.

Všimněte si, že jiné soubor obsahuje konkrétní třídu, která obsahuje metodu s názvem `TransformText()`. Tuto metodu lze volat z vaší aplikace.

### <a name="generating-text-at-run-time"></a>Generování textu za běhu

V kódu aplikace můžete vygenerovat obsah šablony pomocí volání takto:

```csharp
MyWebPage page = new MyWebPage();
String pageContent = page.TransformText();
System.IO.File.WriteAllText("outputPage.html", pageContent);
```

```vb
Dim page = New My.Templates.MyWebPage
Dim pageContent = page.TransformText()
System.IO.File.WriteAllText("outputPage.html", pageContent)
```

Pokud chcete umístit generovaná třída v oboru názvů konkrétní, nastavte **vlastní nástroj Namespace** vlastnost textového souboru šablony.

### <a name="debugging-runtime-text-templates"></a>Ladění za běhu textové šablony

Ladění a testování runtime textové šablony stejně jako obyčejnou kód.

Můžete nastavit zarážky v textové šablony. Pokud spustíte aplikaci v režimu ladění ze sady Visual Studio, můžete kód krokovat a vyhodnocení výrazů obvyklým způsobem.

### <a name="passing-parameters-in-the-constructor"></a>Předávání parametrů v konstruktoru

Šablonu obvykle nutné importovat některá data z dalších částí aplikace. Usnadnění, kód vytvořené šablony je konkrétní třídu. Další součástí stejné třídy můžete vytvořit v jiném souboru ve vašem projektu. Tento soubor může obsahovat konstruktor s parametry, vlastnosti a funkce, které můžete získat přístup, jak kód, který se vloží v šabloně a zbývající aplikace.

Například můžete vytvořit samostatný soubor **MyWebPageCode.cs**:

```csharp
partial class MyWebPage
{
    private MyData m_data;
    public MyWebPage(MyData data) { this.m_data = data; }}
```

V souboru šablony **MyWebPage.tt**, můžete napsat:

```html
<h2>Sales figures</h2>
<table>
<# foreach (MyDataItem item in m_data.Items)
   // m_data is declared in MyWebPageCode.cs
   { #>
      <tr><td> <#= item.Name #> </td>
          <td> <#= item.Value #> </td></tr>
<# } // end of foreach
#>
</table>
```

Chcete-li tuto šablonu použít v aplikaci:

```csharp
MyData data = ...;
MyWebPage page = new MyWebPage(data);
String pageContent = page.TransformText();
System.IO.File.WriteAllText("outputPage.html", pageContent);
```

#### <a name="constructor-parameters-in-visual-basic"></a>Konstruktor parametry v jazyce Visual Basic

V jazyce Visual Basic, samostatný soubor **MyWebPageCode.vb** obsahuje:

```vb
Namespace My.Templates
  Partial Public Class MyWebPage
    Private m_data As MyData
    Public Sub New(ByVal data As MyData)
      m_data = data
    End Sub
  End Class
End Namespace
```

Soubor šablony můžou obsahovat:

```html
<#@ template language="VB" #>
<html><body>
<h1>Sales for January</h2>
<table>
<#
    For Each item In m_data.Items
#>
    <tr><td>Test name <#= item.Name #> </td>
      <td>Test value <#= item.Value #> </td></tr>
<#
    Next
#>
</table>
This report is Company Confidential.
</body></html>
```

Šablony můžete vyvolat předání parametru v konstruktoru:

```vb
Dim data = New My.Templates.MyData
    ' Add data values here ....
Dim page = New My.Templates.MyWebPage(data)
Dim pageContent = page.TransformText()
System.IO.File.WriteAllText("outputPage.html", pageContent)
```

#### <a name="passing-data-in-template-properties"></a>Předávání dat ve vlastnostech šablony

Alternativní způsob předávání dat v šabloně je přidání veřejné vlastnosti pro třídu šablony v definici třídu. Aplikace můžete nastavit vlastnosti před vyvoláním `TransformText()`.

Můžete také přidat pole do vaší třídy šablony v definici částečné. Můžete k předávání dat mezi následných spuštěních šablony.

### <a name="use-partial-classes-for-code"></a>Částečné třídy použijte pro kód

Celá řada vývojářů přednost tomu, aby se zabránilo zápis velké části kódu v šablonách. Místo toho můžete definovat metody v částečné třídy, která má stejný název jako soubor šablony. Tyto metody volejte ze šablony. Tímto způsobem další šablony ukazuje jasně jaké cílový výstupní řetězec bude vypadat. Diskuze o vzhledu výsledku je možné oddělit z logiky vytváření data, která se zobrazí.

### <a name="assemblies-and-references"></a>Sestavení a odkazy

Pokud chcete, aby váš kód šablony k odkazování rozhraní .NET nebo jiných sestavení, jako **System.Xml.dll**, přidejte ho do svého projektu **odkazy** obvyklým způsobem.

Pokud chcete importovat stejným způsobem jako obor názvů `using` prohlášení, můžete k tomu se `import` – direktiva:

```
<#@ import namespace="System.Xml" #>
```

Tyto direktivy musí být umístěny na začátku souboru ihned po `<#@template` – direktiva.

### <a name="shared-content"></a>Sdílený obsah

Pokud máte text, jež jsou sdílena mezi několik šablon, můžete umístit v samostatném souboru a její zahrnutí do každého souboru, ve kterém by se měla objevit:

```
<#@include file="CommonHeader.txt" #>
```

Na zahrnutý obsah může obsahovat všechny směs programovém kódu a prostý text, a může obsahovat jiné zahrnují direktivy a další direktivy.

Direktiva include lze použít kdekoli v rámci textu souboru šablony nebo součástí souboru.

### <a name="inheritance-between-run-time-text-templates"></a>Dědičnosti mezi Run-Time textové šablony

Můžete sdílet obsah mezi šablonami běhu napsáním základní třída šablony, která může být abstraktní. Použití `inherits` parametr `<@#template#>` direktivu pro odkaz jiné třídy šablony modulu runtime.

#### <a name="inheritance-pattern-fragments-in-base-methods"></a>Vzor dědičnosti: fragmenty v základní metody

Ve vzoru použitých v tomto příkladu, který následuje Všimněte si následující body:

- Základní třída `SharedFragments` definuje metod v rámci třídy funkce bloky `<#+ ... #>`.

- Základní třída obsahuje žádné volné. Místo toho všechny jeho text bloky dojít uvnitř funkce metody třídy.

- Vyvolá metody definované v odvozené třídě `SharedFragments`.

- Volání aplikace `TextTransform()` metoda odvozené třídy, ale nebudou transformovat základní třídy `SharedFragments`.

- Základní a odvozené třídy jsou runtime textové šablony; To znamená **Custom Tool** je nastavena na **texttemplatingfilepreprocessor –**.

**SharedFragments.tt:**

```
<#@ template language="C#" #>
<#+
protected void SharedText(int n)
{
#>
   Shared Text <#= n #>
<#+
}
// Insert more methods here if required.
#>
```

**MyTextTemplate1.tt:**

```
<#@ template language="C#" inherits="SharedFragments" #>
begin 1
   <# SharedText(2); #>
end 1
```

**MyProgram.cs:**

```csharp
...
MyTextTemplate1 t1  = new MyTextTemplate1();
string result = t1.TransformText();
Console.WriteLine(result);
```

**Výsledný výstup:**

```
begin 1
    Shared Text 2
end 1
```

#### <a name="inheritance-pattern-text-in-base-body"></a>Vzor dědičnosti: Text v základní text

V tomto alternativním přístupu pomocí šablony dědičnosti hromadné textu je definována v šabloně základní. Odvozené šablony poskytují data a fragmenty textu, který umístit do základní obsah.

**AbstractBaseTemplate1.tt:**

```
<#@ template language="C#" #>

Here is the description for this derived template:
  <#= this.Description #>

Here is the fragment specific to this derived template:
<#
  this.PushIndent("  ");
  SpecificFragment(42);
  this.PopIndent();
#>
End of common template.
<#+
  // State set by derived class before calling TextTransform:
  protected string Description = "";
  // 'abstract' method to be defined in derived classes:
  protected virtual void SpecificFragment(int n) { }
#>
```

**DerivedTemplate1.tt:**

```
<#@ template language="C#" inherits="AbstractBaseTemplate1" #>
<#
  // Set the base template properties:
  base.Description = "Description for this derived class";

  // Run the base template:
  base.TransformText();

#>
End material for DerivedTemplate1.

<#+
// Provide a fragment specific to this derived template:

protected override void SpecificFragment(int n)
{
#>
   Specific to DerivedTemplate1 : <#= n #>
<#+
}
#>
```

**Kód aplikace:**

```csharp
...
DerivedTemplate1 t1 = new DerivedTemplate1();
string result = t1.TransformText();
Console.WriteLine(result);
```

**Výsledný výstup:**

```
Here is the description for this derived template:
  Description for this derived class

Here is the fragment specific to this derived template:
     Specific to DerivedTemplate1 : 42
End of common template.
End material for DerivedTemplate1.
```

## <a name="related-topics"></a>Související témata

Návrh šablony: Pokud chcete použít šablonu pro generování kódu, se stane součástí aplikace, najdete v části [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md).

Spuštění šablony lze použít v jakékoli aplikaci určeným šablony a jejich obsah v době kompilace. Ale pokud chcete zapsat rozšíření sady Visual Studio, který generuje text ze šablon, které změní za běhu, najdete v části [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).

## <a name="see-also"></a>Viz také

- [Vytvoření kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md)
- [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)
- [T4 Toolbox](http://olegsych.com/T4Toolbox/)