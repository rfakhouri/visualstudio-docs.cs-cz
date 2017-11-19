---
title: "Návod: Můj první grafický subsystém WPF Desktopová aplikace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c460fa9-2ea1-413f-ae54-54a1f2a499d1
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- csharp
- vb
ms.openlocfilehash: 75a333c7e5948e13db0c0c91b41128914e23222b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Návod: Můj první grafický subsystém WPF aplikace pracovní plochy
Tento názorný postup obsahuje úvod k vývoji Windows Presentation Foundation (WPF). Vytvoříte základní aplikaci, která obsahuje prvky, které jsou společné pro většinu aplikací klasické pracovní plochy WPF: XAML značek, kódu, definice aplikace, ovládací prvky, rozložení, datové vazby a styly.  
  
## <a name="creating-the-application-project"></a>Vytvoření projektu aplikace  
V této části vytvoříte infrastrukturu aplikace, která zahrnuje projektu a hlavní okno nebo formuláře.  
  
#### <a name="to-create-the-project"></a>Vytvoření projektu  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte **Visual C#** nebo **jazyka Visual Basic** uzlu a zvolte **Windows** uzel a potom rozbalte **Windows** uzel a zvolte **klasický desktopový** uzlu.  
  
3.  V seznamu šablony, vyberte **aplikaci WPF** šablony.  
  
4.  V **název** textového pole zadejte `ExpenseIt`a potom zvolte **OK** tlačítko.  
  
     Vytvoření projektu a soubory projektu budou přidány do **Průzkumníku řešení**a návrháři intervalu pro správu a výchozí aplikace s názvem **MainWindow.xaml** se zobrazí.  
  
#### <a name="to-modify-the-main-window"></a>Chcete-li změnit hlavní okno  
  
1.  V návrháři, vyberte **MainWindow.xaml** kartě, pokud již není aktivní návrháře karty.  
  
2.  Pokud používáte C#, vyhledejte řádek `<Window x:Class="ExpenseIt.MainWindow"` a nahraďte ho `<NavigationWindow x:Class="ExpenseIt.MainWindow"`.  
  
     Pokud používáte Visual Basic, vyhledejte řádek `<Window x:Class=" MainWindow"` a nahraďte ho `<NavigationWindow x:Class="MainWindow"`.  
  
     Všimněte si, že při změně `<Window` značky k `<NavigationWindow`, Intellisense automaticky změní na uzavírací značku a tím `</NavigationWindow>` také.  
  
    > [!NOTE]
    >  Po změně značky, pokud **seznam chyb** je otevřené okno může dojít k několika chybám. Nemusíte si dělat starosti, budou změny provedené v příštích několika krocích tyto přejděte rychle.  
  
3.  Vyberte `<Grid>` a `</Grid>` značky a odstraňte je.  
  
     A **okně navigace** nemůže obsahovat další prvky uživatelského rozhraní, jako **mřížky**.  
  
4.  V **vlastnosti** okno, rozbalte **běžné** uzel kategorie a zvolte **název** vlastnost a potom zadejte `ExpenseIt` a stiskněte klávesu **Enter**  klíč.  
  
     Všimněte si, že **název** element v okně XAML změní tak, aby odpovídala nové hodnotě. Můžete upravit vlastnosti XAML v okně XAML nebo **vlastnosti** okno a změny jsou synchronizovány.  
  
5.  V okně XAML, nastavte hodnotu **výška** element `375`a nastavte hodnotu **šířka** vlastnost, která má `500`.  
  
     Tyto prvky odpovídají **výška** a **šířka** vlastnosti, nalezené v **rozložení** kategorie v **vlastnosti** okno.  
  
     Vaše **MainWindow.xaml** soubor by měl nyní vypadat jako v C#:  
  
    ```xaml  
    <NavigationWindow x:Class="ExpenseIt.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
            xmlns:local="clr-namespace:ExpenseIt"  
            mc:Ignorable="d"  
            Title="ExpenseIt" Height="375" Width="500">    
    </NavigationWindow>  
    ```  
  
     Nebo v jazyce Visual Basic takto:  
  
    ```xaml  
    <NavigationWindow x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
            xmlns:local="clr-namespace:ExpenseIt"  
            mc:Ignorable="d"  
            Title="ExpenseIt" Height="375" Width="500">    
    </NavigationWindow>  
    ```  
  
#### <a name="to-modify-the-code-behind-file-c"></a>K úpravě souboru kódu na pozadí (C#)  
  
1.  V **Průzkumníku řešení**, rozbalte **MainWindow.xaml** uzlu a otevřete **MainWindow.xaml.cs** souboru.  
  
2.  Vyhledejte řádek `public partial class MainWindow : Window` a nahraďte ho `public partial class MainWindow : NavigationWindow`.  
  
     Tato operace změní `MainWindow` odvozena od třídy `NavigationWindow`. V jazyce Visual Basic tomu automaticky dojde při změně okna v jazyce XAML, takže je nutné provést žádné změny kódu.  
  
## <a name="adding-files-to-the-application"></a>Přidávání souborů do aplikace  
 V této části přidáte dvě stránky a bitovou kopii do aplikace.  
  
#### <a name="to-add-a-home-screen"></a>Chcete-li přidat domovskou obrazovku  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ExpenseIt –** uzel a zvolte **přidat**, **stránky**.  
  
2.  V **přidat novou položku** dialogovém okně, vyberte **název** text a zadejte `ExpenseItHome`a potom zvolte **přidat** tlačítko.  
  
     Tato stránka je první okno, které se zobrazí, když je aplikace spuštěna.  
  
3.  V návrháři, vyberte **ExpenseItHome.xaml** kartě, pokud již není aktivní návrháře karty.  
  
4.  Vyberte `<Title>` elementu a změňte název na **ExpenseIt – - Domů**.  
  
     Vaše **ExpenseItHome.xaml** soubor by měl nyní vypadat jako v C#:  
  
    ```xaml  
    <Page x:Class="ExpenseIt.ExpenseItHome"  
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
          xmlns:local="clr-namespace:ExpenseIt"  
          mc:Ignorable="d"   
          d:DesignHeight="300" d:DesignWidth="300"  
          Title="ExpenseIt - Home">    
        <Grid>  
  
        </Grid>  
    </Page>  
    ```  
  
    V jazyce Visual Basic, bude první řádek podle mírně odlišný:  
  
    ```xaml  
    <Page x:Class="ExpenseItHome"  
    ```  
  
5.  V návrháři, vyberte **MainWindow.xaml** kartě.  
  
6.  Vyhledejte řádek `Title="ExpenseIt" Height="375" Width="500">` elementu a přidejte `Source="ExpenseItHome.xaml"` vlastnost.  
  
     Nastaví tato **ExpenseItHome.xaml** na první stránce otevřelo při spuštění aplikace. Vaše **MainWindow.xaml** soubor by měl nyní vypadat jako v C#:  
  
    ```xaml  
    <NavigationWindow x:Class="ExpenseIt.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
            xmlns:local="clr-namespace:ExpenseIt"  
            mc:Ignorable="d"  
            Title="ExpenseIt" Height="375" Width="500" Source="ExpenseItHome.xaml">    
    </NavigationWindow>  
    ```  
  
    V jazyce Visual Basic, bude první řádek podle mírně odlišný:  
  
    ```xaml  
    <NavigationWindow x:Class="MainWindow"
    ```  
  
     Jak se vlastností, které jste nastavili dříve, můžete mít nastavit `Source` vlastnost **různé** kategorii **vlastnosti** okno.  
  
#### <a name="to-add-a-details-window"></a>Chcete-li přidat okno podrobností  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ExpenseIt –** uzel a zvolte **přidat**, **stránky**.  
  
2.  V **přidat novou položku** dialogovém okně, vyberte **název** text a zadejte `ExpenseReportPage`a potom zvolte **přidat** tlačítko.  
  
     Toto okno se zobrazí sestavu jednotlivých výdajů.  
  
3.  V návrháři, vyberte **ExpenseReportPage.xaml** kartě, pokud již není aktivní návrháře karty.  
  
4.  Vyberte `<Title>` elementu a změňte název na **ExpenseIt – - zobrazení výdajů**.  
  
     Váš soubor ExpenseReportPage.xaml by měl nyní vypadat například takto v jazyce C#:  
  
    ```xaml  
    <Page x:Class="ExpenseIt.ExpenseReportPage"  
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
          xmlns:local="clr-namespace:ExpenseIt"  
          mc:Ignorable="d"   
          d:DesignHeight="300" d:DesignWidth="300"  
          Title="ExpenseIt - View Expense">    
        <Grid>  
  
        </Grid>  
    </Page>  
    ```  
  
    V jazyce Visual Basic se jemně liší první řádek:  
  
    ```xaml  
    <Page x:Class="ExpenseReportPage"  
    ```  
  
5.  Na řádku nabídek zvolte **ladění**, **spustit ladění** (nebo stiskněte klávesu F5) ke spuštění aplikace.  
  
     Následující obrázek znázorňuje aplikace s okno navigačních tlačítek.  
  
     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
6.  Zavřete aplikaci se vraťte do režimu návrhu.  
  
## <a name="creating-the-user-interface"></a>Vytvoření uživatelského rozhraní  
 Rozložení poskytuje seřazené způsob, jak umístit elementy a také spravuje velikost a umístění těchto elementů při změně velikosti formuláře. V této části vytvoříte jednoho sloupce mřížky s tři řádky. Budete přidání ovládacích prvků do dvě stránky, přidat kód a nakonec definovat opakovaně použitelné styly pro ovládací prvky.  
  
#### <a name="to-create-the-layout"></a>Chcete-li vytvořit rozložení  
  
1.  Otevřete **ExpenseItHome.xaml** a zvolte `<Grid>` elementu.  
  
2.  V **vlastnosti** okno, rozbalte **rozložení** uzel kategorie a sadu **okraj** hodnoty k `10`, `10`, `0`a `10`, která odpovídá levé, pravé, horní a dolní okraj.  
  
     Element `Margin="10,0,10,10"` je přidán do `<Grid>` element v XAML. Ještě jednou, může zadání těchto hodnot přímo v kódu XAML místo v **vlastnosti** okno s stejného výsledku.  
  
3.  Přidejte následující kód XAML, který `Grid` elementu, který chcete vytvořit definice řádků a sloupců:  
  
    ```xaml  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto"/>  
        <RowDefinition />  
        <RowDefinition Height="Auto"/>  
    </Grid.RowDefinitions>  
    ```  
  
#### <a name="to-add-controls"></a>K přidávání ovládacích prvků  
  
1.  Otevřete **ExpenseItHome.xaml**.  
  
2.  Přidejte následující kód XAML právě vyšší `</Grid>` značky k vytvoření `Border`, `ListBox` a `Button` ovládacích prvků:  
  
    ```xaml  
    <!-- People list -->  
      <Border Grid.Column="0" Grid.Row="0" Height="35" Padding="5" Background="#4E87D4">  
          <Label VerticalAlignment="Center" Foreground="White">Names</Label>  
      </Border>  
      <ListBox Name="peopleListBox" Grid.Column="0" Grid.Row="1">  
          <ListBoxItem>Mike</ListBoxItem>  
          <ListBoxItem>Lisa</ListBoxItem>  
          <ListBoxItem>John</ListBoxItem>  
          <ListBoxItem>Mary</ListBoxItem>  
      </ListBox>  
  
      <!-- View report button -->  
      <Button Grid.Column="0" Grid.Row="2" Margin="0,10,0,0" Width="125"  
    Height="25" HorizontalAlignment="Right">View</Button>    
    ```  
  
     Všimněte si, že ovládací prvky se zobrazí v okně návrhu. Může také vytvoříte ovládací prvky přetažením z **sada nástrojů** okna do okna návrhu a nastavování jejich vlastností **vlastnosti** okno.  
  
3.  Sestavte a spusťte aplikaci. Následující obrázek znázorňuje běhu vzhled ovládacích prvků, které jsou vytvořené pomocí XAML v tomto postupu.  
  
     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
4.  Zavřete aplikaci se vraťte do režimu návrhu.  
  
#### <a name="to-add-a-background-image"></a>Chcete-li přidat obrázek na pozadí  
  
1.  Vyberte následující obrázek a uložte ho jako `watermark.png`.  
  
     ![Vodoznak návod](../designers/media/wpf_watermark.png "WPF_watermark")  
  
    > [!NOTE]
    >  Případně můžete vytvořit vlastní image a uložte ho jako `watermark.png`.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ExpenseIt –** uzel a zvolte **přidat**, **existující položka**.  
  
3.  V **přidat existující položku** dialogové okno, Najít **watermark.png** bitovou kopii, kterou jste právě přidali, zvolte jej a potom zvolte **přidat** tlačítko.  
  
    > [!NOTE]
    >  Budete muset Rozbalit **typy souborů** seznam a vyberte **soubory obrázků**.  
  
4.  Otevřete **ExpenseItHome.xaml** souboru a přidejte následující kód XAML právě vyšší `</Grid>` značka vytvořit obrázek na pozadí:  
  
    ```xaml  
    <Grid.Background>  
        <ImageBrush ImageSource="watermark.png"/>  
    </Grid.Background>    
    ```  
  
#### <a name="to-add-a-title"></a>Přidání názvu  
  
1.  Otevřete **ExpenseItHome.xaml**.  
  
2.  Vyhledejte řádek `<Grid.ColumnDefinitions>` a přidejte následující právě pod ním:  
  
    ```xaml  
    <ColumnDefinition Width="230" />    
    ```  
  
     Tím se vytvoří sloupec nalevo od ostatních sloupců s pevnou šířkou 230 pixelů.  
  
3.  Vyhledejte řádek `<Grid.RowDefinitions>` a přidejte následující právě pod ním:  
  
    ```xaml  
    <RowDefinition />    
    ```  
  
     Tento postup přidá řádek do horní části mřížky.  
  
4.  Přesunout ovládacích prvků na druhý sloupec nastavením `Grid.Column` hodnotu 1. Každý ovládací prvek dolů řádek, zvýšením každý `Grid.Row` hodnoty 1.  
  
    1.  Vyhledejte řádek `<Border Grid.Column="0" Grid.Row="0" Height="35" Padding="5" Background="#4E87D4">`. Změnit `Grid.Column="0"` k `Grid.Column="1"` a změňte `Grid.Row="0"` k `Grid.Row="1"`.  
  
    2.  Vyhledejte řádek `<ListBox Name="peopleListBox" Grid.Column="0" Grid.Row="1"`. Změnit `Grid.Column="0"` k `Grid.Column="1"` a změňte `Grid.Row="1"` k `Grid.Row="2"`.  
  
    3.  Vyhledejte řádek `<Button Grid.Column="0" Grid.Row="2" Margin="0,10,0,0" Width="125"`. Změnit `Grid.Column="0"` k `Grid.Column="1"` a změňte `Grid.Row="2"` k `Grid.Row="3"`.  
  
5.  Těsně před `<Border` element přidejte následující kód XAML zobrazit název:  
  
    ```xaml  
    <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"   
            FontWeight="Bold" FontSize="18" Foreground="#0066cc">  
        View Expense Report  
    </Label>    
    ```  
  
     Obsah **ExpenseItHome.xaml** by teď měl vypadat takto v jazyce C#:  
  
    ```xaml  
    <Page x:Class="ExpenseIt.ExpenseItHome"  
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
          xmlns:local="clr-namespace:ExpenseIt"  
          mc:Ignorable="d"   
          d:DesignHeight="300" d:DesignWidth="300"  
          Title="ExpenseIt - Home">  
        <Grid Margin="10,0,10,10">  
            <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="230" />  
                <ColumnDefinition />  
            </Grid.ColumnDefinitions>  
            <Grid.RowDefinitions>  
                <RowDefinition />  
                <RowDefinition Height="Auto"/>  
                <RowDefinition />  
                <RowDefinition Height="Auto"/>  
            </Grid.RowDefinitions>  
            <Border Grid.Column="1" Grid.Row="1" Height="35" Padding="5" Background="#4E87D4">  
                <Label VerticalAlignment="Center" Foreground="White">Names</Label>  
            </Border>  
            <!-- People list -->  
            <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"   
            FontWeight="Bold" FontSize="18" Foreground="#0066cc">  
                View Expense Report  
            </Label>  
            <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2">  
                <ListBoxItem>Mike</ListBoxItem>  
                <ListBoxItem>Lisa</ListBoxItem>  
                <ListBoxItem>John</ListBoxItem>  
                <ListBoxItem>Mary</ListBoxItem>  
            </ListBox>  
  
            <!-- View report button -->  
            <Button Grid.Column="1" Grid.Row="3" Margin="0,10,0,0" Width="125"  
    Height="25" HorizontalAlignment="Right">View</Button>  
            <Grid.Background>  
                <ImageBrush ImageSource="watermark.png"/>  
            </Grid.Background>  
        </Grid>  
    </Page>  
    ```  
  
    V jazyce Visual Basic se jemně liší první řádek:  
  
    ```xaml  
    <Page x:Class="ExpenseItHome"  
    ```  
  
6.  Pokud sestavení a spuštění aplikace v tomto okamžiku by měl vypadat jako na následujícím obrázku:  
  
     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
#### <a name="to-add-code-to-the-button"></a>Chcete-li přidat kód pro tlačítko  
  
1.  Otevřete **ExpenseItHome.xaml**.  
  
2.  Zvolili `Button` elementu a přidejte následující kód XAML ihned po `HorizontalAlignment="Right"` element: `Click="Button_Click"`.  
  
     Tento postup přidá obslužné rutiny události pro tlačítka `Click` událostí. **Tlačítko** element kódu by teď měl vypadat takto:  
  
    ```xaml  
    <!-- View report button -->  
      <Button Grid.Column="1" Grid.Row="3" Margin="0,10,0,0" Width="125"  
    Height="25" HorizontalAlignment="Right" Click="Button_Click">View</Button>  
    ```  
  
3.  Otevřete **ExpenseItHome.xaml.cs** nebo **ExpenseItHome.xaml.vb** souboru.  
  
4.  Přidejte následující kód, který `ExpenseItHome` třídy:  
  
    ```csharp  
    private void Button_Click(object sender, RoutedEventArgs e)  
    {  
        // View Expense Report  
        ExpenseReportPage expenseReportPage = new ExpenseReportPage();  
        this.NavigationService.Navigate(expenseReportPage);    
    }  
    ```  
  
    ```vb  
    Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
        ' View Expense Report  
        Dim expenseReportPage As New ExpenseReportPage()  
    Me.NavigationService.Navigate(expenseReportPage)  
    End Sub  
    ```  
  
     Tuto obslužnou rutinu události při kliknutí na tlačítko otevře se stránka sestavy náklady.  
  
#### <a name="to-create-the-ui-for-the-report-page"></a>Chcete-li vytvořit uživatelské rozhraní pro stránky sestavy  
  
1.  Otevřete **ExpenseReportPage.xaml**.  
  
     Tato stránka zobrazí vyúčtování osobě, která je vybrána na domovské stránce.  
  
2.  Přidejte následující kód XAML mezi `<Grid>` a `</Grid>` značky:  
  
    ```xaml  
    <Grid.Background>  
        <ImageBrush ImageSource="watermark.png" />  
    </Grid.Background>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="230" />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto" />  
        <RowDefinition />  
    </Grid.RowDefinitions>  
  
    <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"   
    FontWeight="Bold" FontSize="18" Foreground="#0066cc">  
        Expense Report For:  
    </Label>  
    <Grid Margin="10" Grid.Column="1" Grid.Row="1">  
  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
        <Grid.RowDefinitions>  
            <RowDefinition Height="Auto" />  
            <RowDefinition Height="Auto" />  
            <RowDefinition />  
        </Grid.RowDefinitions>  
  
        <!-- Name -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">  
            <Label Margin="0,0,0,5" FontWeight="Bold">Name:</Label>  
            <Label Margin="0,0,0,5" FontWeight="Bold"></Label>  
        </StackPanel>  
  
        <!-- Department -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1" Orientation="Horizontal">  
            <Label Margin="0,0,0,5" FontWeight="Bold">Department:</Label>  
            <Label Margin="0,0,0,5" FontWeight="Bold"></Label>  
        </StackPanel>  
  
        <Grid Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2" VerticalAlignment="Top"   
              HorizontalAlignment="Left">  
            <!-- Expense type and Amount table -->  
            <DataGrid  AutoGenerateColumns="False" RowHeaderWidth="0" >  
                <DataGrid.ColumnHeaderStyle>  
                    <Style TargetType="{x:Type DataGridColumnHeader}">  
                        <Setter Property="Height" Value="35" />  
                        <Setter Property="Padding" Value="5" />  
                        <Setter Property="Background" Value="#4E87D4" />  
                        <Setter Property="Foreground" Value="White" />  
                    </Style>  
                </DataGrid.ColumnHeaderStyle>  
                <DataGrid.Columns>  
                    <DataGridTextColumn Header="ExpenseType" />  
                    <DataGridTextColumn Header="Amount"  />  
                </DataGrid.Columns>  
            </DataGrid>  
        </Grid>  
    </Grid>  
    ```  
  
     Toto uživatelské rozhraní je podobná uživatelského rozhraní pro domovskou stránku vytvořit, ale v se zobrazí data sestavy **DataGrid** ovládacího prvku.  
  
3.  Sestavte a spusťte aplikaci.  
  
4.  Vyberte **zobrazení** tlačítko.  
  
     Zobrazí se stránka sestavy výdajů.  
  
     Následující obrázek znázorňuje stránka sestavy výdajů. Všimněte si, že je povolena back navigační tlačítko.  
  
     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
#### <a name="to-style-controls"></a>Pro ovládací prvky stylu  
  
1.  Otevřete **App.xaml** souboru (C#) nebo **Application.xaml** souboru (Visual Basic).  
  
2.  Přidejte následující XAML mezi `<Application.Resources>` a `</Application.Resources>` značky:  
  
    ```xaml  
    <!-- Header text style -->  
    <Style x:Key="headerTextStyle">  
        <Setter Property="Label.VerticalAlignment" Value="Center"></Setter>  
        <Setter Property="Label.FontFamily" Value="Trebuchet MS"></Setter>  
        <Setter Property="Label.FontWeight" Value="Bold"></Setter>  
        <Setter Property="Label.FontSize" Value="18"></Setter>  
        <Setter Property="Label.Foreground" Value="#0066cc"></Setter>  
    </Style>  
  
    <!-- Label style -->  
    <Style x:Key="labelStyle" TargetType="{x:Type Label}">  
        <Setter Property="VerticalAlignment" Value="Top" />  
        <Setter Property="HorizontalAlignment" Value="Left" />  
        <Setter Property="FontWeight" Value="Bold" />  
        <Setter Property="Margin" Value="0,0,0,5" />  
    </Style>  
  
    <!-- DataGrid header style -->  
    <Style x:Key="columnHeaderStyle" TargetType="{x:Type DataGridColumnHeader}">  
        <Setter Property="Height" Value="35" />  
        <Setter Property="Padding" Value="5" />  
        <Setter Property="Background" Value="#4E87D4" />  
        <Setter Property="Foreground" Value="White" />  
    </Style>  
  
    <!-- List header style -->  
    <Style x:Key="listHeaderStyle" TargetType="{x:Type Border}">  
        <Setter Property="Height" Value="35" />  
        <Setter Property="Padding" Value="5" />  
        <Setter Property="Background" Value="#4E87D4" />  
    </Style>  
  
    <!-- List header text style -->  
    <Style x:Key="listHeaderTextStyle" TargetType="{x:Type Label}">  
        <Setter Property="Foreground" Value="White" />  
        <Setter Property="VerticalAlignment" Value="Center" />  
        <Setter Property="HorizontalAlignment" Value="Left" />  
    </Style>  
  
    <!-- Button style -->  
    <Style x:Key="buttonStyle" TargetType="{x:Type Button}">  
        <Setter Property="Width" Value="125" />  
        <Setter Property="Height" Value="25" />  
        <Setter Property="Margin" Value="0,10,0,0" />  
        <Setter Property="HorizontalAlignment" Value="Right" />  
    </Style>  
    ```  
  
     Tato XAML přidá následující styly:  
  
    -   `headerTextStyle`: Chcete-li formát názvu stránky `Label`.  
  
    -   `labelStyle`: K formátování `Label` ovládací prvky.  
  
    -   `columnHeaderStyle`: K formátování `DataGridColumnHeader`.  
  
    -   `listHeaderStyle`: K formátování záhlaví seznamu `Border` ovládací prvky.  
  
    -   `listHeaderTextStyle`: K formátování záhlaví seznamu **popisek**.  
  
    -   `buttonStyle`: K formátování `Button` na **ExpenseItHome.xaml** pppage.  
  
3.  Otevřete **ExpenseItHome.xaml** a nahraďte všechno mezi `<Grid>` a `</Grid>` prvky s následující XAML:  
  
    ```xaml  
    <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="230" />  
                <ColumnDefinition />  
            </Grid.ColumnDefinitions>  
  
            <Grid.RowDefinitions>  
                <RowDefinition/>  
                <RowDefinition Height="Auto"/>  
                <RowDefinition />  
                <RowDefinition Height="Auto"/>  
            </Grid.RowDefinitions>  
            <Label Grid.Column="1" Style="{StaticResource headerTextStyle}" >  
                View Expense Report  
            </Label>  
            <!-- People list -->  
                  <Border Grid.Column="1" Grid.Row="1" Style="{StaticResource listHeaderStyle}">  
                <Label Style="{StaticResource listHeaderTextStyle}">Names</Label>  
            </Border>  
            <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2">  
                <ListBoxItem>Mike</ListBoxItem>  
                <ListBoxItem>Lisa</ListBoxItem>  
                <ListBoxItem>John</ListBoxItem>  
                <ListBoxItem>Mary</ListBoxItem>  
            </ListBox>  
  
            <!-- View report button -->  
            <Button Grid.Column="1" Grid.Row="3" Click="Button_Click" Style="{StaticResource buttonStyle}">View</Button>  
            <Grid.Background>  
                <ImageBrush ImageSource="watermark.png"  />  
            </Grid.Background>  
    ```  
  
     Vlastnosti, jako `VerticalAlignment` a `FontFamily` které definují, jak vypadá každý ovládací prvek se odeberou a nahrazuje použití stylů.  
  
4.  Otevřete **ExpenseReportPage.xaml** a nahraďte všechno mezi `<Grid>` a finální `</Grid>` prvky s následující XAML:  
  
    ```xaml  
    <Grid.Background>  
        <ImageBrush ImageSource="watermark.png" />  
    </Grid.Background>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="230" />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto" />  
        <RowDefinition />  
    </Grid.RowDefinitions>  
    <Label Grid.Column="1" Style="{StaticResource headerTextStyle}">  
        Expense Report For:  
    </Label>  
    <Grid Margin="10" Grid.Column="1" Grid.Row="1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
        <Grid.RowDefinitions>  
            <RowDefinition Height="Auto" />  
            <RowDefinition Height="Auto" />  
            <RowDefinition />  
        </Grid.RowDefinitions>  
  
        <!-- Name -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">  
            <Label Style="{StaticResource labelStyle}">Name:</Label>  
            <Label Style="{StaticResource labelStyle}"></Label>  
        </StackPanel>  
  
        <!-- Department -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1"   
    Orientation="Horizontal">  
            <Label Style="{StaticResource labelStyle}">Department:</Label>  
            <Label Style="{StaticResource labelStyle}"></Label>  
        </StackPanel>  
  
        <Grid Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2" VerticalAlignment="Top"   
              HorizontalAlignment="Left">  
            <!-- Expense type and Amount table -->  
            <DataGrid ColumnHeaderStyle="{StaticResource columnHeaderStyle}"   
                      AutoGenerateColumns="False" RowHeaderWidth="0" >  
                <DataGrid.Columns>  
                    <DataGridTextColumn Header="ExpenseType" />  
                    <DataGridTextColumn Header="Amount"  />  
                </DataGrid.Columns>  
            </DataGrid>  
        </Grid>  
    </Grid>    
    ```  
  
     Tento postup přidá stylů pro `<Label>` a `<Border>` elementy.  
  
## <a name="connecting-to-data"></a>Připojení k datům  
 V této části vytvoříte zprostředkovatele dat a dat šablonu a potom se připojte ovládacích prvků pro zobrazení dat.  
  
#### <a name="to-bind-data-to-a-control"></a>K vytvoření vazby dat k ovládacímu prvku  
  
1.  Otevřete **ExpenseItHome.xaml** a zvolte `<Grid>` element...  
  
2.  Přidejte následující kód XAML:  
  
    ```xaml    
    <Grid.Resources>  
    <!-- Expense Report Data -->  
    <XmlDataProvider x:Key="ExpenseDataSource" XPath="Expenses">  
        <x:XData>  
            <Expenses xmlns="">  
                <Person Name="Mike" Department="Legal">  
                    <Expense ExpenseType="Lunch" ExpenseAmount="50" />  
                    <Expense ExpenseType="Transportation" ExpenseAmount="50" />  
                </Person>  
                <Person Name="Lisa" Department="Marketing">  
                    <Expense ExpenseType="Document printing"  
          ExpenseAmount="50"/>  
                    <Expense ExpenseType="Gift" ExpenseAmount="125" />  
                </Person>  
                <Person Name="John" Department="Engineering">  
                    <Expense ExpenseType="Magazine subscription"   
         ExpenseAmount="50"/>  
                    <Expense ExpenseType="New machine" ExpenseAmount="600" />  
                    <Expense ExpenseType="Software" ExpenseAmount="500" />  
                </Person>  
                <Person Name="Mary" Department="Finance">  
                    <Expense ExpenseType="Dinner" ExpenseAmount="100" />  
                </Person>  
            </Expenses>  
        </x:XData>  
    </XmlDataProvider>  
    </Grid.Resources>  
    ```  
  
     Tento kód vytvoří `XmlDataProvider` třídu, která obsahuje data pro každou osobu. Obvykle to by načíst jako soubor, ale pro zjednodušení je přidat data vložené.  
  
3.  Uvnitř `<Grid.Resources>` elementu, přidejte následující kód XAML:  
  
    ```xaml  
    <!-- Name item template -->  
    <DataTemplate x:Key="nameItemTemplate">  
        <Label Content="{Binding XPath=@Name}"/>  
    </DataTemplate>  
    ```  
  
     Tím se přidá `Data Template` určující způsob zobrazení dat v **ListBox**.  
  
4.  Nahradit existující `<ListBox>` element s následující XAML:  
  
    ```xaml  
    <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2"   
             ItemsSource="{Binding Source={StaticResource ExpenseDataSource}, XPath=Person}"  
             ItemTemplate="{StaticResource nameItemTemplate}">  
    </ListBox>  
    ```  
  
     Tento kód váže `ItemsSource` vlastnost `ListBox` ke zdroji dat a použije šablona dat jako `ItemTemplate`.  
  
#### <a name="to-connect-data-to-controls"></a>Pro připojení dat k ovládacím prvkům  
  
1.  Otevřete **ExpenseReportPage.xaml.vb** nebo **ExpenseReportPage.xaml.cs**.  
  
2.  V jazyce C#, přidejte následující konstruktor **ExpenseReportPage** třídy, nebo v jazyce Visual Basic nahraďte existující třídy následujícím kódem:  
  
    ```csharp  
    // Custom constructor to pass expense report data  
    public ExpenseReportPage(object data):this()  
    {  
        // Bind to expense report data.  
        this.DataContext = data;  
    }  
    ```  
  
    ```vb  
    Partial Public Class ExpenseReportPage  
    Inherits Page  
        Public Sub New()  
        InitializeComponent()  
        End Sub  
  
        ' Custom constructor to pass expense report data  
        Public Sub New(ByVal data As Object)  
            Me.New()  
            ' Bind to expense report data.  
            Me.DataContext = data  
        End Sub    
    End Class  
    ```  
  
     Tento konstruktor přijímá objekt dat jako parametr. Datový objekt v tomto případě bude obsahovat název vybraného uživatele.  
  
3.  Otevřete **ExpenseItHome.xaml.vb** nebo **ExpenseItHome.xaml.cs**.  
  
4.  Nahraďte `Click` kód obslužné rutiny událostí s následující:  
  
    ```csharp  
    private void Button_Click(object sender, RoutedEventArgs e)  
    {  
        // View Expense Report  
        ExpenseReportPage expenseReportPage = new ExpenseReportPage(this.peopleListBox.SelectedItem);  
        this.NavigationService.Navigate(expenseReportPage);    
    }  
    ```  
  
    ```vb  
    Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
        ' View Expense Report  
        Dim expenseReportPage As New ExpenseReportPage(Me.peopleListBox.SelectedItem)  
        Me.NavigationService.Navigate(expenseReportPage)  
    End Sub  
    ```  
  
     Tento kód zavolá nové konstruktoru.  
  
#### <a name="to-update-the-ui-with-data-templates"></a>Aktualizace uživatelského rozhraní pomocí šablony dat  
  
1.  Otevřete **ExpenseReportPage.xaml**.  
  
2.  Nahraďte kód XAML pro **název** a **oddělení** `<StackPanel` prvky s následující:  
  
    ```xaml  
    <!-- Name -->  
    <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">  
        <Label Style="{StaticResource labelStyle}">Name:</Label>  
        <Label Style="{StaticResource labelStyle}" Content="{Binding XPath=@Name}"></Label>  
    </StackPanel>  
  
    <!-- Department -->  
    <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1" Orientation="Horizontal">  
        <Label Style="{StaticResource labelStyle}">Department:</Label>  
        <Label Style="{StaticResource labelStyle}" Content="{Binding XPath=@Department}"></Label>  
    </StackPanel>    
    ```  
  
     Tím je vytvořena vazba **popisek** ovládací prvky pro vlastnosti zdroje příslušná data.  
  
3.  Přidejte následující kód XAML uvnitř `<Grid>` element:  
  
    ```xaml  
    <!--Templates to display expense report data-->  
    <Grid.Resources>  
        <!-- Reason item template -->  
        <DataTemplate x:Key="typeItemTemplate">  
            <Label Content="{Binding XPath=@ExpenseType}"/>  
        </DataTemplate>  
        <!-- Amount item template -->  
        <DataTemplate x:Key="amountItemTemplate">  
            <Label Content="{Binding XPath=@ExpenseAmount}"/>  
        </DataTemplate>  
    </Grid.Resources>    
    ```  
  
     Definuje způsob, jak zobrazit data sestavy výdajů.  
  
4.  Nahraďte `<DataGrid>` element s následující:  
  
    ```xaml  
    <!-- Expense type and Amount table -->  
    <DataGrid ItemsSource="{Binding XPath=Expense}" ColumnHeaderStyle="{StaticResource columnHeaderStyle}" AutoGenerateColumns="False" RowHeaderWidth="0" >  
  
        <DataGrid.Columns>  
            <DataGridTextColumn Header="ExpenseType" Binding="{Binding XPath=@ExpenseType}"  />  
            <DataGridTextColumn Header="Amount" Binding="{Binding XPath=@ExpenseAmount}" />  
        </DataGrid.Columns>  
  
    </DataGrid>  
    ```  
  
     Tím se přidá **ItemSource** a definuje vazby u položek výdajů.  
  
5.  Sestavte a spusťte aplikaci.  
  
6.  Zvolte osoby a pak **zobrazení** tlačítko.  
  
     Následující obrázek znázorňuje obě stránky aplikace ExpenseIt – ovládací prvky, rozložení, styly, datové vazby a šablony dat použít.  
  
     ![Snímky obrazovky ukázkové ExpenseIt –](../designers/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
##  <a name="Best_Practices"></a>Doporučené postupy  
 Tento příklad ukazuje základy grafického subsystému WPF a v důsledku toho nedodrží osvědčené postupy pro vývoj aplikací. Podle potřeby komplexní přehled WPF a rozhraní .NET Framework aplikace vývoj osvědčené postupy, najdete v následujících tématech:  
  
-   Usnadnění – [usnadnění – doporučené postupy](https://msdn.microsoft.com/en-us/library/aa350483\(v=vs.100\).aspx)  
  
-   Zabezpečení – [zabezpečení systému Windows Presentation Foundation](https://msdn.microsoft.com/en-us/library/aa970906\(v=vs.100\).aspx)  
  
-   Lokalizace - [WPF globalizace a lokalizace – přehled](https://msdn.microsoft.com/en-us/library/ms788718\(v=vs.100\).aspx)  
  
-   Výkon – [optimalizace výkonu aplikace WPF](https://msdn.microsoft.com/en-us/library/aa970683\(v=vs.100\).aspx)  
  
##  <a name="Whats_Next"></a>Co je další  
 Nyní máte několik technik k dispozici pro vytvoření aplikace pomocí grafického subsystému WPF. Teď byste měli mít základní znalosti o stavební bloky aplikace WPF vázané na data. Toto téma je rozhodně není vyčerpávající, ale zpravidla nyní také mít smysl pro některé možnosti, které můžete zjistit, na vlastní nad rámec techniky v tomto tématu.  
  
 Další informace o modelech WPF architektura a programování najdete v následujících tématech:  
  
-   [Architektura WPF](https://msdn.microsoft.com/en-us/library/ms750441\(v=vs.100\).aspx)  
  
-   [XAML – přehled](https://msdn.microsoft.com/en-us/library/ms752059\(v=vs.100\).aspx)  
  
-   [Přehled vlastností závislostí](https://msdn.microsoft.com/en-us/library/ms752914\(v=vs.100\).aspx)  
  
-   [Rozložení systému](https://msdn.microsoft.com/en-us/library/ms745058\(v=vs.100\).aspx)  
  
-   [Styly a šablony](https://msdn.microsoft.com/en-us/library/bb613570\(v=vs.100\).aspx)  
  
 Další informace o vytváření aplikací najdete v následujících tématech:  
  
-   [Přehled vývoje aplikace](https://msdn.microsoft.com/en-us/library/bb613549\(v=vs.100\).aspx)  
  
-   [Přehled ovládacích prvků](https://msdn.microsoft.com/en-us/library/bb613551\(v=vs.100\).aspx)  
  
-   [Přehled vazba dat](https://msdn.microsoft.com/en-us/library/ms752347\(v=vs.100\).aspx)  
  
-   [WPF grafiky, animace a přehled média](https://msdn.microsoft.com/en-us/library/ms742562\(v=vs.100\).aspx)  
  
-   [Dokumenty v grafickém subsystému WPF](https://msdn.microsoft.com/en-us/library/ms748388\(v=vs.100\).aspx)  
  
## <a name="see-also"></a>Viz také  
[Vytvoření moderních aplikací klasické pracovní plochy s Windows Presentation Foundation](../designers/create-modern-desktop-applications-with-windows-presentation-foundation.md)