---
title: Změna vzhledu příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, changing appearance
- menu commands, changing appearance
- menus, changing command appearance
ms.assetid: da2474fa-f92d-4e9e-b8bf-67c61bf249c2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4a19793f16991bc61636a929822757823728a926
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="changing-the-appearance-of-a-command"></a>Změna vzhledu příkazu
Změnou vzhledu příkazu můžete poskytnutí zpětné vazby pro vaše uživatele. Například můžete příkazu, který bude vypadat jinak, když není k dispozici. Můžete nastavit příkazy k dispozici nebo není k dispozici, skrýt nebo je zobrazit, nebo zaškrtněte nebo zrušte zaškrtnutí je v nabídce.  
  
 Chcete-li změnit vzhled příkazu, proveďte jednu z těchto akcí:  
  
-   Zadejte příslušnými příznaky v definici příkazu do příkazového řádku tabulky.  
  
-   Použití <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> služby.  
  
-   Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní a změně objektů nezpracovaná příkaz.  
  
 Následující kroky ukazují, jak najít a aktualizovat vzhled příkaz s použitím spravovaných balíček Framework (MPF).  
  
### <a name="to-change-the-appearance-of-a-menu-command"></a>Chcete-li změnit vzhled příkazu nabídky  
  
1.  Postupujte podle pokynů v [změna Text příkazu v nabídce](../extensibility/changing-the-text-of-a-menu-command.md) vytvoříte položku nabídky s názvem `New Text`.  
  
2.  V souboru ChangeMenuText.cs, přidejte následující příkaz using:  
  
    ```csharp  
    using System.Security.Permissions;  
    ```  
  
3.  V souboru ChangeMenuTextPackageGuids.cs přidejte následující řádek:  
  
    ```csharp  
    public const string guidChangeMenuTextPackageCmdSet= "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    ```  
  
4.  V souboru ChangeMenuText.cs nahraďte kód v metodě ShowMessageBox s následujícími službami:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var command = sender as OleMenuCommand;  
        if (command.Text == "New Text")  
            ChangeMyCommand(command.CommandID.ID, false);}  
    }  
    ```  
  
5.  Získat příkaz, který chcete aktualizovat z <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> objektu a nastavte příslušné vlastnosti v objektu command. Například následující metodu provede zadaný příkaz z příkazu VSPackage nastavení k dispozici nebo není k dispozici. Následující kód vytvoří v nabídce položka s názvem `New Text` není k dispozici po bylo stisknuto.  
  
    ```csharp  
    public bool ChangeMyCommand(int cmdID, bool enableCmd)  
    {  
        bool cmdUpdated = false;  
        var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService))  
            as OleMenuCommandService;  
        var newCmdID = new CommandID(new Guid(ChangeMenuTextPackageGuids.guidChangeMenuTextPackageCmdSet), cmdID);  
        MenuCommand mc = mcs.FindCommand(newCmdID);  
        if (mc != null)  
        {  
            mc.Enabled = enableCmd;  
            cmdUpdated = true;  
        }  
        return cmdUpdated;    }  
    }  
    ```  
  
6.  Sestavte projekt a spusťte ladění. Experimentální instanci sady Visual Studio by se zobrazit.  
  
7.  Na **nástroje** nabídky, klikněte na tlačítko **vyvolání ChangeMenuText** příkaz. V tomto okamžiku je název příkazu **vyvolání ChangeMenuText**, aby obslužná rutina příkazu nemá zavolat ChangeMyCommand().  
  
8.  Na **nástroje** nabídky, měli byste vidět **nového textu**. Klikněte na tlačítko **nového textu**. Příkaz by měl nyní k dispozici.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Jak přidat VSPackages prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)