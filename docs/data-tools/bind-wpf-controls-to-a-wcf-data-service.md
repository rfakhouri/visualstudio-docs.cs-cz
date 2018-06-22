---
title: Vytvoření vazby ovládacích prvků WPF k datové službě WCF
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 8823537c-82f0-41f7-bf30-705f0e5e59fd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a7095b1cd8e386ec93d95f2a7cd13ed753b13a95
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282905"
---
# <a name="bind-wpf-controls-to-a-wcf-data-service"></a>Vytvoření vazby ovládacích prvků WPF k datové službě WCF

V tomto návodu vytvoříte aplikaci WPF, která obsahuje ovládací prvky vázané na data. Ovládací prvky jsou vázány na záznamy o zákaznících, které jsou zapouzdřené v [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]. Taky se přidá tlačítka, které zákazníci mohou používat k zobrazení a aktualizaci záznamů.

Tento návod znázorňuje následující úlohy:

- Vytvoření datového modelu Entity, který se generuje na základě dat v ukázkové databáze AdventureWorksLT.

- Vytváření [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] která zveřejňuje data v datovém modelu Entity k aplikaci WPF.

- Vytváření sadu ovládací prvky vázané na data tak, že přetáhnete položky z **zdroje dat** okna Návrháře WPF.

- Vytváření tlačítek, procházet záznamy o zákaznících vpřed a zpět.

- Vytváření tlačítko, které se uloží změny k datům v ovládací prvky [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] a na podkladový zdroj dat.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Požadavky
K dokončení tohoto návodu budete potřebovat následující komponenty:

-   Visual Studio

-   Přístup k spuštěnou instanci systému SQL Server nebo SQL Server Express, který má ukázkové databáze AdventureWorksLT k němu připojen. Si můžete stáhnout z databáze AdventureWorksLT [webu CodePlex](http://go.microsoft.com/fwlink/?linkid=87843).

Předchozí znalosti následující koncepty je také užitečné, ale není nutné k dokončení průvodce:

-   Služby WCF Data Services. Další informace najdete v tématu [přehled](/dotnet/framework/data/wcf/wcf-data-services-overview).

-   Data modelů v [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)].

-   Entity datové modely a ADO.NET Entity Framework. Další informace najdete v tématu [Entity Framework přehled](/dotnet/framework/data/adonet/ef/overview).

-   Datové vazby WPF. Další informace najdete v tématu [datové vazby přehled](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="create-the-service-project"></a>Vytvoření projektu služby
Začněte tím, že vytvoření projektu pro tento návod [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

### <a name="to-create-the-service-project"></a>Vytvoření projektu služby

1.  Spuštění sady Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.

3.  Rozbalte položku **Visual C#** nebo **jazyka Visual Basic**a potom vyberte **webové**.

4.  Vyberte **webové aplikace ASP.NET** šablona projektu.

5.  V **název** zadejte `AdventureWorksService` a klikněte na tlačítko **OK**.

     Visual Studio vytvoří `AdventureWorksService` projektu.

6.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Default.aspx** a vyberte **odstranit**. Tento soubor není nutné v tomto návodu.

## <a name="create-an-entity-data-model-for-the-service"></a>Vytvoření modelu EDM Entity Data Model pro službu
K zobrazení dat do aplikace pomocí [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], je nutné definovat datový model pro službu. [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] Podporuje dva typy datové modely: Entita datové modely a vlastní datové modely, které jsou definované za použití common language runtime (CLR) objekty, které implementovat <xref:System.Linq.IQueryable%601> rozhraní. V tomto návodu vytvoříte datový Model Entity datového modelu.

### <a name="to-create-an-entity-data-model"></a>K vytvoření datového modelu Entity

1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.

2.  V seznamu nainstalovaných šablonách klikněte na **Data**a pak vyberte **ADO.NET Entity Data Model** položka projektu.

3.  Změňte název `AdventureWorksModel.edmx`a klikněte na tlačítko **přidat**.

     **Datového modelu Entity** otevře se průvodce.

4.  Na **zvolte obsah modelu** klikněte na tlačítko **generování z databáze**a klikněte na tlačítko **Další**.

5.  Na **vybrat datové připojení** vyberte jednu z následujících možností:

    -   Pokud připojení dat k ukázkové databáze AdventureWorksLT je dostupný v rozevíracím seznamu, vyberte ho.

    -   Klikněte na tlačítko **nové připojení**a vytvořit připojení k databázi AdventureWorksLT.

6.  Na **vybrat datové připojení** stránky, ujistěte se, že **uložit nastavení připojení entity v souboru App.Config jako** možnost je vybrána a potom klikněte na **Další**.

7.  Na **zvolte si databázové objekty** rozbalte **tabulky**a pak vyberte **SalesOrderHeader** tabulky.

8.  Klikněte na tlačítko **Dokončit**.

## <a name="create-the-service"></a>Vytvoření služby
Vytvoření [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] vystavit data v datovém modelu Entity k aplikaci WPF.

### <a name="to-create-the-service"></a>Chcete-li vytvořit službu

1.  Na **projektu** nabídce vyberte možnost **přidat novou položku**.

2.  V **nainstalovaných šablonách** seznamu, klikněte na tlačítko **webové**a pak vyberte **služby WCF Data Service** položka projektu.

3.  V **název** zadejte `AdventureWorksService.svc`a klikněte na tlačítko **přidat**.

     Visual Studio. přidá `AdventureWorksService.svc` do projektu.

## <a name="configure-the-service"></a>Konfigurace služby
Musíte nakonfigurovat službu, aby pracoval na datový Model Entity, který jste vytvořili.

### <a name="to-configure-the-service"></a>Ke konfiguraci služby

1.  V `AdventureWorks.svc` kódu souboru, nahraďte `AdventureWorksService` třídy deklarace s následujícím kódem.

     [!code-csharp[Data_WPFWCF#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_1.cs)]
     [!code-vb[Data_WPFWCF#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_1.vb)]

     Tento kód aktualizace `AdventureWorksService` , tak, aby je odvozena od třídy <xref:System.Data.Services.DataService%601> který funguje na `AdventureWorksLTEntities` objektu context – třída v modelu Entity Data Model. Aktualizuje také `InitializeService` metoda umožnit klientům přístup k službě čtení/zápisu do `SalesOrderHeader` entity.

2.  Sestavte projekt a ověřte, že sestavení bez chyb.

## <a name="create-the-wpf-client-application"></a>Vytvořit klientskou aplikaci WPF
Chcete-li zobrazit data z [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], vytvořte novou aplikaci WPF se zdrojem dat, která je založená na službě. Dále v tomto návodu přidáte ovládací prvky vázané na data do aplikace.

### <a name="to-create-the-wpf-client-application"></a>Chcete-li vytvořit klientskou aplikaci WPF

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení, klikněte na **přidat**a vyberte **nový projekt**.

2.  V **nový projekt** dialogové okno, rozbalte položku **Visual C#** nebo **jazyka Visual Basic**a potom vyberte **Windows**.

3.  Vyberte **aplikaci WPF** šablona projektu.

4.  V **název** zadejte `AdventureWorksSalesEditor`a klikněte na tlačítko **OK**.

     Visual Studio. přidá `AdventureWorksSalesEditor` projektu k řešení.

5.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.

     **Zdroje dat** otevře se okno.

6.  V **zdroje dat** okně klikněte na tlačítko **přidat nový zdroj dat**.

     **Konfigurace zdroje dat** otevře se průvodce.

7.  V **zvolte typ zdroje dat** stránce průvodce vyberte **služby**a potom klikněte na **Další**.

8.  V **přidat odkaz na službu** dialogové okno, klikněte na tlačítko **Discover**.

     Visual Studio vyhledá aktuální řešení pro služby k dispozici a přidá `AdventureWorksService.svc` do seznamu dostupných služeb v **služby** pole.

9. V **Namespace** zadejte `AdventureWorksService`.

10. V **služby** pole, klikněte na tlačítko **AdventureWorksService.svc**a potom klikněte na **OK**.

     Visual Studio stáhne informace o služby a vrátí se až **konfigurace zdroje dat** průvodce.

11. V **přidat odkaz na službu** klikněte na tlačítko **Dokončit**.

     Přidá uzly, které představují data vrácená službou pro Visual Studio **zdroje dat** okno.

## <a name="define-the-user-interface-of-the-window"></a>Zadejte uživatelské rozhraní okna
Přidáte několik tlačítka v okně úpravou XAML v Návrháři WPF. Dále v tomto návodu přidáte kód, který umožňuje uživatelům zobrazit a aktualizovat prodeje záznamy pomocí těchto tlačítek.

### <a name="to-create-the-window-layout"></a>Chcete-li vytvořit rozložení okna

1.  V **Průzkumníku řešení**, dvakrát klikněte na **MainWindow.xaml**.

     Otevře se okno v Návrháři WPF.

2.  V [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] zobrazit návrháře, přidejte následující kód mezi `<Grid>` značky:

    ```xaml
    <Grid.RowDefinitions>
        <RowDefinition Height="75" />
        <RowDefinition Height="525" />
    </Grid.RowDefinitions>
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>
    ```

3.  Sestavte projekt.

## <a name="create-the-data-bound-controls"></a>Vytvořit ovládací prvky vázané na data
Vytvořit ovládací prvky, které zobrazují záznamy o zákaznících přetažením `SalesOrderHeaders` uzlu z **zdroje dat** okna návrháře.

### <a name="to-create-the-data-bound-controls"></a>Chcete-li vytvořit ovládací prvky vázané na data

1.  V **zdroje dat** okně klikněte na rozevírací nabídku pro **SalesOrderHeaders** uzel a vyberte možnost **podrobnosti**.

2.  Rozbalte **SalesOrderHeaders** uzlu.

3.  V tomto příkladu některá pole se nezobrazí, takže klikněte na rozevírací nabídku vedle následující uzly a vyberte **žádné**:

    -   **CreditCardApprovalCode**

    -   **ModifiedDate**

    -   **OnlineOrderFlag**

    -   **RevisionNumber**

    -   **ROWGUID**

    Tato akce zabrání Visual Studio vytváření ovládací prvky vázané na data pro tyto uzly v dalším kroku. V tomto návodu předpokládají, že koncový uživatel nemusí zobrazit tato data.

4.  Z **zdroje dat** okna, přetáhněte **SalesOrderHeaders** uzlů na řádek mřížky v řádku, který obsahuje tlačítka.

     Visual Studio vytvoří XAML a kód, který vytvoří sadu ovládacích prvků, které jsou vázané na data v **produktu** tabulky. Další informace o generovaného XAML a kódu najdete v tématu [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

5.  V návrháři, klikněte do textového pole **ID zákazníka** popisek.

6.  V **vlastnosti** okno, zaškrtněte políčko vedle položky **IsReadOnly** vlastnost.

7.  Nastavte **IsReadOnly** vlastnost pro každou z následujících polí:

    -   **Číslo objednávky**

    -   **ID prodejní objednávky**

    -   **Prodejní pořadové číslo**

## <a name="load-the-data-from-the-service"></a>Načíst data ze služby
Pomocí objektu proxy služby načíst prodejní data ze služby. Vrácená data přiřadit zdroje dat pro <xref:System.Windows.Data.CollectionViewSource> v okně WPF.

### <a name="to-load-the-data-from-the-service"></a>Chcete načíst data ze služby

1.  V návrháři, chcete-li vytvořit `Window_Loaded` obslužné rutiny události, klikněte dvakrát na text, který čte: **MainWindow**.

2.  Obslužné rutiny události nahraďte následujícím kódem. Ujistěte se, že nahradíte *localhost* adresa v tento kód se adresu místního hostitele ve svém vývojovém počítači.

     [!code-csharp[Data_WPFWCF#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_2.cs)]
     [!code-vb[Data_WPFWCF#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_2.vb)]

## <a name="navigate-sales-records"></a>Přejděte prodeje záznamů
Přidejte kód, který umožňuje uživatelům procházet prodeje záznamů pomocí **\<** a **>** tlačítka.

### <a name="to-enable-users-to-navigate-sales-records"></a>Chcete-li povolit uživatelům procházet prodeje záznamy

1.  V návrháři, dvakrát klikněte **<** tlačítko na povrchu okno.

     Visual Studio otevře soubor kódu a vytvoří novou `backButton_Click` obslužné rutiny události pro <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí.

2.  Přidejte následující kód do vygenerovaného `backButton_Click` obslužné rutiny události:

     [!code-csharp[Data_WPFWCF#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_3.cs)]
     [!code-vb[Data_WPFWCF#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_3.vb)]

3.  Vrátíte do návrháře a dvakrát klikněte na **>** tlačítko.

     Visual Studio otevře soubor kódu a vytvoří novou `nextButton_Click` obslužné rutiny události pro <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí.

4.  Přidejte následující kód do vygenerovaného `nextButton_Click` obslužné rutiny události:

     [!code-csharp[Data_WPFWCF#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_4.cs)]
     [!code-vb[Data_WPFWCF#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_4.vb)]

## <a name="saving-changes-to-sales-records"></a>Ukládání změn do prodeje záznamů
Přidejte kód, který umožňuje uživatelům zobrazit i uložit změny do prodeje záznamů pomocí **uložit změny** tlačítko.

### <a name="to-add-the-ability-to-save-changes-to-sales-records"></a>Chcete-li přidat možnost uložit změny do prodeje záznamů

1.  V návrháři, dvakrát klikněte **uložit změny** tlačítko.

     Visual Studio otevře soubor kódu a vytvoří novou `saveButton_Click` obslužné rutiny události pro <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí.

2.  Přidejte následující kód, který `saveButton_Click` obslužné rutiny události.

     [!code-csharp[Data_WPFWCF#5](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_5.cs)]
     [!code-vb[Data_WPFWCF#5](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_5.vb)]

## <a name="testing-the-application"></a>Testování aplikace
Sestavte a spusťte aplikaci ověřte, že můžete zobrazit a aktualizovat záznamy o zákaznících.

### <a name="to-test-the-application"></a>Testování aplikace

1.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**. Ověřte, že sestavení řešení bez chyb.

2.  Stiskněte klávesu **Ctrl**+**F5**.

     Visual Studio spustí **AdventureWorksService** projektu, bez ladění.

3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksSalesEditor** projektu.

4.  V místní nabídce v části **ladění**, klikněte na tlačítko **spustit novou instanci**.

     Spuštění aplikace. Ověřte následující:

    -   Do textových polí zobrazit různá pole dat z první položky prodeje, který má ID prodejní objednávky **71774**.

    -   Můžete kliknout na **>** nebo **<** tlačítka Procházet další prodeje záznamy.

5.  V jednom z prodeje záznamy, zadejte text v **komentář** pole a pak klikněte na **uložit změny**.

6.  Ukončete aplikaci a pak spusťte aplikaci znovu ze sady Visual Studio.

7.  Přejděte do prodeje záznam, který jste změnili a ověřte, že změna přetrvává i po zavřete a znovu otevřete aplikaci.

8.  Zavřete aplikaci.

## <a name="next-steps"></a>Další kroky

Po dokončení tohoto průvodce, můžete provádět následující úlohy související:

-   Další informace o použití **zdroje dat** oken v sadě Visual Studio pro vazbu WPF ovládací prvky na jiné typy datových zdrojů. Další informace najdete v tématu [prvky vazby WPF k datové sadě](../data-tools/bind-wpf-controls-to-a-dataset.md).

-   Další informace o použití **zdroje dat** oken v sadě Visual Studio pro zobrazení souvisejících dat (tj. data v relaci nadřazený podřízený) v ovládacích prvků WPF. Další informace najdete v tématu [návod: zobrazování souvisejících dat v aplikaci WPF](../data-tools/display-related-data-in-wpf-applications.md).

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků WPF k datové sadě](../data-tools/bind-wpf-controls-to-a-dataset.md)
- [WCF – přehled (rozhraní .NET Framework)](/dotnet/framework/data/wcf/wcf-data-services-overview)
- [Přehled Entity Framework (rozhraní .NET Framework)](/dotnet/framework/data/adonet/ef/overview)
- [Datová vazba (rozhraní .NET Framework) – přehled](/dotnet/framework/wpf/data/data-binding-overview)