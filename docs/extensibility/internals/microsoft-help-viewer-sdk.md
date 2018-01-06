---
title: Microsoft Help Viewer SDK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 620d7dcd-d462-475e-a449-fbfa06ff12c5
caps.latest.revision: "33"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7c15956bc861f9eb20267dc97446cf5ea49cae31
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="microsoft-help-viewer-sdk"></a>Microsoft Help Viewer SDK
Tento článek obsahuje následující úlohy pro Visual Studio Help Viewer integrátorem:  
  
-   Vytvoření tématu (F1 podpora)  
  
-   Vytváření balíčku obsahu branding Help Viewer  
  
-   Nasazení sady článků  
  
-   Přidání nápovědu k prostředí Visual Studio (integrovaný nebo izolované)  
  
-   Další prostředky  
  
### <a name="creating-a-topic-f1-support"></a>Vytvoření tématu (F1 podpora)  
Tato část obsahuje přehled komponent vidění téma, téma požadavky, a jejich popis vytvoření téma (včetně požadavky na podporu F1) a nakonec tématu příklad s jeho vykreslené výsledek.  
  
**Přehled tématu okna nápovědy**  
  
Při téma je pro vykreslování prohlížeče nápovědy získá brandingu balíček prvky, které jsou přidružené k tomuto tématu v době instalace nebo poslední aktualizace, společně s tématu XHTML a kombinuje dva za následek vidění zobrazení obsahu (branding data + téma data).  Značky balíček obsahuje loga, podporu pro obsah chování a vlastní text (autorských práv, atd.).  "Vytváření Branding balíček" níže naleznete další informace o značce elementy balíčku.  V případě, že neexistuje žádná brandingu balíček přidružené k tématu, Prohlížeč nápovědy použije náhradní označující balíček umístěného v kořenovém aplikace Help Viewer (Branding_en-US.mshc).  
  
**Požadavky na prohlížeč tématu nápovědy**  
  
Mají být zpracovány správně v okně nápovědy, musí být obsah nezpracované tématu W3C základní 1.1 XHTML.  
  
Téma obvykle obsahuje dvě části:  
  
-   Metadata (viz obsahu Metadata odkaz): data o tématu například téma jedinečné ID, hodnota – klíčové slovo, tématu TOC ID nadřazené ID uzlu, atd.  
  
-   Obsah textu: kompatibilní s W3C základní 1.1 XHTML, což zahrnuje podporované obsahu chování (sbalitelné oblasti, fragment kódu, atd. Úplný seznam jsou uvedené dole).  
  
Branding balíček Visual Studio podporují ovládací prvky:  
  
-   Odkazy  
  
-   CodeSnippet  
  
-   CollapsibleArea  
  
-   Zděděného členu  
  
-   LanguageSpecificText  
  
Řetězce podporovaných jazyků (ne velká a malá písmena):  
  
-   JavaScript  
  
-   CSharp nebo c#  
  
-   cplusplus nebo visualc ++ nebo c ++  
  
-   JScript  
  
-   VisualBasic nebo jazyka Visual Basic  
  
-   f # nebo fsharp nebo služby fs  
  
-   Další: řetězec, který představuje název jazyka  
  
**Vytvoření tématu Help Viewer**  
  
Vytvořit nový dokument XHTML s názvem ContosoTopic4.htm a zahrnují název značky (dole).  
  
```html  
<html>  
<head>  
<title>Contoso Topic 4</title>  
</head>  
  
<body>  
  
</body>  
</html>  
  
```  
  
V dalším kroku přidat data jak definovat jak tématu je dodáván (vlastní značky, nebo ne), chcete-li toto téma pro F1, kde existuje v tomto tématu v rámci do obsahu, jeho ID (pro odkaz podle další témata), atd.  Najdete v části "Metadata obsahu" tabulce úplný seznam podporovaných metadat.  
  
-   V tomto případě použijeme vlastní značky balíček hodnotu typu variant vlastního balíčku Visual Studio Help Viewer.  
  
-   Přidejte F1 meta název a hodnotu ("Microsoft.Help.F1" obsah = "ContosoTopic4"), bude shodovat s poskytnutá hodnota F1 v kontejneru objektů IDE.  (Viz část F1 podpory pro další informace.)   Toto je hodnota, která odpovídá klávesy F1 volat z prostředí IDE pro zobrazení v tomto tématu při výběru F1 v prostředí IDE.  
  
-   Přidat ID tématu. Toto je řetězec, který je používán další témata propojit k tomuto tématu.  Je Identifikátor Prohlížeč nápovědy pro toto téma.  
  
-   Do obsahu přidejte toto téma nadřazeného uzlu můžete definovat, kde se zobrazí uzel obsahu tohoto tématu.  
  
-   Do obsahu přidejte pořadí uzlů v tomto tématu. Pokud je nadřazený uzel n počet podřízených uzlů, definujte v pořadí podřízené uzly umístění v tomto tématu. For example, toto téma je 4 počet 4 podřízené témat.)  
  
Příklad metadata části:  
  
```html  
<html>  
<head>  
<title>Contoso Topic 4</title>  
  
<meta name="SelfBranded" content="false" />     
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />  
    <meta name="Microsoft.Help.Id" content="ContosoTopic4" />  
<meta name="Microsoft.Help.F1" content=" ContosoTopic4" />  
    <meta name="Language" content="en-us" />  
<meta name="Microsoft.Help.TocParent" content="ContosoTopic0" />  
<meta name="Microsoft.Help.TocOrder" content="4" />   
  
</head>  
  
<body>  
  
</body>  
</html>  
  
```  
  
**Téma textu**  
  
Text (včetně není v záhlaví a zápatí) v tématu bude obsahovat odkazů na stránky, části Poznámka, sbalitelné oblasti, fragment kódu a část textu pro konkrétní jazyk.  Najdete v části značky informace o těchto oblastem vidění tématu.  
  
1.  Přidání značky název tématu:`<div class="title">Contoso Topic 4</div>`  
  
2.  Přidáte oddíl Poznámka:`<div class="alert"> add your table tag and text </div>`  
  
3.  Přidejte sbalitelné oblasti:`<CollapsibleArea Expanded="1" Title="Collapsible Area Test Heading"> add text  </CollapsibleArea>`  
  
4.  Přidáte fragment kódu:`<CodeSnippet EnableCopyCode="true" Language="CSharp" ContainsMarkup="false" DisplayLanguage="C#" > a block of code </CodeSnippet>`  
  
5.  Přidat kód jazyka konkrétní text: `<LanguageSpecificText devLangcs="CS" devLangvb="VB" devLangcpp="C++" devLangnu="F#" />` Všimněte si, že devLangnu = můžete zadat další jazyky. Například devLangnu = "Fortran" zobrazí Fortran při fragmentu kódu DisplayLanguage = Fortran  
  
6.  Přidání odkazů na stránky:`<a href="ms-xhelp://?Id=ContosoTopic1">Main Topic</a>`  
  
> [!NOTE]
>  Poznámka: pro nepodporovaný nové "zobrazovaný jazyk" (F #, Cobol, Fortran třeba) zabarvení kódu ve fragmentu kódu bude černobílý tisk.  
  
**Příklad tématu Prohlížeč nápovědy** kód ukazuje, jak definovat metadata, fragment kódu, sbalitelné oblast a jazyk zadaný text.  
  
```html
<?xml version="1.0" encoding="utf-8"?>  
<html>  
<head>  
<title>Contoso Topic 4</title>  
  
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />  
    <meta name="Microsoft.Help.Id" content="ContosoTopic4" />  
<meta name="Microsoft.Help.F1" content=" ContosoTopic4" />  
    <meta name="Language" content="en-us" />  
<meta name="Microsoft.Help.TocParent" content="ContosoTopic0" />  
<meta name="Microsoft.Help.TocOrder" content="4" />   
<meta name="SelfBranded" content="false" />     
</head>  
  
<body>  
<div class="title">Contoso Topic 4</div>  
  
  <div id="header">  
<table id="bottomTable" cellpadding="0" cellspacing="0"  width="100%">  
        <tr id="headerTableRow2"><td align="left">  
            <span id="nsrTitle">Contoso Topic 1</span>  
          </td>  
<td align="right">  
</td></tr>  
<tr id="headerTableRow1"><td align="left">  
            <span id="runningHeaderText">Contoso Widgets & Sprockets</span>  
          </td></tr>  
      </table>  
</div>  
  
<h2>Table of Contents</h2>  
  
<ul class="toc">  
<li class="tocline1"><a href="#introduction" target="_self">1.0 Introduction</a></li>  
<li class="tocline1"><a href="#seealso" target="_self">See Also</a></li>  
</ul>  
  
<div class="topic">  
  
<div id="mainSection">  
<div id="mainBody">  
  
<a name="introduction"></a>  
<h2>1.0 Introduction</h2>  
<p>[This documentation is for sample purposes only.]</p>  
  
<p>Contoso Topic 1 contains examples of:  
<ul>  
<li>Collapsible Area</li>  
<li>Bookmark ("See also")</li>  
<li>Code Snippets from Branding Package</li>  
</ul>  
 </p>  
<div class="alert"><table><tr><th>  
<strong>Note </strong></th></tr>  
<tr><td>  
<p>This is an example of a <span class="label">Note </span>section.    
Call out important items for your reader in this <span class="label">Note </span>box.  
</p></td></tr>  
</table>  
</div>  
</div>  
  
<CollapsibleArea Expanded="1" Title="Collapsible Area Test Heading">  
  
            <a id="sectionToggle0"><!----></a>  
  
<div>  
Example of Collapsible Area  
<br/>  
Lorem ipsum dolor sit amet...  
</div>  
</CollapsibleArea>  
  
<div id="snippetGroup" >  
<CodeSnippet EnableCopyCode="true" Language="VisualBasic" ContainsMarkup="false" DisplayLanguage="Visual Basic" >  
Private Sub ToolStripRenderer1_RenderGrip(sender as Object, e as ToolStripGripRenderEventArgs) _ Handles ToolStripRenderer1.RenderGrip  
Dim messageBoxVB as New System.Text.StringBuilder()  
    messageBoxVB.AppendFormat("{0} = {1}", "GripBounds", e.GripBounds)  
    messageBoxVB.AppendLine()  
 ...  
    MessageBox.Show(messageBoxVB.ToString(),"RenderGrip Event")  
End Sub  
</CodeSnippet>  
  
<CodeSnippet EnableCopyCode="true" Language="CSharp" ContainsMarkup="false" DisplayLanguage="C#" >  
private void ToolStripRenderer1_RenderGrip(Object sender, ToolStripGripRenderEventArgs e)   
{   
System.Text.StringBuilder messageBoxCS = new System.Text.StringBuilder();  
messageBoxCS.AppendFormat("{0} = {1}", "GripBounds", e.GripBounds );  
messageBoxCS.AppendLine();  
...  
MessageBox.Show(messageBoxCS.ToString(), "RenderGrip Event" );  
}  
</CodeSnippet>  
  
<CodeSnippet EnableCopyCode="true" Language="fsharp" ContainsMarkup="false" DisplayLanguage="F#" >  
some F# code  
</CodeSnippet>  
</div>  
  
<h4 class="subHeading">Example of code specific text</h4>Language = <LanguageSpecificText devLangcs="CS" devLangvb="VB" devLangcpp="C++" devLangnu="F#" />  
  
<a name="seealso"></a>  
<h1 class="heading">See Also</h1>  
  
    <div id="seeAlsoSection" class="section">   
    <div class="seeAlsoStyle">  
        <a href="ms-xhelp://?Id=ContosoTopic1">Main Topic</a>  
    </div>  
 </div>  
</div>  
</div>  
</body>  
</html>  
  
```  
  
**Podpora F1**  
  
V sadě Visual Studio výběr F1 generuje hodnot poskytnutých z umístění kurzoru v prostředí IDE a naplní "kontejner objektů" se zadanými hodnotami (podle umístění kurzoru. Pokud se ukazatel přes x, funkce x je aktivní nebo vybraný a naplní kontejneru objektů a dat s hodnotami.  Pokud je vybrána F1 se naplní kontejneru objektů a Visual Studio F1 kódu vypadá jestli zdroji zákazníkům výchozího nápovědy jsou místní nebo online (online je výchozí nastavení), potom vytvoří příslušným řetězcem založená na uživatelích nastavení (online je výchozí nastavení) - spouštění prostředí (viz pomůže příručce správce pro soubor exe spusťte parametry) s parametry pro prohlížeč místní nápovědy + klíčová slova z kontejneru objektů, pokud je místní Nápověda výchozí nebo MSDN URL pomocí klíčového slova v seznamu parametrů.  
  
Pokud pro F1 jsou vráceny tyto tři řetězce, označuje jako řetězec s více hodnotami, proveďte první termín, vyhledejte pro klepnutí, a pokud najde, jsme se provádějí; Pokud ne, přejdete na další řetězec.  Záleží na pořadí. Prezentace klíčových slov s více hodnotami by měl být nejdelší řetězec nejkratší řetězec.  Chcete-li to ověřit v případě klíčových slov s více hodnotami, podívejte se na online řetězce adresy URL F1, která bude obsahovat zvolené – klíčové slovo.  
  
V sadě Visual Studio 2012 jsme záměrně provedli silnější dělení mezi online a offline, tak, aby pokud bylo nastavení uživatele pro Online, potom jsme jednoduše F1 žádost předal přímo na naše služba online dotazu na webu MSDN namísto směrování prostřednictvím Agent knihovny nápovědy aby bylo v sadě Visual Studio 2010. Potom spoléháme na stavu "dodavatele obsah nainstalovaný = true" a určí, jestli chcete něco jiného v tomto kontextu. V případě hodnoty true jsme pak provádět tuto logiku analýzy a směrování v závislosti na tom, co chcete podporu pro vaše zákazníky. Není-li pravda, budeme proto přejděte na webu MSDN. Pokud je nastavení uživatele do místní, potom všechna volání jednoduše přejděte k modulu Místní nápověda.  
  
F1 vývojový Diagram:  
  
![Tok F1](../../extensibility/internals/media/f1flow.png "F1flow")  
  
Když zdroj obsahu nápovědy výchozí prohlížeč nápovědy je nastavená na online (spuštění v prohlížeči):  
  
-   Visual Studio partnera (VSP) funkce emitování hodnota balík vlastností F1 (prefix.keyword vlastnosti kontejneru objektů a dat a adresu URL online pro předponu nalezen v registru): F1 odešle URL VSP + parametry do prohlížeče.  
  
-   Funkcích nástroje Visual Studio (jazyk editor, položky nabídky konkrétní sadě Visual Studio atd.): F1 odešle Visual Studio URL do prohlížeče.  
  
Když zdroj obsahu nápovědy výchozí prohlížeč nápovědy je nastavená na místní nápovědy (spuštění v Help Viewer):  
  
-   Funkce VSP tam, kde – klíčové slovo shodují mezi F1 kontejneru objektů a dat a index místní úložiště (tedy prefix.keyword kontejneru vlastnost = hodnota nalezená v místním úložišti index): F1 vykreslí téma v okně nápovědy.  
  
-   Funkcích nástroje Visual Studio (žádná možnost pro VSP přepsat kontejneru objektů a dat a nevydává funkcích nástroje Visual Studio): F1 vykreslí Visual Studio tématu v okně nápovědy.  
  
Nastavte následující hodnoty registru pro povolit záložní F1 pro dodavatele obsahu nápovědy. F1 záložního znamená, že prohlížeč nápovědy je nastavena na hledání obsahu nápovědy F1 online a obsah dodavatele se nainstaluje místně na pevný disk uživatele. Prohlížeč nápovědy by měla vypadat v místní Nápověda pro obsah, i když výchozí nastavení je pro online nápovědy.  
  
1.  Nastavte **VendorContent** hodnotu v klíči registru 2.3 pomáhají:  
  
    -   Pro 32bitové operační systémy:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Catalogs\VisualStudio15  
  
         "VendorContent" = dword: 00000001  
  
    -   Pro 64bitové operační systémy:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15  
  
         "VendorContent" = dword: 00000001  
  
2.  Registrace partnera obor názvů v klíči registru pomůže 2.3:  
  
    -   Pro 32bitové operační systémy:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Partner*\\< obor názvů\>*  
  
         "umístění"="do režimu offline"  
  
    -   Pro 64bitové operační systémy:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Partner*\\< obor názvů\>*  
  
         "umístění"="do režimu offline"  
  
**Základní analýza nativní Namespace**  
  
Pokud chcete zapnout základního oboru názvů nativní analýza, v registru přidejte novou hodnotu DWORD s názvem: BaseNativeNamespaces a jeho hodnotu nastavte na hodnotu 1 (v rámci katalogu klíč, který se má podporovat).  Například pokud chcete používat katalog Visual Studio, můžete přidat klíč k cestě:  
  
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15
  
Když F1 – klíčové slovo ve formátu, který je záhlaví nebo metoda došlo, znak '/' bude možné analyzovat limitu, výsledkem následující konstrukce:  
  
-   ZÁHLAVÍ: bude obor názvů, který slouží k registraci v registru  
  
-   Metoda: to se stane – klíčové slovo, který získá předána.  
  
Například daného vlastní knihovna názvem CustomLibrary a metodu s názvem MyTestMethod, když F1 žádost o pochází v ní bude řada naformátována jako `CustomLibrary/MyTestMethod`.  
  
Uživatele můžete pak zaregistrovat CustomLibrary jako obor názvů v rámci podregistru partnery, zadejte libovolnou umístění klíč chtějí a – klíčové slovo předaný dotaz bude MyTestMethod.  
  
**Povolit ladění nástroj v prostředí IDE nápovědy**  
  
Přidejte následující klíč registru a hodnotu:  
  
Klíč HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Dynamic nápovědy: výstup ladění zobrazení v hodnotě prodejní: Ano  
  
V prostředí IDE, položce nabídky nápovědy vyberte "Ladění pomůže kontext"  
  
**Metadata obsahu**  
  
V následující tabulce je libovolný řetězec, který se zobrazí v hranatých závorkách zástupný symbol, který se musí nahradit odpovídajícími rozpoznaný hodnotu. Například v \<meta name="Microsoft.Help.Locale" obsah = "[kód jazyka]" / >, "[kód jazyka]" se musí nahradit hodnotou, jako "en-us".  
  
|Vlastnost (HTML reprezentace)|Popis|  
|--------------------------------------|-----------------|  
|\<obsah meta name="Microsoft.Help.Locale" = "[– kód jazyka]" / >|Nastaví národní prostředí pro toto téma. Pokud tato značka se používá v tématu, musí být použit pouze jednou a musí být vložený výše jiné značky Microsoft Help. Pokud tato značka se nepoužívá, základní text tohoto tématu je indexovaný pomocí dělení slov, která souvisí s národním prostředí produktu, pokud je zadán; jinak en-us se používá pro dělení slov. Tato značka vyhovuje ISOC RFC 4646. Aby se zajistilo, že Microsoft Help funguje správně, tuto vlastnost použijte místo obecné atributu jazyk.|  
|\<obsah meta name="Microsoft.Help.TopicLocale" = "[– kód jazyka]" / >|Národní prostředí pro toto téma nastavuje, když se také používají jiným národním prostředím. Pokud tato značka se používá v tématu, musíte ho použít pouze jednou. Použijte tuto značku, pokud katalog obsahuje obsah ve více než jednom jazyku. Několika témat v katalogu může mít stejné ID, ale každý musíte zadat jedinečné TopicLocale. Téma, které určuje TopicLocale, odpovídajícímu národnímu katalogu se téma, které se zobrazí v obsahu. Všechny jazykové verze tohoto tématu se však zobrazí ve výsledcích hledání.|  
|\<title > [název] \< /title >|Určuje název tohoto tématu. Tato značka je vyžadován a musí být použit pouze jednou v tématu. Pokud text tématu neobsahuje název \<div > části, tento název se zobrazí v tomto tématu a v obsahu.|  
|\<Meta name = "Microsoft.Help.Keywords" obsah = "[aKeywordPhrase]" / >|Určuje text odkazu, který se zobrazí v podokně indexu nápovědy. Při kliknutí na odkaz, zobrazí se téma. Můžete zadat několik klíčových slov index pro téma nebo tuto značku můžete vynechat, pokud nechcete, aby se odkazy na toto téma se objeví v indexu. Klíčová slova "K" z dřívějších verzí nápovědy lze převést na tuto vlastnost.|  
|\<obsah meta name="Microsoft.Help.Id" = "[TopicID]" / >|Nastaví identifikátor pro toto téma. Tato značka je vyžadován a musí být použit pouze jednou v tématu. ID musí být jedinečný mezi témata v katalogu, které mají stejné nastavení národního prostředí. V jiné téma můžete vytvořit odkaz na toto téma pomocí číslem ID této.|  
|\<Meta name="Microsoft.Help.F1" content="[System.Windows.Controls.Primitives.IRecyclingItemContainerGenerator]"/ >|Určuje klíčové slovo F1 pro toto téma. Můžete zadat několik klíčových slov F1 pro téma nebo tuto značku můžete vynechat, pokud nechcete, aby se v tomto tématu, který se má zobrazit při aplikaci stisknutí klávesy F1. Obvykle je zadán pouze jeden F1 – klíčové slovo pro téma. Klíčová slova "F" z dřívějších verzí nápovědy lze převést na tuto vlastnost.|  
|\<Meta name = "Popis" content = "[tématu Popis]" / >|Poskytuje krátký souhrn obsahu v tomto tématu. Pokud tato značka se používá v tématu, musíte ho použít pouze jednou. Tato vlastnost přistupuje přímo knihovně dotazu; nejsou uložena v souboru indexu.|  
 obsah meta name="Microsoft.Help.TocParent" = "[parent_Id]" / >|Určuje nadřazené téma v tomto tématu v obsahu. Tato značka je vyžadován a musí být použit pouze jednou v tématu. Hodnota je Microsoft.Help.Id nadřazeného objektu. Téma může mít jenom jeden umístění v tabulce obsahu. "-1" je považován za ID tématu pro kořenový obsah. V [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)], že stránka je prohlížeč nápovědy domovské stránky. Toto je ze stejného důvodu, že přidáme konkrétně TocParent =-1 do některá témata zajistit, že se zobrazí v horní úrovni. Prohlížeč nápovědy domovské stránky je stránka systému a proto není výměnná. Pokud VSP se pokusí přidat stránku s ID-1, může se přidají do sady obsahu, ale prohlížeč nápovědy vždycky použijí na stránce systém – Domovská stránka prohlížeč nápovědy|  
|\<obsah meta name="Microsoft.Help.TocOrder" = "[kladné celé číslo]" / >|Určuje, kde v obsahu Toto téma se zobrazí relativně k jeho rovnocenná témata. Tato značka je vyžadován a musí být použit pouze jednou v tématu. Hodnota je celé číslo. Téma, které určuje nižší hodnota celé číslo se zobrazí nad téma, které určuje celé číslo vyšší hodnotu.|  
|\<obsah meta name="Microsoft.Help.Product" = "[kód produktu]" / >|Určuje produkt, který toto téma popisuje. Pokud tato značka se používá v tématu, musíte ho použít pouze jednou. Tyto informace můžete také zadat jako parametr, který je předán indexeru pomoci.|  
|\<obsah meta name="Microsoft.Help.ProductVersion" = "[číslo verze]" / >|Určuje verzi produktu, který toto téma popisuje. Pokud tato značka se používá v tématu, musíte ho použít pouze jednou. Tyto informace můžete také zadat jako parametr, který je předán indexeru pomoci.|  
|\<obsah meta name="Microsoft.Help.Category" = "[řetězec]" / >|Produkty používá k identifikaci témata obsahu. Můžete určit více témata pro téma nebo tuto značku můžete vynechat, pokud nechcete, aby odkazy k identifikaci žádné témata. Tato značka se používá k ukládání atributy pro TargetOS a TargetFrameworkMoniker při převodu téma ze starší verze nápovědy. Formát obsahu je AttributeName:AttributeValue.|  
|\<obsah name="Microsoft.Help.TopicVersion meta ="[tématu číslo verze]"/ >|Určuje této verzi tohoto tématu, když existuje více verzí v katalogu. Protože Microsoft.Help.Id není musí být jedinečný, tato značka je požadován při více než jedna verze téma existuje v katalogu, například když katalog obsahuje téma pro rozhraní .NET Framework 3.5 a téma pro rozhraní .NET Framework 4 a mají stejné Micro logicky. Help.Id.|  
|\<Meta name = "SelfBranded" content = "[hodnotu TRUE nebo FALSE]" / >|Určuje, zda v tomto tématu používá balíček brandingu spuštění Správce knihovny nápovědy nebo brandingu balíček, který je specifická pro téma. Tato značka musí být buď TRUE nebo FALSE. Pokud je hodnota TRUE, pak brandingu balíčku pro přidružené tématu přepsání značce balíček, který je nastaven při spuštění Správce knihovny nápovědy tak, aby tématu je vykreslen tak, jak má i v případě, že se liší od vykreslování jiný obsah. Pokud je FALSE, není v aktuálním tématu vykreslován podle značky balíček, který je nastaven při spuštění Správce knihovny nápovědy. Ve výchozím nastavení předpokládá samoobslužné brandingu měla hodnotu false, pokud proměnnou SelfBranded je deklarován jako TRUE; Správce knihovny nápovědy proto není nutné deklarovat \<meta name = "SelfBranded" content = "FALSE" / >.|  
  
### <a name="creating-a-branding-package"></a>Vytváření vlastní balíček  
Verze Visual Studio zahrnuje několik různých produktů Visual Studio, včetně izolované a integrované prostředí pro partnery, Visual Studio.  Každý z těchto produktů vyžaduje určitý stupeň obsahu na základě téma nápovědy branding podpory, které jsou jedinečné pro produkt.  Témata týkající se sady Visual Studio například musí být konzistentní brand prezentací, zatímco SQL Studio, který zabalí ISO prostředí, vyžaduje svůj vlastní jedinečný nápovědy obsahu branding pro každého tématu.  Partnerem integrované prostředí může být vhodné jejich témata nápovědy, které se v rámci nadřazené obsahu nápovědy produktu Visual Studio při zachování vlastní branding tématu.  
  
Značky balíčky jsou nainstalované ve produktu, který obsahuje Prohlížeč nápovědy.  Pro produkty Visual Studio:  
  
-   Záložní vlastní balíček (Branding_\<národní prostředí > .mshc) je nainstalována v kořenovém adresáři aplikace 2.3 Prohlížeč nápovědy (Příklad: C:\Program Files (x86) \Microsoft Help Viewer\v2.3) podle jazyková sada prohlížeče nápovědy.  Používá se pro případy, kde není nainstalovaná produktu branding balíčku (žádný obsah nejsou nainstalované) nebo kde nainstalované brandingu balíček je poškozený.  Všimněte si, že jsou při záložního kořenové aplikace, branding balíčku se používá ignorovány elementy sady Visual Studio (logo a zpětnou vazbu).  
  
-   Při instalaci sady Visual Studio obsah ze služby obsahu balíčku (pro první scénář čas instalace obsahu) je také nainstalována vlastní balíček.  Pokud dojde k aktualizaci brandingu balíčku, je aktualizace nainstalována případě další aktualizace obsahu nebo akce instalovat další balíčky.  
  
Prohlížeč nápovědy podporuje branding témata na základě metadat tématu.  
  
-   Kde tématu metadata definuje vlastní značky = true, vykreslení tématu, jako je, nedělat nic (Pokud je to branding).  
  
-   Kde tématu metadata definuje vlastní značky = false, použít balíček brandingu asociovaná s hodnotou TopicVendor metadat.  
  
-   Kde tématu metadata definuje name="Microsoft.Help.TopicVendor" obsah =\< brandingu název balíčku v dodavatele MSHA >, používat vlastní balíček definován v hodnotě obsahu.  
  
-   Všimněte si, že v katalogu sady Visual Studio, s prioritou aplikace Branding balíčků.  První sady Visual Studio výchozí branding je platné a pak, pokud definované v metadatech tématu a podporovaná s přidružené branding balíček (podle definice v msha instalace), dodavatele definované branding je použít jako přepsání.  
  
Značky elementů obvykle spadají do tří kategorií:  
  
-   Prvky záhlaví (příklady zahrnují odkaz pro zasílání názorů, text podmíněného zřeknutí se práv, logo)  
  
-   Obsahu chování (příklady zahrnují rozbalit nebo sbalit ovládací prvek text elementy a elementy fragmentu kódu)  
  
-   Elementy zápatí (třeba Copyright)  
  
Položky považuje za partnerské prvky patří (popsané v této specifikaci):  
  
-   Logo katalogu nebo produktu (například Visual Studio)  
  
-   Elementy odkazu a e-mailu zpětné vazby  
  
-   Text zřeknutí se práv  
  
-   Autorským textu  
  
Podpůrné soubory v balíčku brandingu Visual Studio Help Viewer patří:  
  
-   Grafika (loga, ikony, atd.)  
  
-   Branding.js - skriptu soubory podpůrné obsahu chování  
  
-   Branding.XML - řetězce, které používají konzistentní napříč obsahu katalogu.  Poznámka: pro Visual Studio lokalizace elementy textu v branding.xml, zahrnout _locID = "\<jedinečnou hodnotu >"  
  
-   Branding.CSS – styl definice konzistenci prezentace  
  
-   Printing.CSS – styl definice pro konzistentní tisk prezentace  
  
Jak jsme uvedli výše, Branding balíčky jsou přidružené k tomuto tématu:  
  
-   Když SelfBranded = false je definována v metadatech, tématu dědí katalogu branding balíčku  
  
-   Nebo pokud SelfBranded = false a že je jedinečný Branding balíček definováno v MSHA a k dispozici při instalaci obsahu  
  
Pro VSPs implementace vlastní značky balíčky (VSP obsahu, SelfBranded = True), jeden způsob, jak pokračovat má začínat záložní brandingu balíčku (instalovanou se Help Viewer) a změňte název souboru podle potřeby.  Branding_\<národní prostředí > .mshc soubor je soubor zip s příponou souboru změnit tak, aby .mshc, takže jednoduše změňte rozšíření z .mshc na ZIP a extrahujte obsah.  Níže najdete branding balíček elementy a upravit podle potřeby (například změnit logo VSP logo a odkaz na logo v souboru Branding.xml, aktualizovat Branding.xml za VSP specifika atd.).  
  
Po všechny změny, vytvořte soubor zip obsahující požadované prvky pro přizpůsobení a změňte příponu na .mshc.  
  
Chcete-li přidružit vlastní značky balíček, vytvořte MSHA, který obsahuje odkaz na soubor brandingu mshc společně s obsahu mshc (obsahující témata).  Najdete níže "MSHA" jak vytvořit základní MSHA.  
  
Soubor Branding.xml obsahuje prvky seznamů používané k vykreslování konzistentně konkrétní položky v tématu, pokud obsahuje téma \<meta name="Microsoft.Help.SelfBranded" obsah = "false" / >.  Níže je uveden seznam prvků v souboru Branding.xml Visual Studio.  Všimněte si, že tento seznam je určený má být použit jako šablona pro prvními ISO prostředí, kde se upravit tyto prvky (například logo, zpětnou vazbu a Copyright) ke splnění svých vlastních produktu branding potřebám.  
  
Poznámka: proměnné, které jsou označeny "{n}" mají závislostem kódu – odebrání nebo změny těchto hodnot způsobí chyby a případně aplikace havárií. Lokalizace identifikátory (příklad _locID="codesnippet.n") jsou součástí balíčku sady Visual Studio brandingu.  
  
**Branding.XML**  
  
|||  
|-|-|  
|Funkce:|**CollapsibleArea**|  
|Použití:|Rozbalte text sbalí obsahu ovládacího prvku|  
|**Element**|**Hodnota**|  
|ExpandText|Rozbalte položku|  
|CollapseText|Sbalit|  
|Funkce:|**CodeSnippet**|  
|Použití:|Text řízení fragmentu kódu.  Poznámka: Obsah fragmentu kódu s místo "Non-ukončování" bude změněno na místo.|  
|**Element**|**Hodnota**|  
|CopyToClipboard|Kopírovat do schránky|  
|ViewColorizedText|Zobrazení obarvené|  
|CombinedVBTabDisplayLanguage|Visual Basic (ukázka)|  
|VBDeclaration|Deklarace|  
|VBUsage|Použití|  
|Funkce:|**Zpětná vazba, zápatí a loga**|  
|Použití:|Poskytnout zpětnou vazbu ovládacího prvku pro zákazníka, které chcete poskytnout zpětnou vazbu na aktuálním tématu prostřednictvím e-mailu.  Autorským text pro obsah.  Logo definice.|  
|**Element**|**Hodnota (tyto řetězce můžete upravit tak, aby splňovaly potřeby obsahu adopter.)**|  
|CopyRight|© 2013 Microsoft Corporation. Všechna práva vyhrazena.|  
|SendFeedback|\<href = "{0}" {1} > odeslat zpětnou vazbu\</a > k tomuto tématu společnosti Microsoft.|  
|FeedbackLink||  
|LogoTitle|[!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)]|  
|LogoFileName|vs_logo_bk.GIF|  
|LogoFileNameHC|vs_logo_wh.GIF|  
|Funkce:|**Právní omezení**|  
|Použití:|Sadu případu konkrétní omezení pro počítač přeložit obsah.|  
|**Element**|**Hodnota**|  
|MT_Editable|Tento článek byl přeložen strojově. Pokud máte připojení k Internetu, vyberte "Zobrazit online v tomto tématu" k zobrazení této stránky v režimu umožňujícím úpravy původní anglické obsah ve stejnou dobu.|  
|MT_NonEditable|Tento článek byl přeložen strojově. Pokud máte připojení k Internetu, vyberte "Zobrazit online v tomto tématu" k zobrazení této stránky v režimu umožňujícím úpravy původní anglické obsah ve stejnou dobu.|  
|MT_QualityEditable|Tento článek byl přeložen ručně. Pokud máte připojení k Internetu, vyberte "Zobrazit online v tomto tématu" k zobrazení této stránky v režimu umožňujícím úpravy původní anglické obsah ve stejnou dobu.|  
|MT_QualityNonEditable|Tento článek byl přeložen ručně. Pokud máte připojení k Internetu, vyberte "Zobrazit online v tomto tématu" k zobrazení této stránky v režimu umožňujícím úpravy původní anglické obsah ve stejnou dobu.|  
|MT_BetaContents|Tento článek byl přeložen pro předběžná verze strojově. Pokud máte připojení k Internetu, vyberte "Zobrazit online v tomto tématu" k zobrazení této stránky v režimu umožňujícím úpravy původní anglické obsah ve stejnou dobu.|  
|MT_BetaRecycledContents|Tento článek byl přeložen ručně pro předběžné verzi. Pokud máte připojení k Internetu, vyberte "Zobrazit online v tomto tématu" k zobrazení této stránky v režimu umožňujícím úpravy původní anglické obsah ve stejnou dobu.|  
|Funkce:|**LinkTable**|  
|Použití:|Podpora pro online téma obsahuje odkazy|  
|**Element**|**Hodnota**|  
|LinkTableTitle|Odkaz tabulky|  
|TopicEnuLinkText|Zobrazit anglickou verzi\</a > v tomto tématu, která je k dispozici ve vašem počítači.|  
|TopicOnlineLinkText|Zobrazení v tomto tématu \<href = "{0}" {1} > online\</a >|  
|OnlineText|online|  
|Funkce:|**Video zvuk ovládací prvek**|  
|Použití:|Zobrazit elementy a text obsahu videa|  
|**Element**|**Hodnota**|  
|MultiMediaNotSupported|Internet Explorer 9 nebo vyšší musí být nainstalována na podporu obsah {0}.|  
|VideoText|zobrazení video|  
|AudioText|datový proud zvuku|  
|OnlineVideoLinkText|\<p > zobrazte video spojené s tímto tématem, klikněte na tlačítko {0}\<href = "\ {1\}" > {2}here\</a >.\< /p >|  
|OnlineAudioLinkText|\<p > pro naslouchání na zvuk spojené s tímto tématem, klikněte na tlačítko {0}\<href = "\ {1\}" > {2}here\</a >.\< /p >|  
|Funkce:|**Ovládací prvek obsahu není nainstalován**|  
|Použití:|Elementy textu (řetězce) používá pro vykreslování contentnotinstalled.htm|  
|**Element**|**Hodnota**|  
|ContentNotInstalledTitle|V počítači nenašel se žádný obsah.|  
|ContentNotInstalledDownloadContentText|\<p > Chcete-li stáhnout obsah do počítače, \<href = "{0}" {1} > klikněte na kartu Správa\</a >.\< /p >|  
|ContentNotInstalledText|\<p > v počítači je nainstalován žádný obsah. Podrobnosti viz svého správce místní instalace obsahu nápovědy. \</p >|  
|Funkce:|**Téma nebyl nalezen ovládací prvek**|  
|Použití:|Elementy textu (řetězce) používá pro vykreslování topicnotfound.htm|  
|**Element**|**Hodnota**|  
|TopicNotFoundTitle|Nelze najít požadovaný tématu ve vašem počítači.|  
|TopicNotFoundViewOnlineText|\<p > tématu požadovaná nebyl nalezen v počítači, ale můžete \<href = "{0}" {1} > zobrazit v online tématu\</a >.\< /p >|  
|TopicNotFoundDownloadContentText|\<p > naleznete na navigačním panelu odkazů na témata, podobné, nebo \<href = "{0}" {1} > klikněte na kartu Správa\</a > ke stahování obsahu do vašeho počítače.\< /p >|  
|TopicNotFoundText|\<p > tématu požadovaná nebyl nalezen v počítači. \</p >|  
|Funkce:|**Téma poškozený ovládací prvek**|  
|Použití:|Elementy textu (řetězce) používá pro vykreslování topiccorrupted.htm|  
|**Element**|**Hodnota**|  
|TopicCorruptedTitle|Nelze zobrazit požadované téma.|  
|TopicCorruptedViewOnlineText|\<p > Prohlížeč nápovědy nemůže zobrazit požadovaný tématu. Pravděpodobně došlo k chybě v obsahu v tématu nebo základní systémová závislost. \</p >|  
|Funkce:|**Ovládací prvek domovskou stránku**|  
|Použití:|Text Podpora zobrazení obsahu Help Viewer uzel nejvyšší úrovně.|  
|**Element**|**Hodnota**|  
|HomePageTitle|Domovská stránka prohlížeč nápovědy|  
|HomePageIntroduction|\<p > Vítá vás Microsoft prohlížeče nápovědy, základní zdroj informací pro všechny uživatele nástroje, produkty, technologie a služby společnosti Microsoft. Help Viewer umožňuje přístup k postupy a referenční informace, ukázky kódu, technické články a další. Hledání obsahu, budete potřebovat, procházet obsah, použít fulltextové vyhledávání nebo procházení obsahu pomocí indexu – klíčové slovo. \</p >|  
|HomePageContentInstallText|\<p >\<br / > použití \<href = "{0}" {1} > Správa obsahu\</a > provést následující:\<ul >\<li > přidat obsah na váš počítač.\< /li >\<li > zkontrolujte aktualizace lokálního obsahu.\< /li >\<li > odebrat obsah z vašeho počítače.\< /li >\</ul >\</p >|  
|HomePageInstalledBooks|Nainstalované knihy|  
|HomePageNoBooksInstalled|V počítači nenašel se žádný obsah.|  
|HomePageHelpSettings|Nastavení obsahu nápovědy|  
|HomePageHelpSettingsText|\<p > vaše aktuální nastavení je místní Nápověda. Prohlížeč nápovědy zobrazí obsah, který jste nainstalovali ve vašem počítači. \<br / > Chcete-li změnit váš zdroj obsahu nápovědy na panelu nabídek Visual Studio zvolte \<span style = "{0}" > pomoci, nastavit předvolby pomoci\</span >.\< br / >\</p >|  
|Megabajtech|MB|  
  
**Branding.js**  
  
Soubor branding.js obsahuje JavaScript používané prvky přizpůsobení Visual Studio Help Viewer.  Níže je seznam prvky pro přizpůsobení a podpůrné funkce jazyka JavaScript.  Všechny řetězce lokalizovat pro tento soubor jsou definovány v sekci "Lokalizovatelný řetězce" v horní části tohoto souboru.  Všimněte si, že byl vytvořen soubor ICL pro umístění řetězce v rámci tohoto souboru branding.js.  
  
||||  
|-|-|-|  
|**Branding funkce**|**Funkce jazyka JavaScript**|**Popis**|  
|Var...||Definování proměnné|  
|Získat jazyk kódu uživatele|setUserPreferenceLang|mapuje index # pro jazyk kódu|  
|Nastavování a získávání hodnoty souboru cookie|getCookie setCookie||  
|Zděděného členu|changeMembersLabel|Rozbalit nebo sbalit zděděného členu|  
|Když SelfBranded = False|Při načtení|Přečtěte si řetězec dotazu, zkontrolujte, zda se jedná o žádost o tisku.  Nastavte všechny codesnippets a zaměřit se na kartě upřednostňované uživatele.  Pokud je tisku isPrinterFriendly žádost o pak nastavena na hodnotu true. Zkontrolujte, zda režimu vysokého kontrastu.|  
|Fragment kódu|addSpecificTextLanguageTagSet||  
||getIndexFromDevLang||  
||ChangeTab||  
||setCodesnippetLang||  
||setCurrentLang||  
||CopyToClipboard||  
|CollapsibleArea|addToCollapsibleControlSet|Zapište všechny objekt sbalitelné ovládacího prvku do seznamu.|  
||CA_Click|na základě stavu sbalitelné oblasti, definuje, které bitové kopie a text, který má k dispozici|  
|Podpora kontrast Logo|isBlackBackground()|Voláno k určení, zda je černé pozadí.  Pokud jenom přesné v režimu vysokého kontrastu.|  
||isHighContrast()|používejte k detekci režimu vysokého kontrastu barevnou rozpětí|  
||onHighContrast(black)|Volá se, když je zjištěna vysoký kontrast|  
|Funkce Obrázků|||  
||addToLanSpecTextIdSet(id)||  
||updateLST(currentLang)||  
||getDevLangFromCodeSnippet(lang)||  
|Multimediální funkce|Popisek (začít, end, text, styl)||  
||findAllMediaControls(normalizedId)||  
||getActivePlayer(normalizedId)||  
||captionsOnOff(id)||  
||toSeconds(t)||  
||getAllComments(node)||  
||styleRectify (název stylu, styleValue)||  
||showCC(id)||  
||subtitle(ID)||  
  
**SOUBORY HTM**  
  
Značky balíček obsahuje sadu souborů HTM, které podporují scénáře pro komunikaci klíčové informace obsahu uživatelům nápovědy, například domovskou stránku, která obsahuje oddíl popisující, které sady obsahu jsou nainstalované a stránky, která uživatele vyzve, když nelze témata najít v místní sadu témat. Všimněte si, že tyto soubory HTM lze upravit každý produkt.  Dodavatelé ISO prostředí budou moci přijmout výchozí značky balíček a změnit chování a obsah tyto stránek Suite jejich potřebují.  Tyto soubory odkazovat na jejich odpovídající značky balíčku v pořadí pro brandingu značky k získání odpovídající obsahu ze souboru branding.xml.  
  
||||  
|-|-|-|  
|**Soubor**|**Použití**|**Zobrazí zdroje obsahu**|  
|domovskastranka.htm|Toto je stránka, která zobrazuje obsah aktuálně nainstalovaný a jakoukoli jinou zprávu vhodné pro uživatele o jejich obsahu.  Tento soubor má další obsah meta data atribut "Microsoft.Help.Id" = "-1" který nahradí to obsahu v horní části místní obsahu obsah.||  
||< META_HOME_PAGE_TITLE_ADD / >|Branding.XML, značka \<HomePageTitle >|  
||< HOME_PAGE_INTRODUCTION_SECTION_ADD / >|Branding.XML, značka \<HomePageIntroduction >|  
||< HOME_PAGE_CONTENT_INSTALL_SECTION_ADD / >|Branding.XML, značka \<HomePageContentInstallText >|  
||< HOME_PAGE_BOOKS_INSTALLED_SECTION_ADD / >|Záhlaví části značky Branding.xml\<HomePageInstalledBooks >, data vygenerovaná aplikací, \<HomePageNoBooksInstalled > když jsou nainstalovány žádné knihy.|  
||< HOME_PAGE_SETTINGS_SECTION_ADD / >|Záhlaví části značky Branding.xml \<HomePageHelpSettings >, část textu \<HomePageHelpSettingsText >.|  
|topiccorrupted.htm|Pokud téma existuje v sadě místní, ale pro z nějakého důvodu nelze zobrazit (poškozený obsah).||  
||< META_TOPIC_CORRUPTED_TITLE_ADD / >|Branding.XML, značka \<TopicCorruptedTitle >|  
||< TOPIC_CORRUPTED_SECTION_ADD / >|Branding.XML, značka \<TopicCorruptedViewOnlineText >|  
|topicnotfound.htm|Pokud téma nebyl nalezen v místní obsah nastavte, ani není k dispozici online||  
||< META_TOPIC_NOT_FOUND_TITLE_ADD / >|Branding.XML, značka \<TopicNotFoundTitle >|  
||< META_TOPIC_NOT_FOUND_ID_ADD / >|Branding.XML, značka \<TopicNotFoundViewOnlineText > + \<TopicNotFoundDownloadContentText >|  
||< TOPIC_NOT_FOUND_SECTION_ADD / >|Branding.XML, značka \<TopicNotFoundText >|  
|contentnotinstalled.htm|Pokud neexistuje žádný místní obsah pro produkt nainstalována.||  
||< META_CONTENT_NOT_INSTALLED_TITLE_ADD / >|Branding.XML, značka \<ContentNotInstalledTitle >|  
||< META_CONTENT_NOT_INSTALLED_ID_ADD / >|Branding.XML, značka \<ContentNotInstalledDownloadContentText >|  
||< CONTENT_NOT_INSTALLED_SECTION_ADD / >|Branding.XML, značka \<ContentNotInstalledText >|  
  
**Soubory šablon stylů CSS**  
  
Balíčku sady Visual Studio pomůže prohlížeč Branding obsahuje dva soubory šablon stylů css pro podporu konzistentní nápovědě k sadě Visual Studio obsahu prezentace:  
  
-   Branding.CSS – obsahuje prvky šablon stylů css pro vykreslování kde SelfBranded = false  
  
-   Printer.CSS – obsahuje prvky šablon stylů css pro vykreslování kde SelfBranded = false  
  
Soubory Branding.CSS obsahuje definice pro Visual Studio tématu prezentace (přímý přístup paměti je, že branding.css součástí Branding_\<národní prostředí > může změnit .mshc z balíčku služby).  
  
**Grafické soubory**  
  
Visual Studio obsah zobrazuje logo sady Visual Studio, jakož i jiné grafiky.  Úplný seznam grafické soubory v balíčku Visual Studio Help Viewer značky jsou uvedeny níže.  
  
||||  
|-|-|-|  
|**Soubor**|**Použití**|**Příklady**|  
|Clear.GIF|Použít k vykreslení sbalitelné oblasti||  
|footer_slice.GIF|Prezentace zápatí||  
|info_icon.GIF|Použít při zobrazení informací o|Právní omezení|  
|online_icon.GIF|Tato ikona má být přidružen k online odkazy||  
|tabLeftBD.gif|Použít k vykreslení kontejneru fragmentu kódu||  
|tabRightBD.gif|Použít k vykreslení kontejneru fragmentu kódu||  
|vs_logo_bk.GIF|Použít pro odkazy logo normální kontrast definovaným ve značce Branding.xml \<LogoFileName >.  Pro produkty Visual Studio je název logo vs_logo_bk.gif.||  
|vs_logo_wh.GIF|Použít pro odkazy na normální vysoké logo definovaným ve značce Branding.xml \<LogoFileNameHC >.  Pro produkty Visual Studio je název logo vs_logo_wh.gif.||  
|ccOff.png|Přidávání titulků obrázek||  
|ccOn.png|Přidávání titulků obrázek||  
|ImageSprite.png|Použít k vykreslení sbalitelné oblasti|Rozbalit nebo sbalit obrázek|  
  
### <a name="deploying-a-set-of-topics"></a>Nasazení sadu témat  
Toto je velmi jednoduchý a rychlý kurz pro vytvoření nasazení obsahu Help Viewer nastavit comprised MSHA soubor a sadu souborů CAB nebo MSHC obsahující témata. MSHA je soubor XML, který popisuje sadu souborů CAB nebo MSHC soubory. Prohlížeč nápovědy může číst MSHA k získání seznamu obsahu (je. Soubor CAB nebo. Soubory MSHC) k dispozici pro místní instalaci.  
  
Toto je pouze základy popisující velmi základní schématu XML pro prohlížeč MSHA pomoci.  Všimněte si, že je příklad implementace níže Tento stručný přehled a ukázkové HelpContentSetup.msha.  
  
Název MSHA, pro účely tento úvod do je HelpContentSetup.msha (název souboru může být jakýkoli, s příponou. MSHA). HelpContentSetup.msha (následující příklad) by měl obsahovat seznam souborů CAB nebo MSHCs k dispozici.  Všimněte si, že typ souboru musí být konzistentní v rámci MSHA (nepodporuje kombinaci typů souborů MSHA a souborů CAB). Pro každý soubor CAB nebo MSHC, měla by existovat \<div třídy = "balíček" >...  \< /div > (viz následující příklad).  
  
Poznámka: v následujícím příkladu implementace jsme zahrnuli označující balíček. To je důležité zahrnout při získání potřebných elementy vykreslování obsahu sady Visual Studio a obsahu chování.  
  
Ukázkový soubor HelpContentSetup.msha: (nahraďte "obsah nastavit název 1" a "obsahu, název sady 2" atd. s názvy souborů.)  
  
```html
<html>  
<head />  
<body class="vendor-book">  
<div class="details">  
<span class="vendor">Your Company</span>  
<span class="locale">en-us</span>  
<span class="product">Your Company Help Content</span>  
<span class="name">Your Company Help Content</span>  
</div>  
<div class="package-list">  
<div class="package">  
<span class="name">Your_Company _Content_Set_1</span>  
<span class="deployed">True</span>  
<a class="current-link" href="Your_Company _Content_Set_1.mshc">Your_Company _Content_Set_1.mshc </a>  
</div>  
<div class="package">  
<span class="name">Your_Company _Content_Set_2</span>  
<span class="deployed">True</span>  
<a class="current-link"href=" Your_Company _Content_Set_2.mshc "> Your_Company _Content_Set_2.mshc </a>  
</div>.  
  
```  
  
1.  Vytvořte místní složku, něco jako "C:\SampleContent"  
  
2.  V tomto příkladu používáme MSHC soubory tak, aby obsahovala témata.  MSHC je zip s příponou souboru se změnil z .zip na. MSHC.  
  
3.  Vytvořte níže HelpContentSetup.msha jako textový soubor (poznámkového bloku byl použit k vytvoření souboru) a uložte ho do výše uvedené složky (viz krok 1).  
  
Všimněte si, že třída "Branding" existuje a je jedinečný. Branding mshc je součástí tento úvod do tak, aby nainstalované obsahu budou mít branding a obsahu chování, které jsou součástí MSHCs bude mít odpovídající podpora elementy obsažené v balíčku brandingu. Bez toho budou výsledkem chyby při systému vypadá pro podporu položky, které nejsou součástí zkopírované (nainstalována) obsahu.  
  
Pokud chcete získat branding balíčku sady Visual Studio, zkopírujte soubor Branding_en US.mshc v C:\Program Files (x86) \Microsoft Help Viewer\v2.3\ pracovní složky.  
  
```html  
<html>  
<head />  
<body class="vendor-book">  
<div class="details">  
<span class="vendor">Your Company</span>  
<span class="locale">en-us</span>  
<span class="product">Your Company Help Content</span>  
<span class="name">Your Company Help Content</span>  
</div>  
<div class="package-list">  
<div class="package">  
<span class="name">Your_Company _Content_Set_1</span>  
<span class="deployed">True</span>  
<a class="current-link" href="Your_Company _Content_Set_1.mshc">Your_Company _Content_Set_1.mshc </a>  
</div>  
<div class="package">  
<span class="name">Your_Company _Content_Set_2</span>  
<span class="deployed">True</span>  
<a class="current-link"href=" Your_Company _Content_Set_2.mshc "> Your_Company _Content_Set_2.mshc </a>  
</div>  
<div class="package">  
<span class="packageType">branding</span>  
<span class="name">Branding_en-US</span>  
<span class="deployed">True</span>  
<a class="current-link" href="Branding_en-US.mshc">Branding_en-US.mshc</a>  
</div>  
</div>  
</body>  
</html>  
  
```  
  
**Shrnutí**  
  
VSPs nasadit jejich obsahu sady Visual Studio Help Viewer vám umožní pomocí a rozšíření výše uvedené kroky.  
  
### <a name="adding-help-to-the-visual-studio-shell-integrated-and-isolated"></a>Přidání nápovědu k prostředí Visual Studio (integrovaný režim a izolovaná)  
**Úvod**  
  
Tento návod ukazuje, jak začlenit obsahu nápovědy do prostředí sady Visual Studio aplikace a poté ji nasadit.  
  
**Požadavky**  
  
1.  [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)]  
  
2.  [Izolované prostředí Redist Visual Studio 2013](http://www.microsoft.com/visualstudio/11/downloads#vs-shell)  
  
**Přehled**  
  
[!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] Prostředí je verze [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] IDE, na kterém vytváříte aplikaci. Takové aplikace obsahovat izolované prostředí společně s rozšíření, které vytvoříte. Pomocí šablony projektu izolované prostředí, které jsou součástí [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] SDK k sestavení rozšíření.  
  
Základní kroky pro vytvoření aplikace založené na izolované prostředí a jeho nápovědy:  
  
1.  Získat [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] ISO prostředí redistributable (Microsoft ke stažení).  
  
2.  V sadě Visual Studio vytvořte nápovědy příponu, která je založena na izolovaném prostředí, například, rozšíření nápovědy společnosti Contoso, který je popsán dále v tomto návodu.  
  
3.  Zabalení rozšíření a ISO prostředí redistributable do nasazení MSI (instalace aplikací). Tento návod neobsahuje krok instalace.  
  
Vytvoření úložiště obsahu sady Visual Studio. Integrované prostředí scénář změňte Visual Studio12 název katalogu produktů následujícím způsobem:  
  
-   Vytvořte složku C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\VisualStudio15.  
  
-   Vytvořte soubor s názvem CatalogType.xml a přidat jej do složky. Soubor by měl obsahovat následující řádky kódu:  
  
    ```xml
    <?xml version="1.0" encoding="UTF-8"?>  
    <catalogType>UserManaged</catalogType>  
    ```  
  
Definujte úložiště obsahu v registru. Pro integrované prostředí změňte VisualStudio15 katalogu název produktu:  
  
-   HKLM\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15  
  
     Klíč: LocationPath řetězcovou hodnotu: C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\VisualStudio15\  
  
-   HKLM\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15\en-us  
  
     Klíč: Název_katalogu řetězcovou hodnotu: [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] dokumentace  
  
**Vytvoření projektu**  
  
Vytváření rozšíření izolované prostředí:  
  
1.  V sadě Visual Studio v části **soubor**, zvolte **nový projekt**v části **jiné typy projektů** zvolte **rozšiřitelnost**a potom zvolte  **Izolované prostředí Visual Studio**. Název projektu `ContosoHelpShell`) k vytvoření projektu rozšíření založený na šabloně izolované prostředí sady Visual Studio.  
  
2.  V Průzkumníku řešení v projektu ContosoHelpShellUI ve složce soubory prostředků, otevřete ApplicationCommands.vsct. Ujistěte se, že tento řádek je označeno jako komentář (vyhledejte "No_Help"):`<!-- <define name="No_HelpMenuCommands"/> -->`  
  
3.  Zvolte klávesy F5 zkompilování a spuštění **ladění**. V experimentální instance izolované prostředí IDE, zvolte **pomoci** nabídky. Ujistěte se, že **zobrazit nápovědu**, **přidat a odebrat pomůže obsahu**, a **nastavit předvolby pomoci** zobrazí příkazy.  
  
4.  V Průzkumníku řešení otevřete v projektu ContosHelpShell ve složce vlastního nastavení prostředí ContosoHelpShell.pkgdef. Chcete-li definovat katalogu nápovědy společnosti Contoso, přidejte následující řádky:  
  
    ```  
     [$RootKey$\Help]  
    "Product"="Contoso"  
    "Catalog"="Contoso"  
    "Version"="100"  
    "BrandingPackage"="ContosoBrandingPackage.mshc"  
    ```  
  
5.  V Průzkumníku řešení otevřete v projektu ContosHelpShell ve složce vlastního nastavení prostředí ContosoHelpShell.Application.pkgdef. Pokud chcete povolit Nápověda F1, přidejte následující řádky:  
  
    ```  
    // F1 Help Provider  
  
    [$RootKey$\HelpProviders\{C99BDC23-FF29-46bf-9658-ADD634CCAED8}]  
    "Name"="13407"  
    "Package"="{DA9FB551-C724-11d0-AE1F-00A0C90FFFC3}"  
    @="Help3 Provider"  
    [$RootKey$\HelpProviders]  
    @="{C99BDC23-FF29-46bf-9658-ADD634CCAED8}"  
    [$RootKey$\Services\{C99BDC23-FF29-46bf-9658-ADD634CCAED8}]  
    "Name"="Help3 Provider"  
    @="{4A791146-19E4-11D3-B86B-00C04F79F802}"  
    ```  
  
6.  V Průzkumníku řešení, vyberte v místní nabídce řešení ContosoHelpShell **vlastnosti** položku nabídky. V části **vlastnosti konfigurace**, vyberte **nástroje Configuration Manager**. V **konfigurace** sloupce, změňte hodnotu každých "Ladění" na "Verze".  
  
7.  Sestavte řešení. Tím se vytvoří sadu souborů ve složce verze, která bude použita v další části.  
  
Abyste to mohli otestovat jakoby nasazení:  
  
1.  Na počítači nasazujete Contoso do instalace stažené ISO prostředí (výše).  
  
2.  Vytvořte složku v \\\Program Files (x86)\\a pojmenujte ji `Contoso`.  
  
3.  Zkopírujte obsah ve složce release ContosoHelpShell k \\složku \Program Files (x86) \Contoso\.  
  
4.  Spusťte Editor registru tak, že zvolíte **spustit** v **spustit** nabídky a zadáním `Regedit`. V editoru registru zvolte **soubor**a potom **Import**. Přejděte do složky ContosoHelpShell projektu. V dílčí složce ContosoHelpShell zvolte ContosoHelpShell.reg.  
  
5.  Vytvoření úložiště obsahu:  
  
     Pro prostředí ISO - vytvořte obsahu úložiště Contoso C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\ContosoDev12  
  
     Pro [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] integrované prostředí, vytvořte složku C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\VisualStudio15  
  
6.  Vytvořte CatalogType.xml a přidejte k ukládání obsahu (předchozí krok) obsahující:  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <catalogType>UserManaged</catalogType>  
    ```  
  
7.  Přidejte následující klíče registru:  
  
     HKLM\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15Key: LocationPath řetězcovou hodnotu:  
  
     Pro ISO prostředí:  
  
     C:ProgramDataMicrosoftHelpLibrary2CatalogsVisualStudio15  
  
     [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)]Integrované prostředí:  
  
     C:ProgramDataMicrosoftHelpLibrary2CatalogsVisualStudio15en-USA  
  
     Klíč: Název_katalogu řetězcovou hodnotu: [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] dokumentaci. U ISO prostředí je to název katalogu.  
  
8.  Zkopírujte obsah (soubory CAB nebo MSHC a MSHA) do místní složky.  
  
9. Příklad integrované prostředí příkazového řádku pro testování ukládání obsahu. Pro prostředí ISO změňte hodnoty katalogu a launchingApp podle potřeby tak, aby odpovídaly produktu.  
  
     Metoda /helpQuery /catalogName VisualStudio15 "C:\Program soubory (x86) \Microsoft Help Viewer\v2.3\HlpViewer.exe" = "Stránka & id = ContosoTopic0" /launchingApp Microsoft Visual Studio, 12.0  
  
10. Spuštění aplikace Contoso (z kořenového adresáře aplikace Contoso). V rámci prostředí ISO, vyberte **pomoci** položky nabídky a změňte **nastavit předvolby pomoci** k **použití místní nápovědy**.  
  
11. V rámci prostředí, vyberte **pomoci** položky nabídky, pak **zobrazit nápovědu**. Měli spustit místní programu Help viewer. Vyberte **spravovat obsah** kartě. V části **zdroj instalace**, vyberte **disku** tlačítko. Vyberte **...**  tlačítko a přejděte do místní složky obsahující obsah společnosti Contoso (zkopírován do místní složky v předchozím kroku). Vyberte HelpContentSetup.msha. Contoso má nyní zobrazují jako knihy na výběr adresáře. Zvolte **přidat**a potom zvolte **aktualizace** tlačítko (dolního rohu).  
  
12. V rámci společnosti Contoso integrovaného vývojového prostředí zvolte klávesy F1 F1 správnou funkci.  
  
### <a name="additional-resources"></a>Další prostředky  
Rozhraní API modulu Runtime najdete v části [rozhraní API systému Windows pomůže](http://msdn.microsoft.com/library/windows/desktop/hh447318\(v=vs.85\).aspx).  
  
Další informace o tom, jak využít rozhraní API pomůže najdete v tématu [pomoci příklady kódu pro prohlížeč](http://visualstudiogallery.msdn.microsoft.com/f08f296f-7076-4aec-8da3-8f0fbe04461e)  
  
Chcete-li poskytnout zpětnou vazbu o těchto součástí, použijte [Microsoft Connect](http://connect.microsoft.com/).  
  
Prosím návrhy funkcí k [Microsoft User Voice](http://visualstudio.uservoice.com/forums/121579-visual-studio)  
  
Chcete-li získat další pomoc, zkuste [fórech MSDN dokumentaci pro vývojáře a systému nápovědy](http://social.msdn.microsoft.com/Forums/devdocs/threads)  
  
Aktualizace na nejnovější problém, naleznete [Readme Prohlížeč nápovědy](http://go.microsoft.com/fwlink/?LinkID=231397&clcid=0x409)  
  
Obraťte se na tým pomoct PM prohlížeč přímo, pošlete e-mail nahlpfdbk@microsoft.com