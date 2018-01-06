---
title: "Získávání informací o službě z obchodu nastavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7028d440-d16d-4b08-9b94-eb8cc93b25fc
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fdb7e95a4a4379dfbab3e56cc21e9515bb23ec0d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getting-service-information-from-the-settings-store"></a>Získávání informací o službě z obchodu nastavení
Nastavení úložiště můžete použít k vyhledání všech dostupných služeb nebo k určení, zda je nainstalována konkrétní službu. Typ třídy služeb, musíte znát.  
  
### <a name="to-list-the-available-services"></a>Seznam dostupných služeb  
  
1.  Vytvoření projektu VSIX s názvem FindServicesExtension a poté přidejte vlastní příkaz s názvem FindServicesCommand. Další informace o tom, jak vytvořit vlastní příkaz najdete v tématu [vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  V FindServicesCommand.cs, přidejte následující příkazy:  
  
    ```vb  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    using System.Windows.Forms;  
    ```  
  
3.  Získat úložiště nastavení konfigurace a potom najít podřízenou složku s názvem služby. Tato kolekce obsahuje všechny služby k dispozici. V metodě MenuItemCommand odeberte stávající kód a nahraďte ji následujícím textem:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        string message = "Available services:\n";  
        IEnumerable<string> collection = configurationSettingsStore.GetSubCollectionNames("Services");  
        int n = 0;  
        foreach (string service in collection)  
        {  
            message += configurationSettingsStore.GetString("Services\\" + service, "Name", "Unknown") + "\n";  
        }  
  
        MessageBox.Show(message);  
    }  
    ```  
  
4.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
5.  V experimentální instanci na **nástroje** nabídky, klikněte na tlačítko **vyvolání FindServicesCommand**.  
  
     Měli byste vidět okno se zprávou výpis všech služeb.  
  
     Pokud chcete ověřit tato nastavení, můžete použít editor registru.  
  
## <a name="finding-a-specific-service"></a>Vyhledání specifické služby  
 Můžete také <xref:Microsoft.VisualStudio.Settings.SettingsStore.CollectionExists%2A> metoda k určení, zda je nainstalována konkrétní službu. Typ třídy služeb, musíte znát.  
  
1.  V MenuItemCallback projektu, který jste vytvořili v předchozím postupu, vyhledejte v obchodě nastavení konfigurace `Services` kolekce, která obsahuje podřízenou složku s názvem podle identifikátor GUID služby. V takovém případě se podíváme pro službu nápovědy.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        string helpServiceGUID = typeof(SVsHelpService).GUID.ToString("B").ToUpper();  
        bool hasHelpService = configurationSettingsStore.CollectionExists("Services\\" + helpServiceGUID);  
        string message = "Help Service Available: " + hasHelpService;  
  
        MessageBox.Show(message);  
    }  
    ```  
  
2.  Sestavte projekt a spusťte ladění.  
  
3.  V experimentální instanci na **nástroje** nabídky, klikněte na tlačítko **vyvolání FindServicesCommand**.  
  
     Měla zobrazit zpráva s textem **pomoci služby k dispozici:** následuje **True** nebo **False**. Pokud chcete ověřit toto nastavení, můžete pomocí Editoru registru, jak je znázorněno v dřívějších krocích.