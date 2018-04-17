---
title: Přidání podnabídky do nabídky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- context menus
- submenus, cascading
- cascading submenus
- menus, creating cascading submenus
ms.assetid: 692600cb-d052-40e2-bdae-4354ae7c6c84
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6998c275aead7b12b107f700e699f5a82edd84e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-submenu-to-a-menu"></a>Přidání podnabídky do nabídky
Tento názorný postup je založený na ukázky v [přidání nabídky na panelu nabídek Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) ukazuje, jak přidat podnabídky k **TestMenu** nabídky.  
  
 Podnabídky je sekundárním nabídce, která se zobrazí v jiné nabídky. Podnabídky lze identifikovat podle na šipku, která odpovídá jeho názvu. Kliknutím na jméno způsobí, že podnabídky a jeho příkazů, který se má zobrazit.  
  
 Tento návod vytvoří podnabídky v nabídce v řádku nabídek Visual Studio a vloží nový příkaz podnabídky. Průvodce také implementuje nový příkaz.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="adding-a-submenu-to-a-menu"></a>Přidání podnabídky do nabídky  
  
1.  Postupujte podle kroků v [přidání nabídky na panelu nabídek Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) vytvoření položky projektu a nabídky. Postup v tomto návodu předpokládá, že je název projektu VSIX `TopLevelMenu`.  
  
2.  Open TestCommandPackage.vsct. V `<Symbols>` přidejte `<IDSymbol>` element pro podnabídky, jeden pro dílčí skupiny a jeden pro příkaz, ve `<GuidSymbol>` uzel s názvem "guidTopLevelMenuCmdSet." Toto je stejném uzlu, který obsahuje `<IDSymbol>` element nejvyšší úrovně nabídky.  
  
    ```xml  
    <IDSymbol name="SubMenu" value="0x1100"/>  
    <IDSymbol name="SubMenuGroup" value="0x1150"/>  
    <IDSymbol name="cmdidTestSubCommand" value="0x0105"/>  
    ```  
  
3.  Přidejte nově vytvořený podnabídky `<Menus>` oddílu.  
  
    ```xml  
    <Menu guid="guidTestCommandPackageCmdSet" id="SubMenu" priority="0x0100" type="Menu">  
        <Parent guid="guidTestCommandPackageCmdSet" id="MyMenuGroup"/>  
        <Strings>  
            <ButtonText>Sub Menu</ButtonText>  
            <CommandName>Sub Menu</CommandName>  
        </Strings>  
    </Menu>  
    ```  
  
     Určuje dvojice GUID nebo ID nadřazeného objektu skupiny nabídek, který byl vytvořen v [přidání nabídky na panelu nabídek Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md), a je podřízená nabídek nejvyšší úrovně.  
  
4.  Přidat skupinu nabídky definovaný v kroku 2 `<Groups>` části a nastavit jej jako podřízenou podnabídky.  
  
    ```xml  
    <Group guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" priority="0x0000">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenu"/>  
    </Group>  
    ```  
  
5.  Přidejte nový `<Button>` elementu, který chcete `<Buttons>` části zadat příkaz jako položku v podnabídce vytvořili v kroku 2.  
  
    ```xml  
    <Button guid="guidTestCommandPackageCmdSet" id="cmdidTestSubCommand" priority="0x0000" type="Button">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic2" />  
        <Strings>  
           <CommandName>cmdidTestSubCommand</CommandName>  
           <ButtonText>Test Sub Command</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
6.  Sestavte řešení a spuštění ladění. Měli byste vidět experimentální instanci.  
  
7.  Klikněte na tlačítko **TestMenu** zobrazíte nové podnabídky s názvem **dílčí nabídky**. Klikněte na tlačítko **dílčí nabídky** podnabídky Otevřít a zobrazit nový příkaz, **testovací dílčí příkaz**. Všimněte si, že kliknete na **testovací dílčí příkaz** se nic nestane.  
  
## <a name="adding-a-command"></a>Přidání příkaz  
  
1.  Otevřete TestCommand.cs a přidejte následující ID příkazu po stávající ID příkazu.  
  
    ```csharp  
    public const int cmdidTestSubCmd = 0x105;  
    ```  
  
2.  Dílčí příkaz přidáte. Přejděte na příkaz konstruktor. Přidejte následující řádky jen po volání `AddCommand` metoda.  
  
    ```csharp  
    CommandID subCommandID = new CommandID(CommandSet, cmdidTestSubCmd);  
    MenuCommand subItem = new MenuCommand(  
        new EventHandler(SubItemCallback), subCommandID);  
    commandService.AddCommand(subItem);  
  
    ```  
  
     `SubItemCallback` Budou později určené obslužná rutina příkazu. Konstruktor by měl nyní vypadat takto:  
  
    ```csharp  
    private TestCommand(Package package)  
            {  
                if (package == null)  
                {  
                    throw new ArgumentNullException("package");  
                }  
  
                this.package = package;  
  
                OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
                if (commandService != null)  
                {  
                    var menuCommandID = new CommandID(CommandSet, CommandId);  
                    var menuItem = new MenuCommand(this.MenuItemCallback, menuCommandID);  
                    commandService.AddCommand(menuItem);  
                    CommandID subCommandID = new CommandID(CommandSet, cmdidTestSubCmd);  
                    MenuCommand subItem = new MenuCommand(  
                        new EventHandler(SubItemCallback), subCommandID);  
                    commandService.AddCommand(subItem);  
                }  
    ```  
  
3.  Přidejte SubItemCallback(). Toto je metoda, která je volána při kliknutí na nový příkaz v podnabídce.  
  
    ```csharp  
    private void SubItemCallback(object sender, EventArgs e)  
    {  
        IVsUIShell uiShell = (IVsUIShell)this.ServiceProvider.GetService(  
            typeof(SVsUIShell));  
        Guid clsid = Guid.Empty;  
        int result;  
        uiShell.ShowMessageBox(  
            0,  
            ref clsid,  
            "TestCommand",  
            string.Format(CultureInfo.CurrentCulture,  
            "Inside TestCommand.SubItemCallback()",  
            this.ToString()),  
            string.Empty,  
            0,  
            OLEMSGBUTTON.OLEMSGBUTTON_OK,  
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
            OLEMSGICON.OLEMSGICON_INFO,  
            0,  
            out result);  
    }  
    ```  
  
4.  Sestavte projekt a spusťte ladění. Experimentální instanci by se zobrazit.  
  
5.  Na **TestMenu** nabídky, klikněte na tlačítko **dílčí nabídky** a pak klikněte na **testovací dílčí příkaz**. Okno se zprávou by měla zobrazit a zobrazit text "Test příkaz uvnitř TestCommand.SubItemCallback()".  
  
## <a name="see-also"></a>Viz také  
 [Přidání nabídky na panelu nabídek Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)   
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)
