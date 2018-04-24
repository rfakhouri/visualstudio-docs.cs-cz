---
title: Řídicí bloky textových šablon
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, template code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 221985f8bfbac82e294422c57d684322b9036d5f
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="text-template-control-blocks"></a>Řídicí bloky textových šablon
Řídicí bloky umožňují napsat kód v textové šablony, aby bylo možné odlišit výstup. Existují tři druhy řídicí bloky, které jsou rozlišené jejich otvírací závorky:

-   `<# Standard control blocks #>` mohou obsahovat příkazy.

-   `<#= Expression control blocks #>` může obsahovat výrazy.

-   `<#+ Class feature control blocks #>` může obsahovat metody, polí a vlastností.

## <a name="standard-control-block"></a>Blok standardního ovládacího prvku
 Bloky standardního ovládacího prvku obsahovat příkazy. Například následující standardní blok načte názvy všech atributů v dokumentu XML:

```
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>

<#
    List<string> allAttributes = new List<string>();
    XmlDocument xDoc = new XmlDocument();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes.Count > 0)
    {
       foreach (XmlAttribute attr in attributes)
       {
           allAtributes.Add(attr.Name);
       }
     }
#>
```

 Můžete vložit prostý text v rámci složený příkaz `if` nebo `for`. Například fragment vytváří řádku výstupu v každé iteraci smyčky:

```
<#
       foreach (XmlAttribute attr in attributes)
       {
#>
Found another one!
<#
           allAtributes.Add(attr.Name);
       }
#>
```

> [!WARNING]
>  Vždy použijte {...} pro vymezení vnořené příkazy, které obsahují vložených prostý text. V následujícím příkladu se nemusí správně fungovat:
>
>  `<# if (ShouldPrint) #> Some text. -- WRONG`
>
>  Místo toho by měla obsahovat {složené závorky} následujícím způsobem:

```

<#
 if (ShouldPrint)
 {   //  "{" REQUIRED
#>
Some text.
<#
 }
#>

```

## <a name="expression-control-block"></a>Výraz řídicí blok
 Výraz řídicí bloky se používají pro kód, který poskytuje řetězců, které mají být zapsána do výstupního souboru. Například pomocí výše uvedeném příkladu můžete vytisknout názvy atributů do výstupního souboru změnou blok kódu:

```
<#
    XmlDocument xDoc = new XmlDocument();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {
#><#= attr.Name #><#
       }
    }
#>
```

## <a name="class-feature-control-block"></a>Třída funkce řídicí blok
 Třída funkce řídicí bloky můžete použít k přidání metody, vlastnosti, pole nebo i vnořené třídy pro textové šablony. Nejčastěji používá třída funkce bloků je poskytnout pomocných funkcí pro kód v dalších částech tohoto textové šablony. Například následující funkce blok třídy počáteční písmeno názvu atributu (nebo, pokud název obsahuje prázdné znaky, jeho počáteční písmeno každého slova):

```
<#@ import namespace="System.Globalization" #>
```

```
<#+
    private string FixAttributeName(string name)
    {
        return CultureInfo.CurrentCulture.TextInfo.ToTitleCase(name);
    }
#>
```

> [!NOTE]
>  Řídicí blok třída funkce nesmí následovat bloky standardního ovládacího prvku ve stejném souboru šablony. Ale toto omezení se nevztahuje na výsledky pomocí `<#@include#>` direktivy. Každý zahrnuté soubor může mít standardní bloky následuje třída funkce bloky.

 Můžete vytvořit funkci, která generuje výstup vložením text a výraz bloky uvnitř bloku třída funkce ovládacího prvku. Příklad:

```
<#+
    private void OutputFixedAttributeName(string name)
    {
#>
 Attribute:  <#= CultureInfo.CurrentCulture.TextInfo.ToTitleCase(name) #>
<#+  // <<< Notice that this is also a class feature block.
    }
#>
```

 Tato funkce může volat z blok standardní nebo z jiného bloku funkce – třída:

```
<# foreach (Attribute attribute in item.Attributes)
{
  OutputFixedAttributeName(attribute.Name);
}
#>
```

## <a name="how-to-use-control-blocks"></a>Jak používat řídicí bloky
 Všechny kód ve všech do formuláře je kombinaci řídicí bloky standard a výraz v jediné šabloně (včetně všech kód v šablonách zahrnuté) `TransformText()` metoda generovaného kódu. (Další informace o dalších textové šablony s, včetně `include` direktivy, viz [direktivy textových šablon T4](../modeling/t4-text-template-directives.md).)

 Byste měli mít na paměti následující aspekty při použití řídicí bloky:

-   **Jazyk.** Můžete použít buď C# nebo kód jazyka Visual Basic v textové šablony. Je výchozí jazyk C#, ale můžete zadat jazyka Visual Basic s `language` parametr `template` – direktiva. (Další informace o `template` direktivy, viz [direktivy textových šablon T4](../modeling/t4-text-template-directives.md).)

     Jazyk, který používáte v řídicí bloky nijak nesouvisí s jazyk nebo formátu textu, který generovat v textové šablony. Můžete vygenerovat C# s použitím jazyka Visual Basic kód nebo naopak naopak.

     Můžete použít pouze jeden jazyk v šabloně daným textem, včetně všech textových šablon můžete zahrnout `include` – direktiva.

-   **Lokální proměnné.** Vzhledem k tomu, že veškerý kód v ovládacím prvku standard a výraz bloků v textové šablony je generována jako jedinou metodu, měli byste si jisti, že pocházejí ke konfliktům s názvy lokální proměnné. Chcete-li zahrnout další text šablony, musí se ujistěte, že názvy proměnných jsou jedinečné v rámci všech součástí šablony. Jeden způsob, jak zajistit toto je můžete přidat řetězec pro každý místní identifikace textové šablony, ve kterém byla deklarována název proměnné.

     Je také vhodné k chybě při inicializaci místní proměnných rozumný hodnoty, když je deklarovat, zejména v případě, že jsou včetně více textové šablony.

-   **Vnořené řídicí bloky.** Řídicí bloky nelze vnořit do sebe navzájem. Před otevřením jiný musí vždy ukončovat platnost blok daný ovládací prvek. Například následující ukazuje, jak tisknout text v bloku výrazu v rámci bloku standardního ovládacího prvku.

    ```
    <#
    int x = 10;
    while (x-- > 0)
    {
    #>
    <#= x #>
    <# } #>
    ```

-   **Refaktoring.** Chcete-li zachovat text šablony krátká a snadno pochopit, velmi doporučujeme vyhnout se opakují kódu, řešení opakovaně použitelný kód do pomocných funkcí v blocích funkce třídy nebo vytvoření vlastní třídy šablony text, který dědí ze třídy Microsoft.VisualStudio.TextTemplating.TextTransformation.