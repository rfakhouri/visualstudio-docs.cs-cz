---
title: Vytváření a správa modálních dialogových oken | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- dialog boxes, managing in Visual Studio
ms.assetid: 491bc0de-7dba-478c-a76b-923440e090f3
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 29b0066f201fbb791d471d5cfb433d9a335aa775
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62431573"
---
# <a name="creating-and-managing-modal-dialog-boxes"></a>Vytváření a správa modálních dialogových oken
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když vytvoříte modální dialogové okno v sadě Visual Studio, je nutné zajistit, že nadřazené okno dialogového okna je zakázán, když se zobrazí dialogové okno a potom znovu povolit nadřazené okno po zavření dialogových oken. Pokud to neprovedete, zobrazí se chybová zpráva: "Microsoft Visual Studio nelze vypnout, protože je aktivní modální dialogové okno. Zavřete aktivní dialogové okno a zkuste to znovu."  
  
 To provést dvěma způsoby. Doporučeným způsobem, pokud máte dialogovému oknu WPF, je odvozena z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>a pak vyvolejte <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.ShowModal%2A> k zobrazení dialogového okna. Pokud to uděláte, není potřeba spravovat modální stav nadřazeného okna.  
  
 Pokud vaše dialogové okno není WPF nebo pro některého jiného důvodu, že nemůžete odvodit vestavěnou vašem dialogovém okně třídy z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>, pak nadřazené dialogových oken, musíte získat voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.GetDialogOwnerHwnd%2A> a správa modálních stavu sami, voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.EnableModeless%2A> metodou Parametr 0 (false) před zobrazením dialogového okna a volání metody znovu s parametrem 1 (pravda). po zavření dialogového okna.  
  
## <a name="creating-a-dialog-box-derived-from-dialogwindow"></a>Vytvoření dialogového okna odvozený od DialogWindow  
  
1. Vytvořte projekt VSIX s názvem **OpenDialogTest** a přidání příkazu nabídky s názvem **OpenDialog**. Další informace o tom, jak to provést, najdete v části [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2. Použít <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> třídy, je nutné přidat odkazy na následující sestavení (na kartě Framework **přidat odkaz** dialogové okno):  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - WindowsBase  
  
    - System.Xaml  
  
3. V souboru OpenDialog.cs, přidejte následující `using` – příkaz:  
  
    ```csharp  
    using Microsoft.VisualStudio.PlatformUI;  
    ```  
  
4. Deklarovat třídu s názvem **TestDialogWindow** , která je odvozena z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>:  
  
    ```csharp  
    class TestDialogWindow : DialogWindow  
    {. . .}  
    ```  
  
5. Aby bylo možné minimalizovat a maximalizovat dialogové okno, nastavte <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMaximizeButton%2A> a <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMinimizeButton%2A> na hodnotu true:  
  
    ```csharp  
    internal TestDialogWindow()  
    {  
        this.HasMaximizeButton = true;  
        this.HasMinimizeButton = true;  
    }  
    ```  
  
6. V **OpenDialog.ShowMessageBox** metoda, nahraďte existující kód následujícím kódem:  
  
    ```csharp  
    TestDialogWindow testDialog = new TestDialogWindow();  
    testDialog.ShowModal();  
    ```  
  
7. Sestavte a spusťte aplikaci. Experimentální instanci sady Visual Studio by se zobrazit. Na **nástroje** nabídky experimentální instanci byste měli vidět příkaz s názvem **vyvolat OpenDialog**. Po kliknutí na tento příkaz, měli byste vidět dialogového okna. Byste měli minimalizovat a maximalizujte okno.  
  
## <a name="creating-and-managing-a-dialog-box-not-derived-from-dialogwindow"></a>Vytváření a správa dialogové okno není odvozeno od DialogWindow  
  
1. Pro tento postup můžete použít **OpenDialogTest** řešení, které jste vytvořili v předchozím postupu, s odkazy na stejné sestavení.  
  
2. Přidejte následující `using` deklarace:  
  
    ```csharp  
    using System.Windows;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    ```  
  
3. Vytvořte třídu s názvem **TestDialogWindow2** , která je odvozena z <xref:System.Windows.Window>:  
  
    ```csharp  
    class TestDialogWindow2 : Window  
    {. . .}  
    ```  
  
4. Přidejte odkaz na privátní <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>:  
  
    ```  
    private IVsUIShell shell;  
    ```  
  
5. Přidat konstruktor, který nastaví odkaz na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>:  
  
    ```csharp  
    public TestDialogWindow2(IVsUIShell uiShell)  
    {  
        shell = uiShell;  
    }  
    ```  
  
6. V **OpenDialog.ShowMessageBox** metoda, nahraďte existující kód následujícím kódem:  
  
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
  
7. Sestavte a spusťte aplikaci. Na **nástroje** nabídky by se měla zobrazit příkaz s názvem **vyvolat OpenDialog**. Po kliknutí na tento příkaz, měli byste vidět dialogového okna.
