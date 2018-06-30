---
title: 'Návod: Ladění aplikace SharePoint s použitím technologie IntelliTrace | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- IntelliTrace [SharePoint development in Visual Studio]
- standalone data collector
- SharePoint development in Visual Studio, IntelliTrace
- data collector
- IntelliTrace
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 76654568825bd0761097a1edd3ec8eb3bbc7060d
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120282"
---
# <a name="walkthrough-debug-a-sharepoint-application-by-using-intellitrace"></a>Návod: Ladění aplikace SharePoint s použitím technologie IntelliTrace

S použitím technologie IntelliTrace, můžete snadno ladění řešení služby SharePoint. Tradiční ladicí programy získáte jen snímek řešení aktuálně. Ale můžete použít IntelliTrace ke kontrole posledních událostí, které nastaly v řešení a kontext, ve které došlo k chybě a přejděte ke kódu.

 Tento návod ukazuje, jak ladění projektu služby SharePoint 2010 nebo SharePoint 2013 v sadě Visual Studio pomocí agenta Microsoft Monitoring Agent pro shromáždění dat technologie IntelliTrace z nasazené aplikace. K analýze dat, je nutné použít Visual Studio Enterprise. Tento projekt obsahuje příjemce funkce, která, pokud je zapnuta, přidá úkol do seznamu úloh a oznámení do seznamu oznámení. Po deaktivaci funkci úlohy je označena jako dokončená a druhý oznámení se přidá do seznamu oznámení. Postup však obsahuje logické chyby, která brání ve správném spuštění projektu. S použitím technologie IntelliTrace, budete vyhledejte a opravte chybu.

 **Platí pro:** informace v tomto tématu se vztahují na řešení služby SharePoint 2010 a SharePoint 2013, které byly vytvořeny v sadě Visual Studio.

 Tento návod znázorňuje následující úlohy:

- [Vytvoření příjemce funkce](#BKMK_CreateReceiver)

- [Přidejte kód k příjemce funkce](#BKMK_AddCode)

- [Testování projektu](#BKMK_Test1)

- [Shromáždění dat technologie IntelliTrace pomocí agenta Microsoft Monitoring Agent](#BKMK_CollectDiagnosticData)

- [Ladění a opravte řešení služby SharePoint](#BKMK_DebugSolution)

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Požadavky

K dokončení tohoto návodu budete potřebovat následující komponenty:

- Podporované edice systému Windows a služby SharePoint. V tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- Visual Studio Enterprise.

## <a name="create-a-feature-receiver"></a>Vytvoření příjemce funkce

Nejprve je třeba vytvořit prázdný projektu služby SharePoint, který má příjemce funkce.

1. Vytvoření projektu řešení služby SharePoint 2010 nebo SharePoint 2013 a pojmenujte ji **IntelliTraceTest**.

     **Průvodce vlastním nastavením SharePoint** se zobrazí, ve kterém můžete zadat web služby SharePoint pro váš projekt a úrovně důvěryhodnosti řešení.

2. Vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko.

     IntelliTrace funguje pouze na řešení ve farmách.

3. V **Průzkumníku řešení**, otevřete místní nabídku pro **funkce** uzel a potom zvolte **přidat funkce**.

     *Feature1.Feature* se zobrazí.

4. Otevřete místní nabídku pro Feature1.feature a potom zvolte **přidat příjemce událostí** přidat modul kódu s funkcí.

## <a name="add-code-to-the-feature-receiver"></a>Přidejte kód k příjemce funkce

Dál přidejte kód pro dvě metody v příjemce funkce: `FeatureActivated` a `FeatureDeactivating`. Tyto metody se aktivuje vždy, když je funkce aktivace nebo deaktivace ve službě SharePoint, v uvedeném pořadí.

1. V horní části `Feature1EventReceiver` třídy, přidejte následující kód, který deklaruje proměnné, které zadejte web služby SharePoint a podřízené lokality:

    ```vb
    ' SharePoint site and subsite.
    Private siteUrl As String = "http://localhost"
    Private webUrl As String = "/"
    ```

    ```csharp
    // SharePoint site and subsite.
    private string siteUrl = "http://localhost";
    private string webUrl = "/";
    ```

2. Nahraďte `FeatureActivated` metoda následujícím kódem:

    ```vb
    Public Overrides Sub FeatureActivated(ByVal properties As SPFeatureReceiverProperties)
        Try
            Using site As New SPSite(siteUrl)
                Using web As SPWeb = site.OpenWeb(webUrl)
                    ' Reference the lists.
                    Dim announcementsList As SPList = web.Lists("Announcements")
                    Dim taskList As SPList = web.Lists("Tasks")

                    ' Add an announcement to the Announcements list.
                    Dim listItem As SPListItem = announcementsList.Items.Add()
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()
                    listItem.Update()

                    ' Add a task to the Task list.
                    Dim newTask As SPListItem = taskList.Items.Add()
                    newTask("Title") = "Deactivate feature: " & Convert.ToString(properties.Definition.DisplayName)
                    newTask.Update()
                End Using
            End Using

        Catch e As Exception
            Console.WriteLine("Error: " & e.ToString())
        End Try

    End Sub
    ```

    ```csharp
    public override void FeatureActivated(SPFeatureReceiverProperties properties)
    {
        try
        {
            using (SPSite site = new SPSite(siteUrl))
            {
                using (SPWeb web = site.OpenWeb(webUrl))
                {
                    // Reference the lists.
                    SPList announcementsList = web.Lists["Announcements"];
                    SPList taskList = web.Lists["Tasks"];

                    // Add an announcement to the Announcements list.
                    SPListItem listItem = announcementsList.Items.Add();
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " + DateTime.Now.ToString();
                    listItem.Update();

                    // Add a task to the Task list.
                    SPListItem newTask = taskList.Items.Add();
                    newTask["Title"] = "Deactivate feature: " + properties.Definition.DisplayName;
                    newTask.Update();
                }
            }
        }

        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.ToString());
        }

    }
    ```

3. Nahraďte `FeatureDeactivating` metoda následujícím kódem:

    ```vb
    Public Overrides Sub FeatureDeactivating(ByVal properties As SPFeatureReceiverProperties)
        ' The following line induces an error to demonstrate debugging.
        ' Remove this line later for proper operation.
        Throw New System.InvalidOperationException("Serious error occurred!")
        Try
            Using site As New SPSite(siteUrl)
                Using web As SPWeb = site.OpenWeb(webUrl)
                    ' Reference the lists.
                    Dim taskList As SPList = web.Lists("Tasks")
                    Dim announcementsList As SPList = web.Lists("Announcements")

                    ' Add an announcement that the feature was deactivated.
                    Dim listItem As SPListItem = announcementsList.Items.Add()
                    listItem("Title") = "Deactivated Feature: " & Convert.ToString(properties.Definition.DisplayName)
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was deactivated on: " & DateTime.Now.ToString()
                    listItem.Update()

                    ' Find the task that the feature receiver added to the Task list when the
                    ' feature was activated.
                    Dim qry As New SPQuery()
                    qry.Query = "<Where><Contains><FieldRef Name='Title' /><Value Type='Text'>Deactivate</Value></Contains></Where>"
                    Dim taskItems As SPListItemCollection = taskList.GetItems(qry)

                    For Each taskItem As SPListItem In taskItems
                        ' Mark the task as complete.
                        taskItem("PercentComplete") = 1
                        taskItem("Status") = "Completed"
                        taskItem.Update()
                    Next
                End Using

            End Using

        Catch e As Exception
            Console.WriteLine("Error: " & e.ToString())
        End Try

    End Sub
    ```

    ```csharp
    public override void FeatureDeactivating(SPFeatureReceiverProperties properties)
    {
        // The following line induces an error to demonstrate debugging.
        // Remove this line later for proper operation.
        throw new System.InvalidOperationException("A serious error occurred!"); 
        try
        {
            using (SPSite site = new SPSite(siteUrl))
            {
                using (SPWeb web = site.OpenWeb(webUrl))
                {
                    // Reference the lists.
                    SPList taskList = web.Lists["Tasks"];
                    SPList announcementsList = web.Lists["Announcements"];

                    // Add an announcement that the feature was deactivated.
                    SPListItem listItem = announcementsList.Items.Add();
                    listItem["Title"] = "Deactivated Feature: " + properties.Definition.DisplayName;
                    listItem["Body"] = properties.Definition.DisplayName + " was deactivated on: " + DateTime.Now.ToString();
                    listItem.Update();

                    // Find the task that the feature receiver added to the Task list when the
                    // feature was activated.
                    SPQuery qry = new SPQuery();
                    qry.Query = "<Where><Contains><FieldRef Name='Title' /><Value Type='Text'>Deactivate</Value></Contains></Where>";
                    SPListItemCollection taskItems = taskList.GetItems(qry);

                    foreach (SPListItem taskItem in taskItems)
                    {
                        // Mark the task as complete.
                        taskItem["PercentComplete"] = 1;
                        taskItem["Status"] = "Completed";
                        taskItem.Update();
                    }
                }
            }

        }

        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.ToString());
        }
    }
    ```

## <a name="test-the-project"></a>Testování projektu

Teď, když kód se přidá k příjemce funkce a data collector běží, nasadit a provozovat řešení služby SharePoint a otestovat, jestli správně funguje.

> [!IMPORTANT]
> V tomto příkladu je vyvolána chyba v obslužné rutině události FeatureDeactivating. Dále v tomto návodu vyhledejte tuto chybu pomocí .iTrace souboru, který vytvoří kolekci dat.

1. Nasadit řešení služby SharePoint a pak v prohlížeči otevřete web služby SharePoint.

     Tato funkce automaticky aktivuje, způsobuje její příjemce funkce přidat oznámení a úlohy.

2. Zobrazení obsahu seznamů oznámení a úlohy.

     Seznam oznámení by měl mít nové oznámení s názvem **funkce aktivované: IntelliTraceTest_Feature1**, a seznamu úloh by měl mít nový úkol, který je pojmenován **deaktivovat funkce: IntelliTraceTest_ Feature1**. Pokud některý z těchto položek chybí, ověřte, zda je aktivován funkci. Pokud není aktivovaný, aktivujte ji.

3. Deaktivace funkce provedením následujících kroků:

    1. Na **Akce webu** nabídky ve službě SharePoint, zvolte **nastavení lokality**.

    2. V části **Akce webu**, vyberte **spravovat funkce webu** odkaz.

    3. Vedle **IntelliTraceTest Feature1**, vyberte **deaktivovat** tlačítko.

    4. Na stránce s varováním, zvolte **deaktivovat tuto funkci** odkaz.

     Obslužné rutiny události FeatureDeactivating() vrátí chybu.

## <a name="collect-intellitrace-data-by-using-microsoft-monitoring-agent"></a>Shromáždění dat technologie IntelliTrace pomocí agenta Microsoft Monitoring Agent

Pokud instalujete agenta Microsoft Monitoring Agent na počítači se systémem SharePoint, můžete ladit řešení služby SharePoint pomocí dat, která jsou podrobnější než obecné informace, které se vrátí IntelliTrace. Agent funguje mimo Visual Studio pomocí rutin prostředí PowerShell umožňuje zaznamenat informace o ladění při vaší spustí řešení služby SharePoint.

> [!NOTE]
> Informace o konfiguraci v této části je specifické pro tento příklad. Další informace o dalších možnostech konfigurace naleznete v tématu [pomocí samostatného kolektoru IntelliTrace](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).

1. V počítači se systémem SharePoint [nastavení agenta Microsoft Monitoring Agent a začít monitorovat řešení](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).

2. Deaktivace funkce:

    1. Na **Akce webu** nabídky ve službě SharePoint, zvolte **nastavení lokality**.

    2. V části **Akce webu**, vyberte **spravovat funkce webu** odkaz.

    3. Vedle **IntelliTraceTest Feature1**, vyberte **deaktivovat** tlačítko.

    4. Na stránce s varováním, zvolte **deaktivovat tuto funkci** odkaz.

     (V tomto případě z důvodu chyby vyvolána v obslužné rutině události FeatureDeactivating()) dojde k chybě.

3. V okně prostředí PowerShell, spusťte [Stop-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313687) příkaz pro vytvoření souboru .iTrace, zastavení, monitorování a restartování řešení služby SharePoint.

     **Příkaz Stop-WebApplicationMonitoring***"\<SharePointSite >\\< SharePointAppName\>"* 

## <a name="debug-and-fix-the-sharepoint-solution"></a>Ladění a opravte řešení služby SharePoint

Nyní můžete zobrazit soubor protokolu IntelliTrace v sadě Visual Studio můžete najít a opravte chybu v řešení služby SharePoint.

1. Ve složce \IntelliTraceLogs otevřete soubor .iTrace v sadě Visual Studio.

     **IntelliTrace Souhrn** se zobrazí stránka. Protože chyba nebyla zpracována, SharePoint korelační ID (GUID) se zobrazí v oblasti neošetřené výjimce **Analysis** části. Vyberte **zásobníkem volání** tlačítko, pokud chcete zobrazit zásobníku volání, kde došlo k chybě.

2. Vyberte **ladění výjimka** tlačítko.

     Pokud se zobrazí výzva, načte soubory symbolů. V **IntelliTrace** okně výjimka je označený jako "vyvolaná: došlo k vážné chybě!".

     V okně nástroje IntelliTrace vyberte výjimka, která má zobrazit kód, který se nezdařilo.

3. Opravte chybu otevírání řešení služby SharePoint a pak buď komentářů nebo odebráním **throw** příkaz v horní části Postup FeatureDeactivating().

4. Znovu sestavte řešení v sadě Visual Studio a potom znovu nasadit do služby SharePoint.

5. Deaktivace funkce provedením následujících kroků:

    1. Na **Akce webu** nabídky ve službě SharePoint, zvolte **nastavení lokality**.

    2. V části **Akce webu**, vyberte **spravovat funkce webu** odkaz.

    3. Vedle **IntelliTraceTest Feature1**, vyberte **deaktivovat** tlačítko.

    4. Na stránce s varováním, zvolte **deaktivovat tuto funkci** odkaz.

6. Otevřete seznam úkolů a ověřte, zda **stav** hodnotu deaktivovat úlohy je "dokončeno" a jeho **dokončeno %** hodnota je 100 %.

     Spustí kód nástroje nyní správně.

## <a name="see-also"></a>Viz také:

[Ověřte a ladění kódu služby SharePoint](../sharepoint/verifying-and-debugging-sharepoint-code.md)  
[IntelliTrace](/visualstudio/debugger/intellitrace)  
[Návod: Ověření kódu pro SharePoint pomocí testování částí](https://msdn.microsoft.com/library/gg599006(v=vs.100).aspx)
