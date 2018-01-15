---
title: Soubor DslDefinition.dsl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, definition file
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c58dc30285257a8292e8ce8dcf81b7b31cfee2c5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="the-dsldefinitiondsl-file"></a>Soubor DslDefinition.dsl
Toto téma popisuje strukturu souboru DslDefinition.dsl v projektu Dsl [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] řešení, který definuje *jazyka domény*. Soubor DslDefinition.dsl popisuje třídy a vztahy jazyka specifické pro doménu, společně s diagramu, tvarů, konektory, formát serializace a **sada nástrojů** jazyka specifické pro doménu a jeho Nástroje pro úpravy. V řešení jazyka domény je generována kód, který definuje tyto nástroje podle informací v souboru DslDefinition.dsl.  
  
 Obecně platí, použijte *specifické pro doménu jazyk Návrhář* upravit soubor DslDefinition.dsl. Ale je jeho základním formátu XML a můžete otevřít soubor DslDefinition.dsl v editoru XML. Vám může být vhodné pochopit, jaké informace soubor obsahuje a způsobu jejich organizace pro účely ladění a rozšíření.  
  
 Příklady v tomto tématu jsou převzaty ze šablony Diagram komponent řešení. Pokud chcete zobrazit příklad, vytvořte jazyka domény řešení, které je založený na šabloně modely součást řešení. Po vytvoření řešení soubor DslDefinition.dsl se zobrazí v Návrháři jazyk specifické pro doménu. Zavřete soubor, klikněte pravým tlačítkem v **Průzkumníku řešení**, přejděte na příkaz **otevřít v**, klikněte na tlačítko **editoru XML**a potom klikněte na **OK**.  
  
## <a name="sections-of-the-dsldefinitiondsl-file"></a>Části souboru DslDefinition.dsl  
 Kořenový element \<Dsl > a jeho atributy identifikovat název jazyka specifické pro doménu, obor názvů, a hlavní verze a podverze čísla pro správu verzí. `DslDefinitionModel` Schéma definuje obsah a strukturu pro platný soubor DslDefinition.dsl.  
  
 Podřízených elementů \<Dsl > kořenový element jsou následující:  
  
 Třídy  
 Tento oddíl definuje každé domény třídu, která generuje třídu v generovaného kódu.  
  
 Relace  
 Tento oddíl definuje každý vztah v modelu. Zdroj a cíl představují sociálními relace.  
  
 Typy  
 Tento oddíl definuje každý typ a jeho oboru názvů. Vlastnosti domény mají dva typy. `DomainEnumerations`jsou definované v modelu a generovat typy do DomainModel.cs. `ExternalTypes`odkazovat na typy, které jsou definovány jinde (například `String` nebo `Int32`) a není nic generování.  
  
 Obrazce  
 Tento oddíl definuje tvarů, které popisují, jak se zobrazí v Návrháři modelu. Tyto geometrické obrazce jsou namapované na třídy v modelu v části diagramu.  
  
 Konektory  
 Tento oddíl definuje vzhled konektory, které se zobrazí v návrháři. Tyto popisy geometrickou styl jsou namapované na specifické vztahy v modelu v části diagramu.  
  
 XmlSerializationBehavior  
 Tato část definuje schéma serializace a poskytuje další informace o tom, jak je každá třída uloží do souboru.  
  
 ExplorerBehavior  
 Tento oddíl definuje jak **DSL Explorer** okno se zobrazí, když uživatel upravuje modelu.  
  
 ConnectionBuilders  
 Tento oddíl definuje Tvůrce připojení pro každý nástroj connector (nástroj pro vytváření odkazů mezi jakékoli dvě třídy, který může být připojen). V této části určuje, zda se můžete připojit zdrojové a cílové třídy.  
  
 diagram  
 Tento oddíl definuje diagram a použilo ji k určení vlastností, jako je například barva pozadí a kořenová třída. (Kořenová třída je domény třída, která je reprezentována diagram jako celek.) Diagram část také obsahuje ShapeMap a ConnectorMap elementy, které určují tvar nebo konektor, který představuje každé domény třídu nebo vztah.  
  
 Návrhář  
 Tento oddíl definuje návrháře (editor), který spojuje **sada nástrojů**, nastavení ověřování, diagram a schéma serializace. V části Návrhář také definuje kořenová třída modelu, který je obvykle také kořenová třída diagramu.  
  
 Průzkumník  
 Tato část popisuje **DSL Explorer** chování (definovanou v části XmlSerializationBehavior).  
  
## <a name="monikers-in-the-dsldefinitiondsl-file"></a>Zástupných názvů v souboru DslDefinition.dsl  
 V celém souboru DslDefinition.dsl můžete monikery aby křížové odkazy na konkrétní položky. Například každý vztah definice obsahuje část zdroj a cíl část. Každý dílčí část obsahuje Přezdívka třídy objektu, který může být propojený s relace:  
  
```  
<DomainRelationship ...        Name="LibraryHasMembers" Namespace="ExampleNamespace" >    <Source>      <DomainRole ...>  
       <RolePlayer>  
         <DomainClassMoniker Name="Library" />  
       </RolePlayer>  
     </DomainRole>  
   </Source>  
```  
  
 Obvykle, obor názvů odkazovaná položka (v tomto příkladu `Library` domény třída) je stejný jako odkazující položky (v tomto případě relace LibraryHasMembers domény). V takových případech musí dát moniker jenom název třídy. Jinak měli byste použít /Namespace/Name úplný formát:  
  
```  
  
<DomainClassMoniker Name="/ExampleNameSpace/Library" />  
  
```  
  
 Přezdívka systému vyžaduje stejné úrovně ve stromové struktuře XML jedinečné názvy. Z tohoto důvodu chyby ověření dojít, když budete chtít uložit definici jazyka domény, který má například dvě třídy se stejným názvem. Vždy byste měli napravit takové chyby duplicitní název před uložením souboru DslDefinition.dsl tak, aby můžete znovu načíst správně později.  
  
 Každý typ má svůj vlastní typ Přezdívka: DomainClassMoniker, DomainRelationshipMoniker, a tak dále.  
  
## <a name="types"></a>Typy  
 V části typy Určuje všechny typy, které obsahuje soubor DslDefinition.dsl jako typy vlastností. Tyto typy spadají do dva typy: externí typy, jako je například System.String a výčtové typy.  
  
### <a name="external-types"></a>Externí typy  
 Příklad diagramu součást obsahuje sadu standardní primitivní typy, i když se používají jenom některé z nich.  
  
 Každý typ externího definice se skládá z jenom název a obor názvů, jako je například řetězec a systému:  
  
```  
<ExternalType Name="String" Namespace="System" />  
```  
  
 Úplné názvy typů se používají místo ekvivalentní kompilátoru klíčová slova jako je například "řetězec".  
  
 Externí typy nejsou omezeny na typy standardní knihovny.  
  
### <a name="enumerations"></a>Výčty  
 Typické specifikace výčtu vypadá takto: v tomto příkladu:  
  
```  
<DomainEnumeration IsFlags="true" Name="PageSort"          Namespace="Fabrikam.Wizard">  
  <Literals>  
    <EnumerationLiteral Name="Start" Value="1"/>  
    <EnumerationLiteral Name="Decision" Value="2"/>  
  </Literals>  
</DomainEnumeration>  
```  
  
 `IsFlags` Atribut ovládací prvky, zda je generovaný kód předponu `[Flags]` atribut Common Language Runtime (CLR), který určuje, zda hodnoty výčtu, mohou být kombinovány bitový. Pokud tento atribut je nastaven na hodnotu true, musíte zadat power dvě hodnoty pro literálových hodnot.  
  
## <a name="classes"></a>Třídy  
 Většina elementů v žádné definice jazyka domény jsou buď přímo nebo nepřímo instancí `DomainClass`. Měly podtřídy `DomainClass` zahrnují `DomainRelationship`, `Shape`, `Connector`, a `Diagram`. `Classes` Oddílu DslDefinition.dsl souboru je uveden seznam tříd domény.  
  
 Každá třída má sadu vlastností a může mít základní třídu. V příkladu Diagram komponent `NamedElement` je abstraktní třída, která má `Name` vlastnost, jejichž typ je řetězec:  
  
```  
<DomainClass Id="ee3161ca-2818-42c8-b522-88f50fc72de8"  Name="NamedElement" Namespace="Fabrikam.CmptDsl5"      DisplayName="Named Element"  InheritanceModifier="Abstract">  
  <Properties>  
    <DomainProperty Id="ef553cf0-33b5-4e34-a30b-cfcfd86f2261"   Name="Name" DisplayName="Name"  DefaultValue="" Category="" IsElementName="true">  
      <Type>  
        <ExternalTypeMoniker Name="/System/String" />  
      </Type>  
    </DomainProperty>  
  </Properties>  
</DomainClass>  
```  
  
 `NamedElement`je základem řadu jiné třídy, jako `Component`, která má své vlastní vlastnosti kromě `Name` vlastnosti, která je zděděn od `NamedElement`. Baseclass – podřízený uzel obsahuje odkaz na přezdívka. Protože odkazovaná třídy se o stejný obor názvů, je vyžadován pouze jeho název v Přezdívka:  
  
```  
<DomainClass Name="Component" Namespace="Fabrikam.CmptDsl5"              DisplayName="Component">  
  <BaseClass>  
    <DomainClassMoniker Name="NamedElement" />  
  </BaseClass>  
  <Properties>  
    <DomainProperty Name="Kind" DisplayName="Kind" >  
      <Type>  
        <ExternalTypeMoniker Name="/System/String" />  
      </Type>  
    </DomainProperty>  
  </Properties>  
```  
  
 Každá třída domény (včetně relace, tvarů, konektory a diagramy) může mít tyto atributy a jeho podřízené uzly:  
  
-   **ID.** Tento atribut je identifikátor GUID. Pokud nezadáte hodnotu v souboru, návrháře jazyk specifické pro doménu, vytvoří hodnotu. (V obrázky v tomto dokumentu, tento atribut je obvykle vynechaný ušetřit místo.)  
  
-   **Název a Namespace.** Tyto atributy zadejte název a obor názvů, třídy generovaného kódu. Společně musí být jedinečný v rámci jazyka specifické pro doménu.  
  
-   **InheritanceModifier.** Tento atribut je "abstraktní", "zapečetěné" nebo žádný.  
  
-   **DisplayName.** Tento atribut je název, který se zobrazí v **vlastnosti** okno. Atribut DisplayName může obsahovat mezery a jiné interpunkční znaménko.  
  
-   **GeneratesDoubleDerived.** Pokud tento atribut je nastaven na hodnotu true, jsou generovány dvě třídy a jedna je podtřídou třídy dalších. Všechny vygenerované metody jsou v základní a konstruktorů jsou v podtřídy. Nastavením tohoto atributu můžete přepsat libovolné metody generované v vlastní kód.  
  
-   **HasCustomConstructor**. Pokud tento atribut je nastaven na hodnotu true, konstruktoru je vynechaný generovaný kód tak, aby bylo možné napsat vlastní verzi.  
  
-   **Atributy**. Tento atribut obsahuje atributy CLR generované třídy.  
  
-   **Baseclass –**. Pokud zadáte základní třídu, musí být stejného typu. Například třídu domény musí mít jinou třídu domény jako jeho základní a prostoru pro obrazce musí mít tvar prostředí. Pokud nezadáte základní třídu, třída v generovaný kód je odvozena od třídy standardní framework. Například domény třída odvozená z `ModelElement`.  
  
-   **Vlastnosti**. Tento atribut obsahuje vlastnosti, které se udržuje v rámci transakce řízení a jako trvalý, když je uložen modelu.  
  
-   **ElementMergeDirectives**. Každý element sloučení direktiva Určuje, jak jinou instanci jiné třídy se přidá do instance nadřazené třídy. Později v tomto tématu můžete najít další podrobnosti o – element direktivy sloučení.  
  
-   Třída C# se vygeneruje pro každou doménu třídu, která je uvedena v `Classes` oddílu. V Dsl\GeneratedCode\DomainClasses.cs se generují třídy, C#.  
  
### <a name="properties"></a>Vlastnosti  
 Každou vlastnost domény má název a typ. Název musí být jedinečný v rámci třídy domény a jeho přenositelné základů.  
  
 Typ musí odkazovat na jednu z uvedených v `Types` oddílu. Obecně platí Přezdívka musí obsahovat obor názvů.  
  
```  
<DomainProperty Name="Name" DisplayName="Name"  DefaultValue="" Category="" IsElementName="true">  
  <Type>  
    <ExternalTypeMoniker Name="/System/String" />  
  </Type>  
</DomainProperty>  
```  
  
 Každou vlastnost domény může mít také tyto atributy:  
  
-   **IsBrowsable**. Tento atribut určuje, zda vlastnost se zobrazí v **vlastnosti** okně po kliknutí na objekt nadřazené třídy.  
  
-   **IsUIReadOnly**. Tento atribut určuje, jestli uživatel může změnit vlastnost v **vlastnosti** okno nebo prostřednictvím dekoratéra, ve kterém se zobrazí vlastnosti.  
  
-   **Typ**. Tento atribut lze nastavit na normální, vypočítaná nebo CustomStorage. Pokud tento atribut nastavíte na vypočítaná, je nutné zadat vlastní kód, který určuje hodnotu, a vlastnost bude jen pro čtení. Pokud tento atribut nastavíte na CustomStorage, je nutné zadat kód, který získá i nastaví hodnoty.  
  
-   **IsElementName**. Pokud tento atribut je nastaven na hodnotu true, jeho hodnota se automaticky nastaví na jedinečnou hodnotu při vytvoření instance nadřazené třídy. Tento atribut lze nastavit hodnotu true pro pouze jednu vlastnost v každé třídě, na kterém musí být typu string. V příkladu Diagram komponent `Name` vlastnost `NamedElement` má `IsElementName` nastaven na hodnotu true. Vždy, když uživatel vytvoří `Component` – element (který dědí z `NamedElement`), název je automaticky inicializován na něco podobného jako "Component6."  
  
-   `DefaultValue`. Pokud jste zadali tento atribut, hodnotu, která jste zadali přiřazena tomuto atributu pro nové instance této třídy. Pokud `IsElementName` není nastaven atribut DefaultValue Určuje počáteční součástí nového řetězce.  
  
-   **Kategorie** je záhlaví, pod kterým se zobrazí vlastnosti v **vlastnosti** okno.  
  
## <a name="relationships"></a>Relace  
 `Relationships` Části jsou uvedené všechny vztahy v jazyce specifické pro doménu. Každý `Domain Relationship` je binární a směrovanou propojení členy třídy zdroje pro členy cílové třídy. Zdrojové a cílové třídy jsou obvykle třídy domény, ale jsou také povoleny vztahů s jiné relace.  
  
 Relace připojení například propojí členy třídy OutPort členům InPort třídy. Každá instance odkaz relace připojí k instanci InPort instanci OutPort. Vzhledem k tomu, že je relace m: n, každý OutPort může mít řadu odkazů připojení s zdroje a každá instance InPort může mít řadu odkazů připojení, které na ni cílit.  
  
### <a name="source-and-target-roles"></a>Zdrojové a cílové role  
 Každý vztah obsahuje zdrojové a cílové role, které mají následující atributy:  
  
-   `RolePlayer` Atribut odkazuje na třídu domény propojené instancí: OutPort zdroje, InPort pro cíl.  
  
-   `Multiplicity` Atribut má čtyři možné hodnoty (ZeroMany, ZeroOne, jeden a OneMany). Tento atribut označuje počet odkazů na této relace, který může být přidružený jeden player role.  
  
-   `PropertyName` Atribut určuje název, který se používá v roli přehrávání třídy pro přístup k objektům na druhém konci. Tento název se používá v šabloně nebo vlastní kód procházení relace. Například `PropertyName` atribut zdrojovou roli je nastaven na `Targets`. Proto bude fungovat následující kód:  
  
    ```  
    OutPort op = ...; foreach (InPort ip in op.Targets) ...  
    ```  
  
     Podle konvence jsou množném čísle, pokud násobnost ZeroMany nebo OneMany názvů vlastností.  
  
     Násobnosti atributu role odkazuje na kolik opačné role může být přidružen k každou instanci této role. Například v relaci ComponentHasPorts má roli cílový `RolePlayer` atributu na Port, `PropertyName` atributu na komponenty a `Multiplicity` atribut nastaven na ZeroOne. Proto je vhodné kódu pro použití této role:  
  
    ```  
    ComponentPort p = ...; Component c = p.Component; if (c != null) ...  
    ```  
  
-   Role `Name` je název, který se používá v rámci třídy vztah k odkazování na tomto konci propojení. Podle konvence název role je vždy jednotném čísle, protože každý odkaz na obou koncích má pouze jednu instanci. Následující kód pracovat:  
  
    ```  
    Connection connectionLink = ...; OutPort op = connectionLink.Source;  
    ```  
  
-   Ve výchozím nastavení `IsPropertyGenerator` atribut je nastaven na hodnotu true. Pokud je nastavené na hodnotu false, vlastnost se vytvoří na třídě Role Player. (V takovém případě `op.Targets`, například nebude fungovat). Je však stále možné použít vlastní kód pro procházení relace nebo získat přístup k odkazy sami, pokud vlastní kód používá explicitně relace:  
  
    ```  
    OutPort op = ...; foreach (InPort ip in Connection.GetTargets(op)) ...  
    foreach (Connection link in Connection.GetLinksToTargets(op)) ...  
    ```  
  
### <a name="relationship-attributes"></a>Atributy relace  
 Kromě atributy a podřízené uzly, které jsou k dispozici pro všechny třídy má každý vztah tyto atributy:  
  
-   **IsEmbedding**. Tento logický atribut určuje, zda je relace částí vnoření stromu. Každý model musí tvořit stromu s jeho vnoření vztahy. Každá třída domény proto musí být cílem alespoň jeden vnoření relace, pokud je kořenový modelu.  
  
-   **AllowsDuplicates**. Tento logický atribut, který je ve výchozím nastavení hodnotu false, se vztahuje pouze na vztahy, které mají na zdrojovém i cílovém "n" násobnost. Se určuje, zda uživatelé jazyk může připojit jeden dvojice zdrojové a cílové elementy ve více než jeden odkaz stejné relace.  
  
## <a name="designer-and-toolbox-tabs"></a>Návrhář a karty sada nástrojů  
 Hlavní část **Návrhář** část souboru DslDefinition.dsl **ToolboxTab** elementy. Jeden návrhář může mít několik z těchto elementů, z nichž každý představuje zelí oddíl v Návrháři generovaného **sada nástrojů**. Každý **ToolboxTab** element může obsahovat jednu nebo více **ElementTool** elementů **ConnectionTool** elementy nebo obojí.  
  
 Element nástroje můžete vytvořit instance třídy konkrétní doméně. Když uživatel nastavuje tažením nástroj na element do diagramu, výsledek je určen podle elementu sloučení direktivy, jak je popsáno v části o – element direktivy sloučení později v tomto tématu.  
  
 Nástroj pro každé připojení můžete vyvolat konkrétní připojení Tvůrce. Jeden Tvůrce připojení můžete vytvořit více než jeden typ vztahu, v závislosti na tom, kde uživatel klikne na tlačítko myši, jak je popsáno v části o připojení počítačů.  
  
 Ani typ nástroje přímo vytvoří tvarů nebo konektory. Každý vytvoří třídu domény nebo domény vztah; mapování tvar a konektor pak určit, jak se zobrazuje třídy domény nebo domény vztahu.  
  
## <a name="paths"></a>Cesty  
 Domény cesty se zobrazí v několika umístění v souboru DslDefinition.dsl. Tyto cesty zadejte řadu odkazy na jeden element ve model (tedy instance jazyka domény) na jiný. Syntaxe cesty je jednoduchý, ale verbose.  
  
 Cesty se zobrazí v souboru DslDefinition.dsl ve `<DomainPath>...</DomainPath>` značky. I když cesty lze procházet více odkazů, většina příkladů v praxi procházení jenom jeden odkaz.  
  
 Cesta se skládá z pořadí segmentů. Každý segment je směrování z objektu na odkaz nebo odkaz na objekt. Proto přesměrování alternativní obvykle dlouhé cesty. Prvním skoku je z objektu na odkaz, druhé směrování je objekt na druhém konci odkazu, třetí směrování je další odkaz, a tak dále. Příležitostně výjimka, která má toto pořadí je kde vztahu je zdrojová nebo cílová jiné relace.  
  
 Každý segment začíná název vztahu. V směrování propojení objektu relace předchází tečkou a název vlastnosti: "`Relationship . Property`". V objektu propojení hop, relace předchází vykřičník a název role: "`Relationship ! Role`".  
  
 Příklad diagramu součást obsahuje cestu ParentElementPath ShapeMap pro InPort. Tato cesta spustí následujícím způsobem:  
  
```  
    ComponentHasPorts.Component  
```  
  
 V tomto příkladu InPort je podtřídou třídy ComponentPort a má vztah ComponentHasPorts. Vlastnost se nazývá součásti.  
  
 Při zápisu C# pro tento model, můžete přejít přes odkaz v jednom kroku pomocí vlastnosti, která generuje relace na všech tříd, které se vztahuje:  
  
```  
     InPort port; ...  Component c = port.Component;  
```  
  
 Ale je potřeba udělat i směrování explicitně v cestě syntaxi. Kvůli tomuto požadavku můžete snadno přístup k zprostředkující odkazu. Následující kód dokončení přechodu z odkazu na komponentu:  
  
```  
    ComponentHasPorts.Component / ! Component  
```  
  
 (Název vztahu tam, kde je stejný jako předchozí segment můžete vynechat.)  
  
## <a name="element-merge-directives"></a>Merge – element direktivy jazyka  
 Pokud jazyk uživatel nastavuje tažením položku z **sada nástrojů** na diagramu je vidět, je vytvořená instance třídy nástroje. Odkazy jsou také k mezi tuto instanci a stávající elementy modelu. Některé položky, jako je například součástí nebo komentáře, vytvářejí, když jazyk uživatel nastavuje tažením je z **sada nástrojů** do prázdné části diagramu. Další položky se vytvoří při jazyk uživatel nastavuje tažením je na další prvky hostitele. Například OutPort nebo InPort se vytvoří při jazyk uživatel nastavuje tažením ho na komponentu.  
  
 Potenciální třída hostitele, jako je třeba komponenta, bude přijímat nového elementu jen tehdy, pokud třída hostitele direktivu element sloučení pro třídu nového elementu. Například DomainClass uzel s názvem = "Component" obsahuje:  
  
```  
<DomainClass Name="Component" ...> ...  
    <ElementMergeDirective>  
      <Index>  
        <DomainClassMoniker Name="ComponentPort" />  
      </Index>  
      <LinkCreationPaths>  
        <DomainPath>ComponentHasPorts.Ports</DomainPath>  
      </LinkCreationPaths>  
    </ElementMergeDirective> ...  
```  
  
 Přezdívka třídy, který je v uzlu Index odkazuje na třídu elementu, který lze zadat. V takovém případě ComponentPort je abstraktní základní třída InPort a OutPort. Proto mohou být přijaty některý z těchto elementů.  
  
 ComponentModel kořenová třída jazyka, má element direktivy sloučení pro součásti a komentáře. Jazyk uživatele můžete přetáhnout položky pro tyto třídy přímo na diagramu, protože prázdné části diagramu představují kořenová třída. ComponentModel však pro ComponentPort nemá žádné sloučení direktivu element. Jazyk uživatele nelze proto přetáhněte InPorts nebo OutPorts přímo do diagramu.  
  
 Sloučení direktivu element určuje, jaké odkaz nebo odkazy jsou vytvořeny tak, aby nového elementu můžete integrovat nebo sloučit do existujícího modelu. Pro ComponentPort bude vytvořena instance ComponentHasPorts. DomainPath relace i pro vlastnost nadřazené třídy, identifikuje porty, do kterých mají být přidány nového elementu.  
  
 Můžete vytvořit více než jeden odkaz na direktivu element sloučení zahrnutím více než jednu cestu pro vytvoření odkazu. Jedna z cest musí být vložený.  
  
 Můžete vytvořit více než jeden segment cesty vytvoření odkazu. V takovém případě poslední segment definuje, jaký odkaz musí být vytvořený. Starší segmenty přejděte od nadřazené třídy objektu, ze kterého by měl být vytvořen nový odkaz.  
  
 Například můžete přidat tato direktiva sloučení element k třídě součásti:  
  
```  
<DomainClass Name="Component" ...> ...  
  <ElementMergeDirective>  
    <Index>  
       <DomainClassMoniker Name="Comment"/>  
    </Index>  
    <LinkCreationPaths>  
       <DomainPath>          ComponentModelHasComponents . ComponentModel / !ComponentModel         / ComponentModelHasComments.Comments       </DomainPath>  
       <DomainPath>CommentsReferenceComponents.Comments</DomainPath>  
    </LinkCreationPaths>  
  </ElementMergeDirective>  
```  
  
 Jazyk uživatelé pak přetáhněte komentář na komponentu a mít nový komentář se zobrazí odkaz na komponentu automaticky vytvoří.  
  
 První vytváření cestu propojení přejde z `Component` k `ComponentModel` a potom vytvoří instanci vnoření relace `ComponentModelHasComments`. Druhý cestu vytvoření propojení vytvoří odkaz referenční vztah CommentsReferenceComponents z hostitele součástí na nový komentář. Všechny cesty k vytvoření propojení musí začínat třída hostitele a musí končit na odkaz tento postup směrem nově vytvořenou instanci třídy.  
  
## <a name="xmlclassdata"></a>XmlClassData  
 Každá třída domény (včetně vztahy a dalších podtypů) může mít doplňující informace, které jsou součástí `XmlClassData` uzlu, který se zobrazí pod `XmlSerializationBehavior` souboru DslDefinition.dsl. Tyto informace zejména se jedná o, jak instancí třídy jsou uložené v serializovaných formuláře při uložení do souboru.  
  
 Velká část vygenerovaného kódu, který `XmlSerializationBehavior` vlivy je v `Dsl\GeneratedCode\Serializer.cs`.  
  
 Každý `XmlClassData` uzel obsahuje tyto podřízené uzly a atributy:  
  
-   Přezdívka uzlu, který odkazuje na třídu, na které se vztahuje data.  
  
-   **XmlPropertyData** pro každou vlastnost, která je definována v třídě.  
  
-   **XmlRelationshipData** pro každý vztah, který může mít původ v třídě. (Vztahy také mít vlastní XmlClassData uzly.)  
  
-   **TypeName** atribut řetězec, který určuje název pomocná třída serializace generovaného kódu.  
  
-   **Vlastnost ElementName** řetězce, který určuje značky XML serializovaných instance této třídy. Podle konvence ElementName je obvykle stejný jako název třídy s výjimkou první písmeno je malá písmena. Například soubor modelu ukázka začíná takto:  
  
    ```  
    <componentModel ...  
    ```  
  
-   **MonikerElementName** v souborech serializovaných modelu uživatele. Tento atribut zavádí přezdívka, který odkazuje na tato třída.  
  
-   **MonikerAttributeName**, který identifikuje název atributu XML v rámci přezdívka. V tomto fragmentu serializovaných souboru uživatele Autor jazyka domény definované **MonikerElementName** jako "inPortMoniker" a **MonikerAttributeName** jako "cesta":  
  
    ```  
    <inPortMoniker path="//Component2/InPort1" />  
    ```  
  
### <a name="connectionbuilders"></a>ConnectionBuilders  
 Tvůrce připojení je definována pro každý nástroj pro připojení. Každý Tvůrce připojení se skládá z jednoho nebo více elementů LinkConnectDirective, z nichž každý obsahuje jeden či více elementů SourceDirective a jeden či více elementů TargetDirective. Po kliknutí na nástroj pro připojení, může uživatel spustit z libovolného tvaru namapované na element modelu, který se zobrazí v seznamu elementů SourceDirective připojení. Připojení se dají udělat pak na tvar, který se mapuje na element, který se zobrazí v seznamu elementů TargetDirective. Třída relace instanci závisí na element LinkConnectDirective určené, které kde byl spuštěn připojení.  
  
### <a name="xmlpropertydata"></a>XmlPropertyData  
 A **DomainPropertyMoniker** atribut určuje vlastnosti, na který odkazuje data. Tento atribut musí být vlastnost třídy nadřazených tříd.  
  
 **XmlName** atribut poskytuje odpovídající název atributu, který se má zobrazit v souboru XML. Podle konvence, tento řetězec je stejný jako název vlastnosti s výjimkou první písmeno je malá písmena.  
  
 Ve výchozím nastavení **reprezentace** je nastavena na hodnotu atributu. Pokud **reprezentace** je nastaven na Element, podřízený uzel je vytvořen v souboru XML. Pokud **reprezentace** je nastavena na hodnotu ignorovat, vlastnost neserializuje.  
  
 **IsMonikerKey** a **IsMonikerQualifier** atributy poskytnout vlastnost roli při identifikaci instance nadřazené třídy. Můžete nastavit **IsMonikerKey** na hodnotu true pro jednu vlastnost, která je definována v nebo zděděna třídou. Tento atribut určuje jednotlivé instance nadřazené třídy. Vlastnost, která můžete nastavit na hodnotu `IsMonikerKey` je obvykle název nebo identifikátor jiné klíče. Například `Name` vlastnosti řetězce je klíč Přezdívka pro NamedElement a jejich odvozené třídy. Když uživatel uloží do souboru modelu, tento atribut musí obsahovat jedinečné hodnoty pro každou instanci, mezi uzly na stejné úrovni ve stromové struktuře vnoření vztahy.  
  
 V souboru serializovaných modelu je úplná Přezdívka elementu cestu z kořene modelu hlouběji ve stromové struktuře vnoření relace s uvedením klíč Přezdívka u každého bodu. Například InPorts jsou vnořené v rámci komponenty, které jsou naopak vložených v kořenu modelu. Platný Přezdívka je proto:  
  
```  
<inPortMoniker name="//Component2/InPort1" />  
```  
  
 Můžete nastavit **IsMonikerQualifier** atribut pro vlastnosti string a poskytují další způsob vytvoření úplný název elementu. Například v souboru DslDefinition.dsl **Namespace** je kvalifikátor přezdívka.  
  
### <a name="xmlrelationshipdata"></a>XmlRelationshipData  
 V rámci soubor serializovaných modelu odkazů (vložení a referenční dokumentace vztahy) představují podřízené uzly zdrojový konec relace. Pro vkládání relace, obsahuje podřízený uzel podstrom. Pro referenční relace obsahuje podřízený uzel přezdívka, který odkazuje na jinou část stromu.  
  
 **XmlRelationshipData** atribut **XmlClassData** atribut definuje, přesně jak vnořené podřízených uzlů v rámci elementu zdroje. Každý vztah, který je zdrojem k třídě domény má jeden **XmlRelationshipData** atribut.  
  
 **DomainRelationshipMoniker** atribut určuje jedné z relací jako zdroj pro třídu.  
  
 **RoleElementName** atribut poskytuje názvu značky XML, která obklopuje podřízený uzel v serializovaných datech.  
  
 Například soubor DslDefinition.dsl obsahuje:  
  
```  
<XmlClassData ElementName="component" ...>  
  <DomainClassMoniker Name="Component" />  
  <ElementData>  
    <XmlRelationshipData RoleElementName="ports">  
      <DomainRelationshipMoniker Name="ComponentHasPorts" />  
    </XmlRelationshipData>  
```  
  
 Proto serializovaných soubor obsahuje:  
  
```  
<component name="Component1"> <!-- parent ->  
   <ports> <!-- role ->  
     <outPort name="OutPort1"> <!-- child element ->  
       ...  
     </outPort>  
   </ports> ...  
```  
  
 Pokud **UseFullForm** je atribut nastaven na hodnotu true, byla zavedená další úrovně vnoření. Tato vrstva představuje vztah sám sebe. Musí být nastaven na hodnotu true, pokud relace má vlastnosti.  
  
```  
<XmlClassData ElementName="outPort">  
   <DomainClassMoniker Name="OutPort" />  
   <ElementData>  
     <XmlRelationshipData UseFullForm="true" RoleElementName="targets">  
       <DomainRelationshipMoniker Name="Connection" />  
     </XmlRelationshipData>  
   </ElementData>  
 </XmlClassData>  
```  
  
 Serializovaná soubor obsahuje:  
  
```  
<outPort name="OutPort1">  <!-- Parent ->  
   <targets>  <!-- role ->  
     <connection sourceRoleName="X">  <!-- relationship link ->  
         <inPortMoniker name="//Component2/InPort1" /> <!-- child ->  
     </connection>  
    </targets>  
  </outPort>  
```  
  
 (Připojení relace má svou vlastní XML třída data, která poskytuje jeho element názvy a atributů.)  
  
 Pokud **OmitElement** atribut je nastaven na hodnotu true, relace je vynechán název role, která zkrátí serializovaných soubor a je jednoznačné, pokud dvě třídy mají více než jeden vztah. Příklad:  
  
```  
<component name="Component3">  
  <!-- only one relationship could get here: ->  
  <outPort name="OutPort1">    
     <targets> ...  
```  
  
### <a name="serialization-of-a-domain-specific-language-definition"></a>Serializace definici jazyka domény  
 Soubor DslDefinition.dsl je samotný soubor serializovaných a vyhovuje definici jazyka domény. Toto jsou některé příklady definice serializace XML:  
  
-   **DSL** je uzlu RootClass a třída diagramu. DomainClass, DomainRelationship a další elementy jsou vloženy pod `Dsl`.  
  
-   **Třídy** je **RoleElementName** vztahu mezi jazyka domény a DomainClass.  
  
```  
<Dsl Name="CmptDsl5" ...>  
  <Classes>  
    <DomainClass Name="NamedElement" InheritanceModifier="Abstract" ...  
```  
  
-   **XmlSerializationBehavior** atribut vložené v části `Dsl` atribut, ale **OmitElement** nastavení atributu v relaci vnoření. Tedy ne `RoleElementName` zasáhla atribut. Naopak **data třídy** atribut je `RoleElementName` atribut vnoření vztah mezi **XmlSerializationBehavior** atribut a **XmlClassData** atribut.  
  
```  
<Dsl Name="CmptDsl5" ...> ...  
  <XmlSerializationBehavior Name="ComponentsSerializationBehavior" >  
    <ClassData>  
      <XmlClassData ...>...</XmlClassData>  
      <XmlClassData ...>...</XmlClassData>  
```  
  
-   ConnectorHasDecorators se vnoření vztah mezi `Connector` a `Decorator`. `UseFullForm`byla nastavena tak, aby název relace se zobrazí s její seznam vlastností pro každý odkaz z objektu konektoru. Ale `OmitElement` má také nastavit tak, aby žádné `RoleElementName` uzavře více odkazů, která jsou vložena do `Connector`:  
  
```  
<Connector Name="AssociationLink" ...>  
  <ConnectorHasDecorators Position="TargetTop" ...>  
    <TextDecorator Name="TargetRoleName"   />  
  </ConnectorHasDecorators>  
  <ConnectorHasDecorators Position="SourceTop" ...>  
    <TextDecorator Name="SourceRoleName"   />  
  </ConnectorHasDecorators>  
</Connector>  
```  
  
## <a name="shapes-and-connectors"></a>Konektory a obrazců  
 Definice tvar a konektor dědí z třídy domény, kromě těchto atributů a jeho podřízené uzly:  
  
-   `Color`a `Line``Style` atributy.  
  
-   **ExposesFillColorAsProperty** a několika atributů, podobně jako. Tyto logické atributy zkontrolujte proměnnou odpovídající vlastnost uživatelem. Obecně platí, když jazyk kliknutí obrazce v diagramu, vlastnosti, zobrazí se v **vlastnosti** okna jsou instance třídy domény, ke které je mapován tvaru. Pokud `ExposesFillColorAsProperty` je nastaven na hodnotu true, vlastnost tvar samotný taky se zobrazí.  
  
-   **ShapeHasDecorators**. Pro každý text, ikona nebo rozbalit nebo sbalit dekoratéra dojde k instanci tohoto atributu. (V souboru DslDefinition.dsl `ShapeHasDecorators` je vztah s `UseFullForm` nastaven na hodnotu true.)  
  
## <a name="shape-maps"></a>Obrazce mapy  
 Obrazce mapy určit, jak zobrazit instance třídy dané domény na obrazovce reprezentována obrazce. Konektor i tvar mapy vyskytovat v části `Diagram` oddílu DslDefinition.dsl souboru.  
  
 Jako v následujícím příkladu `ShapeMap` prvky mít, minimálně, přezdívka třídy domény, přezdívka obrazce a `ParentElementPath` element:  
  
```  
<ShapeMap>  
  <DomainClassMoniker Name="InPort" />  
  <ParentElementPath>  
    <DomainPath>ComponentHasPorts.Component/!Component</DomainPath>  
  </ParentElementPath>  
  <PortMoniker Name="InPortShape" />  
</ShapeMap>  
```  
  
 Primární funkce `ParentElementPath` element je tak, aby stejnou třídu objektů, může se objevit jako jiný obrazce v různých kontextech. Například pokud `InPort` může také vložit komentář, `InPort` může zobrazovat jako jiné obrazce k tomuto účelu.  
  
 Za druhé cesta Určuje, jak se tvar, který má vztah k nadřazené. Bez vnoření struktura je definována mezi tvary v souboru DslDefinition.dsl. Musí odvodit strukturu z obrazce mapy. Nadřazený obrazce je obrazec, který se mapuje na element domény, který identifikuje nadřazenou cestu elementu. V takovém případě cesta identifikuje komponentu, ke kterému `InPort` patří. Třídy součástí jiné obrazce mapy, se mapují na ComponentShape. Proto nové `InPort` tvar přišla podřízenou tvar jeho součásti `ComponentShape`.  
  
 Pokud přiřazena InPort tvaru diagram místo, nadřazená cesta element by nutné provést další krok k model komponent, která se mapuje na diagramu:  
  
```  
ComponentHasPorts . Component / ! Component /    ComponentModelHasComponents . ComponentModel / ! ComponentModel  
```  
  
 Kořen modelu nemá obrazce mapy. Místo toho se kořenové odkazuje přímo z diagram, který má `Class` element:  
  
```  
<Diagram Name="ComponentDiagram" >  
    <Class>  
      <DomainClassMoniker Name="ComponentModel" />  
    </Class>...  
```  
  
### <a name="decorator-maps"></a>Dekoratéra mapy  
 Mapa dekoratéra přidruží vlastnosti ve třídě namapované na dekoratéra v tvaru. Pokud je vlastnost typu Boolean nebo výčtové, jeho hodnota může určit, zda je dekoratéra viditelné. Pokud dekoratéra je text dekoratéra, hodnota vlastnosti se může zobrazit, a uživatel ho můžete upravit.  
  
### <a name="compartment-shape-maps"></a>Prostředí obrazce mapy  
 Obrazce mapy prostředí jsou podtypů obrazce mapy.  
  
## <a name="connector-maps"></a>Konektor mapy  
 Minimální konektor mapy odkazuje konektor a relace:  
  
```  
<ConnectorMap>  
  <ConnectorMoniker Name="CommentLink" />  
  <DomainRelationshipMoniker Name="CommentsReferenceComponents" />  
</ConnectorMap>  
```  
  
 Konektor maps může také obsahovat dekoratéra mapy.  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md)   
 [Porozumění modelům, třídám a vztahům](../modeling/understanding-models-classes-and-relationships.md)