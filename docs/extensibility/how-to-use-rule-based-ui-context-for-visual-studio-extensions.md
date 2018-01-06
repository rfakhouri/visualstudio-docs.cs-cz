---
title: "Postupy: použití kontextu založený na pravidlech uživatelského rozhraní pro rozšíření Visual Studia | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8dd2cd1d-d8ba-49b9-870a-45acf3a3259d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
ms.workload: vssdk
ms.openlocfilehash: 92166106c1470aaf1af7198a133495dba333c121
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-rule-based-ui-context-for-visual-studio-extensions"></a>Postupy: použití kontextu založený na pravidlech uživatelského rozhraní pro rozšíření Visual Studia
Visual Studio umožňuje načítání VSPackages při určitých známých <xref:Microsoft.VisualStudio.Shell.UIContext>s aktivují. Tyto kontexty uživatelského rozhraní nejsou velmi dobře podrobných, ponechat autorům rozšíření žádný výběr ale vybrat kontextu k dispozici uživatelské rozhraní, která aktivuje před bodem VSPackage načíst ve skutečnosti chtěli. Seznam známých kontexty uživatelského rozhraní, naleznete v části <xref:Microsoft.VisualStudio.Shell.KnownUIContexts>.  
  
 Načítání balíčků může mít dopad na výkon a jejich načtení dříve, než jsou potřeba není doporučený postup. Visual Studio 2015 zaveden koncept založeného na pravidlech kontextů uživatelského rozhraní, mechanismus, který umožňuje autorům rozšíření zadat přesné podmínky, za které se aktivuje kontextu uživatelského rozhraní a přidružené VSPackages načíst.  
  
## <a name="rule-based-ui-context"></a>Kontext založený na pravidlech uživatelského rozhraní  
 "Pravidlo" se skládá z nový kontext uživatelského rozhraní (GUID) a logický výraz, který odkazuje na jeden nebo více "podmínky" kombinovat s logické "a", "nebo", "Ne" operace. "Podmínky" vyhodnocují dynamicky za běhu a výraz se znovu zhodnotí vždy, když některý z jeho podmínky změny. Pokud výraz vyhodnotí jako true, je aktivována kontext přidružený uživatelského rozhraní. Kontext uživatelského rozhraní, jinak je deaktivován.  
  
 Pravidla na základě kontextu uživatelského rozhraní lze použít v mnoha různými způsoby:  
  
1.  Zadejte omezení viditelnosti pro příkazy a nástroje systému windows. Příkazy nebo nástroje windows můžete skrýt, dokud nebude splněna pravidla kontextu uživatelského rozhraní.  
  
2.  Jako automatické omezení zatížení: Automatické načítání balíčků jenom v případě, že při splnění pravidla  
  
3.  Zpožděné úloh: zpoždění načítání, dokud neuplyne o zadaný interval a pravidlo je stále splněna.  
  
 Tento mechanismus, může být používán rozšíření Visual Studia.  
  
## <a name="create-a-rule-based-ui-context"></a>Vytvoření kontextu založený na pravidlech uživatelského rozhraní  
 Předpokládejme, že máte rozšíření názvem TestPackage, který nabízí příkazu v nabídce, která se vztahuje pouze na soubory s příponou ".config". Před VS2015, nejlepší možnost byl načíst TestPackage při <xref:Microsoft.VisualStudio.Shell.KnownUIContexts.SolutionExistsAndFullyLoadedContext%2A> aktivovala kontextu uživatelského rozhraní. Toto není efektivní, protože načíst řešení nesmí obsahovat i soubor .config. Dejte nám naleznete v kontextu založeného na pravidlech uživatelského rozhraní lze aktivovat pouze v případě, že soubor s příponou .config kontextu uživatelského rozhraní je vybrána a způsob načíst TestPackage při aktivaci tohoto kontextu uživatelského rozhraní.  
  
1.  Zadejte nový identifikátor GUID UIContext a přidejte do třídy VSPackage <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> a <xref:Microsoft.VisualStudio.Shell.ProvideUIContextRuleAttribute>.  
  
     Předpokládejme například, nové UIContext "UIContextGuid" má být přidán. Vytvořit identifikátor GUID (identifikátor GUID můžete vytvořit kliknutím na Nástroje -> vytvořit guid) je "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B". Pak přidejte následující uvnitř vaší třídy balíčku:  
  
    ```csharp  
    public const string UIContextGuid = "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B";  
    ```  
  
     Pro atributy, přidejte následující: (podrobnosti o těchto atributů bude vysvětleno později)  
  
    ```csharp  
    [ProvideAutoLoad(TestPackage.UIContextGuid)]      
    [ProvideUIContextRule(TestPackage.UIContextGuid,  
        name: "Test auto load",   
        expression: "DotConfig",  
        termNames: new[] { "DotConfig" },  
        termValues: new[] { "HierSingleSelectionName:.config$" })]  
    ```  
  
     Tato metadata definovat nový identifikátor GUID UIContext (8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B) a výraz odkazující na jeden termín "DotConfig". Termín "DotConfig" vyhodnotí jako true, vždy, když aktuální výběr v aktivní hierarchie má název, který odpovídá regulární výraz "\\.config$" (končí textem ".config"). (Výchozí) definuje nepovinný název pro toto pravidlo, které jsou užitečné pro ladění.  
  
     Hodnoty atributu se přidají do pkgdef vygenerovaných během okamžiku sestavení později.  
  
2.  V souboru VSCT pro příkazy TestPackage přidejte příznak "DynamicVisibility" příslušnými příkazy:  
  
    ```xml  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
3.  V části Visibilities VSCT tie příslušné příkazy, které nové UIContext GUID definované v #1:  
  
    ```xml  
    <VisibilityConstraints>   
        <VisibilityItem guid="guidTestPackageCmdSet" id="TestId"  context="guidTestUIContext"/>   
    </VisibilityConstraints>  
    ```  
  
4.  V části symboly přidejte definici UIContext:  
  
    ```xml  
    <GuidSymbol name="guidTestUIContext" value="{8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B}" />  
    ```  
  
     Příkazy nabídky kontext pro soubory *.config nyní, se nebude zobrazovat jenom v případě, že vybrané položky v Průzkumníku řešení je soubor ".config" a balíčku nebudou načteny, dokud vybrané je jedno z těchto příkazů.  
  
 V dalším kroku použijeme ladicí program k potvrzení, že balíček načte, pouze když Očekáváme, že jej do. Chcete-li ladit TestPackage:  
  
1.  Nastavte zarážky v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
  
2.  Sestavení TestPackage a spusťte ladění.  
  
3.  Vytvoření projektu nebo otevřete ho.  
  
4.  Vyberte všechny soubory s příponou, než .config. Zarážce nesmí přístupů.  
  
5.  Vyberte soubor App.Config.  
  
 TestPackage načte a zastaví u zarážky.  
  
## <a name="adding-more-rules-for-ui-context"></a>Přidání další pravidla pro kontext uživatelského rozhraní  
 Vzhledem k tomu, že pravidla kontextu uživatelského rozhraní jsou logické výrazy, můžete přidat omezenější pravidla pro kontext uživatelského rozhraní. Například v rámci výše uvedené uživatelské rozhraní, můžete zadat, že pravidlo platí, pouze když je načten řešení s projektem. Tímto způsobem příkazy nebude zobrazen Pokud můžete otevřít soubor ".config" jako samostatný soubor, nikoli jako součást projektu.  
  
```csharp  
[ProvideAutoLoad(TestPackage.UIContextGuid)]      
[ProvideUIContextRule(TestPackage.UIContextGuid,    
    name: "Test auto load",  
    expression: "(SingleProject | MultipleProjects) & DotConfig",    
    termNames: new[] { "SingleProject", "MultipleProjects","DotConfig" },     
    termValues: new[] { VSConstants.UICONTEXT_SolutionHasSingleProject_string , VSConstants.UICONTEXT_SolutionHasMultipleProjects_string , "HierSingleSelectionName:.config$" })]  
```  
  
 Nyní výraz odkazuje na tři podmínky. První dvě podmínky, "SingleProject" a "MultipleProjects", naleznete v jiných kontextech dobře známé uživatelské rozhraní (podle identifikátorů GUID). Třetí termín "DotConfig" je založený na pravidlech uživatelského rozhraní kontext definovaného dříve.  
  
## <a name="delayed-activation"></a>Odloženou aktivaci  
 Pravidla může mít volitelné "zpoždění". Zpoždění je zadána v milisekundách. Pokud je k dispozici, způsobí zpoždění aktivace nebo deaktivace kontextu uživatelského rozhraní pravidla k zpožděn tento časový interval. Pokud pravidlo změn zpět před interval prodlevy, pak nic nestane. Tento mechanismus lze "rozložte" kroků inicializace - zejména jednorázové inicializace bez spoléhání na časovače nebo registrace nečinnosti oznámení.  
  
 Můžete například určit pravidla zatížení testovací tak, aby měl zpoždění 100 milisekund:  
  
```csharp  
[ProvideAutoLoad(TestPackage.UIContextGuid)]  
[ProvideUIContextRule(TestPackage.UIContextGuid,   
    name: "Test auto load",  
    expression: "DotConfig",   
    termNames: new[] { "DotConfig" },  
    termValues: new[] { "HierSingleSelectionName:.config$" },   
    delay: 100)]  
```  
  
## <a name="term-types"></a>Typy podmínek  
 Zde jsou různé typy podmínek, které jsou podporovány:  
  
|||  
|-|-|  
|{nnnnnnnn-nnnn-nnnn-nnnn-nnnnnnnnnnnn}|Identifikátor GUID odkazuje na kontext uživatelského rozhraní. Termín bude mít hodnotu true, vždy, když kontext uživatelského rozhraní v opačném případě je aktivní a false.|  
|HierSingleSelectionName:\<vzor >|Termín bude mít hodnotu true, vždy, když je výběr v hierarchii active jednu položku a název vybrané položky odpovídající regulární výraz platformy .net poskytují "vzor".|  
|UserSettingsStoreQuery:\<dotaz >|"dotaz" představuje úplnou cestu do úložiště uživatelských nastavení, které se musí vyhodnotit na hodnotu nula. Dotaz je rozdělená do "kolekce" a "propertyName" v poslední lomítko.|  
|ConfigSettingsStoreQuery:\<dotaz >|"dotaz" představuje úplnou cestu do úložiště nastavení konfigurace, které se musí vyhodnotit na hodnotu nula. Dotaz je rozdělená do "kolekce" a "propertyName" v poslední lomítko.|  
|ActiveProjectFlavor:\<projectTypeGuid >|Termín bude hodnotu true, vždy, když je specifického pro aktuálně vybrané projektu (agregovat) a má příchuť, odpovídající daný projekt typu GUID.|  
|ActiveEditorContentType:\<contentType >|Termín bude true, pokud je vybraný dokument s daným typem obsahu textového editoru.|  
|ActiveProjectCapability:\<výraz >|Výraz hodnotu true, když funkce aktivního projektu odpovídá zadaného výrazu. Výraz může být něco jako VB &#124; CSharp|  
|SolutionHasProjectCapability:\<výraz >|Podobá se výše, ale výraz hodnotu true při řešení má všechny načíst projekt, který odpovídá výrazu.|  
|SolutionHasProjectFlavor:\<projectTypeGuid >|Termín bude mít hodnotu true, vždy, když má projekt, který je specifického (agregovat) řešení a příchuť, odpovídající daný projekt typu GUID.|


  
## <a name="compatibility-with-cross-version-extension"></a>Kompatibilita s příponou napříč verzemi  
 Pravidla na základě kontexty uživatelského rozhraní je nová funkce v sadě Visual Studio 2015 a nebude přesně do starší verze. Vytvoří se tím problém s rozšíření nebo balíčky, které cílení na více verzí sady Visual Studio, který by mohl být automaticky načíst v sadě Visual Studio 2013 a starší, ale může využívat založený na pravidlech uživatelského rozhraní kontexty aby auto načítá ve Visual Studiu 2015.  
  
 Za účelem podpory těchto balíčků, teď AutoLoadPackages položky v registru můžete zadat příznak v jeho poli hodnotu indikující, že se má položka v sadě Visual Studio 2015 a vyšší přeskočit. To lze provést tak, že přidáte příznaky možnost <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags>. Nyní můžete přidat VSPackages **SkipWhenUIContextRulesActive** možnost k jejich <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> atribut k označení položka třeba ji ignorovat v sadě Visual Studio 2015 a novější.  
  
## <a name="extensible-ui-context-rules"></a>Pravidla pro kontext Extensible uživatelského rozhraní  
 V některých případech balíčky nelze použít statická pravidla kontextu uživatelského rozhraní. Předpokládejme například, že máte podporu rozšiřitelnosti, tak, že stav příkazu je založena na editor typů, které jsou podporovány zprostředkovateli MEF importované balíček. Příkaz je povoleno, pokud je podpora aktuální upravit typ rozšíření. V takových případech samotného balíčku nelze statické kontextu uživatelského rozhraní pravidlo použít, protože podmínky změní v závislosti na tom, které MEF jsou dostupná rozšíření.  
  
 Aby bylo možné podporovat tyto balíčky, kontexty založený na pravidlech uživatelského rozhraní podporují výraz pevně zakódované "*" určující všechny níže uvedené podmínky se má propojit s nebo. To umožňuje pro hlavní balíček, který chcete definovat známé pravidla na základě kontextu uživatelského rozhraní a tie jeho stav příkazu k tomuto kontextu. Později můžete přidat jakékoli MEF rozšíření určeno pro hlavní balíček jeho podmínky pro editory, kterou podporuje bez vlivu na jiné podmínky nebo výraz, který hlavní.  
  
 Konstruktor <xref:Microsoft.VisualStudio.Shell.ProvideExtensibleUIContextRuleAttribute.%23ctor%2A> dokumentace ukazuje syntaxi pro extensible pravidla kontextu uživatelského rozhraní.