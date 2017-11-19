---
title: "Přidání místní nabídky v okně nástroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- context menus, adding to tool windows
- menus, context menus
- shortcut menus, adding to tool windows
- tool windows, adding context menus
ms.assetid: 50234537-9e95-4b7e-9cb7-e5cf26d6e9d2
caps.latest.revision: "37"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 81e944d73ae45de1a786a6df27652949a38eec81
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-a-shortcut-menu-in-a-tool-window"></a>Přidání místní nabídky v okně nástroje
Tento názorný postup převádí místní nabídky v okně nástroje. Místní nabídka je nabídka, která se zobrazí, když uživatel klepne pravým tlačítkem na tlačítko, textového pole nebo pozadí okna. Příkazy v místní nabídce se chovají stejně jako příkazy na jinou nabídku nebo panely nástrojů. Pro podporu místní nabídky, zadejte ho do souboru .vsct a zobrazit ji v reakci na klikněte pravým tlačítkem myši.  
  
 Okno nástroje se skládá z uživatelského ovládacího prvku WPF v třídě okno Vlastní nástroj, který dědí z <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>.  
  
 Tento návod ukazuje, jak vytvořit místní nabídku jako nabídce sady Visual Studio, deklarace položek nabídky v souboru .vsct a následným použitím rozhraní spravované balíčku pro jejich implementaci ve třídě, která definuje okno nástroje. Tento přístup zajišťuje přístup k příkazy sady Visual Studio, prvky uživatelského rozhraní a objektový model automatizace.  
  
 Případně, pokud vaše místní nabídky nebude přístup k funkci Visual Studio, můžete také použít <xref:System.Windows.FrameworkElement.ContextMenu%2A> vlastnost elementu XAML v uživatelského ovládacího prvku. Další informace najdete v tématu [ContextMenu](/dotnet/framework/wpf/controls/contextmenu).  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-the-tool-window-shortcut-menu-package"></a>Vytváření balíček nástroje okno místní nabídky  
  
1.  Vytvoření projektu VSIX s názvem `TWShortcutMenu` a přidejte šablonu a nástroj okno s názvem **místní nabídka** k němu. Další informace o vytváření okno nástroje najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="specifying-the-shortcut-menu"></a>Zadáním místní nabídky  
 Místní nabídky, jako uvedeno v tomto návodu umožňuje uživateli vybrat ze seznamu barev, které se používají k vyplnění pozadí okno nástroje.  
  
1.  V ShortcutMenuPackage.vsct najdete v GuidSymbol elementu s názvem guidShortcutMenuPackageCmdSet a deklarovat místní nabídky, místní nabídky skupiny a možnosti nabídky. GuidSymbol element by měl nyní vypadat takto:  
  
    ```xml  
    <GuidSymbol name="guidShortcutMenuPackageCmdSet" value="{00000000-0000-0000-0000-0000}"> // your GUID here  
        <IDSymbol name="ShortcutMenuCommandId" value="0x0100" />  
        <IDSymbol name="ColorMenu" value="0x1000"/>  
        <IDSymbol name="ColorGroup" value="0x1100"/>  
        <IDSymbol name="cmdidRed" value="0x102"/>  
        <IDSymbol name="cmdidYellow" value="0x103"/>  
        <IDSymbol name="cmdidBlue" value="0x104"/>  
    </GuidSymbol>  
    ```  
  
2.  Těsně před prvku tlačítka vytvořit element nabídky a pak v něm definovat místní nabídky.  
  
    ```vb  
    <Menus>  
      <Menu guid="guidShortcutMenuPackageCmdSet" id="ColorMenu" type="Context">  
        <Strings>  
          <ButtonText>Color change</ButtonText>  
          <CommandName>ColorChange</CommandName>  
        </Strings>  
      </Menu>  
    </Menus>  
    ```  
  
     Místní nabídky nemá nadřazený, protože není součástí nabídky nebo panelu nástrojů.  
  
3.  Vytvořte skupiny element s skupinového elementu, který obsahuje položky místní nabídky a přidružte skupinu v místní nabídce.  
  
    ```xml  
    <Groups>  
        <Group guid="guidShortcutMenuPackageCmdSet" id="ColorGroup">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorMenu"/>  
        </Group>  
    </Groups>  
    ```  
  
4.  V elementu tlačítka zadejte jednotlivé příkazy, které se zobrazí v místní nabídce. Element tlačítka by měl vypadat takto:  
  
    ```xml  
    <Buttons>  
        <Button guid="guidShortcutMenuPackageCmdSet" id="ShortcutMenuCommandId" priority="0x0100" type="Button">  
            <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
            <Icon guid="guidImages" id="bmpPic1" />  
            <Strings>  
                <ButtonText>ShortcutMenu</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidRed" priority="1" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Red</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidYellow" priority="3" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Yellow</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidBlue" priority="5" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Blue</ButtonText>  
            </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
5.  ShortcutMenuPackageGuids.cs přidejte definice pro příkaz nastavené identifikátor GUID, v nabídce zástupce a položky nabídky.  
  
    ```csharp  
    public const string guidShortcutMenuPackageCmdSet = "00000000-0000-0000-0000-00000000"; // your GUID will differ  
    public const int ColorMenu = 0x1000;  
    public const int cmdidRed = 0x102;  
    public const int cmdidYellow = 0x103;  
    public const int cmdidBlue = 0x104;  
    ```  
  
     Jedná se o stejné ID příkazů, které jsou definovány v sekci symboly ShortcutMenuPackage.vsct souboru. Kontext skupina není součástí zde protože je vyžadován pouze v souboru .vsct.  
  
## <a name="implementing-the-shortcut-menu"></a>Implementace místní nabídky  
 Tato část implementuje místní nabídky a jeho příkazy.  
  
1.  V ShortcutMenu.cs panel nástrojů můžete získat službu příkaz nabídky, ale nemůže ovládací prvek, který ji obsahuje. Následující kroky ukazují, jak zpřístupnit službu příkaz nabídky uživatelského ovládacího prvku.  
  
2.  V ShortcutMenu.cs, přidejte následující příkazy:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    ```  
  
3.  Přepište metodu Initialize() okno nástroje získat službu příkaz nabídky a přidání ovládacího prvku, předání službu příkaz nabídky contructor:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        commandService = (OleMenuCommandService)GetService(typeof(IMenuCommandService));  
        Content = new ShortcutMenuControl(commandService);  
    }  
    ```  
  
4.  V konstruktoru okno nástroj Místní nabídka odeberte řádek, který přidá ovládacího prvku. Konstruktor by měl nyní vypadat takto:  
  
    ```csharp  
    public ShortcutMenu() : base(null)  
    {  
        this.Caption = "ShortcutMenu";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
    }  
    ```  
  
5.  V ShortcutMenuControl.xaml.cs přidejte soukromé pole pro službu příkaz nabídky a změňte konstruktoru ovládacího prvku provést službu příkaz nabídky. Potom pomocí služby příkaz nabídky přidat příkazy kontextové nabídky. Konstruktor ShortcutMenuControl by teď měl vypadat jako následující kód. Obslužná rutina příkazu bude definován později.  
  
    ```csharp  
    public ShortcutMenuControl(OleMenuCommandService service)  
    {  
        this.InitializeComponent();  
        commandService = service;  
  
        if (null !=commandService)  
        {  
            // Create an alias for the command set guid.  
            Guid guid = new Guid(ShortcutMenuPackageGuids.guidShortcutMenuPackageCmdSet);  
  
            // Create the command IDs.   
            var red = new CommandID(guid, ShortcutMenuPackageGuids.cmdidRed);  
            var yellow = new CommandID(guid, ShortcutMenuPackageGuids.cmdidYellow);  
            var blue = new CommandID(guid, ShortcutMenuPackageGuids.cmdidBlue);  
  
            // Add a command for each command ID.  
            commandService.AddCommand(new MenuCommand(ChangeColor, red));  
            commandService.AddCommand(new MenuCommand(ChangeColor, yellow));  
            commandService.AddCommand(new MenuCommand(ChangeColor, blue));  
        }  
    }  
    ```  
  
6.  V ShortcutMenuControl.xaml, přidejte <xref:System.Windows.UIElement.MouseRightButtonDown> událostí do nejvyšší úrovně <xref:System.Windows.Controls.UserControl> elementu. Soubor XAML by měl nyní vypadat takto:  
  
    ```vb  
    <UserControl x:Class="TWShortcutMenu.ShortcutMenuControl"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            Background="{DynamicResource VsBrush.Window}"  
            Foreground="{DynamicResource VsBrush.WindowText}"  
            mc:Ignorable="d"  
            d:DesignHeight="300" d:DesignWidth="300"  
            Name="MyToolWindow"  
            MouseRightButtonDown="MyToolWindow_MouseRightButtonDown">  
        <Grid>  
            <StackPanel Orientation="Vertical">  
                <TextBlock Margin="10" HorizontalAlignment="Center">ShortcutMenu</TextBlock>  
            </StackPanel>  
        </Grid>  
    </UserControl>  
    ```  
  
7.  ShortcutMenuControl.xaml.cs přidejte zástupnou proceduru pro obslužné rutiny události.  
  
    ```csharp  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
    . . .  
    }  
    ```  
  
8.  Přidejte následující příkazy using do stejného souboru:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    using System;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    ```  
  
9. Implementace `MyToolWindowMouseRightButtonDown` událostí následujícím způsobem.  
  
    ```csharp  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
        if (null != commandService)  
        {  
            CommandID menuID = new CommandID(  
                new Guid(ShortcutMenuPackageGuids.guidShortcutMenuPackageCmdSet),  
                ShortcutMenuPackageGuids.ColorMenu);  
            Point p = this.PointToScreen(e.GetPosition(this));  
            commandService.ShowContextMenu(menuID, (int)p.X, (int)p.Y);  
        }  
    }  
    ```  
  
     Tím se vytvoří <xref:System.ComponentModel.Design.CommandID> objekt pro místní nabídky, identifikuje umístění klikněte na tlačítko myši a v tomto umístění se otevře místní nabídky pomocí <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A> metoda.  
  
10. Implementujte obslužná rutina příkazu.  
  
    ```csharp  
    private void ChangeColor(object sender, EventArgs e)  
    {  
        var mc = sender as MenuCommand;  
  
        switch (mc.CommandID.ID)  
        {  
            case ShortcutMenuPackageGuids.cmdidRed:  
                MyToolWindow.Background = Brushes.Red;  
                break;  
            case ShortcutMenuPackageGuids.cmdidYellow:  
                MyToolWindow.Background = Brushes.Yellow;  
                break;  
            case ShortcutMenuPackageGuids.cmdidBlue:  
                MyToolWindow.Background = Brushes.Blue;  
                break;  
        }  
    }  
    ```  
  
     V takovém případě jedním metoda zpracovává události pro všechny položky nabídky tím, že určíte <xref:System.ComponentModel.Design.CommandID> a nastavení barvy pozadí odpovídajícím způsobem. Pokud položky nabídky měl obsahoval nesouvisejícími příkazy, by jste vytvořili samostatné obslužnou rutinu pro každý příkaz.  
  
## <a name="testing-the-tool-window-features"></a>Testování funkce okno nástroje  
  
1.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
2.  V experimentální instance, klikněte na **zobrazení nebo ostatní okna**a potom klikněte na **místní nabídka**. To by měla zobrazit vaše okno nástroje.  
  
3.  Klikněte pravým tlačítkem myši v těle okno nástroje. Místní nabídky, která má seznam barev mají být zobrazeny.  
  
4.  Klikněte na tlačítko barvy v místní nabídce. Barva pozadí okno nástroj musí změnit tak, aby vybrané barvy.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Použití a poskytování služeb](../extensibility/using-and-providing-services.md)