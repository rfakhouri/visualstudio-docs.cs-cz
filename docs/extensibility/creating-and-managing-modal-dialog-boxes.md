---
title: "Vytváření a správa modální dialogová okna | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dialog boxes, managing in Visual Studio
ms.assetid: 491bc0de-7dba-478c-a76b-923440e090f3
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dc53145a52d6b902ef1b8d15195df37ee6de0d62
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-and-managing-modal-dialog-boxes"></a>Vytváření a správa modálních dialogových oken
Při vytváření modální dialogové okno v sadě Visual Studio, je nutné zakázat nadřazeného okna dialogového okna, když se zobrazí dialogové okno a potom znovu povolit nadřazeného okna po zavření dialogu. Pokud to neuděláte, může dojít k chybě: "Microsoft Visual Studio nelze vypnout, protože modální dialogové okno je aktivní. Zavřete dialogové okno aktivní a akci opakujte."  
  
 To provést dvěma způsoby. Doporučený způsob, pokud máte WPF dialogového okna, je odvozena z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>a pak zavolají <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.ShowModal%2A> k zobrazení dialogového okna. Pokud to uděláte, není potřeba spravovat modální stav nadřazeného okna.  
  
 Pokud vaše dialogové okno není WPF nebo některé další důvod nelze odvodit vašem dialogovém okně třídy z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>, pak nadřazené dialogového okna, musíte si voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.GetDialogOwnerHwnd%2A> a spravovat stav modální sami, voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.EnableModeless%2A> metoda s Parametr 0 (false) před zobrazením dialogového okna a volání metody znovu s parametrem 1 (pravda). po zavření dialogového okna.  
  
## <a name="creating-a-dialog-box-derived-from-dialogwindow"></a>Vytvoření dialogového odvozené z DialogWindow  
  
1.  Vytvoření projektu VSIX s názvem **OpenDialogTest** a přidejte příkaz nabídky s názvem **OpenDialog**. Další informace o tom, jak to udělat najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Použít <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> třídy, je nutné přidat odkazy na následující sestavení (na kartě Framework **přidat odkaz na** dialogové okno):  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   System.Xaml  
  
3.  V OpenDialog.cs, přidejte následující `using` příkaz:  
  
    ```csharp  
    using Microsoft.VisualStudio.PlatformUI;  
    ```  
  
4.  Deklarace třídy s názvem **TestDialogWindow** která je odvozena od <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>:  
  
    ```csharp  
    class TestDialogWindow : DialogWindow  
    {. . .}  
    ```  
  
5.  Abyste mohli minimalizovat a maximalizovat dialogové okno, nastavte <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMaximizeButton%2A> a <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMinimizeButton%2A> na hodnotu true:  
  
    ```csharp  
    internal TestDialogWindow()  
    {  
        this.HasMaximizeButton = true;  
        this.HasMinimizeButton = true;  
    }  
    ```  
  
6.  V **OpenDialog.ShowMessageBox** metody existujícího kódu nahraďte následujícím kódem:  
  
    ```csharp  
    TestDialogWindow testDialog = new TestDialogWindow();  
    testDialog.ShowModal();  
    ```  
  
7.  Sestavte a spusťte aplikaci. Experimentální instanci sady Visual Studio by se zobrazit. Na **nástroje** nabídky experimentální instanci byste měli vidět příkaz s názvem **vyvolání OpenDialog**. Když kliknete na tento příkaz, měli byste vidět dialogového okna. Nyní byste měli mít minimalizovat a maximalizujte okno.  
  
## <a name="creating-and-managing-a-dialog-box-not-derived-from-dialogwindow"></a>Vytváření a správa dialogové okno není odvozen od DialogWindow  
  
1.  Pro tento postup můžete použít **OpenDialogTest** řešení, které jste vytvořili v předchozím postupu, s odkazy na stejné sestavení.  
  
2.  Přidejte následující `using` deklarace:  
  
    ```csharp  
    using System.Windows;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    ```  
  
3.  Vytvoření třídy s názvem **TestDialogWindow2** která je odvozena od <xref:System.Windows.Window>:  
  
    ```csharp  
    class TestDialogWindow2 : Window  
    {. . .}  
    ```  
  
4.  Přidat odkaz na privátní <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>:  
  
    ```  
    private IVsUIShell shell;  
    ```  
  
5.  Přidejte konstruktor, který nastaví odkaz na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>:  
  
    ```csharp  
    public TestDialogWindow2(IVsUIShell uiShell)  
    {  
        shell = uiShell;  
    }  
    ```  
  
6.  V **OpenDialog.ShowMessageBox** metody existujícího kódu nahraďte následujícím kódem:  
  
    ```csharp  
    IVsUIShell uiShell = (IVsUIShell)ServiceProvider.GetService(typeof(SVsUIShell));  
  
    TestDialogWindow2 testDialog2 = new TestDialogWindow2(uiShell);  
    //get the owner of this dialog  
    IntPtr hwnd;  
    uiShell.GetDialogOwnerHwnd(out hwnd);  
    testDialog2.WindowStartupLocation = System.Windows.WindowStartupLocation.CenterOwner;  
    uiShell.EnableModeless(0);  
    try  
    {  
        WindowHelper.ShowModal(testDialog2, hwnd);  
    }  
    finally  
    {  
        // This will take place after the window is closed.  
        uiShell.EnableModeless(1);  
    }  
    ```  
  
7.  Sestavte a spusťte aplikaci. Na **nástroje** nabídky byste měli vidět příkaz s názvem **vyvolání OpenDialog**. Když kliknete na tento příkaz, měli byste vidět dialogového okna.