---
title: 'Návod: Vytvoření webové části Silverlight, která zobrazuje data OData pro službu SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.SilverlightWebPart
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ec4c37c8014fe20b136f01d7170240fc4813d04
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120280"
---
# <a name="walkthrough-create-a-silverlight-web-part-that-displays-odata-for-sharepoint"></a>Návod: Vytvoření webové části Silverlight, která zobrazuje data OData pro službu SharePoint
  SharePoint 2010 zveřejňuje data seznamu prostřednictvím OData. Ve službě SharePoint je služba RESTful ListData.svc implementováno službu OData. Tento návod ukazuje postup vytvoření webové části služby SharePoint, který je hostitelem aplikace Silverlight. Aplikace Silverlight zobrazí informace o seznamu oznámení služby SharePoint pomocí ListData.svc. Další informace najdete v tématu [rozhraní REST SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=225999) a [protokol](http://go.microsoft.com/fwlink/?LinkId=226000).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [Požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
## <a name="create-a-silverlight-application-and-silverlight-web-part"></a>Vytvoření aplikace Silverlight a webové části Silverlight
 Nejprve vytvořte aplikaci Silverlight v sadě Visual Studio. Aplikace Silverlight načítá data z seznamu SharePoint oznámení pomocí služby ListData.svc.  
  
> [!NOTE]  
>  Žádné verze Silverlight před 4.0 podporují rozhraní požadované pro odkazování na data seznamu služby SharePoint.  
  
#### <a name="to-create-a-silverlight-application-and-silverlight-web-part"></a>Chcete-li vytvořit aplikaci Silverlight a webové části Silverlight
  
1.  Na řádku nabídek zvolte **soubor** > **nový** > **projektu** zobrazíte **nový projekt** dialogové okno.  
  
2.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
3.  V podokně šablon vyberte **webové části služby SharePoint 2010 Silverlight** šablony.  
  
4.  V **název** zadejte **SLWebPartTest** a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** zobrazí se dialogové okno.  
  
5.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte adresu URL pro web služby SharePoint server, kde chcete ladit definici lokality nebo použijte výchozí umístění (http://*systémový název*nebo) .  
  
6.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** zvolte **nasadit jako řešení farmy** tlačítko.  
  
     I když tento příklad používá řešení farmy, projekty Silverlight webovou část se dá nasadit jako farmy nebo řešení v izolovaném prostoru. Další informace o řešení v izolovaném prostoru a řešení ve farmách najdete v tématu [aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  V **jak chcete přidružit webové části Silverlight** části **zadejte informace o konfiguraci Silverlight** vyberte **vytvořte nový projekt Silverlight a přidružte ji k webové části** tlačítko.  
  
8.  Změna **název** k **SLApplication**, nastavte **jazyk** buď **jazyka Visual Basic** nebo **Visual C#**, a pak nastavte **Silverlight verzi** k **Silverlight 4.0**.  
  
9. Vyberte **Dokončit** tlačítko. Projekty, které se zobrazí v **Průzkumníku řešení**.  
  
     Řešení obsahuje dva projekty: aplikací Silverlight a webové části Silverlight. Aplikace Silverlight načte a zobrazí seznam data ze služby SharePoint a aplikace Silverlight, umožňuje zobrazit ve službě SharePoint hostuje webové části Silverlight.  
  
## <a name="customize-the-silverlight-application"></a>Přizpůsobit aplikaci Silverlight
 Přidáte elementy kódu a návrhu aplikace Silverlight.  
  
#### <a name="to-customize-the-silverlight-application"></a>Chcete-li přizpůsobit aplikaci Silverlight
  
1.  Přidáte odkaz na sestavení pro System.Windows.Data v aplikaci Silverlight. Další informace najdete v tématu [postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz na](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro **odkazy**a potom zvolte **přidat odkaz na službu**.  
  
    > [!NOTE]  
    >  Pokud používáte Visual Basic, musíte zvolit **zobrazit všechny soubory** v horní části ikonu **Průzkumníku řešení** zobrazíte **odkazy** uzlu.  
  
3.  V poli Adresa **přidat odkaz na službu** dialogové okno pole, zadejte adresu URL webu služby SharePoint, jako **http://MySPSite**a potom zvolte **přejděte** tlačítko.  
  
     Když Silverlight vyhledá službu SharePoint OData ListData.svc, nahradí adresu URL služby úplnou adresu. V tomto příkladu http://myserver stane http://myserver/_vti_bin/ListData.svc.  
  
4.  Vyberte **OK** tlačítko Přidat odkaz na službu do projektu a použít výchozí název služby, ServiceReference1.  
  
5.  Na řádku nabídek zvolte **sestavení** > **sestavit řešení**.  
  
6.  Přidáte nový zdroj dat do projektu na základě služby SharePoint. Chcete-li to provést v řádku nabídek, zvolte **zobrazení** > **ostatní okna** > **zdroje dat**.  
  
     **Zdroje dat** v okně se zobrazí všechny dostupné dat seznamu služby SharePoint, jako jsou úlohy, oznámení a kalendáři.  
  
7.  Přidejte seznam data oznámení do aplikací Silverlight. Můžete přetáhnout "Oznámení" z **zdroje dat** okna do návrháře Silverlight.  
  
     Tím se vytvoří ovládacího prvku mřížky vázána na seznam oznámení web služby SharePoint.  
  
8.  Změnit velikost ovládacího prvku mřížky na jednu stránku Silverlight.  
  
9. V souboru kódu MainPage.xaml (*MainPage.xaml.cs* pro Visual C# nebo *MainPage.xaml.vb* jazyka Visual Basic), přidejte následující odkazy na obor názvů.  
  
    ```vb  
    ' Add the following three Imports statements.  
    Imports SLApplication.ServiceReference1  
    Imports System.Windows.Data  
    Imports System.Data.Services.Client  
    ```  
  
    ```csharp  
    // Add the following three using statements.  
    using SLApplication.ServiceReference1;  
    using System.Windows.Data;  
    using System.Data.Services.Client;  
    ```  
  
10. Přidejte následující deklarace proměnných v horní části třídy.  
  
    ```vb  
    Private context As TeamSiteDataContext  
    Private myCollectionViewSource As CollectionViewSource  
    Private announcements As New DataServiceCollection(Of AnnouncementsItem)()  
    ```  
  
    ```csharp  
    private TeamSiteDataContext context;  
    private CollectionViewSource myCollectionViewSource;  
    DataServiceCollection<AnnouncementsItem> announcements = new DataServiceCollection<AnnouncementsItem>();  
    ```  
   
11. Nahraďte `UserControl_Loaded` postup následujícím kódem.  
  
    ```vb  
    Private Sub UserControl_Loaded_1(sender As Object, e As RoutedEventArgs)  
        ' The URL for the OData service.  
        ' Replace <server name> in the next line with the name of your SharePoint server.  
        context = New TeamSiteDataContext(New Uri("http://<server name>/_vti_bin/ListData.svc"))  
  
        ' Do not load your data at design time.  
        If Not System.ComponentModel.DesignerProperties.GetIsInDesignMode(Me) Then  
            'Load your data here and assign the results to the CollectionViewSource.  
            myCollectionViewSource =   DirectCast(Me.Resources("announcementsViewSource"), System.Windows.Data.CollectionViewSource)  
            announcements.LoadCompleted += New EventHandler(Of LoadCompletedEventArgs)(AddressOf announcements_LoadCompleted)  
            announcements.LoadAsync(context.Announcements)  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void UserControl_Loaded_1(object sender, RoutedEventArgs e)  
    {  
        // The URL for the OData service.  
        // Replace <server name> in the next line with the name of your   
        // SharePoint server.  
        context = new TeamSiteDataContext(new Uri("http://ServerName>/_vti_bin/ListData.svc"));  
  
        // Do not load your data at design time.  
        if (!System.ComponentModel.DesignerProperties.GetIsInDesignMode(this))  
        {  
            //Load your data here and assign the results to the CollectionViewSource.  
            myCollectionViewSource = (System.Windows.Data.CollectionViewSource)this.Resources["announcementsViewSource"];  
            announcements.LoadCompleted += new EventHandler<LoadCompletedEventArgs>(announcements_LoadCompleted);  
            announcements.LoadAsync(context.Announcements);  
        }  
    }  
    ```  
     Nezapomeňte nahradit *ServerName* zástupný symbol název serveru se systémem SharePoint.  
  
12. Přidejte následující postup zpracování chyb.  
  
    ```vb  
    Private Sub announcements_LoadCompleted(sender As Object, e As LoadCompletedEventArgs)  
        ' Handle any errors.  
        If e.[Error] Is Nothing Then  
            myCollectionViewSource.Source = announcements  
        Else  
            MessageBox.Show(String.Format("ERROR: {0}", e.[Error].Message))  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    void announcements_LoadCompleted(object sender, LoadCompletedEventArgs e)  
    {  
        // Handle any errors.  
        if (e.Error == null)  
        {  
            myCollectionViewSource.Source = announcements;  
        }  
        else  
        {  
            MessageBox.Show(string.Format("ERROR: {0}", e.Error.Message));  
        }  
    }  
    ```  
       
## <a name="modify-the-silverlight-web-part"></a>Úprava webové části Silverlight
 Změňte vlastnosti v projektu webové části Silverlight povolit ladění aplikací Silverlight.  
  
#### <a name="to-modify-the-silverlight-web-part"></a>Chcete-li upravit webové části Silverlight  
  
1.  Otevřete místní nabídku pro projekt webové části Silverlight (**SLWebPartTest**) a potom zvolte **vlastnosti**.  
  
2.  V **vlastnosti** okně zvolte **SharePoint** kartě.  
  
3.  Pokud již není vybrána, vyberte **Silverlight povolit ladění (místo ladění skriptů)** zaškrtávací políčko.  
  
4.  Uložte projekt.  
  
## <a name="test-the-silverlight-web-part"></a>Test webové části Silverlight
 Otestujte novou webovou část Silverlight ve službě SharePoint zajistit, že se zobrazí data seznamu SharePoint správně.  
  
#### <a name="to-test-the-silverlight-web-part"></a>K otestování webové části Silverlight  
  
1.  Vyberte **F5** klíč sestavení a spuštění řešení služby SharePoint.  
  
2.  Ve službě SharePoint na **Akce webu** nabídce zvolte **nová stránka**.  
  
3.  V **nová stránka** dialogové okno, zadejte název, například **SL webovou část Test**a potom zvolte **vytvořit** tlačítko.  
  
4.  V návrháři stránky na **nástroje pro úpravu** , zvolte **vložit**.  
  
5.  Na kartě pruhu, zvolte **webovou část**.  
  
6.  V **kategorie** , vyberte **vlastní** složky.  
  
7.  V **webové části** seznam, zvolte webové části Silverlight a pak **přidat** tlačítko Přidat webovou část na návrháře.  
  
8.  Po provedení všech budou přidány do webové stránky, který chcete, vyberte **stránky** a pak klikněte na příkaz **uložit a zavřít** tlačítka na panelu nástrojů.  
  
     Webové části Silverlight by měl být nyní zobrazení dat oznámení z webu služby SharePoint. Ve výchozím nastavení je stránky uloženy v seznamu stránky webu ve službě SharePoint.  
  
    > [!NOTE]  
    >  Při přístupu k datům v programu Silverlight napříč doménami, Silverlight chrání před chybami zabezpečení, které lze použít ke zneužití webových aplikací. Pokud narazíte na potíže při přístupu k vzdálených dat, Silverlight, přečtěte si téma [provádění služby k dispozici za domény hranicemi](http://go.microsoft.com/fwlink/?LinkId=223276).  
  
## <a name="see-also"></a>Viz také:
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Nasazení, publikování a upgradování balíčků řešení služby SharePoint](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)  
  
  
