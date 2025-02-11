---
title: Změna textu příkazu nabídky | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, changing text
- text, menus
- commands, changing text
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
caps.latest.revision: 26
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d8fd3fc01a5dd3e10e633b876b719695d6b26c18
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184495"
---
# <a name="changing-the-text-of-a-menu-command"></a>Změna textu příkazu nabídky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Následující kroky ukazují, jak změnit textový popisek příkazu nabídky pomocí <xref:System.ComponentModel.Design.IMenuCommandService> služby.  
  
## <a name="changing-a-menu-command-label-with-the-imenucommandservice"></a>Změna popisek příkaz nabídky s IMenuCommandService  
  
1. Vytvořte projekt VSIX s názvem `MenuText` pomocí příkazu nabídky s názvem **ChangeMenuText**. Další informace najdete v tématu [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2. V souboru .vstc, přidejte `TextChanges` příznak, který příkaz nabídky, jak je znázorněno v následujícím příkladu.  
  
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
  
3. V souboru ChangeMenuText.cs vytvořte obslužnou rutinu události, která bude volána před provedením příkazu nabídky se zobrazí.  
  
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
  
     Stav příkazu nabídky v této metody můžete také aktualizovat tak, že změníte <xref:System.ComponentModel.Design.MenuCommand.Visible%2A>, <xref:System.ComponentModel.Design.MenuCommand.Checked%2A>, a <xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> vlastnosti <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objektu.  
  
4. V konstruktoru ChangeMenuText nahradit původní kód inicializace a umístění příkazu s kódem, který vytvoří <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> (spíše než `MenuCommand`), který představuje příkaz nabídky, přidá <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> obslužná rutina události a poskytuje v nabídce příkaz pro službu příkazu nabídky.  
  
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
  
5. Sestavte projekt a spusťte ladění. Experimentální instanci sady Visual Studio se zobrazí.  
  
6. Na **nástroje** nabídky by se měla zobrazit příkaz s názvem **vyvolat ChangeMenuText**.  
  
7. Klikněte na příkaz. Měli byste vidět zprávu pole oznamujeme, že MenuItemCallback byla volána. Při zavírání okna se zprávou, byste měli vidět, že název příkazu v nabídce Nástroje nyní **nový Text**.
