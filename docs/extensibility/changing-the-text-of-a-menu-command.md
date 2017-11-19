---
title: "Změna Text příkazu nabídky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus, changing text
- text, menus
- commands, changing text
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 65e7d3d4e3d9a4034a948ee0fa094efbb45b6a93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="changing-the-text-of-a-menu-command"></a>Změna Text příkazu nabídky
Následující kroky ukazují, jak změnit textový popisek příkazu nabídky pomocí <xref:System.ComponentModel.Design.IMenuCommandService> služby.  
  
## <a name="changing-a-menu-command-label-with-the-imenucommandservice"></a>Změna popisek příkaz nabídky IMenuCommandService  
  
1.  Vytvoření projektu VSIX s názvem `MenuText` pomocí příkazu nabídky s názvem **ChangeMenuText**. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  V souboru .vstc, přidejte `TextChanges` příznak do příkazu nabídky, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <Button guid="guidChangeMenuTextPackageCmdSet" id="ChangeMenuTextId" priority="0x0100" type="Button">  
        <Parent guid="guidChangeMenuTextPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <CommandFlag>TextChanges</CommandFlag>  
        <Strings>  
            <ButtonText>Invoke ChangeMenuText</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
3.  V souboru ChangeMenuText.cs vytvořte obslužnou rutinu události, která bude volána před provedením příkazu nabídky se zobrazí.  
  
    ```csharp  
    private void OnBeforeQueryStatus(object sender, EventArgs e)  
    {  
        var myCommand = sender as OleMenuCommand;  
        if (null != myCommand)  
        {  
            myCommand.Text = "New Text";  
        }  
    }  
    ```  
  
     Můžete také aktualizovat stav příkazu nabídky v této metodě změnou <xref:System.ComponentModel.Design.MenuCommand.Visible%2A>, <xref:System.ComponentModel.Design.MenuCommand.Checked%2A>, a <xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> vlastnosti <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objektu.  
  
4.  V konstruktoru ChangeMenuText nahradit původní příkaz inicializace umístění kód a kód, který vytvoří <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> (ne `MenuCommand`), představuje příkaz nabídky, přidá <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> obslužné rutiny události a dává v nabídce příkaz ke službě příkaz nabídky.  
  
     Zde je, co by měl vypadat jako:  
  
    ```csharp  
    private ChangeMenuText(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            OleMenuCommand menuItem = new OleMenuCommand(ShowMessageBox, menuCommandID);  
            menuItem.BeforeQueryStatus +=  
                new EventHandler(OnBeforeQueryStatus);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
5.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci sady Visual Studio.  
  
6.  Na **nástroje** nabídky byste měli vidět příkaz s názvem **vyvolání ChangeMenuText**.  
  
7.  Klikněte na příkaz. Měli byste vidět zprávu pole oznamující, že MenuItemCallback byla volána. Pokud můžete zavřít okno se zprávou, měli byste vidět, název příkazu v nabídce Nástroje pro je nyní **nového textu**.
