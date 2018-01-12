---
title: "Návod: Profilace aplikace SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, profiling
- performance testing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, performance testing
- profiling [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 91952e2f10f025568d356149f63bff63e0c0b1fc
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-profiling-a-sharepoint-application"></a>Postupy: Profilace aplikace SharePoint
  Tento návod ukazuje způsob použití nástrojů pro profilaci k optimalizaci výkonu aplikace SharePoint v sadě Visual Studio. Ukázková aplikace je příjemce událostí funkce služby SharePoint, obsahující nečinné smyčky, která snižuje výkon přijímače událostí funkcí. Visual Studio profiler umožňuje nalézt a eliminovat nejnákladnější (nejpomalejší provádění) součástí projektu, také známé jako *aktivní trase*.  
  
 Tento návod ukazuje následující úlohy:  
  
-   [Přidání funkce a příjemce událostí funkce](#BKMK_AddFtrandFtrEvntReceiver).  
  
-   [Konfigurace a nasazení aplikace SharePoint](#BKMK_ConfigSharePointApp).  
  
-   [Spuštění aplikace SharePoint](#BKMK_RunSPApp).  
  
-   [Zobrazení a interpretací výsledků profilování](#BKMK_ViewResults).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][Požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
## <a name="creating-a-sharepoint-project"></a>Vytvoření projektu SharePoint  
 Nejprve vytvořte projektu služby SharePoint.  
  
#### <a name="to-create-a-sharepoint-project"></a>Vytvoření projektu služby SharePoint  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu** zobrazíte **nový projekt** dialogové okno.  
  
2.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
3.  V podokně šablon vyberte **projektu služby SharePoint 2010** šablony.  
  
4.  V **název** zadejte **ProfileTest**a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
5.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte adresu URL pro web služby SharePoint server, kde chcete ladit definici lokality nebo použijte výchozí umístění (http://*systémový název*nebo) .  
  
6.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** zvolte **nasadit jako řešení farmy** tlačítko.  
  
     V současné době můžete pouze profil řešení ve farmách. Další informace o řešení v izolovaném prostoru a řešení ve farmách najdete v tématu [v izolovaném prostoru aspekty řešení](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  Vyberte **Dokončit** tlačítko. Projekt se objeví v **Průzkumníku řešení**.  
  
##  <a name="BKMK_AddFtrandFtrEvntReceiver"></a>Přidání funkce a příjemce událostí funkce  
 Funkce v dalším kroku přidejte do projektu spolu s přijímače událostí pro funkci. Tento příjemce událostí bude obsahovat kód, který se profilovaným.  
  
#### <a name="to-add-a-feature-and-feature-event-receiver"></a>Chcete-li přidat funkce a příjemce událostí funkce  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **funkce** uzlu, zvolte **přidat funkce**a v výchozí hodnotu, ponechte název **Feature1**.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro **Feature1**a potom zvolte **přidat příjemce událostí**.  
  
     Tím přidáte souboru kódu na funkci s několika obslužné rutiny událostí komentované a otevře soubor pro úpravy.  
  
3.  Ve třídě příjemce událostí přidejte následující deklarace proměnných.  
  
    ```vb  
    ' SharePoint site/subsite.  
    Private siteUrl As String = "http://localhost"  
    Private webUrl As String = "/"  
    ```  
  
    ```csharp  
    // SharePoint site/subsite.  
    private string siteUrl = "http://localhost";  
    private string webUrl = "/";  
    ```  
  
4.  Nahraďte `FeatureActivated` postup následujícím kódem.  
  
    ```vb  
    Public Overrides Sub FeatureActivated(properties As SPFeatureReceiverProperties)  
        Try  
            Using site As New SPSite(siteUrl)  
                Using web As SPWeb = site.OpenWeb(webUrl)  
                    ' Reference the lists.  
                    Dim announcementsList As SPList = web.Lists("Announcements")  
  
                    ' Add a new announcement to the Announcements list.  
                    Dim listItem As SPListItem = announcementsList.Items.Add()  
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()  
                    ' Waste some time.  
                    TimeCounter()  
                    ' Update the list.  
                    listItem.Update()  
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
  
                    // Add a new announcement to the Announcements list.  
                    SPListItem listItem = announcementsList.Items.Add();  
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;  
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " +   
    DateTime.Now.ToString();  
                    // Waste some time.  
                    TimeCounter();  
                    // Update the list.  
                    listItem.Update();                          
                }  
            }  
        }  
  
        catch (Exception e)  
        {  
            Console.WriteLine("Error: " + e.ToString());  
        }  
    }  
    ```  
  
5.  Přidejte následující následující postup `FeatureActivated`postupu.  
  
    ```vb  
  
    Public Sub TimeCounter()  
        Dim result As Integer  
        For i As Integer = 0 To 99999  
            For j As Integer = 0 To 9999  
                result = i * j  
            Next j  
        Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void TimeCounter()  
    {  
        for (int i = 0; i < 100000; i++)  
        {  
            for (int j = 0; j < 10000; j++)  
            {  
                int result = i * j;  
            }  
        }  
    }  
    ```  
  
6.  V **Průzkumníku řešení**, otevřete místní nabídky projektu (**ProfileTest**) a potom zvolte **vlastnosti**.  
  
7.  V **vlastnosti** dialogovém okně vyberte **SharePoint** kartě.  
  
8.  V **aktivní konfigurace nasazení** vyberte **bez aktivace**.  
  
     Výběr tuto konfiguraci nasazení umožňuje ručně aktivovat funkci později ve službě SharePoint.  
  
9. Uložte projekt.  
  
##  <a name="BKMK_ConfigSharePointApp"></a>Konfigurace a nasazení aplikace SharePoint  
 Teď, když projektu služby SharePoint je připraveno, ho nakonfigurovat a nasadit server služby SharePoint.  
  
#### <a name="to-configure-and-deploy-the-sharepoint-application"></a>Umožňuje nakonfigurovat a nasadit aplikace SharePoint  
  
1.  Na **analyzovat** nabídce zvolte **spusťte Průvodce výkonu**.  
  
2.  Na stránce jeden **Průvodce výkonu**, nechte metodě profilace jako **procesoru vzorkování** a zvolte **Další** tlačítko.  
  
     Profilování metody lze použít v pokročilejší profilace situacích. Další informace najdete v tématu [metody kolekce údajů o výkonu Principy](/visualstudio/profiling/understanding-performance-collection-methods).  
  
3.  Na druhou stránku **Průvodce výkonu**, nechte cíl profil jako **ProfileTest** a zvolte **Další** tlačítko.  
  
     Pokud má více projektů řešení, zobrazí se v tomto seznamu.  
  
4.  Na stránce tři **Průvodce výkonu**, zrušte **povolit profilace interakce vrstvy** zaškrtněte políčko a potom vyberte **Další** tlačítko.  
  
     Profilace interakce vrstvy (TIP) funkce je užitečná pro měření výkonu aplikací dotazy na databáze, a pro ukazuje počet, kolikrát se požaduje na webové stránce. Protože tato data se nevyžaduje v tomto příkladu, jsme nebude povolit tuto funkci.  
  
5.  Na stránce čtyři **Průvodce výkonu**, ponechte **spuštění profilace po ukončení průvodce** zaškrtnuté políčko a potom vyberte **Dokončit** tlačítko.  
  
     Průvodce umožňuje profilace aplikací na serveru, zobrazí **prohlížeč výkonu** okna a potom sestavení nasadí a spouští aplikace SharePoint.  
  
##  <a name="BKMK_RunSPApp"></a>Spuštění aplikace SharePoint  
 Aktivovat funkci ve službě SharePoint, která aktivuje `FeatureActivation` událostí kód pro spuštění.  
  
#### <a name="to-run-the-sharepoint-application"></a>Ke spuštění aplikace SharePoint  
  
1.  Ve službě SharePoint, otevřete **Akce webu** nabídce a potom zvolte **nastavení lokality**.  
  
2.  V **Akce webu** seznam, vyberte **spravovat funkce webu** odkaz.  
  
3.  V **funkce** seznam, vyberte **aktivovat** vedle položky **ProfileTest Feature1**.  
  
     Při tomto, z důvodu nečinné smyčky volané pozastavení je `FeatureActivated` funkce.  
  
4.  Na **Snadné spuštění** panel, vyberte **uvádí** a pak v **uvádí** vyberte **oznámení**.  
  
     Všimněte si, že byl přidán do seznamu, s informacemi o tom, že funkci aktivovala nové oznámení.  
  
5.  Zavřete stránku služby SharePoint.  
  
     Po ukončení služby SharePoint, profileru vytvoří a zobrazí zprávu o ukázka profilace a uloží ji jako soubor .vsp v **ProfileTest** složce projektu.  
  
##  <a name="BKMK_ViewResults"></a>Zobrazení a interpretací výsledků profilace  
 Teď, když máte spustit a profilovaným aplikace SharePoint, zobrazíte výsledky testů.  
  
#### <a name="to-view-and-interpret-the-profiling-results"></a>K zobrazení a interpretovat výsledky profilace  
  
1.  V **nejvíce jednotlivých pracuje funkce** části ukázkové sestavy profilace, Všimněte si, že `TimeCounter` je v horní části seznamu.  
  
     Toto umístění znamená, že `TimeCounter` byla jedna z funkcí s nejvyšší počet vzorků, což znamená, je jednou z největších kritické v aplikaci. Není k této situaci překvapení, ale protože je účelově určená tímto způsobem pro demonstrační účely.  
  
2.  V **nejvíce jednotlivých pracuje funkce** zvolte `ProcessRequest` odkaz na distribuci náklady pro `ProcessRequest` funkce.  
  
     V **volat funkce** část `ProcessRequest`, Všimněte si, že **FeatureActiviated** funkce je uveden jako nejnákladnější volal funkci.  
  
3.  V **volat funkce** zvolte **FeatureActivated** tlačítko.  
  
     V **volat funkce** část **FeatureActivated**, `TimeCounter` funkce je uveden jako nejnákladnější volal funkci. V **zobrazení kódu funkce** podokně, zvýrazněný (`TimeCounter`) je aktivního bodu a určuje, kde je potřeba oprava.  
  
4.  Ukázková sestava profilace zavřete.  
  
     Chcete-li zobrazit sestavu kdykoli znovu, otevřete soubor .vsp v **prohlížeč výkonu** okno.  
  
## <a name="fixing-the-code-and-reprofiling-the-application"></a>Oprava kód a Reprofiling aplikace  
 Teď, když byla zjištěna hotspotů funkce v aplikaci služby SharePoint, opravte ji.  
  
#### <a name="to-fix-the-code-and-reprofile-the-application"></a>Kód, a reprofile aplikace  
  
1.  V kódu příjemce událostí funkce komentář `TimeCounter` volání metody `FeatureActivated` zabráníte volána.  
  
2.  Uložte projekt.  
  
3.  V **prohlížeč výkonu**, otevřete složku cíle a potom zvolte **ProfileTest** uzlu.  
  
4.  Na **prohlížeč výkonu** panelu nástrojů v **akce** , zvolte **spuštění profilace** tlačítko.  
  
     Pokud chcete změnit z vlastností profilování před reprofiling aplikace, vyberte **spusťte Průvodce výkonu** tlačítko místo.  
  
5.  Postupujte podle pokynů **spuštění aplikace SharePoint** části dříve v tomto tématu.  
  
     Funkce by měly aktivovat mnohem rychleji teď, když se odstranilo volání nečinné smyčky. Ukázková sestava profilace musí tuto skutečnost.  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](/visualstudio/profiling/performance-explorer)   
 [Přehled výkonnostní relace](/visualstudio/profiling/performance-session-overview)   
 [Průvodce začátečníka profilací výkonu](/visualstudio/profiling/beginners-guide-to-performance-profiling)   
 [Najít kritická místa aplikace pomocí sady Visual Studio Profiler](http://go.microsoft.com/fwlink/?LinkID=137266)  
  
  