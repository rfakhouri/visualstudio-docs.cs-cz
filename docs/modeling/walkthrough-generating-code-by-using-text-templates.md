---
title: "Návod: Vytvoření kódu pomocí textových šablon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- walkthroughs [text templates], generating application code
- walkthroughs [text templates]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 46cbf0c6a28b10434ed364dffd77c4c01620d6ea
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="walkthrough-generating-code-by-using-text-templates"></a>Návod: Vytvoření kódu pomocí textových šablon
Generování kódu umožňuje vytvářet kód programu, který je silného typu a ještě jde snadno změnit, pokud změny modelu zdroje. Tento rozdíl oproti alternativní postup zápisu úplně obecné program, který přijímá konfigurační soubor, který je flexibilnější, ale má za následek kód, který je ani jeden z nich tak snadno přečíst a změnit, ani je takové dobrý výkon. Tento návod ukazuje této výhody.  
  
## <a name="typed-code-for-reading-xml"></a>Zadaný kód pro načítání kódu XML  
 Obor názvů System.Xml poskytuje komplexní nástroje pro načítání dokumentu XML a pak ho volně navigace v paměti. Bohužel se všechny uzly mají stejný typ XmlNode. Proto je velmi snadné uděláte programovací chyby, jako je například očekává nesprávný typ podřízený uzel nebo nesprávný atributy.  
  
 V tomto příkladu projektu šablony čte ukázkový soubor XML a vygeneruje třídy, které odpovídají každý typ uzlu. V ručně psané kódu můžete tyto třídy a přejděte soubor XML. Aplikaci můžete spustit také na všechny soubory, které používají stejné typy uzlů. Účelem ukázkový soubor XML je příklady všechny typy uzlů, které má vaše aplikace k řešení.  
  
> [!NOTE]
>  Aplikace [xsd.exe](http://go.microsoft.com/fwlink/?LinkId=178765), který je součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], můžete vygenerovat silně typované třídy ze souborů XML. Jako příklad je zadána šablona zobrazeny zde.  
  
 Tady je ukázkový soubor:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<catalog>  
  <artist id ="Mike%20Nash" name="Mike Nash Quartet">  
    <song id ="MikeNashJazzBeforeTeatime">Jazz Before Teatime</song>  
    <song id ="MikeNashJazzAfterBreakfast">Jazz After Breakfast</song>  
  </artist>  
  <artist id ="Euan%20Garden" name="Euan Garden">  
    <song id ="GardenScottishCountry">Scottish Country Garden</song>  
  </artist>  
</catalog>  
```  
  
 V projektu vytvoří Tento názorný postup, můžete napsat kód například následující a IntelliSense vyzve správné názvy atributů a podřízené při psaní:  
  
```  
Catalog catalog = new Catalog(xmlDocument);  
foreach (Artist artist in catalog.Artist)  
{  
  Console.WriteLine(artist.name);  
  foreach (Song song in artist.Song)  
  {  
    Console.WriteLine("   " + song.Text);  
  }  
}  
```  
  
 To je podstatný rozdíl oproti netypový kód, který může zapsat bez šablony:  
  
```  
XmlNode catalog = xmlDocument.SelectSingleNode("catalog");  
foreach (XmlNode artist in catalog.SelectNodes("artist"))  
{  
    Console.WriteLine(artist.Attributes["name"].Value);  
    foreach (XmlNode song in artist.SelectNodes("song"))  
    {  
         Console.WriteLine("   " + song.InnerText);  
     }  
}  
```  
  
 Ve verzi silného způsobí změnu schématu XML změny do třídy. Kompilátor bude zvýrazněte části aplikační kód, který je třeba změnit. V netypové verzi, která používá obecné kód XML je takový nepodporuje.  
  
 V tomto projektu jeden soubor šablony slouží ke generování tříd, které umožňují typové verze.  
  
## <a name="setting-up-the-project"></a>Nastavení projektu  
  
### <a name="create-or-open-a-c-project"></a>Vytvořit nebo otevřít projekt C#  
 Tento postup můžete použít na všechny kód projektu. Tento návod používá projekt C# a pro účely testování můžeme použít konzolovou aplikaci.  
  
##### <a name="to-create-the-project"></a>Vytvoření projektu  
  
1.  Na **soubor** nabídce klikněte na tlačítko **nový** a pak klikněte na **projektu**.  
  
2.  Klikněte na tlačítko **Visual C#** uzel a potom v **šablony** podokně klikněte na tlačítko **konzolové aplikace.**  
  
### <a name="add-a-prototype-xml-file-to-the-project"></a>Přidejte do projektu soubor XML prototypu  
 Účelem tohoto souboru je poskytnout ukázky typy uzel XML, které se mají vaši aplikaci, která bude moct číst. Může to být soubor, který se použije pro testování vašich aplikací. Šablona vytvoří třída C# pro každý typ uzlu v tomto souboru.  
  
 Soubor musí být součástí projektu, aby ho mohou číst šablony, ale nebude jde integrovat přímo do kompilované aplikace.  
  
##### <a name="to-add-an-xml-file"></a>Přidání souboru XML  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt, klikněte na **přidat** a pak klikněte na **novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **souboru XML** z **šablony** podokně.  
  
3.  Přidejte ukázkový obsah do souboru.  
  
4.  V tomto návodu název souboru `exampleXml.xml`. Nastavte obsah byl soubor XML uvedené v předchozí části.  
  
 .  
  
### <a name="add-a-test-code-file"></a>Přidání souboru testovacího kódu  
 Přidejte do projektu soubor C# a zápisu v ní ukázkový kód, který chcete být schopni zapisovat. Příklad:  
  
```  
using System;  
namespace MyProject  
{  
  class CodeGeneratorTest  
  {  
    public void TestMethod()  
    {  
      Catalog catalog = new Catalog(@"..\..\exampleXml.xml");  
      foreach (Artist artist in catalog.Artist)  
      {  
        Console.WriteLine(artist.name);  
        foreach (Song song in artist.Song)  
        {  
          Console.WriteLine("   " + song.Text);  
} } } } }  
```  
  
 V této fázi tento kód se nepovede zkompilovat. Při psaní šabloně vygeneruje třídy, které aby ji bylo úspěšné.  
  
 Komplexnější testu může zkontrolujte výstup této funkce testovací proti známé obsah příklad souboru XML. V tomto návodu budeme bude ji však splněna při kompilaci metodu test.  
  
### <a name="add-a-text-template-file"></a>Přidání souboru textové šablony  
 Přidejte textový soubor šablony a nastavte výstup rozšíření pro ".cs".  
  
##### <a name="to-add-a-text-template-file-to-your-project"></a>Chcete-li přidat textový soubor šablony do projektu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt, klikněte na **přidat**a potom klikněte na **novou položku**.  
  
2.  V **přidat novou položku** dialogové okno pole vyberte **textové šablony** z **šablony** podokně.  
  
    > [!NOTE]
    >  Ujistěte se, že přidáte textové šablony a ne zpracované textové šablony.  
  
3.  V souboru ve – direktiva šablony, změnit `hostspecific` atribut `true`.  
  
     Tato změna vám umožní kód šablony k získání přístupu k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] služby.  
  
4.  V direktivě výstup změňte atribut rozšíření ".cs" tak, aby šablona generuje soubor C#. V projektu jazyka Visual Basic by ho změnit na "VB".  
  
5.  Uložte soubor. V této fázi se k textovému souboru šablony musí obsahovat tyto řádky:  
  
    ```  
    <#@ template debug="false" hostspecific="true" language="C#" #>  
    <#@ output extension=".cs" #>  
    ```  
  
 .  
  
 Všimněte si, že soubor cs zobrazí v Průzkumníku řešení jako pobočky souboru šablony. Zobrazí se kliknutím na [+] vedle názvu souboru šablony. Tento soubor se generují z soubor šablony při každém uložení nebo Přesun zaměření mimo soubor šablony. Vygenerovaný soubor se zkompiluje jako součást projektu.  
  
 Ke zvýšení pohodlí při vývoji soubor šablony, uspořádejte okna soubor šablony a vygenerovaný soubor, abyste je viděli vedle sebe. Díky tomu můžete zobrazit výstup šablony okamžitě. Také si všimněte, že pokud vaše šablona vygeneruje neplatný kód C#, chyb se zobrazí v okně chybové zprávy.  
  
 Vždy, když je uložen soubor šablony, budou ztraceny všechny úpravy, které můžete provádět přímo v vygenerovaný soubor. Si proto Vyhněte se úpravám vygenerovaný soubor, nebo upravit pouze pro krátké experimenty. Někdy je užitečné zkuste krátké fragment kódu vygenerovaný soubor, kde jsou IntelliSense v operaci, a pak je zkopírovat do souboru šablony.  
  
## <a name="developing-the-text-template"></a>Vývoj textové šablony  
 Následující doporučené pokyny na agilní vývoj jsme vyvíjet šablony v malých krocích vymazání některé chyby na každý přírůstek, dokud testovacího kódu zkompiluje a běží správně.  
  
### <a name="prototype-the-code-to-be-generated"></a>Prototyp kód, který má být vygenerován  
 Testovací kód vyžaduje třídu pro každý uzel v souboru. Proto některé chyby kompilace zmizí Pokud připojit tyto řádky do šablony a pak ho uložte:  
  
```  
class Catalog {}   
class Artist {}  
class Song {}  
```  
  
 To pomůže můžete zjistit, co je požadováno, ale deklarací by měl být vygenerován z typy uzlů v ukázkovém souboru XML. Odstraňte tyto experimentální řádky ze šablony.  
  
### <a name="generate-application-code-from-the-model-xml-file"></a>Generování kódu aplikace ze souboru XML modelu  
 Ke čtení souboru XML a generování deklarace tříd, nahraďte obsah následujícím kódem šablony šablony:  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".cs" #>  
<#@ assembly name="System.Xml"#>  
<#@ import namespace="System.Xml" #>  
<#  
 XmlDocument doc = new XmlDocument();  
 // Replace this file path with yours:  
 doc.Load(@"C:\MySolution\MyProject\exampleXml.xml");  
 foreach (XmlNode node in doc.SelectNodes("//*"))  
 {  
#>  
  public partial class <#= node.Name #> {}  
<#  
 }  
#>  
```  
  
 Cesta k souboru nahraďte správnou cestu pro váš projekt.  
  
 Všimněte si, oddělovače bloku kódu `<#...#>`. Tyto oddělovače závorka fragment kódu programu, který generuje text. Oddělovače bloku výraz `<#=...#>` závorka výraz, který lze vyhodnotit na řetězec.  
  
 Když vytváříte šablonu, která generuje zdrojového kódu pro aplikace, se kterou chcete pracovat dva texty a samostatný program. Program uvnitř oddělovače bloku kódu se spustí pokaždé, když uložíte šablonu nebo přesunout fokus na další okno. Text, který se vygeneruje, která se zobrazí mimo oddělovače, se zkopíruje do vygenerovaný soubor a stane součástí kódu aplikace.  
  
 `<#@assembly#>` – Direktiva chová jako odkaz na zpřístupnění sestavení kód šablony. Seznam sestavení vidět šablony je oddělené od seznamu odkazů v projektu aplikace.  
  
 `<#@import#>` – Direktiva pracuje stejně jako `using` prohlášení, budete moci použít krátké názvy tříd v importovaných oboru názvů.  
  
 Bohužel, i když tato šablona generuje kód, vyvolá deklaraci třídy pro každý uzel v souboru XML třeba tak, aby pokud máte několik instancí `<song>` uzlu, zobrazí se několik deklarace skladbu třídy.  
  
### <a name="read-the-model-file-then-generate-the-code"></a>Čtení souboru modelu a generování kódu  
 Mnoho textových šablon postupujte podle vzoru, ve kterém první část šablony přečte zdrojový soubor a druhou částí generuje šablony. Potřebujeme ke čtení všech příklad souboru ke shrnutí typy uzlů, které obsahuje a pak generovat deklarace tříd. Jiné `<#@import#>` je potřeba, aby můžeme použít`Dictionary<>:`  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".cs" #>  
<#@ assembly name="System.Xml"#>  
<#@ import namespace="System.Xml" #>  
<#@ import namespace="System.Collections.Generic" #>  
<#  
 // Read the model file  
 XmlDocument doc = new XmlDocument();  
 doc.Load(@"C:\MySolution\MyProject\exampleXml.xml");  
 Dictionary <string, string> nodeTypes =   
        new Dictionary<string, string>();  
 foreach (XmlNode node in doc.SelectNodes("//*"))  
 {  
   nodeTypes[node.Name] = "";  
 }  
 // Generate the code  
 foreach (string nodeName in nodeTypes.Keys)  
 {  
#>  
  public partial class <#= nodeName #> {}  
<#  
 }  
#>  
```  
  
### <a name="add-an-auxiliary-method"></a>Přidat Pomocná metoda  
 Řídicí blok třída funkce je blok, ve kterém můžete definovat pomocné metody. Je oddělená bloku `<#+...#>` a musí se zobrazí jako poslední blok v souboru.  
  
 Pokud dáváte přednost názvy tříd začínat velkým písmenem, můžete nahradit následující kód šablony poslední část šablony:  
  
```  
// Generate the code  
 foreach (string nodeName in nodeTypes.Keys)  
 {  
#>  
  public partial class <#= UpperInitial(nodeName) #> {}  
<#  
 }  
#>  
<#+  
 private string UpperInitial(string name)  
 { return name[0].ToString().ToUpperInvariant() + name.Substring(1); }  
#>  
```  
  
 V této fázi generovaného .cs souboru obsahuje následující deklarace:  
  
```  
public partial class Catalog {}  
public partial class Artist {}  
public partial class Song {}  
```  
  
 Další podrobnosti, například vlastnosti pro podřízené uzly, atributy a vnitřní text lze přidat pomocí stejný přístup.  
  
### <a name="accessing-the-visual-studio-api"></a>Přístup k sadě Visual Studio rozhraní API  
 Nastavení `hostspecific` atribut `<#@template#>` – direktiva umožňuje šablonu, kterou chcete získat přístup k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní API. Šablonu můžete použít k získání umístění souborů projektu, která nechcete používat absolutní cestu k souboru v kódu šablony.  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
...  
<#@ assembly name="EnvDTE" #>  
...  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
// Open the prototype document.  
XmlDocument doc = new XmlDocument();  
doc.Load(System.IO.Path.Combine(dte.ActiveDocument.Path, "exampleXml.xml"));  
```  
  
## <a name="completing-the-text-template"></a>Dokončení textové šablony  
 Následující obsah šablony generuje kód, který umožňuje testovacího kódu na zkompilování a spuštění.  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".cs" #>  
<#@ assembly name="System.Xml" #>  
<#@ assembly name="EnvDTE" #>  
<#@ import namespace="System.Xml" #>  
<#@ import namespace="System.Collections.Generic" #>  
using System;using System.Collections.Generic;using System.Linq;using System.Xml;namespace MyProject{  
<#  
 // Map node name --> child name --> child node type  
 Dictionary<string, Dictionary<string, XmlNodeType>> nodeTypes = new Dictionary<string, Dictionary<string, XmlNodeType>>();  
  
 // The Visual Studio host, to get the local file path.  
 EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
 // Open the prototype document.  
 XmlDocument doc = new XmlDocument();  
 doc.Load(System.IO.Path.Combine(dte.ActiveDocument.Path, "exampleXml.xml"));  
 // Inspect all the nodes in the document.  
 // The example might contain many nodes of the same type,   
 // so make a dictionary of node types and their children.  
 foreach (XmlNode node in doc.SelectNodes("//*"))  
 {  
   Dictionary<string, XmlNodeType> subs = null;  
   if (!nodeTypes.TryGetValue(node.Name, out subs))  
   {  
     subs = new Dictionary<string, XmlNodeType>();  
     nodeTypes.Add(node.Name, subs);  
   }  
   foreach (XmlNode child in node.ChildNodes)  
   {  
     subs[child.Name] = child.NodeType;  
   }   
   foreach (XmlNode child in node.Attributes)  
   {  
     subs[child.Name] = child.NodeType;  
   }  
 }  
 // Generate a class for each node type.  
 foreach (string className in nodeTypes.Keys)  
 {  
    // Capitalize the first character of the name.  
#>  
    partial class <#= UpperInitial(className) #>  
    {      private XmlNode thisNode;      public <#= UpperInitial(className) #>(XmlNode node)       { thisNode = node; }  
  
<#  
    // Generate a property for each child.  
    foreach (string childName in nodeTypes[className].Keys)  
    {  
      // Allow for different types of child.  
      switch (nodeTypes[className][childName])  
      {  
         // Child nodes:  
         case XmlNodeType.Element:  
#>  
      public IEnumerable<<#=UpperInitial(childName)#>><#=UpperInitial(childName) #>      {         get         {            foreach (XmlNode node in                thisNode.SelectNodes("<#=childName#>"))              yield return new <#=UpperInitial(childName)#>(node);       } }  
<#  
         break;  
         // Child attributes:  
         case XmlNodeType.Attribute:  
#>  
      public string <#=childName #>      { get { return thisNode.Attributes["<#=childName#>"].Value; } }  
<#  
         break;  
         // Plain text:  
         case XmlNodeType.Text:  
#>  
      public string Text  { get { return thisNode.InnerText; } }  
<#  
         break;  
       } // switch  
     } // foreach class child  
  // End of the generated class:  
#>  
   }   
<#  
 } // foreach class  
  
   // Add a constructor for the root class   
   // that accepts an XML filename.  
   string rootClassName = doc.SelectSingleNode("*").Name;  
#>  
   partial class <#= UpperInitial(rootClassName) #>   {      public <#= UpperInitial(rootClassName) #>(string fileName){        XmlDocument doc = new XmlDocument();        doc.Load(fileName);        thisNode = doc.SelectSingleNode("<#=rootClassName#>");}   }}  
<#+  
   private string UpperInitial(string name)  
   {  
      return name[0].ToString().ToUpperInvariant() + name.Substring(1);  
   }  
#>  
```  
  
### <a name="running-the-test-program"></a>Spuštění programu testu  
 V hlavní aplikaci konzoly provede následující řádky metodu test. Stisknutím klávesy F5 spusťte program v režimu ladění:  
  
```  
using System;  
namespace MyProject  
{ class Program  
  { static void Main(string[] args)  
    { new CodeGeneratorTest().TestMethod();  
      // Allow user to see the output:  
      Console.ReadLine();  
} } }  
```  
  
### <a name="writing-and-updating-the-application"></a>Psaní a aktualizace aplikace  
 Aplikace, můžete nyní napsaná v silného typu styl, místo použití obecném kódu XML pomocí vygenerované třídy.  
  
 Když se změní schéma XML, lze snadno generovat nové třídy. Kompilátor bude informovat vývojáře, kde se musí aktualizovat kód aplikace.  
  
 Chcete-li znovu vygenerovat třídy při změně příklad souboru XML, klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů v Průzkumníku řešení.  
  
## <a name="conclusion"></a>Závěr  
 Tento návod ukazuje několik technik a výhod generování kódu:  
  
-   *Generování kódu* je vytvoření součástí zdrojového kódu aplikace *modelu*. Model obsahuje informace ve formuláři vhodné do domény aplikace a může změnit během životního cyklu aplikace.  
  
-   Silného typování je jednou z výhod generování kódu. Pokud model reprezentuje informace ve formě vhodnější pro uživatele, umožňuje generovaný kód dalších částí aplikace pracují s informacemi o pomocí sady typy.  
  
-   Funkce IntelliSense a kompilátor vám pomůže vytvořit kód, který dodržuje schéma modelu, můžete zadat nový kód i při schéma se aktualizuje.  
  
-   Přidání souboru jeden nekomplikované šablony do projektu mohou poskytovat i tyto výhody.  
  
-   Textové šablony můžete vyvinuté a testovat rychle a postupně.  
  
 V tomto návodu se generují z instance modelu, reprezentativní příklad soubory XML, které aplikace se zpracovávají ve skutečnosti kód programu. V rámci více formální přístupu schématu XML by vstup šabloně ve formě soubor XSD nebo definici jazyka domény. Tento přístup by bylo snazší pro šablonu, kterou chcete určit, charakteristiky jako násobnosti relace.  
  
## <a name="troubleshooting-the-text-template"></a>Řešení potíží s textové šablony  
 Pokud jste viděli transformace nebo kompilace chyby šablony v **seznam chyb**, nebo pokud výstupní soubor nebyl správně vytvořen, textové šablony můžete řešit pomocí technik popsaných v [generování Soubory pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)   
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)