---
title: Jak přidat VSPackages prvky uživatelského rozhraní | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, adding elements
- UI element design [Visual Studio SDK], VSPackages
- VSPackages, contributing UI elements
ms.assetid: abc5d9d9-b267-48a1-92ad-75fbf2f4c1b9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 930ab9e741b2fd5bbc0ca2954192fe5e2c4313d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-vspackages-add-user-interface-elements"></a>Jak přidat VSPackages prvky uživatelského rozhraní
VSPackage můžete přidávat prvky uživatelského rozhraní (UI, například nabídky panely nástrojů) a nástroje systému windows pro Visual Studio prostřednictvím .vsct souboru.  
  
 Můžete najít pokynů pro návrh pro prvky uživatelského rozhraní v [Visual Studio prostředí pro práci uživatelů](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
## <a name="the-visual-studio-command-table-architecture"></a>Architektura sady Visual Studio příkaz tabulky  
 Jak jsme uvedli, podporuje architekturu tabulky příkaz uvedenou architektury zásady. Principů za abstrakce, datové struktury a nástroje architektury tabulka příkazu jsou následující:  
  
-   Existují tři základní typy položek: nabídky, příkazy a skupiny. Nabídky mohou být zpřístupněny v uživatelském rozhraní jako nabídky dílčích, panely nástrojů nebo nástroje systému windows. Příkazy jsou postupy, které uživatel může spustit v prostředí IDE, a mohou být zpřístupněny jako položky nabídky, tlačítek, seznamy nebo další ovládací prvky. Skupiny jsou kontejnery pro nabídek a příkazů.  
  
-   Každá položka je určena definicí, která popisuje položky, jeho prioritu relativně k dalším položkám a příznaky, které mění své chování.  
  
-   Každá položka má umístění, která popisuje nadřazené položky. Položka může mít několik nadřazených objektů, tak, aby se může objevit v několika umístěních v uživatelském rozhraní.  
  
     Každý příkaz musí mít skupinu jako jeho nadřazeným prvkem, i když je jediným podřízeným v této skupině. Každé standardní nabídky musí také mít nadřazenou skupinu. Panely nástrojů a nástroje systému windows fungovat jako vlastní nadřazené položky. Skupina může mít jako nadřazené hlavní nabídce sady Visual Studio, nebo všechny nabídky, panelu nástrojů nebo okno nástroje.  
  
### <a name="how-items-are-defined"></a>Jak jsou definovány položky  
 . Vsct soubory jsou ve formátu XML. Soubor .vsct definuje prvky uživatelského rozhraní pro balíček a určuje, kde se zobrazí tyto prvky v prostředí IDE. Všechny nabídky, skupinu nebo příkaz v balíčku poprvé přiřazen GUID a ID v `Symbols` oddílu. Po celý zbytek .vsct soubor, každou nabídku, příkaz a skupiny je určen kombinací GUID a ID. Následující příklad ukazuje typické `Symbols` části generovaná balíček šablonou Visual Studio při **příkaz nabídky** je vybraný v šabloně.  
  
```xml  
<Symbols>  
  <!-- This is the package guid. -->  
  <GuidSymbol name="guidMenuTextPkg" value="{b1253bc6-d266-402b-89e7-5e3d3b22c746}" />  
  
  <!-- This is the guid used to group the menu commands together -->  
  <GuidSymbol name="guidMenuTextCmdSet" value="{a633d4e4-6c65-4436-a138-1abeba7c9a69}">  
  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
  </GuidSymbol>  
  
  <GuidSymbol name="guidImages" value="{53323d9a-972d-4671-bb5b-9e418480922f}" >  
    <IDSymbol name="bmpPic1" value="1" />  
    <IDSymbol name="bmpPic2" value="2" />  
    <IDSymbol name="bmpPicSearch" value="3" />  
    <IDSymbol name="bmpPicX" value="4" />  
    <IDSymbol name="bmpPicArrows" value="5" />  
  </GuidSymbol>  
</Symbols>  
```  
  
 Element nejvyšší úrovně z `Symbols` je oddíl [GuidSymbol Element](../../extensibility/guidsymbol-element.md). `GuidSymbol` Elementy mapování názvů pro identifikátory GUID, které používají rozhraní IDE pro identifikaci balíčky a jejich části.  
  
> [!NOTE]
>  Identifikátory GUID automaticky generované šabloně balíček Visual Studio. Kliknutím můžete také vytvořit jedinečný identifikátor GUID **vytvořit GUID** na **nástroje** nabídky.  
  
 První `GuidSymbol` elementu "guid [název balíčku] Pkg", je identifikátor GUID balíčku sám sebe. Toto je identifikátor GUID, který je používán Visual Studio načíst balíček. Nemá obvykle podřízené elementy.  
  
 Podle konvence, nabídek a příkazů jsou seskupené v rámci druhý `GuidSymbol` elementu "guid [název balíčku] CmdSet", a jsou v části třetí `GuidSymbol` element, "guidImages". Není nutné postupovat podle touto konvencí, ale každý nabídky, skupiny, příkaz a rastrový obrázek musí být podřízenou `GuidSymbol` elementu.  
  
 Ve druhém `GuidSymbol` element, který představuje sadu příkazů nástroje balíčku, je několik `IDSymbol` elementy. Každý [IDSymbol Element](../../extensibility/idsymbol-element.md) mapuje název na číselnou hodnotu a může představovat nabídky, skupinu nebo příkaz, který je součástí sadu příkazů. `IDSymbol` Elementů ve třetí `GuidSymbol` bitmap představují element, který se dá použít jako ikony pro příkazy. Protože dvojice GUID nebo ID musí být jedinečný v aplikaci, žádné dva podřízené objekty na stejné `GuidSymbol` element může mít stejnou hodnotu.  
  
### <a name="menus-groups-and-commands"></a>Nabídky, skupiny a příkazy  
 Když nabídky, skupinu nebo příkaz obsahuje GUID a ID, můžete ho přidat do prostředí IDE. Každý element uživatelského rozhraní musí mít následující akce:  
  
-   A `guid` atribut, který odpovídá názvu `GuidSymbol` element definovaný v rámci elementu uživatelského rozhraní.  
  
-   `id` Atribut, který odpovídá názvu přidruženého `IDSymbol` elementu.  
  
     Společně `guid` a `id` tvoří atributy *podpis* prvku uživatelského rozhraní.  
  
-   A `priority` atribut, který určuje umístění prvku uživatelského rozhraní v jeho nadřazený nabídky nebo skupině.  
  
-   A [nadřazený Element](../../extensibility/parent-element.md) s `guid` a `id` atributy, které určují podpis nadřazené nabídky nebo skupiny.  
  
#### <a name="menus"></a>Nabídky  
 Jednotlivé nabídky je definován jako [Menu Element](../../extensibility/menu-element.md) v `Menus` oddílu. Nabídky musí mít `guid`, `id`, a `priority` atributů a `Parent` elementu a také následující další atributy a podřízené položky:  
  
-   A `type` atribut, který určuje, zda se má v nabídce Zobrazit v integrovaném vývojovém prostředí jako typ nabídky nebo panelu nástrojů.  
  
-   A [řetězce Element](../../extensibility/strings-element.md) obsahující [ButtonText Element](../../extensibility/buttontext-element.md), která určuje název v nabídce v prostředí IDE a [CommandName Element](../../extensibility/commandname-element.md), která určuje název, který je používány **příkaz** okna pro přístup k nabídce.  
  
-   Volitelné příznaky. A [Element Command příznak](../../extensibility/command-flag-element.md) se mohou objevit v nabídce definice změnit jeho vzhled a chování v prostředí IDE.  
  
 Každý `Menu` element musí mít skupinu jako jeho nadřazeným prvkem, pokud je element lze ukotvit například panelu nástrojů. Lze ukotvit nabídka je vlastní nadřazený objekt. Další informace o nabídky a hodnoty `type` atributů najdete v tématu [Menu Element](../../extensibility/menu-element.md) dokumentaci.  
  
 Následující příklad ukazuje nabídky, který se zobrazí na panelu nabídek Visual Studio vedle **nástroje** nabídky.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet"  
id="TopLevelMenu" priority="0x700" type="Menu">  
  <Parent guid="guidSHLMainMenu"  
          id="IDG_VS_MM_TOOLSADDINS" />  
  <Strings>  
    <ButtonText>TestMenu</ButtonText>  
    <CommandName>TestMenu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="groups"></a>Skupiny  
 Skupina je položku, která je definována v `Groups` oddílu .vsct souboru. Skupiny jsou jenom kontejnery. Že se nezobrazí v integrovaném vývojovém prostředí s výjimkou jako dělicí čáru v nabídce. Proto [skupinového elementu](../../extensibility/group-element.md) je definována pouze jeho podpis, prioritu a nadřazené.  
  
 Skupina může mít nabídky, jiné skupiny nebo sám sebe jako nadřazený. Nadřazený je však obvykle nabídky nebo panelu nástrojů. V nabídce v předchozím příkladu je podřízená `IDG_VS_MM_TOOLSADDINS` skupiny a že skupiny je podřízená nabídek v sadě Visual Studio. Skupina v následujícím příkladu je podřízená položka nabídky v předchozího příkladu.  
  
```  
 <Group guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"  
priority="0x0600">  
   <Parent guid="guidTopLevelMenuCmdSet" id="TopLevelMenu"/>  
 </Group>  
```  
  
 Protože je součástí nabídky, tato skupina by obvykle obsahovat příkazy. Však mohou obsahovat také jiné nabídky. Toto je, jak jsou definovány dílčích, jak je znázorněno v následujícím příkladu.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet" id="SubMenu"  
priority="0x0100" type="Menu">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"/>  
  <Strings>  
    <ButtonText>Sub Menu</ButtonText>  
    <CommandName>Sub Menu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="commands"></a>Příkazy  
 Příkaz, který je zadán pro IDE je definován jako buď [Button Element](../../extensibility/button-element.md) nebo [Element pole se seznamem](../../extensibility/combo-element.md). Chcete-li zobrazen v nabídce nebo panel nástrojů, příkaz, musíte mít skupinu jako svůj nadřazený uzel.  
  
##### <a name="buttons"></a>Tlačítka  
 Tlačítka jsou definovány v `Buttons` oddílu. Všechny položky nabídky, tlačítko nebo jiného elementu, který uživatel klikne na spuštění jednoduchého příkazu je považován za tlačítko. Některé typy tlačítko může zahrnovat funkce seznamu. Tlačítka mají stejné požadované a volitelné atributy, které mají nabídky, a může mít také [Element ikony](../../extensibility/icon-element.md) určující identifikátor GUID a ID rastrový obrázek, který reprezentuje tlačítko v prostředí IDE. Další informace o tlačítka a jejich atributy, najdete v článku [tlačítka Element](../../extensibility/buttons-element.md) dokumentaci.  
  
 Tlačítko v následujícím příkladu je podřízená skupiny v předchozího příkladu a se zobrazí v prostředí IDE jako položku nabídky v nabídce nadřazené této skupiny.  
  
```  
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />  
  <Icon guid="guidImages" id="bmpPic1" />  
  <Strings>  
    <CommandName>cmdidTestCommand</CommandName>  
    <ButtonText>Test Command</ButtonText>  
  </Strings>  
</Button>  
```  
  
##### <a name="combos"></a>Kláves  
 Kláves jsou definovány v `Combos` oddílu. Každý `Combo` element reprezentuje rozevíracím seznamu v prostředí IDE. Pole se seznamem může nebo nemusí být zápis uživatelů, v závislosti na hodnotě `type` atribut se seznamem se. Kláves mají stejné prvky a chování, které tlačítka mít a může mít následující další atributy:  
  
-   A `defaultWidth` atribut, který určuje šířka v pixelech.  
  
-   `idCommandList` Atribut, který určuje seznam, který obsahuje položky, které se zobrazí v seznamu. Příkaz seznamu musí být deklarován stejným `GuidSymbol` uzlu, který obsahuje se seznamem se.  
  
 V následujícím příkladu definuje prvku pole se seznamem.  
  
```xml  
<Combos>  
  <Combo guid="guidFirstToolWinCmdSet"  
         id="cmdidWindowsMediaFilename"  
         priority="0x0100" type="DynamicCombo"  
         idCommandList="cmdidWindowsMediaFilenameGetList"  
         defaultWidth="130">  
    <Parent guid="guidFirstToolWinCmdSet"  
            id="ToolbarGroupID" />  
    <CommandFlag>IconAndText</CommandFlag>  
    <CommandFlag>CommandWellOnly</CommandFlag>  
    <CommandFlag>StretchHorizontally</CommandFlag>  
    <Strings>  
      <CommandName>Filename</CommandName>  
      <ButtonText>Enter a Filename</ButtonText>  
    </Strings>  
  </Combo>  
</Combos>  
```  
  
##### <a name="bitmaps"></a>Rastrové obrázky  
 Musí obsahovat příkazy, které se zobrazí spolu s ikonu `Icon` element, který odkazuje na rastrový obrázek pomocí jeho identifikátoru GUID a ID. Každý rastrového obrázku je definován jako [rastrový obrázek Element](../../extensibility/bitmap-element.md) v `Bitmaps` části. Jediné požadované atributy `Bitmap` jsou definice `guid` a `href`, který odkazuje na zdrojový soubor. Pokud zdrojový soubor barevný proužek prostředků **usedList** atribut je také nutný, seznam dostupných imagí v pruh. Další informace najdete v tématu [rastrový obrázek Element](../../extensibility/bitmap-element.md) dokumentaci.  
  
### <a name="parenting"></a>Správa nadřazených  
 Následující pravidla řídí, jak položky může volat jinou položku jako svůj nadřazený uzel.  
  
|Prvek|Definované v této části tabulky příkaz|Mohou být obsaženy (jako nadřazená nebo umístění v `CommandPlacements` oddílu, nebo obojí)|Může obsahovat (označované jako nadřízenou položku.)|  
|-------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------|  
|Skupina|[Groups – Element](../../extensibility/groups-element.md), IDE, ostatní VSPackages|Z nabídky, skupinu, samotné položky|Nabídky, skupiny a příkazy|  
|Nabídka|[Element nabídky](../../extensibility/menus-element.md), IDE, ostatní VSPackages|1 *n* skupiny|0 *n* skupiny|  
|Panel nástrojů|[Element nabídky](../../extensibility/menus-element.md), IDE, ostatní VSPackages|Samotnou položku|0 *n* skupiny|  
|Položka nabídky|[Tlačítka Element](../../extensibility/buttons-element.md), IDE, ostatní VSPackages|1 *n* skupin, samotné položky|-0 *n* skupiny|  
|Tlačítko|[Tlačítka Element](../../extensibility/buttons-element.md), IDE, ostatní VSPackages|1 *n* skupin, samotné položky||  
|Pole se seznamem|[Element kláves](../../extensibility/combos-element.md), IDE, ostatní VSPackages|1 *n* skupin, samotné položky||  
  
### <a name="menu-command-and-group-placement"></a>Nabídky, příkazu a umístění skupiny  
 Nabídky, skupinu nebo příkaz můžete zobrazit na více než jednom místě v prostředí IDE. Pro položku, kterou chcete jsou zobrazeny na několika místech, musí být přidaný do `CommandPlacements` části jako [CommandPlacement Element](../../extensibility/commandplacement-element.md). Všechny nabídky, skupinu nebo příkaz se dá přidat jako příkaz umístění. Panely nástrojů nelze však umístit tímto způsobem, protože nelze vložit do víc kontextová umístění.  
  
 Příkaz umísťováním mít `guid`, `id`, a `priority` atributy. Identifikátor GUID a ID musí odpovídat názvům položky, které je umístěné. `priority` Atribut určuje umístění položky s ohledem na ostatní položky. Při IDE Sloučí dvě nebo více položek, které mají stejnou prioritu, jsou jejich umísťováním definován, protože rozhraní IDE není zaručeno, že se balíček prostředků ve stejném pořadí čtou pokaždé, když je balíček založený.  
  
 Z nabídky nebo skupiny se zobrazí na více místech, zobrazí se všechny podřízené objekty dané nabídky nebo skupiny v každé instanci.  
  
## <a name="command-visibility-and-context"></a>Příkaz viditelnost a kontext  
 Při instalaci více VSPackages připojovaném nabídek, položek nabídek a panelů nástrojů může zaplnit rozhraní IDE. Chcete-li se tomuto problému vyhnout, můžete řídit viditelnost jednotlivé prvky uživatelského rozhraní pomocí *omezení viditelnosti* a příznaky příkazu.  
  
##### <a name="visibility-constraints"></a>Omezení viditelnosti  
 Omezení viditelnosti je nastaven jako [VisibilityItem Element](../../extensibility/visibilityitem-element.md) v `VisibilityConstraints` oddílu. Omezení viditelnosti definuje konkrétní kontexty uživatelského rozhraní, ve kterých je cílová položka viditelné. Nabídky nebo příkazu, který je zahrnut v této části je viditelná jenom v případě, že jedna z definovaných kontexty je aktivní. Pokud nabídky nebo příkaz není odkazy v této části, je vždy viditelné ve výchozím nastavení. Tato část se nevztahuje na skupiny.  
  
 `VisibilityItem` elementy musí mít tři atributy takto: `guid` a `id` prvku uživatelského rozhraní, a `context`. `context` Určuje atribut, když cílová položka se bude zobrazovat a trvá jakýkoli platný kontext uživatelského rozhraní jako jeho hodnotu. Konstanty kontextu uživatelského rozhraní pro sadu Visual Studio jsou členy <xref:Microsoft.VisualStudio.VSConstants> třídy. Každý `VisibilityItem` element může trvat kontextu pouze jednu hodnotu. Druhý kontextu použít, vytvořte druhý `VisibilityItem` element, který odkazuje na položku stejné, jak je znázorněno v následujícím příkladu.  
  
```xml  
<VisibilityConstraints>  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasSingleProject" />  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasMultipleProjects" />  
</VisibilityConstraints>  
```  
  
##### <a name="command-flags"></a>Příkaz příznaky  
 Následující příznaky příkazu může ovlivnit viditelnost nabídek a příkazů, které se vztahují na.  
  
 AlwaysCreate  
 I když nemá žádné skupiny nebo tlačítek, vytvoří se nabídky.  
  
 Platné pro: `Menu`  
  
 CommandWellOnly  
 Použít tento příznak Pokud příkaz nezobrazí v nabídce nejvyšší úrovně a chcete, aby byl k dispozici pro přizpůsobení další prostředí, například vazbu klíče. Po instalaci VSPackage uživatele můžete přizpůsobit tyto příkazy otevřením **možnosti** dialogové okno a potom úpravy příkaz umístění v rámci **klávesnice prostředí** kategorie. Nemá vliv na umístění v místní nabídky, panely nástrojů, nabídky řadiče nebo dílčích.  
  
 Platná pro: `Button`, `Combo`  
  
 DefaultDisabled  
 Ve výchozím nastavení příkaz vypnutá, pokud VSPackage, který implementuje příkaz není načten nebo nebyla zavolána metoda QueryStatus.  
  
 Platná pro: `Button`, `Combo`  
  
 DefaultInvisible  
 Ve výchozím nastavení je příkaz Pokud VSPackage, který implementuje příkaz není načten nebo nebyla zavolána metoda QueryStatus neviditelná.  
  
 Měly být spojeny s `DynamicVisibility` příznak.  
  
 Platná pro: `Button`, `Combo`, `Menu`  
  
 DynamicVisibility  
 Viditelnost příkazu můžete změnit pomocí metody QueryStatus nebo kontextu identifikátor GUID, který je součástí `VisibilityConstraints` části.  
  
 Platí pro příkazy, které se zobrazují v nabídkách, nikoli na panely nástrojů. Položky panelu nástrojů nejvyšší úrovně můžete zakázat, ale není skryté, když je příznak OLECMDF_INVISIBLE vrátila z metody QueryStatus.  
  
 V nabídce tento příznak také znamená, že ho měli při jeho členové budou skryti automaticky skryty. Tento příznak je přiřazen dílčích obvykle, protože už máte toto chování nabídek nejvyšší úrovně.  
  
 Měly být spojeny s `DefaultInvisible` příznak.  
  
 Platná pro: `Button`, `Combo`, `Menu`  
  
 NoShowOnMenuController  
 Pokud je příkaz, který má tento příznak nastavený na řadiči nabídky, příkaz se v rozevíracím seznamu nezobrazí.  
  
 Platné pro: `Button`  
  
 Další informace o příkazu příznaky najdete v tématu [Element Command příznak](../../extensibility/command-flag-element.md) dokumentaci.  
  
##### <a name="general-requirements"></a>Obecné požadavky  
 Váš příkaz musí projít následující řadu testů, než lze zobrazit a povolit:  
  
-   Příkaz je správně nastavený.  
  
-   `DefaultInvisible` Není nastaven příznak.  
  
-   Nadřazené nabídky nebo panelu nástrojů je viditelný.  
  
-   Příkaz není z důvodu kontextu položku v neviditelná [VisibilityConstraints Element](../../extensibility/visibilityconstraints-element.md) části.  
  
-   VSPackage kód, který implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní zobrazuje a umožňuje příkazu. Žádný kód rozhraní zachytili ji a u něj.  
  
-   Když uživatel klikne příkazu, stane se v rámci postupu popsané v [směrování algoritmus](../../extensibility/internals/command-routing-algorithm.md).  
  
## <a name="calling-pre-defined-commands"></a>Předem definované příkazy volání  
 [UsedCommands Element](../../extensibility/usedcommands-element.md) VSPackages umožňuje přístup k příkazům, které jsou k dispozici další VSPackages nebo rozhraní IDE. Chcete-li to provést, vytvořte [UsedCommand Element](../../extensibility/usedcommand-element.md) s identifikátorem GUID a ID pomocí příkazu. To zajistí, že příkaz budou načteny Visual Studio, i v případě, že není součástí aktuální konfigurace sady Visual Studio. Další informace najdete v tématu [UsedCommand Element](../../extensibility/usedcommand-element.md).  
  
## <a name="interface-element-appearance"></a>Vzhled elementu rozhraní  
 Důležité informace pro výběr a umístění prvků příkazu jsou následující:  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nabízí mnoho prvky uživatelského rozhraní, které se zobrazují odlišně v závislosti na umístění.  
  
-   Prvku uživatelského rozhraní, která je definována pomocí `DefaultInvisible` příznak se nezobrazí v prostředí IDE, pokud je buď zobrazí jeho implementace VSPackage <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> metoda, nebo ve spojení s konkrétní kontext uživatelského rozhraní v `VisibilityConstraints` části.  
  
-   I úspěšně umístěného příkaz se nemusí zobrazit. Tato možnost je vzhledem k tomu, že rozhraní IDE automaticky skryje nebo zobrazí některé příkazy, v závislosti na rozhraní, která VSPackage má (nebo nejsou) implementovaná. Například VSPackage implementace některých sestavení rozhraní položky související s sestavení nabídky příčiny automaticky zobrazený.  
  
-   Použití `CommandWellOnly` příznak v definici elementu uživatelského rozhraní znamená, že příkaz lze přidat pouze pomocí vlastního nastavení.  
  
-   Příkazy může být k dispozici pouze v určitých uživatelského rozhraní kontextů, například jenom v případě, že když integrovaného vývojového prostředí v zobrazení návrhu, zobrazí se dialogové okno.  
  
-   Chcete-li způsobit, že některé prvky uživatelského rozhraní, který se má zobrazit v prostředí IDE, musíte implementovat jednu nebo více rozhraní nebo napsat kód.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřování nabídek a příkazů](../../extensibility/extending-menus-and-commands.md)