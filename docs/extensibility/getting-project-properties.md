---
title: Získání vlastností projektu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties, displaying in tool window
- tool windows, displaying project propeties
ms.assetid: 96ba07ca-0811-4013-8602-12550ac4ba79
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d93e941c98293ca1d28f92bce1bc8c21f5ca2121
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127621"
---
# <a name="getting-project-properties"></a>Získání vlastností projektu
Tento návod ukazuje, jak vlastnosti projektu zobrazí v okně nástroje.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="to-create-a-vsix-project-and-add-a-tool-window"></a>Vytvoření projektu VSIX a přidat okno nástroje  
  
1.  Každé rozšíření sady Visual Studio začíná projekt nasazení VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projektu s názvem `ProjectPropertiesExtension`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Přidat okno nástroje přidáním okno nástroje vlastní šablonu položka s názvem `ProjectPropertiesToolWindow`. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **dialogové okno Přidat novou položku**, přejděte na **Visual C# položky nebo rozšíření** a vyberte **okno nástroje vlastní**. V **název** pole v dolní části dialogového okna, změňte název souboru `ProjectPropertiesToolWindow.cs`. Další informace o tom, jak vytvořit vlastní nástroj okno najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
3.  Sestavte řešení a ověřte, že se zkompiluje bez chyb.  
  
### <a name="to-display-project-properties-in-a-tool-window"></a>Chcete-li zobrazit vlastnosti projektu v okně nástroje  
  
1.  V souboru ProjectPropertiesToolWindowCommand.cs přidejte následující příkazy using.  
  
    ```csharp  
    using EnvDTE;  
    using System.Windows.Controls;  
  
    ```  
  
2.  V ProjectPropertiesToolWindowControl.xaml odeberte existující tlačítko a přidejte elementu TreeView z panelu nástrojů. Rovněž můžete odebrat obslužnou rutinu události kliknutí ze souboru ProjectPropertiesToolWindowControl.xaml.cs.  
  
3.  V ProjectPropertiesToolWindowCommand.cs použijte metodu ShowToolWindow() projektu otevřít a přečíst si jeho vlastnosti a pak přidejte vlastnosti do stromovém zobrazení. Kód pro ShowToolWindow by měl vypadat asi takto:  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        ToolWindowPane window = this.package.FindToolWindow(typeof(ProjectPropertiesToolWindow), 0, true);  
        if ((null == window) || (null == window.Frame))  
        {  
            throw new NotSupportedException("Cannot create window.");  
        }  
        IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
  
        // Get the tree view and populate it if there is a project open.  
        ProjectPropertiesToolWindowControl control = (ProjectPropertiesToolWindowControl)window.Content;  
        TreeView treeView = control.treeView;  
  
        // Reset the TreeView to 0 items.  
        treeView.Items.Clear();  
  
        DTE dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
        Projects projects = dte.Solution.Projects;  
        if (projects.Count == 0)   // no project is open  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.Name = "Projects";  
            item.ItemsSource = new string[]{ "no projects are open." };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
            return;  
        }  
  
        Project project = projects.Item(1);  
        TreeViewItem item1 = new TreeViewItem();  
        item1.Header = project.Name + "Properties";  
        treeView.Items.Add(item1);  
  
        foreach (Property property in project.Properties)  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.ItemsSource = new string[] { property.Name };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
        }  
    }  
    ```  
  
4.  Sestavte projekt a spusťte ladění. Experimentální instanci by se zobrazit.  
  
5.  V experimentální instanci otevřete projekt.  
  
6.  V **zobrazení nebo ostatní okna** klikněte na tlačítko **ProjectPropertiesToolWindow**.  
  
     Měli byste vidět stromu ovládacího prvku panel nástrojů společně s název první projekt a všechny jeho vlastnosti projektu.