---
title: "Vytvoření jednoduché datové aplikace pomocí grafického subsystému WPF a Entity Framework 6 | Microsoft Docs"
ms.custom: 
ms.date: 08/22/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 394dbf9aba422f8fbf16857d6980a53b353e931a
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2018
---
# <a name="create-a-simple-data-application-with-wpf-and-entity-framework-6"></a>Vytvoření jednoduché datové aplikace pomocí grafického subsystému WPF a Entity Framework 6

Tato walkthough ukazuje, jak vytvořit základní "forms over data" aplikaci v sadě Visual Studio s SQL Server LocalDB, Northwind databáze, Entity Framework 6 a Windows Presentation Foundation. Ukazuje, jak provést základní vazby dat s hlavní podrobné zobrazení, která je také vlastní "vazby Navigátor" pomocí tlačítka pro "Přesunout další", "Přesunout na předchozí," "Přesunout na začátek," "přesunout na konec," "Aktualizovat" a "Delete".  
  
 Tento článek se zaměřuje na pomocí nástrojů data v sadě Visual Studio a nebude pokoušet o vysvětlují základní technologie žádné podrobněji. Přitom se předpokládá, že máte základní znalost jazyka XAML, rozhraní Entity Framework a SQL. Tento příklad také nepředvádí architektury Model-View-View Model (modelem MVVM), což je standard pro aplikace WPF. Tento kód však můžete zkopírovat do rozhraní MVVM aplikace s velmi málo úpravy.  
  
## <a name="install-and-connect-to-northwind"></a>Nainstalujte a připojte se k Northwind

Tento příklad používá SQL Server Express LocalDB a ukázková databáze Northwind. Ho měli spolupracovat s ostatními produkty databáze SQL stejně dobře, pokud zprostředkovatel ADO.NET data provider pro tento produkt podporuje rozhraní Entity Framework.  

1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **vývoj aplikací .NET** zatížení, nebo jako jednotlivých součástí.

2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:  

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .  

       Otevře se okno editoru dotazů.  

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.  

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.  
  
3.  [Přidat nové připojení](../data-tools/add-new-connections.md) pro Northwind.  
  
## <a name="configure-the-project"></a>Konfigurace projektu
  
1.  V sadě Visual Studio, vyberte **soubor**, **nový**, **projektu...**  a poté vytvořit novou aplikaci WPF C#.  
  
2.  Další přidáme balíček NuGet pro Entity Framework 6. V Průzkumníku řešení vyberte uzel projektu. V hlavní nabídce zvolte **projektu**, **spravovat balíčky NuGet...**  
  
     ![Spravovat balíčky NuGet položky nabídky](../data-tools/media/raddata_vs2015_manage_nuget_packages.png "raddata_vs2015_manage_nuget_packages")  
  
3.  V Správce balíčků NuGet, klikněte na **Procházet** odkaz. Horní balíčku v seznamu je pravděpodobně rozhraní Entity Framework. Klikněte na tlačítko **nainstalovat** v pravém podokně a postupujte podle pokynů. Ve výstupním okně zjistíte po dokončení instalace.  
  
     ![Balíček NuGet Entity Framework](../data-tools/media/raddata_vs2015_nuget_ef.png "raddata_vs2015_Nuget_EF")  
  
4.  Visual Studio jsme teď můžete použít k vytvoření modelu založenému na databázi Northwind.  
  
## <a name="create-the-model"></a>Vytvoření modelu
  
1.  Klikněte pravým tlačítkem na uzel projektu v Průzkumníku řešení a zvolte **přidat**, **novou položku...** . V levém podokně pod uzlem C# vyberte **Data** a v prostředním podokně vyberte **ADO.NET Entity Data Model**.  
  
     ![Entity Framework modelu nové položky projektu](../data-tools/media/raddata-ef-new-project-item.png "raddata EF nové položky projektu")  

  2.  Volání modelu `Northwind_model` a na tlačítko OK. Po výběru této možnosti **Entity Data Model Wizard**. Zvolte **EF Designer z databáze** a pak klikněte na **Další**.  
  
     ![Model EF z databáze](../data-tools/media/raddata-ef-model-from-database.png "raddata EF Model z databáze")  
  
3.  Na další obrazovce, zvolte vaší instanci LocalDB Northwind připojení a klikněte na tlačítko **Další**.  
  
4.  Na další stránce průvodce vybereme možnost které tabulky, uložené procedury a ostatní databázové objekty chcete zahrnout do modelu Entity Framework. Rozbalte uzel dbo ve stromovém zobrazení a zvolte zákazníky, objednávky a podrobnosti o objednávce. Nechte zaškrtnuté výchozí hodnoty a klikněte na **Dokončit**.  
  
     ![Vyberte objekty databáze pro model](../data-tools/media/raddata-choose-ef-objects.png "raddata zvolte EF objekty")  
  
5.  Průvodce vytvoří třídy C#, které představují model Entity Framework. Jedná se o prostý staré třídy jazyka C# a jsou co provedeme databind do uživatelského rozhraní grafického subsystému WPF. Soubor EDMX popisuje vztahy a další metadata, která přidruží třídy objektů v databázi.  Soubory .tt jsou šablony T4, které generování kódu, které budou fungovat v modelu a uložte změny do databáze. Zobrazí se všechny tyto soubory v Průzkumníku řešení v uzlu Northwind_model:  

       ![Soubory model EF Průzkumníka řešení](../data-tools/media/raddata-solution-explorer-ef-model-files.png "soubory modelu raddata EF Průzkumník řešení")  
  
     Plochu návrháře pro soubor EDMX můžete upravit některé vlastnosti a vztahy v modelu. Nebudete jsme použít Návrháře v tomto průvodci.  
  
6.  Soubory .tt jsou pro obecné účely a je potřeba upravit jeden z nich pro práci s datové vazby WPF, který vyžaduje ObservableCollections.  V Průzkumníku řešení rozbalte uzel Northwind_model vyhledejte Northwind_model.tt. (Zajistěte, aby se **není** v *. Kontext .tt souboru, který je přímo pod soubor EDMX).  
  
    -   Nahraďte dva výskyty <xref:System.Collections.ICollection> s <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
    -   Nahraďte první výskyt <xref:System.Collections.Generic.HashSet%601> s <xref:System.Collections.ObjectModel.ObservableCollection%601> kolem řádku 51. Nepřepisovat existující druhého výskytu HashSet  
  
    -   Nahradit pouze výskyt <xref:System.Collections.Generic> (kolem řádku 431) s <xref:System.Collections.ObjectModel>.  
  
7.  Stiskněte klávesu **Ctrl + Shift + B** a tím projekt sestavit. Po dokončení sestavení se zobrazí Průvodce zdrojů dat třídy modelu.  
  
Nyní jsme připraveni spojit tento model na stránku XAML, takže jsme zobrazení, přejděte a upravit data.  
  
## <a name="databind-the-model-to-the-xaml-page"></a>DataBind modelu na stránku XAML

Je možné napsat vlastní kód datové vazby, ale je mnohem snazší nechte nástroj Visual Studio to pro vás udělal.  
  
1.  Z hlavní nabídky zvolte **Projekt > Přidat nový zdroj dat** se zprovoznit **Průvodce konfigurací zdroje dat**. Zvolte **objekt** vzhledem k tomu, že jsme vazbu k tříd modelu, není pro databázi:  
  
     ![Průvodce konfigurací zdroje dat se zdrojem objekt](../data-tools/media/raddata-data-source-configuration-wizard-with-object-source.png "raddata Průvodce konfigurací zdroje dat se zdrojem objektu")  
  
2.  Vyberte zákazníka.  (Zdrojů pro objednávky budou automaticky generovány z objednávky navigační vlastnost u zákazníka.)  
  
     ![Přidání třídy entity jako zdroje dat](../data-tools/media/raddata-add-entity-classes-as-data-sources.png "raddata přidat entity třídy jako zdroje dat")  
  
3.  Klikněte na tlačítko **dokončit**  
  
4.  Přejděte do MainWindow.xaml v zobrazení kódu. Budeme udržovat XAML pro účely tohoto příkladu velmi jednoduché. Změňte název MainWindow na více popisný text a zvýšit jeho výška a šířka na 600 x 800 teď. Můžete ho kdykoliv změnit později. Nyní přidejte tyto tři řádek definice do hlavní mřížky, jeden řádek pro navigační tlačítka, jeden pro zákazníka podrobnosti, jeden pro mřížky, která zobrazí jejich objednávky:  

    ```xaml  
    <Grid.RowDefinitions>  
            <RowDefinition Height="auto"/>  
            <RowDefinition Height="auto"/>  
            <RowDefinition Height="*"/>  
        </Grid.RowDefinitions>
    ```

5.  Nyní otevřete MainWindow.xaml tak, aby si prohlížíte v návrháři. To způsobí, že okna zdroje dat, než se objeví jako možnost v sadě Visual Studio okno okraji vedle panel nástrojů. Klikněte na kartu a otevřete okno nebo jinak stiskněte **Shift + Alt + D** nebo zvolte **zobrazení &#124; Další Windows &#124; Zdroje dat**. Nyní klikněte na Zobrazit každou vlastnost v třídě zákazníkům vlastní jednotlivých textového pole. Nejprve klikněte na šipku v poli se seznamem zákazníků a zvolte **podrobnosti**. Pak přetáhněte uzel na střední část návrhovou plochu, tak, aby návrháře ví, že se má přejít v prostředním řádku.  Pokud někam nezaložili ho, můžete zadat řádek ručně později v XAML. Ve výchozím nastavení ovládací prvky jsou umístěny ve svislém směru v prvku mřížky, ale v tuto chvíli můžete uspořádat je ale chcete ve formuláři.  Například může mít smysl pro umístění textového pole název v horní části výše adresu. Ukázkové aplikace pro tohoto článku změní pole a jejich Přeuspořádá do dvou sloupců.  
  
     ![Zákazníci data zdrojová vazba na jednotlivé ovládací prvky](../data-tools/media/raddata-customers-data-source-binding-to-individual-controls.png "raddata zákazníkům datového zdroje vazby ke jednotlivých ovládacích prvků")  
  
     V zobrazení kódu, se nyní zobrazí nový `Grid` element v řádku 1 (střední řádek) nadřazeného prvku mřížky. Nadřazené má mřížky `DataContext` atribut, který odkazuje na CollectionViewSource, který byl přidán do `Windows.Resources` elementu. Zadána tohoto kontextu dat při první textového pole, například vazby "Vyřešit" Tento název je namapována na `Address` vlastnost v aktuální `Customer` objekt v CollectionViewSource.  
  
    ```xaml  
    <Grid DataContext="{StaticResource customerViewSource}">  
    ```  

6.  Pokud zákazník je zobrazen v horní polovině okna, chceme půl prohlédnout jejich příkazy v dolní části. Ukážeme objednávky v ovládacím prvku mřížky jednoho zobrazení. Pro datové vazby seznam podrobnosti k fungovat podle očekávání je důležité, jsme vazby pro vlastnost objednávky ve třídě zákazníkům, aby samostatný uzel objednávky. Věnovali pozornost tomu na následujícím obrázku! Přetáhněte objednávky vlastnosti třídy zákazníkům spodní polovině formuláře, tak, aby návrháře převádí ho na řádku 2:  
  
     ![Přetáhněte objednávky třídy jako mřížky](../data-tools/media/raddata-drag-orders-classes-as-grid.png "raddata přetáhněte objednávky třídy jako mřížky")  
  
7.  Visual Studio vygenerovala všechny vazby kód, který připojí ovládacích prvků uživatelského rozhraní na události v modelu. Všechny, které je potřeba provést, chcete-li zobrazit některá data je napsat kód, který naplnit modelu. První umožňuje přejděte do MainWindow.xaml.cs a přidejte do třídy MainWindow pro kontext dat člena. Tento objekt, který byl vygenerován pro nás, funguje něco podobného jako ovládací prvek, který sleduje změny a události v modelu. Také přidáme inicializace logiku konstruktoru. Horní části Naše třída by měla vypadat takto:  
  
     [!code-csharp[MainWindow#1](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#1)]  
     
     Přidat `using` direktivy pro System.Data.Entity tím metodu načtení rozšíření do rozsahu:  
  
     ```csharp
     using System.Data.Entity;  
     ```  

     Nyní přejděte dolů a najděte Window_Loaded obslužné rutiny události. Všimněte si, že sada Visual Studio přidala objekt CollectionViewSource pro nás. Reprezentuje objekt NorthwindEntities, který jsme vybrali při jsme vytvořili modelu. Umožňuje přidat kód do Window_Loaded tak, aby celý metoda nyní vypadat třeba takto:  

     [!code-csharp[Window_Loaded#2](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#2)]  

8.  Stiskněte klávesu **F5**. Měli byste vidět podrobnosti pro první zákazníka, která byla načtena do CollectionViewSource. Měli byste taky vidět jejich objednávky v datové mřížce. Formátování, které není skvělé, takže umožňuje oprava. Také vytvoříme způsob, jak zobrazit další záznamy a provést základní operace CRUD.  

## <a name="adjust-the-page-design-and-add-grids-for-new-customers-and-orders"></a>Upravte návrh stránek a přidat nové zákazníky a objednávky mřížky

Výchozí uspořádání vytvářených Visual Studio není ideální pro naši aplikaci, takže jsme budete provádět některé změny ručně v XAML. Chcete-li povolit uživateli přidat nového zákazníka nebo pořadí jsme také potřebovat některé "forms" (které jsou ve skutečnosti mřížky). Aby bylo možné přidat nové zákazníka a pořadí, potřebujeme samostatnou sadu textová pole, které nejsou vázané na data na `CollectionViewSource`. Jsme budete řídit mřížky, které uživateli se zobrazí v každém okamžiku nastavením vlastnosti viditelné v metodách obslužné rutiny. Nakonec přidáme tlačítko Odstranit pro každý řádek v mřížce objednávky umožňující uživateli odstranit jednotlivé pořadí.  
  
Nejprve přidejte tyto styly prvku Windows.Resources v MainWindow.xaml:  
  
```xaml  
<Style x:Key="Label" TargetType="{x:Type Label}" BasedOn="{x:Null}">  
    <Setter Property="HorizontalAlignment" Value="Left"/>  
    <Setter Property="VerticalAlignment" Value="Center"/>  
    <Setter Property="Margin" Value="3"/>  
    <Setter Property="Height" Value="23"/>  
</Style>  
<Style x:Key="CustTextBox" TargetType="{x:Type TextBox}" BasedOn="{x:Null}">  
    <Setter Property="HorizontalAlignment" Value="Right"/>  
    <Setter Property="VerticalAlignment" Value="Center"/>  
    <Setter Property="Margin" Value="3"/>  
    <Setter Property="Height" Value="26"/>  
    <Setter Property="Width" Value="120"/>  
</Style>  
```  
  
Celý vnější mřížky vedle, nahraďte tento kód:  
  
```xaml  
<Grid>  
     <Grid.RowDefinitions>  
         <RowDefinition Height="auto"/>  
         <RowDefinition Height="auto"/>  
         <RowDefinition Height="*"/>  
     </Grid.RowDefinitions>   
     <Grid x:Name="existingCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" Margin="5" Visibility="Visible" VerticalAlignment="Top" Background="AntiqueWhite" DataContext="{StaticResource customerViewSource}">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>  
         <TextBox x:Name="customerIDTextBox"  Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Company Name:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="companyNameTextBox"  Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Name:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Title:"  Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>  
         <TextBox x:Name="addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="City:" Grid.Column="1" Grid.Row="0"  Style="{StaticResource Label}"/>  
         <TextBox x:Name="cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>  
         <TextBox x:Name="postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <Grid x:Name="newCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type Window}}, Path=newCustomer, UpdateSourceTrigger=Explicit}" Visibility="Collapsed" Background="CornflowerBlue">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_customerIDTextBox"  Grid.Row="0"  Style="{StaticResource CustTextBox}"   
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Company Name:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_companyNameTextBox"  Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true }"/>  
         <Label Content="Contact Name:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Title:"  Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="City:" Grid.Column="1" Grid.Row="0"  Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <Grid x:Name="newOrderGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding Path=newOrder, Mode=TwoWay}" Visibility="Collapsed" Background="LightGreen">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="New Order Form" FontWeight="Bold"/>  
         <Label Content="Employee ID:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_employeeIDTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding EmployeeID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Order Date:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_orderDatePicker" Grid.Row="2"  HorizontalAlignment="Right" Width="120"  
                 SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Required Date:" Grid.Row="3" Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_requiredDatePicker" Grid.Row="3" HorizontalAlignment="Right" Width="120"  
                  SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Shipped Date:"  Grid.Row="4"  Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_shippedDatePicker"  Grid.Row="4"  HorizontalAlignment="Right" Width="120"  
                 SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Ship Via:"  Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_ShipViaTextBox"  Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ShipVia, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Freight"  Grid.Row="6" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_freightTextBox" Grid.Row="6" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Freight, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <DataGrid x:Name="ordersDataGrid" SelectionUnit="Cell" SelectionMode="Single" AutoGenerateColumns="False" CanUserAddRows="false" IsEnabled="True" EnableRowVirtualization="True" Width="auto" ItemsSource="{Binding Source={StaticResource customerOrdersViewSource}}" Margin="10,10,10,10" Grid.Row="2" RowDetailsVisibilityMode="VisibleWhenSelected">  
         <DataGrid.Columns>  
             <DataGridTemplateColumn>  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <Button Content="Delete"  Command="{StaticResource DeleteOrderCommand}" CommandParameter="{Binding}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="customerIDColumn" Binding="{Binding CustomerID}" Header="Customer ID" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="employeeIDColumn" Binding="{Binding EmployeeID}" Header="Employee ID" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="freightColumn" Binding="{Binding Freight}" Header="Freight" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="orderDateColumn" Header="Order Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="orderIDColumn" Binding="{Binding OrderID}" Header="Order ID" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="requiredDateColumn" Header="Required Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="shipAddressColumn" Binding="{Binding ShipAddress}" Header="Ship Address" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipCityColumn" Binding="{Binding ShipCity}" Header="Ship City" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipCountryColumn" Binding="{Binding ShipCountry}" Header="Ship Country" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipNameColumn" Binding="{Binding ShipName}" Header="Ship Name" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="shippedDateColumn" Header="Shipped Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="shipPostalCodeColumn" Binding="{Binding ShipPostalCode}" Header="Ship Postal Code" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipRegionColumn" Binding="{Binding ShipRegion}" Header="Ship Region" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipViaColumn" Binding="{Binding ShipVia}" Header="Ship Via" Width="SizeToHeader"/>  
         </DataGrid.Columns>  
     </DataGrid>  
 </Grid>  
```  
  
## <a name="add-buttons-to-navigate-add-update-and-delete"></a>Přidání tlačítek přejděte, přidat, aktualizovat a odstranit  

V aplikacích Windows Forms načíst objekt BindingNavigator s tlačítka pro procházení řádků v databázi a provádění základních operací CRUD. WPF neposkytuje BindingNavigator, ale je dostatečně snadné ji vytvořit. Jsme to udělat pomocí tlačítka uvnitř vodorovné StackPanel a jsme budete tlačítka přidružit příkazy, které jsou vázány na metody v kódu.  
  
Příkaz logiku se skládá fours částí: (1) příkazy, (2) vazby, (3) tlačítka a (4) obslužné rutiny příkazů v modelu code-behind.  
  
### <a name="add-commands-bindings-and-buttons-in-xaml"></a>Přidání tlačítka, vazby a příkazy v jazyce XAML
  
1.  Nejprve v našem MainWindow.xaml souboru uvnitř elementu Windows.Resources přidejme příkazy:  
  
    ```xaml  
    <RoutedUICommand x:Key="FirstCommand" Text="First"/>  
    <RoutedUICommand x:Key="LastCommand" Text="Last"/>  
    <RoutedUICommand x:Key="NextCommand" Text="Next"/>  
    <RoutedUICommand x:Key="PreviousCommand" Text="Previous"/>  
    <RoutedUICommand x:Key="DeleteCustomerCommand" Text="Delete Customer"/>  
    <RoutedUICommand x:Key="DeleteOrderCommand" Text="Delete Order"/>  
    <RoutedUICommand x:Key="UpdateCommand" Text="Update"/>  
    <RoutedUICommand x:Key="AddCommand" Text="Add"/>  
    <RoutedUICommand x:Key="CancelCommand" Text="Cancel"/>  
    ```  
  
2.  CommandBinding mapuje RoutedUICommand událostí na metodu v kódu. Přidejte tento element CommandBindings po Windows.Resources ukončovací značka:  
  
    ```xaml  
    <Window.CommandBindings>  
        <CommandBinding Command="{StaticResource FirstCommand}" Executed="FirstCommandHandler"/>  
        <CommandBinding Command="{StaticResource LastCommand}" Executed="LastCommandHandler"/>  
        <CommandBinding Command="{StaticResource NextCommand}" Executed="NextCommandHandler"/>  
        <CommandBinding Command="{StaticResource PreviousCommand}" Executed="PreviousCommandHandler"/>  
        <CommandBinding Command="{StaticResource DeleteCustomerCommand}" Executed="DeleteCustomerCommandHandler"/>  
        <CommandBinding Command="{StaticResource DeleteOrderCommand}" Executed="DeleteOrderCommandHandler"/>  
        <CommandBinding Command="{StaticResource UpdateCommand}" Executed="UpdateCommandHandler"/>  
        <CommandBinding Command="{StaticResource AddCommand}" Executed="AddCommandHandler"/>  
        <CommandBinding Command="{StaticResource CancelCommand}" Executed="CancelCommandHandler"/>  
    </Window.CommandBindings>  
    ```  
  
3.  Nyní Pojďme přidat StackPanel s navigaci, přidat, odstranit a aktualizaci tlačítka. Nejprve přidejte tento styl Windows.Resources:  
  
    ```xaml  
    <Style x:Key="NavButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="FontSize" Value="24"/>  
        <Setter Property="FontFamily" Value="Segoe UI Symbol"/>  
        <Setter Property="Margin" Value="2,2,2,0"/>  
        <Setter Property="Width" Value="40"/>  
        <Setter Property="Height" Value="auto"/>  
    </Style>  
    ```  
  
     Druhý vložte tento kód bezprostředně za RowDefinitions pro vnější elementů v mřížce, k horní části stránky XAML:  
  
    ```xaml  
    <StackPanel Orientation="Horizontal" Margin="2,2,2,0" Height="36" VerticalAlignment="Top" Background="Gainsboro" DataContext="{StaticResource customerViewSource}" d:LayoutOverrides="LeftMargin, RightMargin, TopMargin, BottomMargin">  
        <Button Name="btnFirst" Content="|◄" Command="{StaticResource FirstCommand}" Style="{StaticResource NavButton}"  />  
        <Button Name="btnPrev" Content="◄" Command="{StaticResource PreviousCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnNext" Content="►" Command="{StaticResource NextCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnLast" Content="►|" Command="{StaticResource LastCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnDelete" Content="Delete Customer" Command="{StaticResource DeleteCustomerCommand}" FontSize="11" Width="120" Style="{StaticResource NavButton}"/>  
        <Button Name="btnAdd" Content="New Customer" Command="{StaticResource AddCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
        <Button Content="New Order" Name="btnNewOrder" FontSize="11" Width="80" Style="{StaticResource NavButton}" Click="NewOrder_click"/>  
        <Button Name="btnUpdate" Content="Commit" Command="{StaticResource UpdateCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
        <Button Content="Cancel" Name="btnCancel" Command="{StaticResource CancelCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
    </StackPanel>  
    ```  
  
### <a name="add-command-handlers-to-the-mainwindow-class"></a>Přidejte obslužné rutiny příkazů do třídy MainWindow  
  
Kódu je minimální s výjimkou metody přidat a odstranit. Navigace provádí volání metod na vlastnost zobrazení CollectionViewSource. DeleteOrderCommandHandler ukazuje, jak provádět kaskádové odstranění na pořadí. Musíme nejprve odstranit Order_Details, které jsou k ní přidružena. UpdateCommandHandler přidá nový zákazník nebo pořadí do kolekce, jinak pouze změny provedené v textových polích uživatel aktualizuje existujícího zákazníka nebo pořadí.  
  
Přidejte do třídy MainWindow v MainWindow.xaml.cs tyto metody obslužné rutiny. Pokud vaše CollectionViewSource pro tabulku zákazníků má jiný název, budete muset upravit název v každé z těchto metod:  
  
[!code-csharp[CommandHandlers#3](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#3)]  
  
## <a name="run-the-application"></a>Spuštění aplikace

Chcete-li začít, ladění, stiskněte **F5**. Měli byste vidět zákazníka a pořadí data vložené do mřížky a navigačních tlačítek by měla fungovat podle očekávání. Klikněte na "Potvrzení" Přidat nového zákazníka nebo pořadí modelu po zadání data. Klikněte na "Zrušit" zpět bez uložení dat z nového zákazníka nebo nového formuláře pořadí. Můžete provést úpravy existující zákazníci a objednávky přímo do textových polí a tyto změny se zapisují do modelu automaticky.  
  
## <a name="see-also"></a>Viz také

[Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)  
[Dokumentaci Entity Framework](/ef/)