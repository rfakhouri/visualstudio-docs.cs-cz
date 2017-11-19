---
redirect_url: /azure/app-service-mobile/app-service-mobile-windows-store-dotnet-get-started
title: "Návod: Vytvoření aplikace WPF plochy připojené k mobilní služby Azure | Microsoft Docs"
ms.custom: 
ms.date: 10/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d42620f-553b-4b04-a38b-f6b306d73a50
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- csharp
- vb
ms.openlocfilehash: 8bf11425439387a13db2bb77f0ce798bef076461
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-create-a-wpf-desktop-application-connected-to-an-azure-mobile-service"></a>Návod: Vytvoření aplikace WPF plochy připojené k mobilní služby Azure
Windows Presentation Foundation (WPF) můžete rychle vytvořit moderní plochy aplikaci, která využívá mobilní služby Azure k ukládání a poskytují data.  
  
## <a name="prerequisites"></a>Požadavky  
Následující příkaz pro dokončení tohoto návodu budete potřebovat:  
  
-   Visual Studio 2017 nebo všechny verze, která podporuje vývoj WPF.  
  
-   Aktivní účet Microsoft Azure.  
  
    -   Můžete si zaregistrovat Bezplatný zkušební účet [zde](http://azure.microsoft.com/en-us/pricing/free-trial/).  
  
    -   Můžete si aktivovat [výhody pro předplatitele MSDN](https://azure.microsoft.com/en-us/pricing/member-offers/msdn-benefits-details/?WT.mc_id=A261C142F). Vaše předplatné MSDN vám dává kredity každý měsíc, které můžete použít pro placené služby Azure.  
  
## <a name="create-a-project-and-add-references"></a>Vytvořte projekt a přidejte odkazy na  
 Prvním krokem je vytvoření projekt WPF a přidání balíčku NuGet, který vám umožní připojit se k Azure Mobile Services.  
  
#### <a name="to-create-the-project"></a>Vytvoření projektu  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte **Visual C#** nebo **jazyka Visual Basic** uzel a zvolte **Windows Classic Desktop** uzlu.  
  
3.  V seznamu šablony, vyberte **aplikace WPF (rozhraní .NET Framework)** šablony.  
  
4.  V **název** textového pole zadejte `WPFQuickStart`a potom zvolte **OK** tlačítko.  
  
     Vytvoření projektu a soubory projektu budou přidány do **Průzkumníku řešení**. Návrhář intervalu pro správu a výchozí aplikace s názvem **MainWindow.xaml** se zobrazí.  
  
#### <a name="to-add-a-reference-to-the-windows-azure-mobile-services-sdk"></a>Chcete-li přidat odkaz na sadu Windows Azure Mobile Services SDK  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **odkazy** uzel a zvolte **spravovat balíčky NuGet...** .  
  
2.  V **Správce balíčků NuGet**, zvolte **Procházet** horní části, pak zadejte `mobileservices` do vyhledávacího pole.  
  
3.  V levém podokně vyberte **WindowsAzure.MobileServices**a poté v pravém podokně vyberte **nainstalovat** tlačítko.  
  
    > [!NOTE]
    >  Pokud **Preview** dialogové okno se zobrazí, přečtěte si navrhované změny a pak vyberte **OK** tlačítko.  
  
4.  V **přijetí licence** dialogové okno, zkontrolujte licenční podmínky a přijměte je tak, že zvolíte **souhlasím** tlačítko.  
  
     Nezbytné odkazy budou přidány do **Průzkumníku řešení**.  
  
    > [!NOTE]
    >  Pokud nesouhlasíte s licenčními podmínkami, vyberte **I odmítnout** tlačítko. Nebudete moct dokončit zbývající návodu.  
  
## <a name="create-the-user-interface"></a>Vytvoření uživatelského rozhraní  
Dalším krokem je vytvoření uživatelského rozhraní pro aplikaci. Nejdřív vytvoříte opakovaně použitelné uživatelský ovládací prvek, který zobrazí standardní vedle sebe dva podokně rozložení. Budete přidat uživatelský ovládací prvek do okna hlavní aplikaci a přidání ovládacích prvků k zadání a zobrazovat data a pak napsat kód, který definovat interakci s back-end mobilní služby.  
  
#### <a name="to-add-a-user-control"></a>Chcete-li přidat uživatelský ovládací prvek  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **WPFQuickStart** uzel a zvolte **přidat**, **novou složku**.  
  
2.  Název složky `Common`.  
  
3.  Otevřete místní nabídku pro **běžné** složky a vyberte **přidat**, **uživatelský ovládací prvek**.  
  
4.  V **přidat novou položku** dialogové okno, zvolte název pole a zadejte `QuickStartTask`a potom zvolte **přidat** tlačítko.  
  
     Uživatelský ovládací prvek bude přidán do projektu a **QuickStartTask.xaml** soubor se otevře v návrháři.  
  
5.  V dolním podokně návrháře, vyberte `<Grid>` a `</Grid>` značky a nahraďte následujícím kódem XAML:  
  
    ```xaml  
    <Grid VerticalAlignment="Top">
        <StackPanel Orientation="Horizontal">
            <Border BorderThickness="0,0,1,0" BorderBrush="DarkGray" Margin="0,10" MinWidth="70">
                <TextBlock Text="{Binding Number}" FontSize="45" Foreground="DarkGray" Margin="20,0"/>
            </Border>
            <StackPanel>
                <TextBlock Text="{Binding Title}" Margin="10,10,0,0" FontSize="16" FontWeight="Bold" />
                <TextBlock Text="{Binding Description}" Margin="10,0,0,0" TextWrapping="Wrap" MaxWidth="500" />
            </StackPanel>
        </StackPanel>
    </Grid>  
    ```  
  
     Tento kód XAML vytvoří opakovaně použitelné rozložení se zástupnými symboly pro číslo, název a popis. Jak je znázorněno na následujícím obrázku, lze v době běhu nahradit zástupné symboly s textem.  
  
     ![Uživatelský ovládací prvek QuickStartTask](../designers/media/wpfquickstart1.PNG "WPFQuickStart1")  
  
6.  V **Průzkumníku řešení**, rozbalte **QuickStartTask.xaml** uzlu a otevřete **QuickStartTask.xaml.cs** nebo **QuickStartTask.xaml.vb**souboru.  
  
7.  V editoru kódu nahraďte `namespace WPFQuickStart.Common` obor názvů (C#) nebo `Public Class QuickStartTask` – třída (VB) s následujícím kódem:  
  
    ```csharp  
    namespace WPFQuickStart.Common  
    {  
        /// <summary>  
        /// Interaction logic for QuickStartTask.xaml  
        /// </summary>  
        public partial class QuickStartTask : UserControl  
        {  
            public QuickStartTask()  
            {  
                this.InitializeComponent();  
                this.DataContext = this;  
            }  
  
            public int Number  
            {  
                get { return (int)GetValue(NumberProperty); }  
                set { SetValue(NumberProperty, value); }  
            }  
  
            // Using a DependencyProperty as the backing store for Number.  This enables animation, styling, binding, etc...  
            public static readonly DependencyProperty NumberProperty =  
                DependencyProperty.Register("Number", typeof(int), typeof(QuickStartTask), new PropertyMetadata(0));  
  
            public string Title  
            {  
                get { return (string)GetValue(TitleProperty); }  
                set { SetValue(TitleProperty, value); }  
            }  
  
            // Using a DependencyProperty as the backing store for Title.  This enables animation, styling, binding, etc...  
            public static readonly DependencyProperty TitleProperty =  
                DependencyProperty.Register("Title", typeof(string), typeof(QuickStartTask), new PropertyMetadata(default(string)));  
  
            public string Description  
            {  
                get { return (string)GetValue(DescriptionProperty); }  
                set { SetValue(DescriptionProperty, value); }  
            }  
  
            // Using a DependencyProperty as the backing store for Description.  This enables animation, styling, binding, etc...  
            public static readonly DependencyProperty DescriptionProperty =  
                DependencyProperty.Register("Description", typeof(string), typeof(QuickStartTask), new PropertyMetadata(default(string)));  
        }  
    }  
    ```  
  
    ```vb  
    Partial Public Class QuickStartTask  
            Inherits UserControl  
  
            Public Sub New()  
                Me.InitializeComponent()  
                Me.DataContext = Me  
            End Sub  
  
            Public Property Number() As Integer  
                Get  
                    Return CInt(Fix(GetValue(NumberProperty)))  
                End Get  
                Set(ByVal value As Integer)  
                    SetValue(NumberProperty, value)  
                End Set  
            End Property  
  
            ' Using a DependencyProperty as the backing store for Number.  This enables animation, styling, binding, etc...  
            Public Shared ReadOnly NumberProperty As DependencyProperty = DependencyProperty.Register("Number", GetType(Integer), GetType(QuickStartTask), New PropertyMetadata(0))  
  
            Public Property Title() As String  
                Get  
                    Return CStr(GetValue(TitleProperty))  
                End Get  
                Set(ByVal value As String)  
                    SetValue(TitleProperty, value)  
                End Set  
            End Property  
  
            ' Using a DependencyProperty as the backing store for Title.  This enables animation, styling, binding, etc...  
            Public Shared ReadOnly TitleProperty As DependencyProperty = DependencyProperty.Register("Title", GetType(String), GetType(QuickStartTask), New PropertyMetadata(Nothing))  
  
            Public Property Description() As String  
                Get  
                    Return CStr(GetValue(DescriptionProperty))  
                End Get  
                Set(ByVal value As String)  
                    SetValue(DescriptionProperty, value)  
                End Set  
            End Property  
  
            ' Using a DependencyProperty as the backing store for Description.  This enables animation, styling, binding, etc...  
            Public Shared ReadOnly DescriptionProperty As DependencyProperty = DependencyProperty.Register("Description", GetType(String), GetType(QuickStartTask), New PropertyMetadata(Nothing))  
        End Class  
    ```  
  
     Tento kód používá k nastavení hodnot pro pole číslo, název a popis v době běhu vlastností závislostí.  
  
8.  Na řádku nabídek zvolte **sestavení**, **sestavení WPFQuickStart** k vytvoření uživatelského ovládacího prvku.  
  
#### <a name="to-create-and-modify-the-main-window"></a>Vytvoření a změna hlavní okno  
  
1.  V **Průzkumníku řešení**, otevřete **MainWindow.xaml** souboru.  
  
2.  **Důležité**. Tento krok je k dispozici pouze pro jazyk C#. Pokud používáte Visual Basic, přejděte k dalšímu kroku. V dolním podokně návrháře, vyhledejte řádek `xmlns:local="clr-namespace:WPFQuickStart"` a nahraďte ji následujícím kódem XAML:  
  
    ```xaml  
    xmlns:local="clr-namespace:WPFQuickStart.Common"  
    ```  
  
3.  V **vlastnosti** okno, rozbalte **běžné** uzel kategorie a zvolte **název** vlastnost a potom zadejte `WPF Todo List` a stiskněte klávesu **Enter**  klíč.  
  
     Všimněte si, že **název** element v okně XAML změní tak, aby odpovídala nové hodnotě. Můžete upravit vlastnosti XAML v okně XAML nebo **vlastnosti** okno a změny jsou synchronizovány.  
  
4.  V okně XAML, nastavte hodnotu **výška** element `768`a nastavte hodnotu **šířka** vlastnost, která má `1280`.  
  
     Tyto prvky odpovídají **výška** a **šířka** vlastnosti, nalezené v **rozložení** kategorie v **vlastnosti** okno.  
  
5.  Vyberte `<Grid>` a `</Grid>` značky a nahraďte následujícím kódem XAML:  
  
    ```xaml  
    <Grid>
        <Grid Margin="50,50,10,10">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="*" />
                <ColumnDefinition Width="*" />
            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
                <RowDefinition Height="Auto" />
                <RowDefinition Height="*" />
            </Grid.RowDefinitions>
            <Grid Grid.Row="0" Grid.ColumnSpan="2" Margin="0,0,0,20">
                <StackPanel>
                    <TextBlock Foreground="#0094ff" FontFamily="Segoe UI Light" Margin="0,0,0,6">MICROSOFT AZURE MOBILE SERVICES</TextBlock>
                    <TextBlock Foreground="Gray" FontFamily="Segoe UI Light" FontSize="45" ><Run Text="My Todo List"/></TextBlock>
                </StackPanel>
            </Grid>
            <Grid Grid.Row="1">
                <StackPanel>
                    <local:QuickStartTask Number="1" Title="Insert a TodoItem" Description="Enter some text below and click Save to insert a new todo item into the list." />
                    <StackPanel Orientation="Horizontal" Margin="72,0,0,0">
                        <TextBox x:Name="TodoInput" Margin="5" MinWidth="300"/>
                        <Button x:Name="ButtonSave" Click="ButtonSave_Click" Content="Save"/>
                    </StackPanel>
                </StackPanel>
            </Grid>
            <Grid Grid.Row="1" Grid.Column="1">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition />
                </Grid.RowDefinitions>
                <StackPanel>
                    <local:QuickStartTask Number="2" Title="Query and Update Data" Description="Click the Refresh button to load the unfinished TodoItems from the Azure Mobile Service. Select the checkbox to mark a ToDo item as complete and update the list." />
                    <Button Margin="72,0,0,0" Name="ButtonRefresh" Click="ButtonRefresh_Click">Refresh</Button>
                </StackPanel>
                <ListView Name="ListItems" Margin="62,10,0,0" Grid.Row="1">
                    <ListView.ItemTemplate>
                        <DataTemplate>
                            <StackPanel Orientation="Horizontal">
                                <CheckBox Name="CheckBoxComplete" IsChecked="{Binding Complete, Mode=TwoWay}" Checked="CheckBoxComplete_Checked" Content="{Binding Text}" Margin="10,5" VerticalAlignment="Center"/>
                            </StackPanel>
                        </DataTemplate>
                    </ListView.ItemTemplate>
                </ListView>
            </Grid>
        </Grid>
    </Grid>  
    ```  
  
     Všimněte si, že změny se projeví v okně návrh. Znovu, můžete také může mít definované uživatelské rozhraní přidání ovládacích prvků z **sada nástrojů** okno a nastavení vlastností ve **vlastnosti** okno. Všechno, co můžete udělat v Návrháři lze provést v kódu XAML a naopak.  
  
     V návrhu v tomto okamžiku by měl vypadat jako na následujícím obrázku.  
  
     ![MainWindow v návrháři](../designers/media/wpfquickstart2.PNG "WPFQuickStart2")  
  
    > [!NOTE]
    >  Při další několik postupů může zobrazit chyby v **seznam chyb** Pokud je otevřen. Nemusíte si dělat starosti; Tyto chyby zmizí po dokončení další postupy.  
  
6.  V **Průzkumníku řešení**, rozbalte **MainWindow.xaml** uzlu a otevřete **MainWindow.xaml.cs** nebo **MainWindow.xaml.vb** souboru.  
  
7.  V editoru kódu, přidejte následující `using` nebo `Imports` direktivy do horní části souboru:  
  
    ```csharp  
    using Microsoft.WindowsAzure.MobileServices;  
    using Newtonsoft.Json;   
    ```  
  
    ```vb  
    Imports Microsoft.WindowsAzure.MobileServices  
    Imports Newtonsoft.Json  
    ```  
  
8.  Nahraďte kód v **WPFQuickStart** obor názvů (C#) nebo **třída MainWindow** – třída (VB) s následujícím kódem:  
  
    ```csharp  
    namespace WPFQuickStart  
    {  
        /// <summary>  
        /// Interaction logic for MainWindow.xaml  
        /// </summary>  
        public class TodoItem  
        {  
            public string Id { get; set; }  
  
            [JsonProperty(PropertyName = "text")]  
            public string Text { get; set; }  
  
            [JsonProperty(PropertyName = "complete")]  
            public bool Complete { get; set; }  
        }  
  
        public partial class MainWindow : Window  
        {  
            private MobileServiceCollection<TodoItem, TodoItem> items;  
            private IMobileServiceTable<TodoItem> todoTable = App.MobileService.GetTable<TodoItem>();  
  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            private async void InsertTodoItem(TodoItem todoItem)  
            {  
                // This code inserts a new TodoItem into the database. When the operation completes  
                // and Mobile Services has assigned an Id, the item is added to the CollectionView  
                await todoTable.InsertAsync(todoItem);  
                items.Add(todoItem);  
            }  
  
            private async void RefreshTodoItems()  
            {  
                try  
                {  
                    // This code refreshes the entries in the list view by querying the TodoItem table.  
                    // The query excludes completed TodoItems  
                    items = await todoTable  
                        .Where(todoItem => todoItem.Complete == false)  
                        .ToCollectionAsync();  
                    ListItems.ItemsSource = items;  
                }  
                catch (MobileServiceInvalidOperationException e)  
                {  
                    MessageBox.Show(e.Message, "Error loading items");  
                }  
            }  
  
            private async void UpdateCheckedTodoItem(TodoItem item)  
            {  
                // This code takes a freshly completed TodoItem and updates the database. When the MobileService   
                // responds, the item is removed from the list   
                await todoTable.UpdateAsync(item);  
                items.Remove(item);  
            }  
  
            private void ButtonRefresh_Click(object sender, RoutedEventArgs e)  
            {  
                RefreshTodoItems();  
            }  
  
            private void ButtonSave_Click(object sender, RoutedEventArgs e)  
            {  
                var todoItem = new TodoItem { Text = TodoInput.Text };  
                InsertTodoItem(todoItem);  
                TodoInput.Text = "";  
            }  
  
            private void CheckBoxComplete_Checked(object sender, RoutedEventArgs e)  
            {  
                CheckBox cb = (CheckBox)sender;  
                TodoItem item = cb.DataContext as TodoItem;  
                UpdateCheckedTodoItem(item);  
            }  
  
            protected override void OnActivated(EventArgs e)  
            {  
                RefreshTodoItems();  
            }  
        }  
  
    }  
    ```  
  
    ```vb  
    Public Class TodoItem  
        Public Property Id() As String  
  
        <JsonProperty(PropertyName:="text")>  
        Public Property Text() As String  
  
        <JsonProperty(PropertyName:="complete")>  
        Public Property Complete() As Boolean  
    End Class  
  
    Partial Public Class MainWindow  
        Inherits Window  
  
        Private items As MobileServiceCollection(Of TodoItem, TodoItem)  
        Private todoTable As IMobileServiceTable(Of TodoItem) = Application.MobileService.GetTable(Of TodoItem)()  
  
        Public Sub New()  
            InitializeComponent()  
        End Sub  
  
        Private Async Sub InsertTodoItem(ByVal todoItem As TodoItem)  
            ' This code inserts a new TodoItem into the database. When the operation completes  
            ' and Mobile Services has assigned an Id, the item is added to the CollectionView  
            Await todoTable.InsertAsync(todoItem)  
            items.Add(todoItem)  
        End Sub  
  
        Private Async Sub RefreshTodoItems()  
            Dim exception As MobileServiceInvalidOperationException = Nothing  
            Try  
                ' This code refreshes the entries in the list view by querying the TodoItem table.  
                ' The query excludes completed TodoItems  
                items = Await todoTable.Where(Function(todoItem) todoItem.Complete = False).ToCollectionAsync()  
            Catch e As MobileServiceInvalidOperationException  
                exception = e  
            End Try  
  
            If exception IsNot Nothing Then  
                MessageBox.Show(exception.Message, "Error loading items")  
            Else  
                ListItems.ItemsSource = items  
            End If  
        End Sub  
  
        Private Async Sub UpdateCheckedTodoItem(ByVal item As TodoItem)  
            ' This code takes a freshly completed TodoItem and updates the database. When the MobileService   
            ' responds, the item is removed from the list   
            Await todoTable.UpdateAsync(item)  
            items.Remove(item)  
        End Sub  
  
        Private Sub ButtonRefresh_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
            RefreshTodoItems()  
        End Sub  
  
        Private Sub ButtonSave_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
            Dim todoItem = New TodoItem With {.Text = TodoInput.Text}  
            InsertTodoItem(todoItem)  
            TodoInput.Text = ""  
        End Sub  
  
        Private Sub CheckBoxComplete_Checked(ByVal sender As Object, ByVal e As RoutedEventArgs)  
            Dim cb As CheckBox = DirectCast(sender, CheckBox)  
            Dim item As TodoItem = TryCast(cb.DataContext, TodoItem)  
            UpdateCheckedTodoItem(item)  
        End Sub  
  
        Protected Overrides Sub OnActivated(ByVal e As EventArgs)  
            RefreshTodoItems()  
        End Sub  
    End Class  
    ```  
  
     Tento kód definuje interakce mezi uživatelské rozhraní a databáze v rámci mobilní služby použití asynchronních metod.  
  
## <a name="create-the-azure-mobile-service"></a>Vytvoření mobilní služby Azure  
 Posledním krokem je vytvoření mobilní služby ve službě Microsoft Azure přidat tabulku pro ukládání dat a pak odkazovat instance služby z vaší aplikace.  
  
#### <a name="to-create-a-mobile-service"></a>Vytvoření mobilní služby  
  
1.  Otevřete webový prohlížeč a přihlaste se k portálu Microsoft Azure a pak zvolte **MOBILE SERVICES** kartě.  
  
2.  Vyberte **nový** tlačítko a v zobrazeném dialogu vyberte **výpočetní**, **mobilní služby, vytvořit**.  
  
3.  V **novou mobilní službu** dialogovém okně, vyberte **URL** textové pole a zadejte `wpfquickstart01`.  
  
    > [!NOTE]
    >  Budete muset změnit její číselnou část adresy URL. Microsoft Azure vyžaduje jedinečnou adresu URL pro každý mobilní služby.  
  
    Toto nastaví adresu URL pro službu, kterou chcete *https://wpfquickstart01.azure-mobile.net/*.  
  
4.  V **databáze** seznamu, vyberte možnost databáze. Vzhledem k tomu, že toto je aplikace, která pravděpodobně nebude získat spoustu využití, můžete vybrat **vytvoření databáze SQL 20MB volného** možnost, nebo zvolte bezplatné databázi již spojen s vaším předplatným.  
  
5.  V **oblast** vyberte datové centrum, kde chcete nasadit na mobilní službu a pak vyberte **Další** tlačítko (šipka vpravo).  
  
    > [!NOTE]
    >  Pro tuto službu budete používat výchozí **back-end** nastavení, **JavaScript**.  
  
6.  Pokud vytváříte novou databázi, na **zadejte nastavení databáze** stránky v **SERVER** seznamu zvolte **nové SQL databázový server**, zadejte vaše **přihlášení k serveru SQL NÁZEV** a **heslo**a potom zvolte **Complete** tlačítko (zaškrtnutí).  
  
7.  Pokud jste vybrali existující databázi, na **nastavení databáze** zadejte vaše **heslo pro přihlášení** a potom zvolte **Complete** tlačítko (zaškrtnutí).  
  
     Proces vytváření mobilní služby, bude zahájena. Po dokončení tohoto procesu se stav změní na **připraven** , a můžete přejít další krok.  
  
8.  Na portálu, vyberte nově vytvořenou mobilní služby a potom zvolte **Správa KLÍČŮ** tlačítko.  
  
9. V **spravovat přístupové klíče** dialogové okno, kopie **klíč aplikace**.  
  
     Toto budete používat v dalším postupu.  
  
#### <a name="to-create-a-table"></a>K vytvoření tabulky  
  
1.  Na portálu Microsoft Azure, zvolte na šipku vpravo vedle názvu vaší mobilní služby a na panelu nabídek a potom vyberte **DATA**a potom zvolte **tabulku A přidat** odkaz.  
  
2.  V **vytvořit novou tabulku** dialogové okno, v **název tabulky** textového pole zadejte `TodoItem`a potom zvolte **Complete** tlačítko (zaškrtnutí).  
  
     Počkejte tabulku, kterou chcete vytvořit a potom přejít na poslední postup.  
  
#### <a name="to-add-a-declaration-for-the-mobile-service"></a>Chcete-li přidat deklaraci mobilní služby  
  
1.  Vraťte se k sadě Visual Studio. V **Průzkumníku řešení**, rozbalte **App.xaml** (C#) nebo **Application.xaml** uzlu (Visual Basic) a otevřete **App.xaml.cs** nebo  **App.XAML.vb** souboru.  
  
2.  V editoru kódu, přidejte následující `using` nebo **importy** direktivy do horní části souboru:  
  
    ```csharp  
    using Microsoft.WindowsAzure.MobileServices;  
    ```  
  
    ```vb  
    Imports Microsoft.WindowsAzure.MobileServices  
    ```  
  
3.  Přidejte následující deklarace do třídy, nahraďte *YOUR SERVICE_HERE* s názvem adresy URL služby a nahrazení *YOUR-KEY-zde* klíčem aplikace, kterou jste zkopírovali v předchozím Postup:  
  
    ```csharp  
    public static MobileServiceClient MobileService = new MobileServiceClient(  
                 "https://YOUR-SERVICE-HERE.azure-mobile.net/",  
                 "YOUR-KEY-HERE"  
             );  
    ```  
  
    ```vb  
    Public Shared MobileService As New MobileServiceClient("https://YOUR-SERVICE-HERE.azure-mobile.net/", "YOUR-KEY-HERE")  
    ```  
  
     Tento kód umožňuje aplikaci získat přístup k mobilní službě systémem Microsoft Azure.  
  
## <a name="test-the-application"></a>Testování aplikace  
 Je to – WPF aplikace pracovní plochy, který přistupuje k mobilní služby Azure jste vytvořili. Nyní již zbývá je spuštění aplikace a pozorování v akci.  
  
#### <a name="to-run-the-application"></a>Ke spuštění aplikace  
  
1.  Na řádku nabídek zvolte **ladění**, **spustit ladění** (nebo stiskněte klávesu **F5**).  
  
2.  V **vložení úkolu** textovému poli, zadejte `Do something`a potom zvolte **Uložit** tlačítko.  
  
3.  Zadejte `Do something else`a potom zvolte **Uložit** tlačítko znovu.  
  
     Všimněte si, že dvě položky jsou přidány do **dotazů a aktualizace dat** seznamu, jak je znázorněno na následujícím obrázku.  
  
     ![Položky Todo budou přidány do seznamu. ] (../designers/media/wpfquickstart3.PNG "WPFQuickStart3")  
  
4.  Zaškrtněte políčko **dělejte něco jiného** položku v seznamu.  
  
     Volá **UpdateCheckedTodoItem** metoda a odebere položku ze seznamu a databáze.  
  
## <a name="next-steps"></a>Další kroky  
 Po dokončení poměrně zneužívající vlastností prohlížeče příkladem aplikace WPF s Azure back-end. Samozřejmě reálné aplikaci je pravděpodobně mnohem složitější, ale základní koncepty použity. V tématu [grafického subsystému WPF v rozhraní .NET Framework](https://msdn.microsoft.com/en-us/library/ms754130\(v=vs.100\).aspx).  
  
 Více přitažlivými uživatelského rozhraní můžete provést přidáním barvu, tvarů, grafiky a animace. V tématu [vytvoření uživatelského rozhraní pomocí návrháře XAML v sadě Visual Studio](creating-a-ui-by-using-xaml-designer-in-visual-studio.md) a [vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](creating-a-ui-by-using-blend-for-visual-studio.md). Porovnání mezi nástroje najdete v tématu [navrhování XAML v sadě Visual Studio a nástroj Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md).  

 Můžete připojit k existující databáze SQL nebo jiné zdroje dat pomocí Azure Mobile Services. V tématu [Mobile Services dokumentaci](http://azure.microsoft.com/en-us/services/app-service/mobile/).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Můj první grafický subsystém WPF aplikace pracovní plochy](../designers/walkthrough-my-first-wpf-desktop-application2.md)   
 [Vytvoření moderních aplikací klasické pracovní plochy s Windows Presentation Foundation](../designers/create-modern-desktop-applications-with-windows-presentation-foundation.md)