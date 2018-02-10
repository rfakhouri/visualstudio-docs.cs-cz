---
title: MenuCommands Vs. OleMenuCommands | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, creating in VSPackages
- command buttons, creating and placing
- menus, creating commands
ms.assetid: 553d5e07-3e19-4aba-b490-6c7dd05fd82e
caps.latest.revision: 
manager: douge
ms.openlocfilehash: 0465057549543d8e07742e3b3806ebdcab28eb28
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="menucommands-vs-olemenucommands"></a>MenuCommands Vs. OleMenuCommands
Příkazy nabídky můžete vytvořit buď z odvozením <xref:System.ComponentModel.Design.MenuCommand> nebo z <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objekt a impementling obslužné rutiny příslušné události. Ve většině případů můžete použít <xref:System.ComponentModel.Design.MenuCommand>, jak je šablona projektu VSPackage provádí, ale někdy budete možná muset použít <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>.  
  
 Příkazy, že VSPackage zpřístupňují integrovaného vývojového prostředí musí být viditelné a povolené před uživatele můžete je používat. Příkazy jsou v souboru .vsct vytvořen pomocí šablony projektu balíček Visual Studio, jsou viditelné a povolené ve výchozím nastavení. Některé příznaky příkazu, například nastavení `DynamicItemStart`, můžete změnit výchozí chování. Viditelnost, povolený stav a další vlastnosti příkazu lze také změnit v kódu v době běhu přímým přístupem <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objekt, který je přidružený příkaz.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="template-locations-for-the-visual-studio-package-template"></a>Šablona umístění balíčku šablony sady Visual Studio  
 Šablony balíček Visual Studio můžete najít **nový projekt** dialogové okno pod **jazyka Visual Basic nebo rozšíření**, **C# nebo rozšíření**, nebo **jiných Typy projektů nebo rozšíření**.  
  
## <a name="creating-a-command"></a>Vytváření příkazu  
 Všechny příkazy, příkaz skupin, nabídek, panely nástrojů a nástroje systému windows jsou definovány v souboru .vsct. Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Pokud vytváříte VSPackage pomocí šablony balíčku, vyberte **příkaz nabídky** vytvořte soubor .vsct a definování příkazu nabídky výchozí. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
#### <a name="to-add-a-command-to-the-ide"></a>Chcete-li přidat příkaz k prostředí IDE  
  
1.  Otevřete soubor .vsct.  
  
2.  V `Symbols` část, vyhledejte [GuidSymbol](../extensibility/guidsymbol-element.md) elementu, který obsahuje skupiny a příkazy.  
  
3.  Vytvoření [IDSymbol](../extensibility/idsymbol-element.md) element pro každou nabídky, skupiny nebo příkazu, kterou chcete přidat, jak je znázorněno v následujícím příkladu.  
  
     <!--FIXME [!CODE [ButtonGroup#01](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#01)]  -->
    ```xaml  
    <GuidSymbol name="guidButtonGroupCmdSet" value="{f69209e9-975a-4543-821d-1f4a2c52d737}">
      <IDSymbol name="MyMenuGroup" value="0x1020" />
      <IDSymbol name="cmdidMyCommand" value="0x0100" />
    </GuidSymbol>
    ```  
  
    `name` Atributy `GuidSymbol` a `IDSymbol` prvky poskytují pár GUID:ID pro každou novou nabídku, skupiny nebo příkaz. `guid` Představuje sadu příkazů, který je definovaný pro váš VSPackage. Můžete definovat více sady příkazů. Každý pár GUID:ID musí být jedinečný.  
  
4.  V [tlačítka](../extensibility/buttons-element.md) , vytvořte [tlačítko](../extensibility/button-element.md) elementu, který chcete definovat příkaz, jak je uvedeno v následujícím příkladu.  
  
     <!--FIXME [!CODE [ButtonGroup#03](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#03)]  -->
    ```xaml  
    <Button guid="guidButtonGroupCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
      <Parent guid="guidButtonGroupCmdSet" id="MyMenuGroup" />
      <Icon guid="guidImages" id="bmpPic1" />
      <Strings>
        <CommandName>cmdidMyCommand</CommandName>
        <ButtonText>My Command name</ButtonText>
      </Strings>
    </Button>
    ```  
  
    1.  Nastavte `guid` a `id` pole tak, aby odpovídaly GUID:ID nového příkazu.  
  
    2.  Nastavte `priority` atribut.  
  
         `priority` Atribut pomocí .vsct slouží k určení umístění tlačítka mezi ostatní objekty v své nadřazené skupiny.  
  
         Příkazy, které mají nižší hodnoty priority se zobrazí nad nebo nalevo od příkazy, které mají vyšší hodnoty priority. Priorita duplicitní hodnoty jsou povolené, ale relativní pozici příkazy, které mají stejnou prioritu je určen podle pořadí, ve kterém jsou zpracovány VSPackages v době běhu a tohoto pořadí nemůže být předem určený.  
  
         Vynechání `priority` atribut nastaví jeho hodnotu na 0.  
  
    3.  Nastavte `type` atribut. Ve většině případů budou mít hodnotu `"Button"`. Popis jiné typy platný tlačítko najdete v tématu [Button Element](../extensibility/button-element.md).  
  
5.  V definici tlačítko vytvořit [řetězce](../extensibility/strings-element.md) elementu, který obsahuje [ButtonText](../extensibility/buttontext-element.md) element tak, aby obsahovala název nabídky, jak se objevuje v prostředí IDE a [CommandName](../extensibility/commandname-element.md) Element tak, aby obsahovala název příkazu, který se používá pro přístup k nabídce v **příkaz** okno.  
  
     Pokud tlačítko textový řetězec obsahuje znak 'a', může uživatel otevřít v nabídce stisknutím klávesy ALT a to hned následuje znak 'a'.  
  
     Přidání `Tooltip` element způsobí, že obsahují text, který se zobrazí při umístění ukazatele myši nad tlačítko.  
  
6.  Přidat [ikonu](../extensibility/icon-element.md) elementu, který chcete zadat ikonu, pokud existuje, který se má zobrazit pomocí příkazu. Ikony se vyžadují pro tlačítka v panelech nástrojů, ale ne pro položky nabídky. `guid` a `id` z `Icon` element musí odpovídat názvům [rastrový obrázek](../extensibility/bitmap-element.md) element definovaný v `Bitmaps` části.  
  
7.  Přidejte příkaz příznaky, podle potřeby, chcete-li změnit vzhled a chování tlačítka. Chcete-li to provést, přidejte [CommandFlag](../extensibility/command-flag-element.md) element v definici nabídky.  
  
8.  Nastavte nadřazená skupina příkazu. Nadřazená skupina může být skupinu, kterou vytvoříte, skupinu z jiný balíček nebo skupinu z prostředí IDE. Například pro úpravy panel nástrojů Visual Studio, přidat příkazu vedle **komentář** a **odebrat komentář** tlačítka, nastavte na guidStdEditor:IDG_VS_EDITTOOLBAR_COMMENT nadřazený. Pokud nadřazená položka uživatelem definovanou skupinu, musí být podřízeným nabídky, panelu nástrojů nebo okno nástroje, které se zobrazí v prostředí IDE.  
  
     Můžete k tomu v jednom ze dvou způsobů, v závislosti na návrhu:  
  
    -   V `Button` elementu, vytvořit [nadřazené](../extensibility/parent-element.md) elementu a sadu jeho `guid` a `id` pole Identifikátor Guid a ID skupiny, který bude hostitelem příkazu, také známé jako *primárnínadřazenéskupiny*.  
  
         V následujícím příkladu definuje příkaz, který se zobrazí v nabídce definovaný uživatelem.  
  
         <!--FIXME [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  -->
        ```xaml  
        <Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">
          <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />
          <Icon guid="guidImages" id="bmpPic1" />
          <Strings>
            <CommandName>cmdidTestCommand</CommandName>
            <ButtonText>Test Command</ButtonText>
          </Strings>
        </Button>
        ```  
  
    -   Může vynechat `Parent` elementu, pokud příkaz má být umístěny pomocí příkazu umístění. Vytvoření [CommandPlacements](../extensibility/commandplacements-element.md) element před `Symbols` a přidejte [CommandPlacement](../extensibility/commandplacement-element.md) element, který má `guid` a `id` příkazu, `priority`a nadřazené, jak je znázorněno v následujícím příkladu.  
  
         <!-- FIXME [!CODE [ButtonGroup#04](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#04)] -->  
        ```xaml  
        <CommandPlacements>
          <CommandPlacement guid="guidButtonGroupCmdSet" id="cmdidMyCommand" priority="0x105">
            <Parent guid="guidButtonGroupCmdSet" id="MyMenuGroup" />
          </CommandPlacement>
        </CommandPlacements>
        ```  
  
         Vytvoření více příkaz umístění, která mají stejné GUID:ID a mají jiné nadřazené položky způsobí, že nabídky se objeví na více místech. Další informace najdete v tématu [CommandPlacements](../extensibility/commandplacements-element.md) element.  
  
     Další informace o skupinách příkazu a vztahy k nadřazeným položkám najdete v tématu [vytváření skupin opakovaně použitelného z tlačítka](../extensibility/creating-reusable-groups-of-buttons.md).  
  
 Příkaz v tomto okamžiku se nebude zobrazovat v prostředí IDE, ale nebude mít žádné funkce. Pokud příkaz byl vytvořen pomocí šablony balíček, ve výchozím nastavení bude mít klikněte na tlačítko obslužná rutina, která zobrazí zprávu.  
  
## <a name="handling-the-new-command"></a>Zpracování nový příkaz  
 Většina příkazů ve spravovaném kódu lze zpracovávat pomocí na spravované balíček Framework (MPF) tím, že přidružíte příkaz s <xref:System.ComponentModel.Design.MenuCommand> objekt nebo <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objektu a implementace jeho obslužné rutiny událostí.  
  
 Pro kód, který používá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní přímo pro příkaz zpracování, je nutné implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní a její metody. Jsou dvě nejdůležitější metody <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>.  
  
1.  Získat <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> instance, jak je znázorněno v následujícím příkladu.  
  
     [!code-csharp[ButtonGroup#21](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_5.cs)]  
  
2.  Vytvoření <xref:System.ComponentModel.Design.CommandID> objekt, který má jako jeho parametry identifikátoru GUID a ID příkazu pro zpracování, jak je znázorněno v následujícím příkladu.  
  
     [!code-csharp[ButtonGroup#22](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_6.cs)]  
  
     Šablona balíček Visual Studio poskytuje dvě kolekce `GuidList` a `PkgCmdIDList`, aby udržení identifikátory příkazů a identifikátory GUID. Tyto jsou naplněny automaticky pro příkazy, které jsou přidány šablony, ale pro příkazy, které přidáváte ručně, musíte taky přidat záznam ID, který má `PkgCmdIdList` třídy.  
  
     Alternativně můžete naplnit <xref:System.ComponentModel.Design.CommandID> objekt pomocí Nezpracovaný řetězec hodnotu identifikátoru GUID a celočíselná hodnota ID.  
  
3.  Vytvoření instance buď <xref:System.ComponentModel.Design.MenuCommand> nebo <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objekt, který určuje metoda, která zpracovává příkazu s <xref:System.ComponentModel.Design.CommandID>, jak je znázorněno v následujícím příkladu.  
  
     [!code-csharp[ButtonGroup#23](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_7.cs)]  
  
     <xref:System.ComponentModel.Design.MenuCommand> Je vhodný pro statické příkazy. Zobrazí položky dynamické nabídky vyžadují QueryStatus obslužné rutiny událostí. <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> Přidá <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> událost, která nastane, když v nabídce hostitele příkazu je otevřen a některé další vlastnosti, například <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Ve výchozím nastavení se předávají příkazů vytvořených šablonou balíček <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objekt v `Initialize()` metoda třídy balíčku.  
  
4.  <xref:System.ComponentModel.Design.MenuCommand> Je vhodný pro statické příkazy. Zobrazí položky dynamické nabídky vyžadují QueryStatus obslužné rutiny událostí. <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> Přidá <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> událost, která nastane, když v nabídce hostitele příkazu je otevřen a některé další vlastnosti, například <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Ve výchozím nastavení se předávají příkazů vytvořených šablonou balíček <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objekt v `Initialize()` metoda třídy balíčku. Průvodce sady Visual Studio implementuje `Initialize` metoda pomocí `MenuCommand`. Zobrazí položky dynamické nabídky, je třeba změnit na `OleMenuCommand`, jak je vidět v dalším kroku. Kromě toho pokud chcete změnit text položky nabídky, musíte přidat příznak TextChanges příkazu do příkazového tlačítka nabídky v souboru .vsct znázorněné v následujícím příkladu  
  
     <!--FIXME [!CODE [MenuText#02](../CodeSnippet/VS_Snippets_VSSDK/menutext#02)]-->  
    ```xaml  
    <Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
      <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
      <Icon guid="guidImages" id="bmpPic1" />
      <CommandFlag>TextChanges</CommandFlag>
      <Strings>
        <CommandName>cmdidMyCommand</CommandName>
        <ButtonText>My Command name</ButtonText>
      </Strings>
    </Button>
    ```
  
5.  Nový příkaz nabídky ke předat <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> metoda v <xref:System.ComponentModel.Design.IMenuCommandService> rozhraní. To se provádí ve výchozím nastavení pro příkazy vytvořených šablonou balíček, jak je znázorněno v následujícím příkladu  
  
     [!code-csharp[ButtonGroup#24](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_9.cs)]  
  
6.  Implementujte metodu, která zpracovává příkaz.  
  
#### <a name="to-implement-querystatus"></a>K implementaci QueryStatus  
  
1.  Předtím, než se zobrazí příkaz dojde k události QueryStatus. To umožňuje vlastnosti tohoto příkazu nastavit události obslužná rutina před dosažením uživatele. Pouze příkazy, které jsou přidány jako <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objektů můžete přístup k této metodě.  
  
     Přidat `EventHandler` do objektu <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> událost v <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objektu, který je vytvořen pro zpracování příkazu, jak je znázorněno v následujícím příkladu (`menuItem` je <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> instance).  
  
     [!code-csharp[MenuText#14](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_10.cs)]
     [!code-vb[MenuText#14](../extensibility/codesnippet/VisualBasic/menucommands-vs-olemenucommands_10.vb)]  
  
     `EventHandler` Objektu je uveden název metody, která je volána, když je dotazován stav příkazu nabídky.  
  
2.  Implementujte metodu dotazu stav obslužné rutiny pro příkaz. `object` `sender` Může být parametr převeden <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objekt, který se používá k nastavení různých atributů příkaz nabídky, včetně textu. Následující tabulka uvádí vlastnosti na <xref:System.ComponentModel.Design.MenuCommand> – třída (které třídy sady MPF <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> je odvozena z), odpovídají <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> příznaky.  
  
    |Vlastnost nabídka – příkaz|Příznak OLECMDF|  
    |--------------------------|------------------|  
    |<xref:System.ComponentModel.Design.MenuCommand.Checked%2A> = `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
    |<xref:System.ComponentModel.Design.MenuCommand.Visible%2A> = `false`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
    |<xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> = `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
  
     Můžete změnit text příkazu v nabídce <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> vlastnost <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objektu, jak je znázorněno v následujícím příkladu.  
  
     [!code-csharp[MenuText#11](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_11.cs)]
     [!code-vb[MenuText#11](../extensibility/codesnippet/VisualBasic/menucommands-vs-olemenucommands_11.vb)]  
  
 Sady MPF zpracovává automaticky v případě neznámý nebo nepodporovaný skupin. Pokud příkaz byl přidán do <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> pomocí <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> metoda příkaz není podporována.  
  
### <a name="handling-commands-by-using-the-iolecommandtarget-interface"></a>Zpracování příkazů pomocí IOleCommandTarget – rozhraní  
 Pro kód, který používá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní přímo, VSPackage musí implementovat i <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Pokud VSPackage implementuje hierarchie projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> místo toho by měla být implementována rozhraní.  
  
 Jak <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody jsou navrženy pro příjem sadu jeden příkaz `GUID` a pole ID příkazů jako vstup. Doporučujeme vám, že VSPackages plně podporují tento koncept víc ID jedno volání. Ale tak dlouho, dokud není VSPackage volat z jiných VSPackages, můžete předpokládat, že pole příkaz obsahuje pouze jeden příkaz ID, protože <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody jsou spouštěny v pořadí od dobře definovaný. Další informace o směrování, najdete v části [směrování příkazů v VSPackages](../extensibility/internals/command-routing-in-vspackages.md).  
  
 Pro kód, který používá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní přímo pro příkaz zpracování, je nutné implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda v VSPackage takto pro zpracování příkazů.  
  
##### <a name="to-implement-the-querystatus-method"></a>Chcete-li implementovat metodu QueryStatus  
  
1.  Vrátí <xref:Microsoft.VisualStudio.VSConstants.S_OK> pro platné příkazy.  
  
2.  Nastavte `cmdf` element `prgCmds` parametr.  
  
     Hodnota `cmdf` element je logické sjednocení hodnot z <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> výčtu kombinaci pomocí logických nebo (`|`) operátor.  
  
     Použijte odpovídající výčtu, na základě stavu příkazu:  
  
    -   Pokud je příkaz:  
  
         `prgCmds[0].cmdf = OLECMDF_SUPPORTED;`  
  
    -   Pokud v tuto chvíli by měl být neviditelná příkaz:  
  
         `prgCmds[0].cmdf |= OLECMDF_INVISIBLE;`  
  
    -   Pokud příkaz se již byly použity a je zapnutá:  
  
         `prgCmds[0].cmdf |= OLECMDF_LATCHED;`  
  
         V případě zpracování příkazů, které jsou hostované v nabídce typu `MenuControllerLatched`, první příkaz, který je označena kvalifikátorem `OLECMDF_LATCHED` příznak je výchozí příkaz, který se zobrazí v nabídce na spuštění. Další informace o `MenuController` najdete v nabídce typy [Menu Element](../extensibility/menu-element.md).  
  
    -   Pokud příkaz momentálně je zapnutá:  
  
         `prgCmds[0].cmdf |= OLECMDF_ENABLED;`  
  
    -   Pokud příkaz je součástí místní nabídky a je skrytý ve výchozím nastavení:  
  
         `prgCmds[0] cmdf |= OLECMDF_DEFHIDEONCTXMENU`  
  
    -   Pokud příkaz používá `TEXTCHANGES` příznak, nastavte `rgwz` element `pCmdText` parametr na nový text příkazu a sadu `cwActual` element `pCmdText` parametr velikost řetězce příkaz.  
  
     Pro chybové podmínky <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda musí zpracovávat následující chybových případech:  
  
    -   Pokud je identifikátor GUID je neznámý nebo není podporována, vrátí `OLECMDERR_E_UNKNOWNGROUP`.  
  
    -   Pokud je známý identifikátor GUID, ale ID příkazu je neznámý nebo není podporována, vrátí `OLECMDERR_E_NOTSUPPORTED`.  
  
 Implementace VSPackage <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda musí také návratové kódy konkrétní chyby, v závislosti na tom, jestli se podporuje příkaz a jestli se příkaz úspěšně zpracováno.  
  
##### <a name="to-implement-the-exec-method"></a>K implementaci Exec – metoda  
  
-   Pokud příkaz `GUID` neznámý, vrátí `OLECMDERR_E_UNKNOWNGROUP`.  
  
-   Pokud `GUID` je známé, ale příkaz ID neznámý, vraťte se `OLECMDERR_E_NOTSUPPORTED`.  
  
-   Pokud `GUID` a příkaz ID shodovat pár GUID:ID, který je používán příkaz v souboru .vsct, spustit kód, který je přidružený k příkazu a vrátit <xref:Microsoft.VisualStudio.VSConstants.S_OK>.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu VSCT XML](../extensibility/vsct-xml-schema-reference.md)   
 [Rozšiřování nabídek a příkazů](../extensibility/extending-menus-and-commands.md)