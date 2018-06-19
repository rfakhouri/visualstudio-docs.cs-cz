---
title: Pomocí nastavení úložiště | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Settings Store, using
ms.assetid: 447ec08a-eca5-40b8-89b0-f98fdf3d39a4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3919ee3973194967f9d0367ecd13c495b3b62af2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139286"
---
# <a name="using-the-settings-store"></a>Pomocí nastavení úložiště
Existují dva druhy nastavení úložiště:  
  
-   Nastavení konfigurace, které jsou jen pro čtení sady Visual Studio a VSPackage nastavení. Visual Studio sloučí nastavení z všechny známé .pkgdef soubory do tohoto úložiště.  
  
-   Uživatelská nastavení, která jsou zapisovatelné nastavení, jako jsou ty, které se zobrazují na stránkách v **možnosti** dialogové okno stránky vlastností a některé další dialogová okna. Rozšíření pro Visual Studio může použít pro místní úložiště malých objemů dat.  
  
 Tento návod ukazuje, jak číst data z úložiště nastavení konfigurace. V tématu [zápis do úložiště uživatelských nastavení](../extensibility/writing-to-the-user-settings-store.md) Další informace o tom, jak psát do úložiště uživatelských nastavení.  
  
## <a name="creating-the-example-project"></a>Vytváření příklad projektu  
 V této části ukazuje, jak vytvořit jednoduché rozšíření projekt se příkaz nabídky pro předvedení.  
  
1.  Každé rozšíření sady Visual Studio začíná projekt nasazení VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projektu s názvem `SettingsStoreExtension`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Nyní přidejte šablonu a vlastní příkaz položka s názvem **SettingsStoreCommand**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **vlastní příkaz**. V **název** pole v dolní části okna, změňte název souboru příkaz **SettingsStoreCommand.cs**. Další informace o tom, jak vytvořit vlastní příkaz najdete v tématu [vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
## <a name="using-the-configuration-settings-store"></a>Pomocí nastavení úložiště konfigurace  
 V této části ukazuje, jak zjistit a zobrazit nastavení konfigurace.  
  
1.  V souboru SettingsStorageCommand.cs, přidejte následující příkazy:  
  
    ```  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    using System.Windows.Forms;  
    ```  
  
2.  V `MenuItemCallback`, odeberte text metody a přidejte tyto řádky získat úložiště nastavení konfigurace:  
  
    ```  
    SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
    SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Settings.ShellSettingsManager> Je spravovaný pomocná třída přes <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager> služby.  
  
3.  Nyní zjistěte, jestli jsou nainstalované nástroje Windows Phone. Kód by měl vypadat takto:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        bool arePhoneToolsInstalled = configurationSettingsStore.CollectionExists(@"InstalledProducts\Microsoft Windows Phone Developer Tools");  
        string message = "Microsoft Windows Phone Developer Tools: " + arePhoneToolsInstalled;  
        MessageBox.Show(message);  
    }  
    ```  
  
4.  Testování kódu. Sestavte projekt a spusťte ladění.  
  
5.  V experimentální instanci na **nástroje** nabídky, klikněte na tlačítko **vyvolání SettingsStoreCommand**.  
  
     Měla by se zobrazit zpráva pole **vývojové nástroje společnosti Microsoft Windows Phone:** následuje **True** nebo **False**.  
  
 Visual Studio udržuje úložišti nastavení v registru systému.  
  
#### <a name="to-use-a-registry-editor-to-verify-configuration-settings"></a>Pomocí Editoru registru ověřte nastavení konfigurace  
  
1.  Otevřete Regedit.exe.  
  
2.  Přejděte na HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0Exp_Config\InstalledProducts\\.  
  
    > [!NOTE]
    >  Ujistěte se, že hledáte na klíč, který obsahuje \14.0Exp_Config\ a není \14.0_Config\\. Když spustíte experimentální instanci sady Visual Studio, jsou nastavení konfigurace v podregistru "14.0Exp_Config".  
  
3.  Rozbalte uzel \Installed Products\. Pokud zpráva v předchozích krocích je **nástroje Microsoft Windows Phone Developer nainstalovat: True**, pak \Installed Products\ by měl obsahovat uzlem Microsoft Windows Phone Developer Tools. Pokud zpráva je **nástroje Microsoft Windows Phone Developer nainstalovat: False**, pak \Installed Products\ nesmí obsahovat uzlem Microsoft Windows Phone Developer Tools.