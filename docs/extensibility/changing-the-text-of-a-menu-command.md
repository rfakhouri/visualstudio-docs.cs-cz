---
title: Změna textu příkazu nabídky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, changing text
- text, menus
- commands, changing text
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6ba19a6536be7f0f5855ee9035e80989c105cbf7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321113"
---
# <a name="change-the-text-of-a-menu-command"></a>Změna textu příkazu nabídky
Následující kroky ukazují, jak změnit textový popisek příkazu nabídky pomocí <xref:System.ComponentModel.Design.IMenuCommandService> služby.

## <a name="changing-a-menu-command-label-with-the-imenucommandservice"></a>Změna popisek příkaz nabídky s IMenuCommandService

1. Vytvořte projekt VSIX s názvem `MenuText` pomocí příkazu nabídky s názvem **ChangeMenuText**. Další informace najdete v tématu [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).

2. V *.vsct* přidejte `TextChanges` příznak, který příkaz nabídky, jak je znázorněno v následujícím příkladu.

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

3. V *ChangeMenuText.cs* soubor, vytvořit obslužnou rutinu události, která bude volána před provedením příkazu nabídky se zobrazí.

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

7. Klikněte na příkaz. Měli byste vidět okně se zprávou, která oznámení **MenuItemCallback** byla volána. Při zavírání okna se zprávou, byste měli vidět, že název příkazu v nabídce Nástroje nyní **nový Text**.
