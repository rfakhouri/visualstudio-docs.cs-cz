---
title: Rozšíření na stavovém řádku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- status bars, about status bars
- status bars, overview
ms.assetid: f955115c-4c5f-45ec-b41b-365868c5ec0c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a766e0c607d4d669fada794e1cf0779559f2346b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130489"
---
# <a name="extending-the-status-bar"></a>Rozšíření stavového řádku
Stavový řádek sady Visual Studio můžete v dolní části rozhraní IDE pro zobrazení informací.  
  
 Když rozšíříte stavového řádku, můžete zobrazit informace a uživatelského rozhraní v čtyři oblasti: oblasti zpětnou vazbu, indikátoru průběhu, oblast animace a oblasti návrháře. Oblasti zpětné vazby umožňuje zobrazit text a zvýraznit zobrazovaného textu. Indikátor průběhu ukazuje přírůstkové průběhu pro operace krátce běžící například ukládání souboru. Oblasti animace zobrazí animace průběžně smyčce dlouho běžící operace nebo operace neurčená délky, jako je například sestavování více projektů v řešení. A oblasti návrháře zobrazuje číslo řádku a ve sloupci umístění kurzoru.  
  
 Stavový řádek můžete získat pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> rozhraní (z <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> služby). Kromě toho můžete zaregistrovat libovolný objekt umístěný na rámec okna jako stavovém řádku objekt klienta implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> rozhraní. Vždy, když okno se aktivuje, Visual Studio dotazuje umístěný v tomto okně pro objekt `IVsStatusbarUser` rozhraní. Pokud se najde, zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> metodu na vrácených rozhraní a objekt můžete aktualizovat stavového řádku z v rámci této metody. Windows, například dokumentů, můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> metoda aktualizovat informace v oblasti návrháře, když bude aktivní.  
  
 Následujících postupech se předpokládá, že rozumíte postup vytvoření projektu VSIX a přidání příkazu vlastní nabídky. Informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="modifying-the-status-bar"></a>Úprava stavového řádku  
 Tento postup ukazuje, jak nastavit a získáte text, zobrazit statický text a zvýrazněte zobrazovaného textu v oblasti zpětnou vazbu na stavovém řádku.  
  
#### <a name="reading-and-writing-to-the-status-bar"></a>Čtení a zápis do stavového řádku  
  
1.  Vytvoření projektu VSIX s názvem **TestStatusBarExtension** a přidejte příkaz nabídky s názvem **TestStatusBarCommand**.  
  
2.  V TestStatusBarCommand.cs nahraďte kód metoda obslužná rutina příkazu (MenuItemCallback) s následujícími službami:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Make sure the status bar is not frozen  
        int frozen;  
  
        statusBar.IsFrozen(out frozen);  
  
        if (frozen != 0)   
        {  
            statusBar.FreezeOutput(0);  
        }  
  
        // Set the status bar text and make its display static.  
        statusBar.SetText("We just wrote to the status bar.");  
  
        // Freeze the status bar.  
        statusBar.FreezeOutput(1);  
  
        // Get the status bar text.   
        string text;  
        statusBar.GetText(out text);  
        System.Windows.Forms.MessageBox.Show(text);  
  
        // Clear the status bar text.  
        statusBar.FreezeOutput(0);  
        statusBar.Clear();  
    }  
    ```  
  
3.  Zkompilovat kód a spusťte ladění.  
  
4.  Otevřete **nástroje** nabídky v experimentální instanci sady Visual Studio. Klikněte **vyvolání TestStatusBarCommand** tlačítko.  
  
     Měli byste vidět, který text ve stavovém řádku nyní čtení **"Právě napsali jsme na stavovém řádku."** a zobrazeném dialogovém okně se stejný text.  
  
#### <a name="updating-the-progress-bar"></a>Aktualizace indikátoru průběhu  
  
1.  V tomto postupu jsme se ukazují, jak k inicializaci a aktualizovat indikátor průběhu.  
  
2.  Otevřete soubor TestStatusBarCommand.cs a metodu MenuItemCallback nahraďte následujícím kódem:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
        uint cookie = 0;  
        string label = "Writing to the progress bar";  
  
        // Initialize the progress bar.  
        statusBar.Progress(ref cookie, 1, "", 0, 0);  
  
        for (uint i = 0, total = 20; i <= total; i++)  
        {  
            // Display progress every second.  
            statusBar.Progress(ref cookie, 1, label, i, total);  
            System.Threading.Thread.Sleep(1000);  
        }  
  
        // Clear the progress bar.  
        statusBar.Progress(ref cookie, 0, "", 0, 0);  
    }  
    ```  
  
3.  Zkompilovat kód a spusťte ladění.  
  
4.  Otevřete **nástroje** nabídky v experimentální instanci sady Visual Studio. Klikněte na tlačítko **vyvolání TestStatusBarCommand** tlačítko.  
  
     Měli byste vidět, který text ve stavovém řádku nyní čtení **"Zápis do indikátor průběhu."** Měli byste taky vidět indikátor průběhu aktualizovat každou sekundu 20 sekund. Následně se na stavovém řádku a indikátor průběhu, jsou vymazány.  
  
#### <a name="displaying-an-animation"></a>Zobrazení animace  
  
1.  Stavový řádek zobrazí opakování animace, která určuje, buď dlouho běžící operace (například sestavování více projektů v určitém řešení). Pokud se tato animace nezobrazí, ujistěte se, máte správný **Nástroje / možnosti** nastavení:  
  
     Přejděte na **Nástroje/možnosti / Obecné** kartě a zrušte zaškrtnutí políčka **automaticky upravit visual prostředí založené na výkon klienta**. Pak zkontrolujte možnost dílčí **Povolit plně funkčního klienta visual prostředí**. Teď by měla být animace uvidí, když vytváříte projekt v experimentální instanci sady Visual Studio.  
  
     V tomto postupu, zobrazuje se standardní animace Visual Studio, která představuje vytváření projekt nebo řešení.  
  
2.  Otevřete soubor TestStatusBarCommand.cs a metodu MenuItemCallback nahraďte následujícím kódem:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar =(IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Use the standard Visual Studio icon for building.  
        object icon = (short)Microsoft.VisualStudio.Shell.Interop.Constants.SBAI_Build;  
  
        // Display the icon in the Animation region.  
        statusBar.Animation(1, ref icon);  
  
        // The message box pauses execution for you to look at the animation.  
        System.Windows.Forms.MessageBox.Show("showing?");  
  
        // Stop the animation.   
        statusBar.Animation(0, ref icon);  
    }  
    ```  
  
3.  Zkompilovat kód a spusťte ladění.  
  
4.  Otevřete **nástroje** nabídky v sadě Visual Studio a klikněte na tlačítko experimentální instanci **vyvolání TestStatusBarCommand**.  
  
     Když se zobrazí okno se zprávou, měli byste taky vidět animace ve stavovém řádku úplně vpravo. Pokud jste zavřít okno se zprávou, animace zmizí.