---
title: "Rozšíření ve výstupním okně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Output window, about Output window
ms.assetid: b02fa88c-f92a-4ff6-ba5f-2eb4d48a643a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8fa99e2c741d11c79cb41226e3958b04d0265621
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-output-window"></a>Rozšíření ve výstupním okně
**Výstup** okno je sada podokna text pro čtení a zápis. Visual Studio má tyto předdefinované podokna: **sestavení**, v projekty, které komunikují zprávy o sestavení a **Obecné**, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komunikuje zprávy o rozhraní IDE. Projekty získat odkaz na **sestavení** podokně automaticky pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> metody rozhraní a Visual Studio nabízí přímý přístup k **Obecné** podokně prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.SVsGeneralOutputWindowPane> Služba. Kromě předdefinovaných podokna můžete vytvořit a spravovat vlastní vlastního podokna.  
  
 Můžete řídit **výstup** okno přímo pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane> rozhraní. <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> Rozhraní, které nabízí <xref:Microsoft.VisualStudio.Shell.Interop.SVsOutputWindow> služby, definuje metody pro vytváření, získávání a odstraňování **výstup** podokna. <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> Rozhraní definuje metody pro zobrazení podoken, skrytí podokna a manipulace s jejich text. Alternativní způsob řízení **výstup** okno je prostřednictvím <xref:EnvDTE.OutputWindow> a <xref:EnvDTE.OutputWindowPane> objekty v modelu objektu automatizace Visual Studio. Tyto objekty zapouzdřují téměř všechny funkce <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane> rozhraní. Kromě toho <xref:EnvDTE.OutputWindow> a <xref:EnvDTE.OutputWindowPane> objekty přidat některé vyšší úrovně funkce usnadnění výčet **výstup** podokna a načtení textu ze podokna.  
  
## <a name="creating-an-extension-that-uses-the-output-pane"></a>Vytvoření rozšíření, která používá podokno výstup  
 Můžete nastavit příponu, která vykonává různých aspektů podokno výstup.  
  
1.  Vytvoření projektu VSIX s názvem `TestOutput` pomocí příkazu nabídky s názvem **TestOutput**. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Přidejte následující odkazy:  
  
    1.  EnvDTE  
  
    2.  EnvDTE80  
  
3.  V TestOutput.cs, přidejte následující příkaz using:  
  
    ```f#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  V TestOutput.cs odstraňte metodu ShowMessageBox. Přidejte následující metodu stub:  
  
    ```csharp  
    private void OutputCommandHandler(object sender, EventArgs e)  
    {  
    }  
    ```  
  
5.  V konstruktoru TestOutput změňte na OutputCommandHandler obslužná rutina příkazu. Zde je část, která přidá příkazy:  
  
    ```csharp  
    OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
    if (commandService != null)  
    {  
        CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
        EventHandler eventHandler = OutputCommandHandler;  
        MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
        commandService.AddCommand(menuItem);  
    }  
    ```  
  
6.  V níže uvedených částech mají různé metody, které jsou ukázány různé způsoby práci s podokno výstup. Tyto metody do těla metody OutputCommandHandler() můžete volat. Následující kód například přidá metoda CreatePane() zadané v další části.  
  
    ```csharp  
    private void OutputCommandHandler(object sender, EventArgs e)  
    {  
        CreatePane(new Guid(), "Created Pane", true, false);  
    }  
    ```  
  
## <a name="creating-an-output-window-with-ivsoutputwindow"></a>Vytvoření výstupní okno s IVsOutputWindow  
 Tento příklad ukazuje, jak vytvořit nový **výstup** podokna pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> rozhraní.  
  
```csharp  
void CreatePane(Guid paneGuid, string title,   
    bool visible, bool clearWithSolution)  
{  
    IVsOutputWindow output =   
        (IVsOutputWindow)GetService(typeof(SVsOutputWindow));  
    IVsOutputWindowPane pane;  
  
    // Create a new pane.  
    output.CreatePane(  
        ref paneGuid,   
        title,   
        Convert.ToInt32(visible),   
        Convert.ToInt32(clearWithSolution));  
  
    // Retrieve the new pane.  
    output.GetPane(ref paneGuid, out pane);  
  
     pane.OutputString("This is the Created Pane \n");  
}  
```  
  
 Pokud tuto metodu přidejte rozšíření uveden v předchozím oddílu, po kliknutí na tlačítko **vyvolání TestOutput** příkaz, měli byste vidět **výstup** okno s hlavičku, která uvádí, že **zobrazit výstup z: CreatedPane** a slova **jde podokně vytvořit** v podokně sám sebe.  
  
## <a name="creating-an-output-window-with-outputwindow"></a>Vytvoření výstupní okno s OutputWindow  
 Tento příklad ukazuje, jak vytvořit **výstup** podokna pomocí <xref:EnvDTE.OutputWindow> objektu.  
  
```csharp  
void CreatePane(string title)  
{  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    OutputWindowPanes panes =  
        dte.ToolWindows.OutputWindow.OutputWindowPanes;  
  
    try  
    {  
        // If the pane exists already, write to it.  
        panes.Item(title);  
    }  
    catch (ArgumentException)  
    {  
        // Create a new pane and write to it.  
        return panes.Add(title);  
    }  
}  
```  
  
 I když <xref:EnvDTE.OutputWindowPanes> kolekce umožňuje načíst **výstup** podokna podle názvu, názvy podokně nemusí být jedinečný. Pokud jste pochybovat jedinečnosti produktu, použijte <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow.GetPane%2A> metoda pro načtení podokně správné podle její identifikátor GUID.  
  
 Pokud tuto metodu přidejte rozšíření uveden v předchozím oddílu, po kliknutí na tlačítko **vyvolání TestOutput** příkaz byste měli vidět ve výstupním okně s hlavičku, která uvádí, že **zobrazit výstup z: DTEPane** a slova **přidat podokně DTE** v podokně sám sebe.  
  
## <a name="deleting-an-output-window"></a>Odstraňuje se výstup – okno  
 Tento příklad ukazuje, jak odstranit **výstup** podokna.  
  
```csharp  
void DeletePane(Guid paneGuid)  
{  
    IVsOutputWindow output =  
    (IVsOutputWindow)ServiceProvider.GetService(typeof(SVsOutputWindow));  
  
    IVsOutputWindowPane pane;  
    output.GetPane(ref paneGuid, out pane);  
  
    if (pane == null)  
    {  
        CreatePane(paneGuid, "New Pane\n", true, true);  
    }  
     else  
    {  
        output.DeletePane(ref paneGuid);  
    }  
}  
```  
  
 Pokud tuto metodu přidejte rozšíření uveden v předchozím oddílu, po kliknutí na tlačítko **vyvolání TestOutput** příkaz byste měli vidět ve výstupním okně s hlavičku, která uvádí, že **zobrazit výstup z: nové podokno** a slova **přidat vytvořili podokně** v podokně sám sebe. Pokud kliknete **vyvolání TestOutput** příkaz znovu v podokně se odstraní.  
  
## <a name="getting-the-general-pane-of-the-output-window"></a>Získávání podokně Obecné v okně výstupu.  
 Tento příklad ukazuje, jak získat integrované **Obecné** podokně **výstup** okno.  
  
```csharp  
void GetGeneralPane()  
{  
    return (IVsOutputWindowPane)GetService(  
        typeof(SVsGeneralOutputWindowPane));  
}  
```  
  
 Pokud tuto metodu přidejte rozšíření uveden v předchozím oddílu, po kliknutí na tlačítko **vyvolání TestOutput** příkaz, měli byste vidět, který **výstup** v okně se zobrazí slova **nalezen obecné Podokno** v podokně.  
  
## <a name="getting-the-build-pane-of-the-output-window"></a>Získávání podokně sestavení v okně výstupu.  
 Tento příklad ukazuje, jak můžete najít v podokně sestavení a do něj zapisovat. Vzhledem k tomu, že ve výchozím nastavení není aktivována podokně sestavení, aktivuje jej také.  
  
```csharp  
void OutputTaskItemStringExExample(string buildMessage)  
{  
    EnvDTE80.DTE2 dte = (EnvDTE80.DTE2)ServiceProvider.GetService(typeof(EnvDTE.DTE));  
  
    EnvDTE.OutputWindowPanes panes =  
        dte.ToolWindows.OutputWindow.OutputWindowPanes;  
    foreach (EnvDTE.OutputWindowPane pane in panes)  
        {  
            if (pane.Name.Contains("Build"))  
            {  
                pane.OutputString(buildMessage + "\n");  
                pane.Activate();  
                return;  
             }  
        }  
}  
```