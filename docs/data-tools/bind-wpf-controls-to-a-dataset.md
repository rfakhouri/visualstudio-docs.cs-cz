---
title: Vytvoření vazby ovládacích prvků WPF k datové sadě
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 177420b9-568b-4dad-9d16-1b0e98a24d71
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 917bf166057ef304f3d045898838b7074d76c467
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34690715"
---
# <a name="bind-wpf-controls-to-a-dataset"></a>Vytvoření vazby ovládacích prvků WPF k datové sadě
V tomto návodu vytvoříte aplikaci WPF, která obsahuje ovládací prvky vázané na data. Ovládací prvky jsou vázány na záznamy produktu, které jsou zapouzdřené v datové sadě. Taky se přidá tlačítka Procházet produkty a uložit změny do produktu, záznamů.

Tento návod znázorňuje následující úlohy:

- Vytvoření aplikace WPF a datovou sadu, která se generují z dat v ukázkové databáze AdventureWorksLT.

- Vytváření sadu ovládací prvky vázané na data tak, že přetáhnete tabulku dat z **zdroje dat** okna okno v Návrháři WPF.

- Vytváření tlačítek, procházet záznamy produktů vpřed a zpět.

- Vytváření tlačítek, který uloží změny, které uživatelé provádět na záznamy produktu v tabulce dat a na podkladový zdroj dat.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Požadavky
K dokončení tohoto návodu budete potřebovat následující komponenty:

-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]

-   Přístup k spuštěnou instanci systému SQL Server nebo SQL Server Express, který má ukázkové databáze AdventureWorksLT k němu připojen. Si můžete stáhnout z databáze AdventureWorksLT [webu CodePlex](http://go.microsoft.com/fwlink/?linkid=87843).

Předchozí znalosti následující koncepty je také užitečné, ale není nutné k dokončení průvodce:

-   Datových sad a TableAdapters. Další informace najdete v tématu [datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md) a [TableAdapter](../data-tools/create-and-configure-tableadapters.md).

-   Datové vazby WPF. Další informace najdete v tématu [přehled vazby dat](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="create-the-project"></a>Vytvoření projektu
 Vytvořte nový projekt WPF. Projekt se zobrazí záznamy produktů.

#### <a name="to-create-the-project"></a>Vytvoření projektu

1.  Spuštění sady Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.

3.  Rozbalte položku **jazyka Visual Basic** nebo **Visual C#** a potom vyberte **Windows**.

4.  Vyberte **aplikaci WPF** šablona projektu.

5.  V **název** zadejte `AdventureWorksProductsEditor` a klikněte na tlačítko **OK**.

     Visual Studio vytvoří `AdventureWorksProductsEditor` projektu.

## <a name="create-a-dataset-for-the-application"></a>Vytvořit datovou sadu pro aplikaci
 Před vytvořením ovládací prvky vázané na data, musíte pro svoji aplikaci definovat datový model a přidat jej do **zdroje dat** okno. V tomto návodu vytvoříte datové sady sloužící jako datový model.

#### <a name="to-create-a-dataset"></a>Chcete-li vytvořit datové sady

1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.

     **Zdroje dat** otevře se okno.

2.  V **zdroje dat** okně klikněte na tlačítko **přidat nový zdroj dat**.

     **Konfigurace zdroje dat** otevře se průvodce.

3.  Na **zvolte typ zdroje dat** vyberte **databáze**a potom klikněte na **Další**.

4.  Na **vyberte Model databáze** vyberte **datovou sadu**a potom klikněte na **Další**.

5.  Na **vybrat datové připojení** vyberte jednu z následujících možností:

    -   Pokud připojení dat k ukázkové databáze AdventureWorksLT je dostupný v rozevíracím seznamu, vyberte ho a pak klikněte na tlačítko **Další**.

    -   Klikněte na tlačítko **nové připojení**a vytvořit připojení k databázi AdventureWorksLT.

6.  Na **uložit připojovací řetězec k souboru konfigurace aplikace** vyberte **Ano, uložte připojení jako** zaškrtněte políčko a potom klikněte na **Další**.

7.  Na **zvolte si databázové objekty** rozbalte **tabulky**a pak vyberte **produkt (SalesLT)** tabulky.

8.  Klikněte na tlačítko **Dokončit**.

     Visual Studio. přidá nový `AdventureWorksLTDataSet.xsd` přidá soubor do projektu ale odpovídající **AdventureWorksLTDataSet** položkou **zdroje dat** okno. `AdventureWorksLTDataSet.xsd` Soubor definuje typové datové sady s názvem `AdventureWorksLTDataSet` a TableAdapter s názvem `ProductTableAdapter`. Dále v tomto návodu budete používat `ProductTableAdapter` vyplnění datové sady s daty a uložte změny zpět do databáze.

9. Sestavte projekt.

## <a name="edit-the-default-fill-method-of-the-tableadapter"></a>Upravit výchozí metodu výplně TableAdapter
 Chcete-li vyplnit datovou sadu dat, použijte `Fill` metodu `ProductTableAdapter`. Ve výchozím nastavení `Fill` metoda výplněmi `ProductDataTable` v `AdventureWorksLTDataSet` se všechny řádky dat z tabulky produktu. Tato metoda vrátí pouze podmnožinu řádků, můžete upravit. V tomto návodu upravit `Fill` metoda vrátí řádky pouze pro produkty, které mají fotografie.

#### <a name="to-load-product-rows-that-have-photos"></a>Chcete-li načíst produktu řádků, které mají fotografie

1.  V **Průzkumníku řešení**, dvakrát klikněte `AdventureWorksLTDataSet.xsd` souboru.

     Otevře se Návrhář datových sad.

2.  V návrháři, klikněte pravým tlačítkem myši **vyplnění GetData()** dotazu a vyberte **konfigurace**.

     **TableAdapter konfigurace** otevře se průvodce.

3.  V **zadejte příkazu jazyka SQL** přidejte následující klauzule WHERE po `SELECT` příkaz v textovém poli.

    ```sql
    WHERE ThumbnailPhotoFileName <> 'no_image_available_small.gif'
    ```

4.  Klikněte na tlačítko **Dokončit**.

## <a name="define-the-user-interface"></a>Definování uživatelského rozhraní
 Přidáte několik tlačítka v okně úpravou XAML v Návrháři WPF. Dále v tomto návodu přidáte kód, který umožňuje uživatelům posuňte prostřednictvím a uložte změny produkty záznamů pomocí těchto tlačítek.

#### <a name="to-define-the-user-interface-of-the-window"></a>Chcete-li definovat uživatelské rozhraní okna

1.  V **Průzkumníku**, dvakrát klikněte na MainWindow.xaml.

     Otevře se okno v Návrháři WPF.

2.  V [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] zobrazit návrháře, přidejte následující kód mezi `<Grid>` značky:

    ```xaml
    <Grid.RowDefinitions>
        <RowDefinition Height="75" />
        <RowDefinition Height="625" />
    </Grid.RowDefinitions>
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>
    ```

3.  Sestavte projekt.

## <a name="create-data-bound-controls"></a>Vytvořit ovládací prvky vázané na data
 Vytvořit ovládací prvky, které zobrazují záznamy o zákaznících přetažením `Product` tabulce **zdroje dat** okna Návrháře WPF.

#### <a name="to-create-data-bound-controls"></a>Chcete-li vytvořit ovládací prvky vázané na data

1.  V **zdroje dat** okně klikněte na rozevírací nabídku pro **produktu** uzel a vyberte možnost **podrobnosti**.

2.  Rozbalte **produktu** uzlu.

3.  V tomto příkladu některá pole se nezobrazí, takže klikněte na rozevírací nabídku vedle následující uzly a vyberte **žádné**:

    -   ProductCategoryID

    -   ProductModelID

    -   ThumbnailPhotoFileName

    -   ROWGUID

    -   ModifiedDate

4.  Klikněte na rozevírací nabídku vedle **ThumbNailPhoto** uzel a vyberte možnost **Image**.

    > [!NOTE]
    >  Ve výchozím nastavení, položky v **zdroje dat** okno, které představují obrázky nemají své výchozí kontrolu nastavena na **žádné**. Je to proto, že obrázky se ukládají jako pole bajtů v databázích a bajtová pole může obsahovat vše od jednoduchého pole bajtů ke spustitelnému souboru rozsáhlé aplikace.

5.  Z **zdroje dat** okno, přetáhněte **produktu** uzlů na řádek mřížky v řádku, který obsahuje tlačítka.

     Generuje XAML, který definuje sadu ovládacích prvků, které jsou vázané na data v sadě Visual Studio **produkty** tabulky. Rovněž vygeneruje kód, který načte data. Další informace o generovaného XAML a kódu najdete v tématu [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

6.  V návrháři, klikněte do textového pole **ID produktu** popisek.

7.  V **vlastnosti** okno, zaškrtněte políčko vedle položky **IsReadOnly** vlastnost.

## <a name="navigating-product-records"></a>Procházení záznamů produktu
 Přidejte kód, který umožňuje uživatelům procházet záznamy produktu pomocí **\<** a **>** tlačítka.

#### <a name="to-enable-users-to-navigate-product-records"></a>Chcete-li povolit uživatelům procházet záznamy produktu

1.  V návrháři, dvakrát klikněte **<** tlačítko na povrchu okno.

     Visual Studio otevře soubor kódu a vytvoří novou `backButton_Click` obslužné rutiny události pro <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí.

2.  Změnit `Window_Loaded` obslužné rutiny události, proto `ProductViewSource`, `AdventureWorksLTDataSet`, a `AdventureWorksLTDataSetProductTableAdapter` jsou mimo metodu a přístup k celému formuláři. Deklarovat pouze tyto globální formuláře a přiřadit je v rámci `Window_Loaded` obslužné rutiny události podobný následujícímu:

     [!code-csharp[Data_WPFDATASET#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_1.cs)]
     [!code-vb[Data_WPFDATASET#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_1.vb)]

3.  Přidejte následující kód, který `backButton_Click` obslužné rutiny události:

     [!code-csharp[Data_WPFDATASET#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_2.cs)]
     [!code-vb[Data_WPFDATASET#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_2.vb)]

4.  Vrátí pro návrháře a dvojitým kliknutím **>** tlačítko.

5.  Přidejte následující kód, který `nextButton_Click` obslužné rutiny události:

     [!code-csharp[Data_WPFDATASET#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_3.cs)]
     [!code-vb[Data_WPFDATASET#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_3.vb)]

## <a name="save-changes-to-product-records"></a>Uložit změny do produktu, záznamů
Přidejte kód, který umožňuje uživatelům uložit změny do záznamů produktu pomocí **uložit změny** tlačítko.

#### <a name="to-add-the-ability-to-save-changes-to-product-records"></a>Chcete-li přidat možnost uložit změny do produktu, záznamů

1.  V návrháři, dvakrát klikněte **uložit změny** tlačítko.

     Visual Studio otevře soubor kódu a vytvoří novou `saveButton_Click` obslužné rutiny události pro <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí.

2.  Přidejte následující kód, který `saveButton_Click` obslužné rutiny události:

     [!code-csharp[Data_WPFDATASET#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_4.cs)]
     [!code-vb[Data_WPFDATASET#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_4.vb)]

    > [!NOTE]
    >  Tento příklad používá `Save` metodu `TableAdapter` a uložte změny. Je to vhodné v tomto návodu, proto mění se pouze jednu datovou tabulku. Pokud potřebujete se uložit změny do více tabulek dat, případně můžete použít `UpdateAll` metodu `TableAdapterManager` vygenerovanou s datovou sadu Visual Studio. Další informace najdete v tématu [TableAdapters](../data-tools/create-and-configure-tableadapters.md).

## <a name="test-the-application"></a>Testování aplikace
 Sestavte a spusťte aplikaci. Ověřte, že můžete zobrazit a aktualizovat záznamy produktu.

#### <a name="to-test-the-application"></a>Testování aplikace

1.  Stiskněte klávesu **F5**.

     Aplikace vytvoří a spustí. Ověřte následující:

    -   Do textových polí zobrazit data z první položky produktu, který má fotografie. Tento produkt má produkt ID 713 a název **dlouho obal Logo Jersey, S**.

    -   Můžete kliknout na **>** nebo **<** tlačítka Procházet další záznamy produktu.

2.  V jednom z záznamy produktů změnit **velikost** hodnotu a pak klikněte na **uložit změny**.

3.  Ukončete aplikaci a restartujte aplikaci stisknutím **F5** v sadě Visual Studio.

4.  Přejděte k záznamu produktu, které jste změnili a ověřte, že trvalé změny.

5.  Zavřete aplikaci.

## <a name="next-steps"></a>Další kroky
 Po dokončení tohoto průvodce, můžete provádět následující úlohy související:

-   Další informace o použití **zdroje dat** oken v sadě Visual Studio pro vazbu WPF ovládací prvky na jiné typy datových zdrojů. Další informace najdete v tématu [prvky vazby WPF služby WCF data Service](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md).

-   Další informace o použití **zdroje dat** oken v sadě Visual Studio pro zobrazení souvisejících dat (tj. data v relaci nadřazený podřízený) v ovládacích prvků WPF. Další informace najdete v tématu [návod: zobrazení souvisejících dat v aplikaci WPF](../data-tools/display-related-data-in-wpf-applications.md).

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Přehled datových vazeb](/dotnet/framework/wpf/data/data-binding-overview)