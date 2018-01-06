---
title: "Přidávání řadiče nabídky na panel nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Visual Studio], adding menu controllers
- menus, adding menu controllers to toolbars
- menu controllers, adding to toolbars
ms.assetid: 6af9b0b4-037f-404c-bb40-aaa1970768ea
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 720aeb5670127d64e7b3fc9b016a032c0526c083
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="adding-a-menu-controller-to-a-toolbar"></a>Přidávání řadiče nabídky na panelu nástrojů
Tento názorný postup je založený na [přidání panelu nástrojů na okno nástroje](../extensibility/adding-a-toolbar-to-a-tool-window.md) návod a ukazuje, jak přidat řadič nabídky na panelu nástrojů okna. Postupy v tomto poli lze použít také na panelu nástrojů, který je vytvořen v [přidávání panelů nástrojů](../extensibility/adding-a-toolbar.md) návod.  
  
 Řadič nabídky je ovládací prvek rozdělení. Levá strana řadiče nabídky obsahuje příkaz naposledy použité a spuštěním kliknutím. Šipka není pravé straně nabídky řadiče, při kliknutí na, otevře se seznam další příkazy. Po klepnutí na příkaz v seznamu, je příkaz spuštěn, a nahrazuje příkaz v levé nabídce řadiče. Tímto způsobem řadičem nabídky funguje jako příkazového tlačítka, které vždy zobrazí příkaz naposledy použité ze seznamu.  
  
 Nabídky řadiče může zobrazit v nabídkách ale používají se nejčastěji používá na panely nástrojů.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-menu-controller"></a>Vytvoření řadiče nabídky  
  
#### <a name="to-create-a-menu-controller"></a>Pokud chcete vytvořit řadič nabídky  
  
1.  Postupujte podle postupů popsaných v [přidání panelu nástrojů na okno nástroje](../extensibility/adding-a-toolbar-to-a-tool-window.md) vytvořit okno nástroje, který má panelu nástrojů.  
  
2.  V TWTestCommandPackage.vsct přejděte do části symboly. V elementu GuidSymbol s názvem **guidTWTestCommandPackageCmdSet**, deklarovat řadiči nabídky, nabídky řadiče skupiny a tři položky nabídky.  
  
    ```xml  
    <IDSymbol name="TestMenuController" value="0x1300" /><IDSymbol name="TestMenuControllerGroup" value="0x1060" /><IDSymbol name="cmdidMCItem1" value="0x0130" /><IDSymbol name="cmdidMCItem2" value="0x0131" /><IDSymbol name="cmdidMCItem3" value="0x0132" />  
    ```  
  
3.  V části nabídky po poslední položky nabídky, definujte jako nabídky řadičem nabídky.  
  
    ```xml  
    <Menu guid="guidTWTestCommandPackageCmdSet" id="TestMenuController" priority="0x0100" type="MenuController">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <CommandFlag>TextChanges</CommandFlag>  
        <CommandFlag>TextIsAnchorCommand</CommandFlag>  
        <Strings>  
            <ButtonText>Test Menu Controller</ButtonText>  
            <CommandName>Test Menu Controller</CommandName>  
        </Strings>  
    </Menu>  
    ```  
  
     `TextChanges` a `TextIsAnchorCommand` příznaky musí být zahrnut povolit řadičem nabídky tak, aby odrážela poslední vybraný příkaz.  
  
4.  Ve skupinách části poslední položku skupiny, přidejte skupinu řadiče nabídky.  
  
    ```xml  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" priority="0x000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuController" />  
    </Group>  
    ```  
  
     Nastavením řadičem nabídky jako nadřazená položka žádné příkazy umístěny v této skupině zobrazí v nabídce kontroleru. `priority` Atribut je vynechán, která nastaví na výchozí hodnotu 0, protože budou pouze skupiny na řadiči nabídky.  
  
5.  V části tlačítka po poslední tlačítko položky, přidejte Button element pro každou z položek nabídky.  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="cmdidMCItem1" priority="0x0000" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <Strings>  
            <ButtonText>MC Item 1</ButtonText>  
            <CommandName>MC Item 1</CommandName>  
        </Strings>  
    </Button>  
    <Button guid="guidTWTestCommandPackageCmdSet" id="cmdidMCItem2" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" />  
        <Icon guid="guidImages" id="bmpPic2" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <Strings>  
            <ButtonText>MC Item 2</ButtonText>  
            <CommandName>MC Item 2</CommandName>  
        </Strings>  
    </Button>  
    <Button guid="guidTWTestCommandPackageCmdSet" id="cmdidMCItem3" priority="0x0200" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" />  
        <Icon guid="guidImages" id="bmpPicSearch" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <Strings>  
            <ButtonText>MC Item 3</ButtonText>  
            <CommandName>MC Item 3</CommandName>  
        </Strings>  
    </Button>  
    ```  
  
6.  V tomto okamžiku můžete prohlížet řadičem nabídky. Sestavte projekt a spusťte ladění. Měli byste vidět experimentální instanci.  
  
    1.  Na **zobrazení nebo ostatní okna** nabídce otevřete **okno Test nástrojů**.  
  
    2.  Řadiče nabídky se zobrazí na panelu nástrojů v okně nástroje.  
  
    3.  Klikněte na šipku na pravé straně nabídky řadiče se tři možné příkazy.  
  
     Všimněte, že když kliknete příkaz, název nabídky řadiče změní k zobrazení tohoto příkazu. V další části přidáme kód pro aktivaci těchto příkazů.  
  
## <a name="implementing-the-menu-controller-commands"></a>Implementace řadiče příkazy nabídky  
  
1.  V TWTestCommandPackageGuids.cs přidejte po existující příkaz ID ID příkazu pro vaše položky tři nabídky.  
  
    ```csharp  
    public const int cmdidMCItem1 = 0x130;  
    public const int cmdidMCItem2 = 0x131;  
    public const int cmdidMCItem3 = 0x132;  
    ```  
  
2.  V TWTestCommand.cs přidejte následující kód v horní části třídy TWTestCommand.  
  
    ```csharp  
    private int currentMCCommand; // The currently selected menu controller command  
    ```  
  
3.  V konstruktoru TWTestCommand po posledním volání `AddCommand` metoda, přidat kód pro směrování události pro každý příkaz prostřednictvím stejné obslužné rutiny.  
  
    ```csharp  
    for (int i = TWTestCommandPackageGuids.cmdidMCItem1; i <=  
        TWTestCommandPackageGuids.cmdidMCItem3; i++)  
    {  
        CommandID cmdID = new  
        CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), i);  
        OleMenuCommand mc = new OleMenuCommand(new  
          EventHandler(OnMCItemClicked), cmdID);  
        mc.BeforeQueryStatus += new EventHandler(OnMCItemQueryStatus);  
        commandService.AddCommand(mc);  
        // The first item is, by default, checked.   
        if (TWTestCommandPackageGuids.cmdidMCItem1 == i)  
        {  
            mc.Checked = true;  
            this.currentMCCommand = i;  
        }  
    }  
    ```  
  
4.  Přidání obslužné rutiny události pro třídu TWTestCommand označit vybraný příkaz jako zaškrtnuté.  
  
    ```csharp  
    private void OnMCItemQueryStatus(object sender, EventArgs e)  
    {  
        OleMenuCommand mc = sender as OleMenuCommand;  
        if (null != mc)  
        {  
            mc.Checked = (mc.CommandID.ID == this.currentMCCommand);  
        }  
    }  
    ```  
  
5.  Přidání obslužné rutiny události, který se zobrazí MessageBox, když uživatel vybere příkaz nabídky řadiče:  
  
    ```csharp  
    private void OnMCItemClicked(object sender, EventArgs e)  
    {  
        OleMenuCommand mc = sender as OleMenuCommand;  
        if (null != mc)  
        {  
            string selection;  
            switch (mc.CommandID.ID)  
            {  
                case c.cmdidMCItem1:  
                    selection = "Menu controller Item 1";  
                    break;  
  
                case TWTestCommandPackageGuids.cmdidMCItem2:  
                    selection = "Menu controller Item 2";  
                    break;  
  
                case TWTestCommandPackageGuids.cmdidMCItem3:  
                    selection = "Menu controller Item 3";  
                    break;  
  
                default:  
                    selection = "Unknown command";  
                    break;  
            }  
            this.currentMCCommand = mc.CommandID.ID;  
  
            IVsUIShell uiShell =  
              (IVsUIShell) ServiceProvider.GetService(typeof(SVsUIShell));  
            Guid clsid = Guid.Empty;  
            int result;  
            uiShell.ShowMessageBox(  
                       0,  
                       ref clsid,  
                       "Test Tool Window Toolbar Package",  
                       string.Format(CultureInfo.CurrentCulture,  
                                     "You selected {0}", selection),  
                       string.Empty,  
                       0,  
                       OLEMSGBUTTON.OLEMSGBUTTON_OK,  
                       OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
                       OLEMSGICON.OLEMSGICON_INFO,  
                       0,  
                       out result);  
        }  
    }  
    ```  
  
## <a name="testing-the-menu-controller"></a>Testování řadičem nabídky  
  
1.  Sestavte projekt a spusťte ladění. Měli byste vidět experimentální instanci.  
  
2.  Otevřete **okno Test nástrojů** na **zobrazení nebo ostatní okna** nabídky.  
  
     Řadičem nabídky se zobrazí na panelu nástrojů v okně nástroje a zobrazí **MC položka 1**.  
  
3.  Klikněte na tlačítko řadiče nabídce nalevo na šipku.  
  
     Měli byste vidět tři položky, první z nich je vybraná a kolem jeho ikonu obdélník zvýraznění. Klikněte na tlačítko **MC položky 3**.  
  
     Zobrazí se dialogové okno se zprávou **jste vybrali nabídky řadiče 3 položky**. Všimněte si, zda zpráva odpovídá na text na tlačítku řadiče nabídky. Tlačítko nabídky řadiče teď zobrazuje **3 položky MC**.  
  
## <a name="see-also"></a>Viz také  
 [Přidávání panelů nástrojů do okno nástroje](../extensibility/adding-a-toolbar-to-a-tool-window.md)   
 [Přidání panelu nástrojů](../extensibility/adding-a-toolbar.md)