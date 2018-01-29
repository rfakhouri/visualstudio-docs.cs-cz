---
title: "Referenční dokumentace schématu fragmenty kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema reference [Visual Studio]
- snippets [Visual Studio], schema reference
- code snippets [Visual Studio], schema reference
- IntelliSense Code Snippets, XML Schema
ms.assetid: 58a60621-725f-4763-93b7-62ea5424ef88
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c267b110b67a69b526bb7efc985bb22bb954b3a1
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="code-snippets-schema-reference"></a>Fragmenty kódu – odkaz schématu
IntelliSense – fragmenty kódu jsou předem vytvořené části kódu, které jsou připravené pro vložení do vaší aplikace pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Svou produktivitu můžete zvýšit tak, že vytvoříte fragmenty kódu, které snižují množství času stráveného zadáváním opakujícího se kódu nebo hledáním ukázek. Schéma XML fragment kódu technologie IntelliSense vám pomůže vytvořit vlastní fragmenty kódu a přidat je do fragmenty kódu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] již obsahuje.  
  
## <a name="intellisense-code-snippets-schema-elements"></a>Elementy schématu fragmentů kódu technologie IntelliSense  
  
||||  
|-|-|-|  
|[Assembly – Element](../ide/code-snippets-schema-reference.md#assembly)|[HelpUrl Element](../ide/code-snippets-schema-reference.md#helpurl)|[Element odkazů](../ide/code-snippets-schema-reference.md#references)|  
|[Autor – Element](../ide/code-snippets-schema-reference.md#author)|[ID elementu](../ide/code-snippets-schema-reference.md#id)|[Zástupce – Element](../ide/code-snippets-schema-reference.md#shortcut)|  
|[Element kódu](../ide/code-snippets-schema-reference.md#code)|[Import – Element](../ide/code-snippets-schema-reference.md#import)|[Element fragmentu kódu](../ide/code-snippets-schema-reference.md#snippet)|  
|[CodeSnippet Element](../ide/code-snippets-schema-reference.md#codesnippet)|[Import – Element](../ide/code-snippets-schema-reference.md#imports)|[SnippetType Element](../ide/code-snippets-schema-reference.md#snippettype)|  
|[CodeSnippets Element](../ide/code-snippets-schema-reference.md#codesnippets)|[Element – klíčové slovo](../ide/code-snippets-schema-reference.md#keyword)|[SnippetTypes Element](../ide/code-snippets-schema-reference.md#snippettypes)|  
|[Deklarace Element](../ide/code-snippets-schema-reference.md#declarations)|[Keywords Element](../ide/code-snippets-schema-reference.md#keywords)|[Title Element](../ide/code-snippets-schema-reference.md#title)|  
|[Výchozí Element](../ide/code-snippets-schema-reference.md#default)|[Literál elementu](../ide/code-snippets-schema-reference.md#literal)|[Element popisu tlačítka](../ide/code-snippets-schema-reference.md#tooltip)|  
|[Description – Element](../ide/code-snippets-schema-reference.md#description)|[Namespace Element](../ide/code-snippets-schema-reference.md#namespace)|[Typ elementu](../ide/code-snippets-schema-reference.md#type)|  
|[Element – funkce](../ide/code-snippets-schema-reference.md#function)|[Object Element](../ide/code-snippets-schema-reference.md#object)|[Adresa URL elementu](../ide/code-snippets-schema-reference.md#url)|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|[Referenční dokumentace elementu](../ide/code-snippets-schema-reference.md#reference)||  
  
##  <a name="assembly"></a>Assembly – Element  
 Určuje název sestavení, na které se odkazuje fragment kódu.
  
 Textovou hodnotu **sestavení** element, jako je název popisný text sestavení, `System.dll`, nebo jeho silným názvem, jako třeba `System,Version=1.0.0.1,Culture=neutral,PublicKeyToken=9b35aa323c18d4fb1`.  
  
```xml  
<Assembly>  
    AssemblyName  
</Assembly>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Referenční dokumentace elementu](../ide/code-snippets-schema-reference.md#reference)|Obsahuje informace o odkazech na sestavení vyžadovaných fragmentem kódu.|  
  
 Je vyžadována textová hodnota. Tento text určuje sestavení, na které se odkazuje fragment kódu.  
  
##  <a name="author"></a>Autor – Element  
 Určuje jméno autora fragmentu kódu. **Správce fragmentů kódu** zobrazí název uložené v `Author` element fragmentu kódu.  
  
```xml  
<Author>  
   Code Snippet Author  
</Author>    
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Obsahuje obecné informace o fragmentu kódu.|  
  
 Je vyžadována textová hodnota. Tento text určuje autora fragmentu kódu.  
  
## <a name="a-namecode--code-element"></a><a name="code" />Element kódu  
Poskytuje kontejner pro krátké bloky kódu.  
  
### <a name="keywords"></a>Klíčová slova
Dvě vyhrazená slova jsou k dispozici pro použití v textu `Code` element: `$end$` a `$selected$`. `$end$`označuje umístění umístěte kurzor po vložení fragmentu kódu. `$selected$`představuje text vybraný v dokumentu, který se má být vložen do fragmentu při vyvolání. Například uděleno fragment kódu, který zahrnuje:  
  
```  
$selected$ is a great color.  
```  
  
Pokud je slovo "Blue" je vybrána, když uživatel vyvolá šablony, výsledkem je:  
  
```  
Blue is a great color.  
```  
  
Nesmíte používat buď `$end$` nebo `$selected$` více než jednou ve fragmentu kódu. V takovém případě se rozpozná pouze druhou instanci. Zadaný fragment kódu, který zahrnuje:  
  
```  
$selected$ is a great color. I love $selected$.  
```  
  
Pokud je vybrána slovo "Blue", výsledkem je:  
  
```  
 is a great color. I love Blue.  
```  
  
Počáteční místa se zobrazí, protože je mezera mezi `$selected$` a `is`.  
  
Všechny ostatní `$` klíčová slova jsou dynamicky definované v `<Literal>` a `<Object>` značky.  

Toto je struktura elementu kódu:
  
```xml  
<Code Language="Language"  
    Kind="method body/method decl/type decl/page/file/any"  
    Delimiter="Delimiter">  
    Code to insert  
</Code>  
```

Je vyžadována textová hodnota. Tento text určuje kód, společně s literály a objekty, které můžete použít, když je tento fragment kódu vložíte do souboru kódu.  

### <a name="attributes"></a>Atributy
Nejsou k dispozici pro tento element kódu tři atributy:

- **Jazyk** - _požadované_ atribut, který určuje jazyk fragmentu kódu. Hodnota může být jeden z následujících akcí:

   |Hodnota|Popis|  
   |-----|-----------|  
   |`VB`|Identifikuje fragment kódu jazyka Visual Basic.|  
   |`CSharp`|Identifikuje fragment kódu jazyka C#.|  
   |`CPP`|Identifikuje fragment kódu jazyka C++.|  
   |`XML`|Identifikuje fragment kódu jazyka XML.|  
   |`JavaScript`|Identifikuje fragment kódu jazyka JavaScript.|  
   |`SQL`|Identifikuje fragment kódu jazyka SQL.|  
   |`HTML`|Identifikuje fragment kódu jazyka HTML.|
 
- **Druh** - _volitelné_ atribut, který určuje druh kód, který obsahuje fragmentu a umístění, ve kterém je nutné vložit fragment kódu pro fragmentu kódu ke kompilaci. Hodnota může být jeden z následujících akcí:

   |Hodnota|Popis|  
   |-----|-----------|  
   |`method body`|Určuje, že fragment kódu je tělo metody, a proto musí být vložen dovnitř deklarace metody.|  
   |`method decl`|Určuje, že fragment kódu je metoda, a proto musí být vložen dovnitř třídy nebo modulu.|  
   |`type decl`|Určuje, že fragment kódu je typ, a proto musí být vložen dovnitř třídy, modulu nebo oboru názvů.|  
   |`file`|Určuje, že fragment kódu je celý soubor kódu. Tyto fragmenty kódu lze vložit samotné do souboru kódu nebo do oboru názvů.|  
   |`any`|Určuje, že fragment kódu lze vložit kamkoli. Tato značka se používá pro fragmenty kódu, které jsou nezávislé na kontextu, například pro komentáře.|

- **Oddělovač** - _volitelné_ atribut, který určuje oddělovač použitý k popisu literály a objekty v kódu. Ve výchozím nastavení, oddělovač, který je `$`.

### <a name="parent-element"></a>Nadřazený element
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Element fragmentu kódu](../ide/code-snippets-schema-reference.md#snippet)|Obsahuje odkazy, direktivy import, deklarace a kód fragmentu kódu.|
  
##  <a name="codesnippet"></a>CodeSnippet Element  
 Umožňuje zadat záhlaví a jeden nebo více fragmentů kódu technologie IntelliSense, které lze vložit do souborů kódu sady Visual Studio.  
  
```xml  
<CodeSnippet Format="x.x.x">  
    <Header>... </Header>  
    <Snippet>... </Snippet>  
</CodeSnippet>  
```  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Format`|Požadovaný atribut. Určuje verzi schématu fragmentu kódu. Atribut Format musí být řetězec, který používá syntaxi x.x.x, kde každé písmeno „x“ představuje číselnou hodnotu čísla verze. Visual Studio bude ignorovat fragmenty kódu s `Format` atributy, které není srozumitelný.|  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Požadovaný element. Obsahuje obecné informace o fragmentu kódu. Musí být přesně jeden `Header` element ve fragmentu kódu.|  
|[Element fragmentu kódu](../ide/code-snippets-schema-reference.md#snippet)|Požadovaný element. Obsahuje kód, který bude vložen sadou Visual Studio. Musí být přesně jeden `Snippet` element ve fragmentu kódu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[CodeSnippets Element](../ide/code-snippets-schema-reference.md#codesnippets)|Kořenový element schématu XML fragmentu kódu|  
  
##  <a name="codesnippets"></a>CodeSnippets Element  
 Skupiny [CodeSnippet Element](../ide/code-snippets-schema-reference.md#codesnippet)elementy. `CodeSnippets` Element není kořenovým elementem schématu XML fragment kódu.  
  
```xml  
<CodeSnippets>  
    <CodeSnippet>... </CodeSnippet>  
</CodeSnippets>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[CodeSnippet Element](../ide/code-snippets-schema-reference.md#codesnippet)|Volitelný element. Nadřazený element pro všechna data fragmentu kódu. Může být nula nebo více `CodeSnippet` elementů v `CodeSnippets` elementu.|  
  
##  <a name="declarations"></a>Deklarace Element  
 Určuje literály a objekty tvořící části fragmentu kódu, které lze upravovat.  
  
```xml  
<Declarations>  
    <Literal>... </Literal>  
    <Object>... </Object>  
</Declarations>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Literál elementu](../ide/code-snippets-schema-reference.md#literal)|Volitelný element. Definuje literály fragmentu kódu, které lze upravovat. Může být nula nebo více `Literal` elementů v `Declarations` elementu.|  
|[Object Element](../ide/code-snippets-schema-reference.md#object)|Volitelný element. Definuje objekty fragmentu kódu, které lze upravovat. Může být nula nebo více `Object` elementů v `Declarations` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Element fragmentu kódu](../ide/code-snippets-schema-reference.md#snippet)|Obsahuje odkazy, direktivy import, deklarace a kód fragmentu kódu.|  
  
##  <a name="default"></a>Výchozí Element  
 Určuje výchozí hodnotu literálu nebo objektu pro fragment kódu technologie IntelliSense.  
  
```xml  
<Default>  
    Default value  
</Default>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Literál elementu](../ide/code-snippets-schema-reference.md#literal)|Definuje pole literálu fragmentu kódu, která lze upravovat.|  
|[Object Element](../ide/code-snippets-schema-reference.md#object)|Definuje pole objektu fragment kódu, která lze upravovat.|  
  
 Je vyžadována textová hodnota. Tento text určuje výchozí hodnotu literálu nebo objektu, pomocí níž budou naplněna pole fragmentu kódu, která lze upravovat.  
  
##  <a name="description"></a>Description – Element  
 Určuje popisné informace o obsahu fragmentu kódu technologie IntelliSense.  
  
```xml  
<Description>  
    Code Snippet Description  
</Description>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Obsahuje obecné informace o fragmentu kódu.|  
  
 Je vyžadována textová hodnota. Tento text popisuje fragment kódu.  
  
##  <a name="function"></a>Element – funkce  
 Určuje funkci, která se má provést, když literál nebo objekt získá fokus v sadě Visual Studio.  
  
> [!NOTE]
>  `Function` Element je podporována pouze v fragmenty kódu v C#.  
  
```xml  
<Function>  
    FunctionName  
</Function>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Literál elementu](../ide/code-snippets-schema-reference.md#literal)|Definuje pole literálu fragmentu kódu, která lze upravovat.|  
|[Object Element](../ide/code-snippets-schema-reference.md#object)|Definuje pole objektu fragment kódu, která lze upravovat.|  
  
 Je vyžadována textová hodnota. Tento text určuje funkci, která se má provést, když pole literálu nebo objektu získá fokus v sadě Visual Studio.  
  
##  <a name="header"></a>Header Element  
 Určuje obecné informace o fragmentu kódu technologie IntelliSense.  
  
```xml  
<Header>  
    <Title>... </Title>  
    <Author>... </Author>  
    <Description>... </Description>  
    <HelpUrl>... </HelpUrl>  
    <SnippetTypes>... </SnippetTypes>  
    <Keywords>... </Keywords>  
    <Shortcut>... </Shortcut>  
</Header>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Autor – Element](../ide/code-snippets-schema-reference.md#author)|Volitelný element. Jméno osoby nebo společnosti, která fragment kódu vytvořila. Může být nula nebo jeden `Author` elementů v `Header` elementu.|  
|[Description – Element](../ide/code-snippets-schema-reference.md#description)|Volitelný element. Popis fragmentu kódu. Může být nula nebo jeden `Description` elementů v `Header` elementu.|  
|[HelpUrl Element](../ide/code-snippets-schema-reference.md#helpurl)|Volitelný element. Adresa URL s dalšími informacemi o fragmentu kódu. Může být nula nebo jeden `HelpURL` prvky v záhlaví elementu. **Poznámka:** Visual Studio nepoužívá `HelpUrl` elementu. Tento element je součástí schématu XML fragmentu kódu technologie IntelliSense a jakékoli fragmenty kódu, které tento element obsahují, budou úspěšně ověřeny, ale hodnota elementu nebude nikdy použita.|  
|[Keywords Element](../ide/code-snippets-schema-reference.md#keywords)|Volitelný element. Skupiny `Keyword` elementy. Může být nula nebo jeden `Keywords` elementů v `Header` elementu.|  
|[Zástupce – Element](../ide/code-snippets-schema-reference.md#shortcut)|Volitelný element. Určuje textovou zkratku, pomocí níž lze fragment kódu vložit. Může být nula nebo jeden `Shortcut` elementů v `Header` elementu.|  
|[SnippetTypes Element](../ide/code-snippets-schema-reference.md#snippettypes)|Volitelný element. Skupiny `SnippetType` elementy. Může být nula nebo jeden `SnippetTypes` elementů v `Header` elementu. Pokud neexistují žádné `SnippetTypes` elementů fragmentu kódu je vždy platný.|  
|[Title Element](../ide/code-snippets-schema-reference.md#title)|Požadovaný element. Popisný název fragmentu kódu. Musí být přesně jeden `Title` element v `Header` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[CodeSnippet Element](../ide/code-snippets-schema-reference.md#codesnippet)|Nadřazený element pro všechna data fragmentu kódu.|  
  
##  <a name="helpurl"></a>HelpUrl Element  
 Určujte adresu URL s dalšími informacemi o fragmentu kódu.  
  
> [!NOTE]
>  Visual Studio nepoužívá `HelpUrl` elementu. Tento element je součástí schématu XML fragmentu kódu technologie IntelliSense a jakékoli fragmenty kódu, které tento element obsahují, budou úspěšně ověřeny, ale hodnota elementu nebude nikdy použita.  
  
```xml  
<HelpUrl>  
    www.microsoft.com  
</HelpUrl>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Obsahuje obecné informace o fragmentu kódu.|  
  
 Textová hodnota je volitelná. Tento text určuje adresu URL, na níž naleznete další informace o fragmentu kódu.  
  
##  <a name="id"></a>ID elementu  
 Určuje jedinečný identifikátor `Literal` nebo `Object` elementu. Žádné dvě literály nebo objekty ve stejné fragmentu kódu můžou mít stejnou hodnotu textu jejich `ID` elementy. Nemůže obsahovat literály a objekty `ID` element s hodnotou elementu end. Hodnota `$end$` je vyhrazen a slouží k označení umístění umístěte kurzor po vložení fragmentu kódu.  
  
```xml  
<ID>  
    Unique Identifier  
</ID>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Literál elementu](../ide/code-snippets-schema-reference.md#literal)|Definuje pole literálu fragmentu kódu, která lze upravovat.|  
|[Object Element](../ide/code-snippets-schema-reference.md#object)|Definuje pole objektu fragment kódu, která lze upravovat.|  
  
 Je vyžadována textová hodnota. Tento text určuje jedinečný identifikátor pro objekt nebo literál.  
  
##  <a name="import"></a>Import – Element  
 Určuje naimportované obory názvů používané fragmentem kódu technologie IntelliSense.  
  
> [!NOTE]
>  `Import` Element je podporována pouze pro projekty Visual Basic.  
  
```xml  
<Import>  
    <Namespace>... </Namespace>  
</Import>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Namespace Element](../ide/code-snippets-schema-reference.md#namespace)|Požadovaný element. Určuje obor názvů používaný fragmentem kódu. Musí být přesně jeden `Namespace` element v `Import` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Import – Element](../ide/code-snippets-schema-reference.md#imports)|Element seskupení pro **Import** elementy.|  
  
##  <a name="imports"></a>Import – Element  
 Jednotlivé skupiny `Import` elementy.  
  
> [!NOTE]
>  `Imports` Element je podporována pouze pro projekty Visual Basic.  
  
```xml  
<Imports>  
    <Import>... </Import>  
<Imports>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Import – Element](../ide/code-snippets-schema-reference.md#import)|Volitelný element. Obsahuje naimportované obory názvů pro fragment kódu. Může být nula nebo více **Import** elementů v `Imports` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Element fragmentu kódu](../ide/code-snippets-schema-reference.md#snippet)|Obsahuje odkazy, direktivy import, deklarace a kód fragmentu kódu.|  
  
##  <a name="keyword"></a>Element – klíčové slovo  
 Určuje vlastní klíčové slovo pro fragment kódu. Klíčová slova fragmentů kódu používá sada Visual Studio a představují standardní způsob pro online poskytovatele obsahu, jak přidávat vlastní klíčová slova pro vyhledávání nebo kategorizaci.  
  
```xml  
<Keyword>  
    Code Snippet Keyword  
</Keyword>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Keywords Element](../ide/code-snippets-schema-reference.md#keywords)|Jednotlivé skupiny `Keyword` elementy.|  
  
 Je vyžadována textová hodnota. Klíčové slovo fragmentu kódu.  
  
##  <a name="keywords"></a>Element klíčová slova  
 Jednotlivé skupiny `Keyword` elementy. Klíčová slova fragmentů kódu používá sada Visual Studio a představují standardní způsob pro online poskytovatele obsahu, jak přidávat vlastní klíčová slova pro vyhledávání nebo kategorizaci.  
  
```xml  
<Keywords>  
    <Keyword>... </Keyword>  
    <Keyword>... </Keyword>  
<Keywords>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Element – klíčové slovo](../ide/code-snippets-schema-reference.md#keyword)|Volitelný element. Obsahuje jednotlivá klíčová slova pro fragment kódu. Může být nula nebo více `Keyword` elementů v `Keywords` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Obsahuje obecné informace o fragmentu kódu.|  
  
##  <a name="literal"></a>Literál elementu  
 Definuje literály fragmentu kódu, které lze upravovat. `Literal` Element se používá k identifikaci náhradní pro kód, který je zcela obsažen v rámci fragment kódu, ale pravděpodobně přizpůsobit po vložení do kódu. Jako literály by měly být deklarovány například řetězcové literály, číselné hodnoty a některé názvy proměnných.  
  
 Nemůže obsahovat literály a objekty **ID** element s hodnotou vybrané nebo ukončit. Hodnota `$selected$` představuje vybraného v dokumentu, který se má být vložen do fragmentu při vyvolání textu. `$end$`označuje umístění umístěte kurzor po vložení fragmentu kódu.  
  
```xml  
<Literal Editable="true/false">  
   <ID>... </ID>  
   <ToolTip>... </ToolTip>  
   <Default>... </Default>  
   <Function>... </Function>  
</Literal>  
```  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Editable`|Volitelné `Boolean` atribut. Určuje, zda lze literál po vložení fragmentu kódu upravit. Výchozí hodnota tohoto atributu je `true`.|  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Výchozí Element](../ide/code-snippets-schema-reference.md#default)|Požadovaný element. Určuje výchozí hodnotu literálu při vložení fragmentu kódu. Musí být přesně jeden `Default` element v `Literal` elementu.|  
|[Element – funkce](../ide/code-snippets-schema-reference.md#function)|Volitelný element. Určuje funkci, která se má provést, když literál získá fokus v sadě Visual Studio. Může být nula nebo jeden `Function` elementů v `Literal` elementu.|  
|[ID elementu](../ide/code-snippets-schema-reference.md#id)|Požadovaný element. Určuje jedinečný identifikátor literálu. Musí být přesně jeden `ID` element v `Literal` elementu.|  
|[Element popisu tlačítka](../ide/code-snippets-schema-reference.md#tooltip)|Volitelný element. Popisuje očekávanou hodnotu a použití literálu. Může být nula nebo jeden **popisek** elementů v `Literal` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Deklarace Element](../ide/code-snippets-schema-reference.md#declarations)|Obsahuje literály a objekty fragmentu kódu, které lze upravovat.|  
  
##  <a name="namespace"></a>Namespace – Element  
 Určuje obor názvů, který musí být naimportován, aby bylo možné fragment kódu zkompilovat a spustit. Obor názvů specifikovaný v `Namespace` element se automaticky přidá do `Imports` příkaz na začátku kódu, pokud ještě neexistuje.  
  
> [!NOTE]
>  `Namespace` Element je podporována pouze pro projekty Visual Basic.  
  
```xml  
<Namespace>  
    Namespace  
</Namespace>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Import – Element](../ide/code-snippets-schema-reference.md#import)|Naimportuje zadaný obor názvů.|  
  
 Je vyžadována textová hodnota. Tento text určuje obor názvů, o kterém fragment kódu předpokládá, že bude naimportován.  
  
##  <a name="object"></a>Object Element  
 Definuje objekty fragmentu kódu, které lze upravovat. `Object` Element se používá k identifikaci položku, která požaduje fragment kódu, ale může být definován mimo fragmentu sám sebe. Jako objekty by měly být deklarovány například ovládací prvky modelu Windows Forms, ovládací prvky technologie ASP.NET nebo instance typů. Deklarace objektu vyžadují, aby byl specifikován typu, který provádí pomocí `Type` elementu.  
  
```xml  
<Object Editable="true/false">  
    <ID>... </ID>  
    <Type>... </Type>  
    <ToolTip>... </ToolTip>  
    <Default>... </Default>  
    <Function>... </Function>  
</Object>  
```  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Editable`|Volitelné `Boolean` atribut. Určuje, zda lze literál po vložení fragmentu kódu upravit. Výchozí hodnota tohoto atributu je `true`.|  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Výchozí Element](../ide/code-snippets-schema-reference.md#default)|Požadovaný element. Určuje výchozí hodnotu literálu při vložení fragmentu kódu. Musí být přesně jeden `Default` element v `Literal` elementu.|  
|[Element – funkce](../ide/code-snippets-schema-reference.md#function)|Volitelný element. Určuje funkci, která se má provést, když literál získá fokus v sadě Visual Studio. Může být nula nebo jeden `Function` elementů v `Literal` elementu.|  
|[ID elementu](../ide/code-snippets-schema-reference.md#id)|Požadovaný element. Určuje jedinečný identifikátor literálu. Musí být přesně jeden `ID` element v `Literal` elementu.|  
|[Element popisu tlačítka](../ide/code-snippets-schema-reference.md#tooltip)|Volitelný element. Popisuje očekávanou hodnotu a použití literálu. Může být nula nebo jeden **popisek** elementů v `Literal` elementu.|  
|[Typ elementu](../ide/code-snippets-schema-reference.md#type)|Požadovaný element. Určuje typ objektu. Musí být přesně jeden `Type` element v `Object` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Deklarace Element](../ide/code-snippets-schema-reference.md#declarations)|Obsahuje literály a objekty fragmentu kódu, které lze upravovat.|  
  
##  <a name="reference"></a>Referenční dokumentace elementu  
 Určuje informace o odkazech na sestavení vyžadovaných fragmentem kódu. 
  
```xml  
<Reference>  
    <Assembly>... </Assembly>  
    <Url>... </Url>  
</Reference>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Assembly – Element](../ide/code-snippets-schema-reference.md#assembly)|Požadovaný element. Obsahuje název sestavení, na které se odkazuje fragment kódu. Musí být přesně jeden `Assembly` element v `Reference` elementu.|  
|[Adresa URL elementu](../ide/code-snippets-schema-reference.md#url)|Volitelný element. Obsahuje adresu URL s dalšími informacemi o odkazovaném sestavení. Může být nula nebo jeden `Url` elementů v `Reference` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Element odkazů](../ide/code-snippets-schema-reference.md#references)|Element seskupení pro `Reference` elementy.|  
  
##  <a name="references"></a>Element odkazů  
 Jednotlivé skupiny `Reference` elementy.  
  
```xml  
<References>  
    <Reference>... </Reference>  
</References>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Referenční dokumentace elementu](../ide/code-snippets-schema-reference.md#reference)|Volitelný element. Obsahuje informace o odkazech na sestavení pro fragment kódu. Může být nula nebo více `Reference` elementů v `References` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Element fragmentu kódu](../ide/code-snippets-schema-reference.md#snippet)|Obsahuje odkazy, direktivy import, deklarace a kód fragmentu kódu.|  
  
##  <a name="shortcut"></a>Zástupce – Element  
 Určuje textovou zkratku, pomocí níž lze fragment kódu vložit. Hodnota textu `Shortcut` element může obsahovat pouze alfanumerické znaky, pomlčkami (-) a podtržítka (_).  
  
> [!CAUTION]
>  _ a - nejsou podporované znaků zkratky fragment kódu C++.  
  
```xml  
<Shortcut>  
    Shortcut Text  
</Shortcut>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Obsahuje obecné informace o fragmentu kódu.|  
  
 Textová hodnota je volitelná. Tento text slouží jako zkratka pro vkládání fragmentů kódu.  
  
##  <a name="snippet"></a>Element fragmentu kódu  
 Určuje odkazy, direktivy import, deklarace a kód fragmentu kódu.  
  
```xml  
<Snippet>  
    <References>... </References>  
    <Imports>... </Imports>  
    <Declarations>... </Declarations>  
    <Code>... </Code>  
</Snippet>    
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[Element kódu](../ide/code-snippets-schema-reference.md#code)|Požadovaný element. Určuje kód, který chcete vložit do souboru dokumentace. Musí být přesně jeden `Code` element v `Snippet` elementu.|  
|[Deklarace Element](../ide/code-snippets-schema-reference.md#declarations)|Volitelný element. Určuje literály a objekty tvořící části fragmentu kódu, které lze upravovat. Může být nula nebo jeden `Declarations` elementů v `Snippet` elementu.|  
|[Import – Element](../ide/code-snippets-schema-reference.md#imports)|Volitelný element. Jednotlivé skupiny `Import` elementy. Může být nula nebo jeden `Imports` elementů v `Snippet` elementu.|  
||Volitelný element. Jednotlivé skupiny `Reference` elementy. Může být nula nebo jeden `References` elementů v `Snippet` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[CodeSnippet Element](../ide/code-snippets-schema-reference.md#codesnippet)|Umožňuje zadat záhlaví a jeden nebo více fragmentů kódu technologie IntelliSense, které lze vložit do souborů kódu sady Visual Studio.|  
  
##  <a name="snippettype"></a>SnippetType Element  
 Určuje, jak sada Visual Studio vloží fragment kódu.  
  
```xml  
<SnippetType>  
    SurroundsWith/Expansion  
<SnippetType>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[SnippetTypes Element](../ide/code-snippets-schema-reference.md#snippettypes)|Skupiny `SnippetType` elementy.|  
  
 Textová hodnota musí být jedna z následujících hodnot:  
  
-   `SurroundsWith`: umožňuje fragmentu kódu umístit kolem vybraný úsek kódu.  
  
-   `Expansion`: umožňuje fragment kódu, který má být vložen na pozici kurzoru.  
  
-   `Refactoring`: Určuje, že je během C# refaktoring používá fragmentu kódu. `Refactoring`nelze použít v fragmenty vlastní kód.  
  
##  <a name="snippettypes"></a>SnippetTypes Element  
 Jednotlivé skupiny `SnippetType` elementy. Pokud `SnippetTypes` element není k dispozici, fragmentu kódu můžete vložit kdekoli v kódu.  
  
```xml  
<SnippetTypes>  
    <SnippetType>... </SnippetType>  
    <SnippetType>... </SnippetType>  
<SnippetTypes>  
```  
  
|Podřízený element|Popis|  
|-------------------|-----------------|  
|[SnippetType Element](../ide/code-snippets-schema-reference.md#snippettype)|Volitelný element. Určuje, jak sada Visual Studio vloží fragment kódu do kódu. Může být nula nebo více `SnippetType` elementů v `SnippetTypes` elementu.|  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Určuje obecné informace o fragmentu kódu.|  
  
##  <a name="title"></a>Title Element  
 Určuje název fragmentu kódu. Název uložené v `Title` element fragmentu kódu se zobrazí v **Sběrač fragmentů kódu** a v popisu fragmentu kódu v **Správce fragmentů kódu**.  
  
```xml  
<Title>  
    Code Snippet Title  
<Title>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Header Element](../ide/code-snippets-schema-reference.md#header)|Určuje obecné informace o fragmentu kódu.|  
  
 Je vyžadována textová hodnota. Tento text určuje název fragmentu kódu.  
  
##  <a name="tooltip"></a>Element popisu tlačítka  
 Popisuje očekávanou hodnotu a použití literálu nebo objektu ve fragmentu kódu. Sada Visual Studio tyto informace zobrazí v popisku při vložení fragmentu kódu do projektu. Text popisku se zobrazí po vložení fragmentu kódu po umístění ukazatele myši na literál nebo objekt.  
  
```xml  
<ToolTip>  
    ToolTip description  
</ToolTip>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Literál elementu](../ide/code-snippets-schema-reference.md#literal)|Definuje pole literálu fragmentu kódu, která lze upravovat.|  
|[Object Element](../ide/code-snippets-schema-reference.md#object)|Definuje pole objektu fragment kódu, která lze upravovat.|  
  
 Je vyžadována textová hodnota. Tento text určuje popisek přidružený k objektu nebo literálu ve fragmentu kódu.  
  
##  <a name="type"></a>Typ elementu  
 Určuje typ objektu. `Object` Element se používá k identifikaci položku, která požaduje fragment kódu, ale může být definován mimo fragmentu sám sebe. Jako objekty by měly být deklarovány například ovládací prvky modelu Windows Forms, ovládací prvky technologie ASP.NET nebo instance typů. Deklarace objektu vyžadují, aby byl specifikován typu, který provádí pomocí `Type` elementu.  
  
```xml  
<Type>  
    Type  
</Type>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Object Element](../ide/code-snippets-schema-reference.md#object)|Definuje pole objektu fragment kódu, která lze upravovat.|  
  
 Je vyžadována textová hodnota. Tento text určuje typ objektu.  
  
##  <a name="url"></a>Adresa URL elementu  
 Určuje adresu URL s dalšími informacemi o odkazovaném sestavení.  
  
> [!NOTE]
>  `Url` Element je podporována pouze pro projekty Visual Basic.  
  
```xml  
<Url>  
    www.microsoft.com  
</Url>  
```  
  
|Nadřazený element|Popis|  
|--------------------|-----------------|  
|[Referenční dokumentace elementu](../ide/code-snippets-schema-reference.md#reference)|Určuje odkazy na sestavení vyžadované fragmentem kódu.|  
  
 Je vyžadována textová hodnota. Tento text určuje adresu URL s dalšími informacemi o odkazovaném sestavení. Tato adresa URL se zobrazí, pokud odkaz nelze přidat do projektu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu](../ide/code-snippets.md)   
 [Návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md)