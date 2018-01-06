---
title: "Úvod k použití WPF | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- csharp
- vb
ms.workload: multiple
ms.openlocfilehash: a756b7a0cbc69e02c530ffc95d776aefbc96afa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-wpf"></a>Úvod do WPF
Windows Presentation Foundation (WPF) umožňuje vytvářet aplikace pro Windows klient plochy s vizuálně omráčení koncových uživatelů.  
  
 ![Ukázka uživatelského rozhraní zdravotní péče contoso](../designers/media/wpfintrofigure24.png "WPFIntroFigure24")  
  
 Základní WPF je nezávislé na rozlišení a vektorové vykreslování modul, který byl vytvořen, aby využívat moderní grafiky hardware. WPF rozšiřuje základní komplexní sadu funkcí pro vývoj aplikací, které zahrnují rozšiřitelné aplikace Markup Language (XAML), ovládací prvky, vazby dat, rozložení, 2-D a 3D grafický, animace, styly, šablony, dokumenty, média, text, a Typografie. WPF je obsažena v rozhraní .NET Framework, proto mohou vytvářet aplikace, které obsahují další prvky knihovně tříd rozhraní .NET Framework.  
  
 Tento přehled je určen pro nové uživatele a popisuje klíčové funkce a koncepty WPF.  
  
##  <a name="Programming_with_WPF"></a>Programování v grafickém subsystému WPF  
 WPF existuje jako podmnožinu rozhraní .NET Framework typů, které se nacházejí ve většině případů ve <xref:System.Windows> oboru názvů. Pokud jste dříve vytvořili aplikace v rozhraní .NET Framework pomocí spravovaného technologie, jako je technologie ASP.NET a Windows Forms, základní WPF programovací prostředí měli seznámit; vytváření instancí třídy, nastavte vlastnosti, volání metod a popisovač události, všechny pomocí vašeho oblíbeného rozhraní .NET programovací jazyk, například C# nebo Visual Basic.  
  
 WPF zahrnuje další programovací konstrukce, které zlepšují vlastností a událostí: [vlastností závislostí](/dotnet/framework/wpf/advanced/dependency-properties-overview) a [směrované události](/dotnet/framework/wpf/advanced/routed-events-overview).  
  
##  <a name="Markup_And_Codebehind"></a>Značek a kódu  
 WPF umožňuje vyvíjet aplikace pomocí obou *značek* a *kódu*, prostředí, které by měl být obeznámeni s vývojáře využívající technologii ASP.NET. Pomocí značek XAML obecně implementovat vzhled aplikace při použití spravovaných programovací jazyky (kódu) k implementaci své chování. Toto rozdělení vzhled a chování má následující výhody:  
  
-   Náklady na vývoj a údržba jsou snížit, protože specifické vzhled značek není pevně spojená s kódu pro konkrétní chování.  
  
-   Vývoj je efektivnější, protože Designer můžete implementovat aplikace vzhled současně s vývojáři, kteří jsou implementace chování aplikace.  
  
-   [Globalizace a lokalizace](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview) pro grafický subsystém WPF je zjednodušený aplikace.  
  
 Zde je stručný úvod do WPF značek a kódu.  
  
### <a name="markup"></a>Značek  
 XAML je založený na jazyce XML značek jazyk, který se používá k implementaci aplikace vzhled deklarativně. Technická dokumentace se obvykle používá k vytvoření windows, dialogová okna, stránky a uživatelské ovládací prvky a jejich vyplníte ovládací prvky, tvarů a grafiky.  
  
 Následující příklad používá XAML k implementaci vzhled časového období, který obsahuje jedno tlačítko.  
  
```xaml  
<Window  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    Title="Window with Button"  
    Width="250" Height="100">  
  
  <!-- Add button to window -->  
  <Button Name="button">Click Me!</Button>  
  
</Window>  
```  
  
 Konkrétně tato XAML definuje okno a tlačítko, pomocí `Window` a `Button` prvky, v uvedeném pořadí. Každý prvek je nakonfigurovaný s atributy, jako `Window` elementu `Title` atributu zadejte text záhlaví okna. WPF v době běhu, převede elementů a atributů, které jsou definovány v značek pro instance tříd WPF. Například `Window` element jsou převedeny na instanci <xref:System.Windows.Window> třídy jehož <xref:System.Windows.Window.Title%2A> vlastnost je hodnota `Title` atribut.  
  
 Následující obrázek znázorňuje uživatelské rozhraní (UI), který je definován XAML v předchozím příkladu.  
  
 ![Okno, které obsahuje tlačítko](../designers/media/wpfintrofigure10.png "WPFIntroFigure10")  
  
 Vzhledem k tomu, že XAML je založený na jazyce XML, je v hierarchii vnořených elementů známé jako sestaví uživatelské rozhraní, které tvoří ho [element stromu](/dotnet/framework/wpf/advanced/trees-in-wpf). Element stromu poskytuje logické a intuitivní způsob, jak vytvořit a spravovat uživatelská rozhraní.  
  
### <a name="code-behind"></a>Kódu  
 Hlavní chování aplikace je funkce, která reaguje na interakce s uživatelem, včetně zpracování událostí (např. Kliknutím na nabídku, panel nástrojů nebo tlačítko) implementace a volání obchodní logiku a data přístup logiku v odpovědi. V grafickém subsystému WPF je toto chování obecně implementovat v kódu, který je přidružen značek. Tento typ kódu se označuje jako kódu. Následující příklad ukazuje kód aktualizované z předchozí příklad a modelu code-behind.  
  
```xaml  
<Window  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Class="SDKSample.AWindow"  
    Title="Window with Button"  
    Width="250" Height="100">  
  
  <!-- Add button to window -->  
  <Button Name="button" Click="button_Click">Click Me!</Button>  
  
</Window>  
```  
  
```csharp  
using System.Windows; // Window, RoutedEventArgs, MessageBox   
  
namespace SDKSample  
{  
    public partial class AWindow : Window  
    {  
        public AWindow()  
        {  
            // InitializeComponent call is required to merge the UI   
            // that is defined in markup with this class, including    
            // setting properties and registering event handlers  
            InitializeComponent();  
        }  
  
        void button_Click(object sender, RoutedEventArgs e)  
        {  
            // Show message box when button is clicked  
            MessageBox.Show("Hello, Windows Presentation Foundation!");  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
  
    Partial Public Class AWindow  
        Inherits System.Windows.Window  
  
        Public Sub New()  
  
            ' InitializeComponent call is required to merge the UI   
            ' that is defined in markup with this class, including    
            ' setting properties and registering event handlers  
            InitializeComponent()  
  
        End Sub   
  
        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
  
            ' Show message box when button is clicked  
            MessageBox.Show("Hello, Windows Presentation Foundation!")  
  
        End Sub   
  
    End Class   
  
End Namespace  
  
```  
  
 V tomto příkladu modelu code-behind implementuje třídu odvozenou z <xref:System.Windows.Window> třídy. `x:Class` Atribut se používá k přidružit třídu kódem v pozadí značky. `InitializeComponent`je volána z konstruktoru třídy kódu sloučit uživatelského rozhraní, která je definována v kódu pomocí třídy kódu. (`InitializeComponent` se vygeneruje pro vás, když vaše aplikace je sestavena, proto není nutné implementovat ručně.) Kombinace `x:Class` a `InitializeComponent` zkontrolujte vaší implementace je vždy, když je vytvořen správně inicializovat. Třída kódu také implementuje obslužné rutiny události pro tlačítka <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí. Při kliknutí na tlačítko obslužné rutiny události zobrazí okno se zprávou voláním <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> metoda.  
  
 Následující obrázek znázorňuje výsledek při kliknutí na tlačítko.  
  
 ![MessageBox](../designers/media/wpfintrofigure25.png "WPFIntroFigure25")  
  
##  <a name="Controls"></a>Ovládací prvky  
 Činnosti koncových uživatelů, které jsou doručovány prostřednictvím modelu aplikací jsou sestavené ovládací prvky. V grafickém subsystému WPF "řízení" je také souhrnný název, který se vztahuje na kategorii WPF třídy, které jsou hostované v okně nebo na stránce, mít uživatelské rozhraní a implementovat některé chování.  
  
 Další informace najdete v tématu [ovládací prvky](/dotnet/framework/wpf/controls/index).  
  
### <a name="wpf-controls-by-function"></a>Ovládacích prvků WPF podle funkce  
 Předdefinované ovládacích prvků WPF jsou zde uvedeny.  
  
-   **Tlačítka**: <xref:System.Windows.Controls.Button> a <xref:System.Windows.Controls.Primitives.RepeatButton>.  
  
-   **Zobrazení dat**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, a <xref:System.Windows.Controls.TreeView>.  
  
-   **Datum zobrazení a výběr**: <xref:System.Windows.Controls.Calendar> a <xref:System.Windows.Controls.DatePicker>.  
  
-   **Dialogová okna**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, a <xref:Microsoft.Win32.SaveFileDialog>.  
  
-   **Digitální rukopisu**: <xref:System.Windows.Controls.InkCanvas> a <xref:System.Windows.Controls.InkPresenter>.  
  
-   **Dokumenty**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, a <xref:System.Windows.Controls.StickyNoteControl>.  
  
-   **Vstup**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, a <xref:System.Windows.Controls.PasswordBox>.  
  
-   **Rozložení**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>,  <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, a <xref:System.Windows.Controls.WrapPanel>.  
  
-   **Média**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, a <xref:System.Windows.Controls.SoundPlayerAction>.  
  
-   **Nabídky**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, a <xref:System.Windows.Controls.ToolBar>.  
  
-   **Navigační**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, a <xref:System.Windows.Controls.TabControl>.  
  
-   **Výběr**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, a <xref:System.Windows.Controls.Slider>.  
  
-   **Informace o uživateli**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, a <xref:System.Windows.Controls.ToolTip>.  
  
##  <a name="Input_And_Commanding"></a>Vstup a tvorba příkazů  
 Ovládací prvky nejčastěji zjistit a reagovat na vstup uživatele. [WPF vstupní systému](/dotnet/framework/wpf/advanced/input-overview) používá přímé i směrované události pro podporu zadávání textu, správu fokusu a myš umístění.  
  
 Aplikace mají často složité vstupní požadavky. Poskytuje WPF [příkaz systému](/dotnet/framework/wpf/advanced/commanding-overview) který odděluje vstupní akcí uživatele z kódu, který reaguje na tyto akce.  
  
##  <a name="Layout"></a>Rozložení  
 Při vytváření uživatelského rozhraní, je uspořádat vaše ovládací prvky podle umístění a velikost na formuláři rozložení. Klíčovým požadavkem žádné rozložení je přizpůsobit na změny v velikost okna a zobrazení nastavení. Místo psaní kódu pro přizpůsobení rozložení za těchto okolností vynucení, poskytuje WPF systém první třídy, extensible rozložení pro vás.  
  
 Kamenem systému rozložení je relativní umístění, což zvyšuje schopnost přizpůsobit změnou okno a zobrazit podmínky. Kromě toho rozložení systému spravuje vyjednávání mezi ovládacími prvky k určení rozložení. Vyjednávání je dvoustupňový proces: nejdřív ovládacího prvku informuje nadřazené jaké umístění a velikost vyžaduje; druhý nadřazený říká ovládacímu prvku místo, jaké může mít.  
  
 Rozložení systému je vystaven podřízených ovládacích prvků pomocí třídy base WPF. Pro běžné rozložení například mřížky, překrývání a dokování WPF obsahuje několik rozložení ovládacích prvků:  
  
-   <xref:System.Windows.Controls.Canvas>: Podřízené ovládací prvky zadat své vlastní rozložení.  
  
-   <xref:System.Windows.Controls.DockPanel>: Je zarovnán podřízené ovládací prvky hrany panelu.  
  
-   <xref:System.Windows.Controls.Grid>: Podřízené ovládací prvky jsou umístěny podle řádků a sloupců.  
  
-   <xref:System.Windows.Controls.StackPanel>: Podřízené ovládací prvky jsou skládaný buď vodorovně nebo svisle.  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>: Podřízené ovládací prvky jsou virtualizované a uspořádané na jeden řádek, který je orientované vodorovně nebo svisle.  
  
-   <xref:System.Windows.Controls.WrapPanel>: Podřízené ovládací prvky jsou umístěna v pořadí zleva doprava a zabalen na další řádek, když existují další ovládací prvky na aktuálním řádku než místa na disku.  
  
 Následující příklad používá <xref:System.Windows.Controls.DockPanel> k rozložení několik <xref:System.Windows.Controls.TextBox> ovládací prvky.  
  
 [!code-xaml[IntroToWPFSnippets#LayoutMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_1.xaml)]  
  
 <xref:System.Windows.Controls.DockPanel> Umožňuje podřízená <xref:System.Windows.Controls.TextBox> ovládací prvky zjistit, jak můžete uspořádat. K tomu, <xref:System.Windows.Controls.DockPanel> implementuje `Dock` připojené vlastnosti, který je zveřejněný k podřízené ovládací prvky umožňující každý z nich určit styl ukotvení.  
  
> [!NOTE]
>  Vlastnost, která je implementováno modulem nadřazeného ovládacího prvku pro použití podřízených ovládacích prvků WPF konstrukce volána [přidružená vlastnost](/dotnet/framework/wpf/advanced/attached-properties-overview).  
  
 Následující obrázek znázorňuje výsledek kód XAML v předchozím příkladu.  
  
 ![Stránka DockPanel](../designers/media/wpfintrofigure11.png "WPFIntroFigure11")  
  
##  <a name="Data_Binding"></a>Datová vazba  
 Většina aplikací jsou vytvořeny uživatelům poskytnout způsob, jak zobrazit a upravit data. Pro aplikace WPF práci při ukládání a přístup k datům už poskytuje pro technologie, jako je například SQL Server a ADO .NET. Jakmile je přístupu k datům a načtena do aplikace spravované objekty, začne náročné práce pro aplikace WPF. V podstatě to zahrnuje dvě věci:  
  
1.  Kopírování dat do ovládacích prvků, kde můžete zobrazit a upravit data ze spravovaných objektů.  
  
2.  Zajištění, že se zkopírují změny dat pomocí ovládacích prvků zpět do spravovaných objektů.  
  
 Pro zjednodušení vývoj aplikací, WPF poskytuje modul vazby dat automaticky provádět tyto kroky. Základní jednotka stroje vazby dat je <xref:System.Windows.Data.Binding> třídy, jejichž povinnostem je vytvoření vazby ovládacího prvku (vazba cíl) na datový objekt (vazby zdroje). Tento vztah je zobrazená ve na následujícím obrázku.  
  
 ![Diagram základní datové vazby](../designers/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 Následující příklad ukazuje, jak vytvořit vazbu <xref:System.Windows.Controls.TextBox> na instanci vlastní `Person` objektu. `Person` Implementace je znázorněno v následujícím kódu.  
  
 [!code-vb[SimpleDataBindingSnippets#PersonClassCODE](../designers/codesnippet/VisualBasic/introduction-to-wpf_2.vb)]
 [!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](../designers/codesnippet/CSharp/introduction-to-wpf_2.cs)]  
  
 Následující kód vytvoří vazbu <xref:System.Windows.Controls.TextBox> na instanci vlastní `Person` objektu.  

 ```xaml  
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">  

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />  

 </Window>
 ```
  
 [!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_6.vb)]
 [!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_6.cs)]  
  
 V tomto příkladu `Person` třídy je vytvořena instance v kódu a je nastaven jako kontext dat pro `DataBindingWindow`. V kódu <xref:System.Windows.Controls.TextBox.Text%2A> vlastnost <xref:System.Windows.Controls.TextBox> je vázána `Person.Name` vlastnost (pomocí "`{Binding ... }`" XAML syntaxe). Tato XAML informuje WPF k vytvoření vazby <xref:System.Windows.Controls.TextBox> řídit k `Person` objekt, který je uložen v <xref:System.Windows.FrameworkElement.DataContext%2A> vlastnost okna.  
  
 Stroje vazby dat WPF poskytuje další podporu, která zahrnuje ověření, řazení a filtrování, seskupování. Datová vazba navíc podporuje použití šablon dat. Chcete-li vytvořit vlastní uživatelské rozhraní pro vázaný datový uživatelské rozhraní zobrazí standardní ovládacích prvků WPF vhodné není.  
  
 Další informace najdete v tématu [přehled vazby dat](/dotnet/framework/wpf/data/data-binding-overview).  
  
##  <a name="Graphics"></a>Grafika  
 WPF zavádí rozsáhlé, škálovatelná a flexibilní sadu grafických funkcí, které mají následující výhody:  
  
-   **Nezávislé na řešení a nezávislé na zařízení grafiky**. Základní jednotka měření grafika systému WPF je nezávislé pixelů zařízení, která je 1/96 palce, bez ohledu na to, skutečné rozlišení obrazovky a poskytuje základ pro vykreslování nezávislé na řešení a nezávislé na zařízení. Každý pixelů nezávislé na zařízení automaticky přizpůsobí tak, aby odpovídaly nastavení bodů na palec (dpi), který se vykreslí v systému.  
  
-   **Vylepšené přesnost**. Systém souřadnic WPF se měří Dvojitá přesnost – čísla s plovoucí desetinnou čárkou než jednoduchou přesností. Transformace a krytí hodnoty jsou také vyjádřené jako dvojitou přesností. WPF také podporuje širokou barevný rozsah (scRGB) a poskytuje integrovanou podporu pro správu vstupy z různých barevných prostorů.  
  
-   **Grafika a animace podpora rozšířené**. WPF zjednodušuje programování grafiky tím, že správa animace scény pro vás; není nutné se obávat scény zpracování, vykreslování smyčky a bilineární interpolace. Kromě toho poskytuje WPF vstupů do testování podporu a podporu úplné alpha skládání.  
  
-   **Hardwarová akcelerace**. Grafika systému WPF využívá grafiky hardwaru, abyste minimalizovali využití procesoru.  
  
### <a name="2-d-shapes"></a>2D obrazce  
 WPF poskytuje knihovnu běžných vykreslené vektoru 2D obrazce, například obdélníků a symbol tří teček, která jsou zobrazená na následujícím obrázku.  
  
 ![Výpustky a obdélníky](../designers/media/wpfintrofigure4.PNG "WPFIntroFigure4")  
  
 Zajímavé funkce tvarů je, že nejsou jen pro zobrazení; tvary implementovat řadu funkcí, které byste očekávali z ovládacích prvků, včetně klávesnici a myš vstup. Následující příklad ukazuje <xref:System.Windows.UIElement.MouseUp> události <xref:System.Windows.Shapes.Ellipse> ke zpracování.  
  
 [!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_7.xaml)]  
  
 [!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_8.vb)]
 [!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_8.cs)]  
  
 Následující obrázek znázorňuje, co je produkovaný předchozí kód.  
  
 ![Okno s textem "kliknuli jste na tlačítko se třemi tečkami & č. 33;" ] (../designers/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Další informace najdete v tématu [tvarů a základní kreslení v přehledu WPF](/dotnet/framework/wpf/data/data-binding-overview).  
  
### <a name="2-d-geometries"></a>2D geometrie  
 2D obrazce poskytované WPF zahrnují standardní sadu základních tvarů. Potřebujete však vytvořit vlastní tvary usnadňuje návrh přizpůsobené uživatelské rozhraní. Pro tento účel WPF poskytuje geometrie. Následující obrázek ukazuje použití geometrie vytvořit vlastní tvar, který můžete vykresluje přímo, použít jako štětce nebo použít na jiných tvarů a ovládacích prvků v případě potřeby upraví.  
  
 <xref:System.Windows.Shapes.Path>objekty lze použít k vykreslení uzavřené nebo otevřít, více tvarů nebo i zakřivené.  
  
 <xref:System.Windows.Media.Geometry>objekty lze použít pro výstřižek, stiskněte klávesu testování a grafické datech pro vykreslení 2-D.  
  
 ![Různé použití cesty](../designers/media/wpfintrofigure5.PNG "WPFIntroFigure5")  
  
 Další informace najdete v tématu [geometrie přehled](/dotnet/framework/wpf/graphics-multimedia/geometry-overview).  
  
### <a name="2-d-effects"></a>2D efekty  
 Podmnožinu WPF 2-D možnosti zahrnuje vizuálních efektů, například přechody, rastrové obrázky, kresby, Malování videa, otáčení, změnu velikosti a zkosení. Tyto jsou všechny dosáhnout s štětce; Následující obrázek ukazuje některé příklady.  
  
 ![Ilustrace různých štětců](../designers/media/wpfintrofigure6.PNG "WPFIntroFigure6")  
  
 Další informace najdete v tématu [WPF štětce přehled](/dotnet/framework/wpf/graphics-multimedia/wpf-brushes-overview).  
  
### <a name="3-d-rendering"></a>3D vykreslení  
 WPF také obsahuje funkce 3D vykreslování, které integrovat 2D grafiky umožňující vytvoření více zajímavé a zajímavé uživatelská rozhraní. Například následující obrázek znázorňuje 2-D Image vykresleny také na 3D tvarů.  
  
 ![Snímek obrazovky Visual3D –](../designers/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Další informace najdete v tématu [3D přehled grafiky](/dotnet/framework/wpf/graphics-multimedia/3-d-graphics-overview).  
  
##  <a name="Animation"></a>Animace  
 Umožňuje podporu animace WPF provedené ovládací prvky růst, zatřesením, typu číselník a objevování, chcete-li vytvořit zajímavé stránky přechody a další. Můžete animace Většina tříd WPF, dokonce i vlastní třídy. Následující obrázek znázorňuje jednoduchý animace v akci.  
  
 ![Bitové kopie animovaný datové krychle](../designers/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Další informace najdete v tématu [animace přehled](/dotnet/framework/wpf/graphics-multimedia/animation-overview).  
  
##  <a name="Media"></a>Média  
 Je možné vyjádřit bohaté obsah prostřednictvím audiovizuální média. WPF poskytuje speciální podporu pro obrázky, videa a zvuku.  
  
### <a name="images"></a>Obrázky  
 Bitové kopie jsou společné pro většinu aplikací a WPF poskytuje několik způsobů, jak je používat. Následující obrázek znázorňuje uživatelské rozhraní s pole se seznamem, který obsahuje obrázky miniatur. Pokud je vybrána na miniaturu, se zobrazí obrázek plné velikosti.  
  
 ![Obrázky miniatur a úplné & č. 45; velikost obrázku](../designers/media/wpfintrofigure8.PNG "WPFIntroFigure8")  
  
 Další informace najdete v tématu [Imaging přehled](/dotnet/framework/wpf/graphics-multimedia/imaging-overview).  
  
### <a name="video-and-audio"></a>Videa a zvuku  
 <xref:System.Windows.Controls.MediaElement> Řízení může přehrávání videa a audia a je dostatečně flexibilní, aby se základ pro vlastní media player. Následující kód XAML implementuje přehrávač médií.  
  
 [!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_9.xaml)]  
  
 Okno v následující obrázek ukazuje <xref:System.Windows.Controls.MediaElement> ovládací prvek v akci.  
  
 ![Ovládací prvek MediaElement se audio a video](../designers/media/wpfintrofigure1.png "WPFIntroFigure1")  
  
 Další informace najdete v tématu [grafika a multimédia](/dotnet/framework/wpf/graphics-multimedia).  
  
##  <a name="Text_and_Typography"></a>Text a typografii  
 Pro usnadnění vykreslování vysokou kvalitu textu, WPF nabízí následující funkce:  
  
-   Podpora písem OpenType.  
  
-   Vylepšení ClearType.  
  
-   Vysoký výkon, který využívá hardwarovou akceleraci.  
  
-   Integrace textu média, grafika a animace.  
  
-   Mezinárodní písma podporu a záložního mechanismy.  
  
 Jako ukázkový text integrace s grafiky následující obrázek znázorňuje aplikace textové dekorace.  
  
 ![Text s různé textové dekorace](../designers/media/wpfintrofigure23.png "WPFIntroFigure23")  
  
 Další informace najdete v tématu [typografii v systému Windows Presentation Foundation](/dotnet/framework/wpf/advanced/typography-in-wpf).  
  
##  <a name="WPF_Customization"></a>Přizpůsobení aplikace WPF  
 V tomto okamžiku jste se seznámili WPF základní stavební bloky pro vývoj aplikací. Aplikační model použijete k hostování a doručovat obsah aplikace, která je tvořena především ovládací prvky. Pro zjednodušení uspořádání ovládacích prvků v uživatelském rozhraní a k Ujistěte se, že se při krátkodobém změny velikosti okna udržuje uspořádání a nastavení zobrazit, použijete systém rozložení WPF. Vzhledem k tomu, že většina aplikací mít uživatelé povolenou interakci s daty, použijete datové vazby k snížit pracovní integrace uživatelské rozhraní s daty. K vylepšení vzhled vaší aplikace, použijte komplexní rozsah podpora grafiky, animace a média poskytované WPF.  
  
 Často ale základy nejsou dost pro vytváření a správu skutečně odlišné a vizuálně omráčení činnost koncového uživatele. Standardní ovládacích prvků WPF nebude možné integrovat požadovaný vzhled vaší aplikace. Data se nemusí zobrazit v jedním z nejúčinnějších způsobů. Celkové uživatelské prostředí aplikace nemusí být vhodné pro výchozí vzhled a chování motivy systému Windows. V mnoha směrech technologie prezentace musí visual rozšiřitelnost co nejvíc jakýkoli jiný druh rozšíření.  
  
 Z tohoto důvodu WPF poskytuje celou řadu mechanismy pro vytvoření jedinečné uživatelského prostředí, včetně bohaté modelu obsahu pro ovládací prvky, aktivační události, řízení a šablony dat, styly, prostředky uživatelského rozhraní a motivy a vzhledy.  
  
### <a name="content-model"></a>Model obsahu  
 Je hlavním účelem většiny ovládacích prvků WPF k zobrazení obsahu. V grafickém subsystému WPF, typ a počet položek, které mohou představovat obsah ovládacího prvku se označuje jako ovládacího prvku *modelu obsahu*. Některé ovládací prvky může obsahovat jednu položku a typu obsahu; například obsah <xref:System.Windows.Controls.TextBox> je řetězcová hodnota, která je přiřazena k <xref:System.Windows.Controls.TextBox.Text%2A> vlastnost. Následující příklad nastaví obsah <xref:System.Windows.Controls.TextBox>.  

```xaml  
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">  

    <TextBox Text="This is the content of a TextBox." />  
</Window>  
```
  
 Následující obrázek znázorňuje výsledek.  
  
 ![Textové pole ovládací prvek, který obsahuje text](../designers/media/wpfintrofigure21.png "WPFIntroFigure21")  
  
 Další ovládací prvky, ale může obsahovat více položek různých typů obsahu; obsah <xref:System.Windows.Controls.Button>zadaný pomocí <xref:System.Windows.Controls.ContentControl.Content%2A> vlastnost, může obsahovat celou řadu položek včetně rozložení ovládacích prvků, text, obrázky a tvarů. Následující příklad ukazuje <xref:System.Windows.Controls.Button> s obsahem, který zahrnuje <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Border>a <xref:System.Windows.Controls.MediaElement>.  
  
```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">  

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2" 
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>  
</Window>  
```
  
 Následující obrázek znázorňuje obsah toto tlačítko.  
  
 ![Tlačítko, které obsahuje několik typů obsahu](../designers/media/wpfintrofigure22.png "WPFIntroFigure22")  
  
 Další informace o obsahu, který podporují různé ovládací prvky najdete v tématu [modelu obsahu WPF](/dotnet/framework/wpf/controls/wpf-content-model).  
  
### <a name="triggers"></a>Aktivační procedury  
 I když je hlavním účelem XAML značek k implementaci aplikace vzhled, také můžete XAML pro implementaci některých aspektů chování aplikace. Jedním z příkladů je použití služby aktivačních událostí, chcete-li změnit vzhled aplikace na základě interakcí uživatele. Další informace najdete v tématu [stylů a ukázka](/dotnet/framework/wpf/controls/styling-and-templating).  
  
### <a name="control-templates"></a>Šablon ovládacích prvků  
 Výchozí uživatelského rozhraní pro ovládacích prvků WPF se obvykle vytvářejí z jiných ovládacích prvků a tvarů. Například <xref:System.Windows.Controls.Button> se skládá z obou <xref:Microsoft.Windows.Themes.ButtonChrome> a <xref:System.Windows.Controls.ContentPresenter> ovládací prvky. <xref:Microsoft.Windows.Themes.ButtonChrome> Poskytuje standardní tlačítko vzhled při <xref:System.Windows.Controls.ContentPresenter> zobrazí obsah, na tlačítko, podle specifikace <xref:System.Windows.Controls.ContentControl.Content%2A> vlastnost.  
  
 V některých případech může být výchozí vzhledu ovládacího prvku incongruent s celkový vzhled aplikace. V takovém případě můžete použít <xref:System.Windows.Controls.ControlTemplate> Změna vzhledu ovládacího prvku uživatelského rozhraní beze změny jeho obsahu a chování.  
  
 Například následující příklad ukazuje, jak změnit vzhled <xref:System.Windows.Controls.Button> pomocí <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_16.xaml)]  
  
 [!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_17.cs)]
 [!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_17.vb)]  
  
 V tomto příkladu se nahradil výchozí tlačítko uživatelské rozhraní <xref:System.Windows.Shapes.Ellipse> , má tmavý modré ohraničení a vyplněno pomocí <xref:System.Windows.Media.RadialGradientBrush>. <xref:System.Windows.Controls.ContentPresenter> Zobrazí obsah <xref:System.Windows.Controls.Button>, "Kliknutím mi!" Když <xref:System.Windows.Controls.Button> po kliknutí na <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událost se vyvolá, stále jako součást <xref:System.Windows.Controls.Button> výchozí chování ovládacího prvku. Výsledkem je znázorněno na následujícím obrázku.  
  
 ![Tlačítko ve tvaru elipsy a druhé okno](../designers/media/wpfintrofigure2.png "WPFIntroFigure2")  
  
### <a name="data-templates"></a>Šablony dat  
 Zatímco šablony ovládacího prvku slouží k určení vzhledu ovládacího prvku, datová šablona vám umožní určit vzhled ovládacího prvku obsahu. Šablony dat se často používají k vylepšení jak vázaných dat se zobrazí. Následující obrázek znázorňuje výchozí vzhled <xref:System.Windows.Controls.ListBox> která je vázaná na kolekci `Task` objekty, kde každý úkol má název, popis a priority.  
  
 ![Pole se seznamem s výchozím vzhledem](../designers/media/wpfintrofigure18.png "WPFIntroFigure18")  
  
 Výchozí vzhled je byste očekávali od <xref:System.Windows.Controls.ListBox>. Výchozí vzhled každý úkol, ale obsahuje pouze název úlohy. Chcete-li zobrazit název úlohy, popisu a prioritu, výchozí vzhled <xref:System.Windows.Controls.ListBox> položky seznamu vázaného ovládacího prvku musí změnit pomocí <xref:System.Windows.DataTemplate>. Definuje následující XAML, například <xref:System.Windows.DataTemplate>, které platí pro každou úlohu pomocí <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> atribut.  
  
```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2" 
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>  
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>
  
    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox 
      ItemsSource="{Binding}" 
      ItemTemplate="{StaticResource myTaskTemplate}" 
      HorizontalContentAlignment="Stretch" 
      IsSynchronizedWithCurrentItem="True" 
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```  
  
 Následující obrázek znázorňuje účinek tohoto kódu.  
  
 ![Llist pole, které používá šablonu dat](../designers/media/wpfintrofigure19.png "WPFIntroFigure19")  
  
 Všimněte si, že <xref:System.Windows.Controls.ListBox> si jeho chování a celkový vzhled; se změnil pouze vzhled obsahu v zobrazení seznamu.  
  
 Další informace najdete v tématu [přehled Ukázka dat](/dotnet/framework/wpf/data/data-templating-overview).  
  
### <a name="styles"></a>Styly  
 Styly povolit vývojářů a návrhářů, standardizovali na konkrétní vzhled jejich produktu. WPF poskytuje model silné styl, foundation, které je <xref:System.Windows.Style> elementu. Následující příklad vytvoří styl, který nastaví barvu pozadí pro každý <xref:System.Windows.Controls.Button> na okno s `Orange`.  
  
```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">  
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>  
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>  
</Window>
```  
  
 Protože tento styl cílem všechny <xref:System.Windows.Controls.Button> ovládací prvky, styl se automaticky použije na všechny tlačítka v okně, jak je znázorněno na následujícím obrázku.  
  
 ![Dvě oranžové tlačítka](../designers/media/wpfintrofigure20.png "WPFIntroFigure20")  
  
 Další informace najdete v tématu [stylů a ukázka](/dotnet/framework/wpf/controls/styling-and-templating).  
  
### <a name="resources"></a>Prostředky  
 Ovládací prvky aplikace by měly sdílet stejný vzhled, které můžou obsahovat vše od řídit šablony, data šablony a styly písma a barvy pozadí. WPF na podporu pro prostředky uživatelského rozhraní můžete použít k zapouzdření tyto prostředky na jednom místě pro opakované použití.  
  
 V následujícím příkladu definuje běžné barvu pozadí, který je sdílen <xref:System.Windows.Controls.Button> a <xref:System.Windows.Controls.Label>.  
  
```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">
  
  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>  

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>  
</Window>
``` 
  
 Tento příklad implementuje prostředek barvu pozadí pomocí `Window.Resources` element vlastnosti. Tento prostředek je k dispozici pro všechny podřízené objekty <xref:System.Windows.Window>. Existuje mnoho různých prostředku obory, včetně následujících uvedeny v pořadí, ve kterém jsou vyřešeny:  
  
1.  Ovládací prvek jednotlivých (pomocí zděděnou <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> vlastnost).  
  
2.  A <xref:System.Windows.Window> nebo <xref:System.Windows.Controls.Page> (také pomocí zděděnou <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> vlastnost).  
  
3.  <xref:System.Windows.Application> (Pomocí <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> vlastnost).  
  
 Řadu obory poskytuje flexibilitu s ohledem na způsob, ve kterém můžete definovat a sdílet vaše prostředky.  
  
 Jako alternativu k přímo přiřazení prostředkům na určitém rozsahu, můžete balíček jeden nebo více zdrojů pomocí samostatné <xref:System.Windows.ResourceDictionary> , může být odkazováno v dalších částí aplikace. Například v následujícím příkladu definuje výchozí barvu pozadí ve slovníku prostředků.  
  
```xaml
<ResourceDictionary 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```  
  
 V následujícím příkladu odkazuje slovník prostředků, které jsou definované v předchozím příkladu tak, aby byl sdílen napříč aplikace.  
  
```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">
  
  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```  
  
 Prostředky a slovnících prostředků jsou základem WPF podpory pro motivy a vzhledy.  
  
 Další informace najdete v tématu [Přehled prostředků](/dotnet/framework/wpf/advanced/xaml-resources).  
  
### <a name="custom-controls"></a>Vlastní ovládací prvky  
 Přestože WPF poskytuje hostitel přizpůsobení podpory, v některých situacích, kde existujících ovládacích prvků WPF nesplňují potřebám vaší aplikace nebo svým uživatelům. Tato situace může nastat při:  
  
-   Uživatelské rozhraní, které budete potřebovat, nedá se vytvořit pomocí přizpůsobení vzhledu a chování existující implementace WPF.  
  
-   Chování, které budete potřebovat nepodporuje (nebo podporovány nejsou snadno) existující implementacemi WPF.  
  
 V tomto okamžiku by ale můžete využít výhod tři modely WPF vytvořit nový ovládací prvek. Každý model cílí na konkrétní scénář a vyžaduje vlastního ovládacího prvku k odvozování z určité základní třídy grafického subsystému WPF. Tři modely jsou zde uvedeny:  
  
-   **Uživatelského ovládacího prvku modelu**. Vlastní ovládací prvek je odvozena z <xref:System.Windows.Controls.UserControl> a se skládá z jednoho nebo více dalších ovládacích prvků.  
  
-   **Řízení modelu**. Vlastní ovládací prvek je odvozena z <xref:System.Windows.Controls.Control> a slouží k vytvoření implementace, které oddělují jejich chování z jejich vzhled pomocí šablon, podobně jako většina ovládacích prvků WPF. Odvozování z <xref:System.Windows.Controls.Control> vám dává větší svobodu pro vytvoření vlastní uživatelské rozhraní než uživatelské ovládací prvky, ale může vyžadovat další úsilí.  
  
-   **Model elementu Framework**. Vlastní ovládací prvek je odvozena z <xref:System.Windows.FrameworkElement> při její vzhled je definováno logikou vlastní vykreslení (ne šablony).  
  
 Následující příklad ukazuje vlastní číselné nahoru/dolů ovládací prvek, který je odvozen od <xref:System.Windows.Controls.UserControl>.  
  
 [!code-xaml[IntroToWPFSnippets#UserControlMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_33.xaml)]  
  
 [!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](../designers/codesnippet/CSharp/introduction-to-wpf_34.cs)]
 [!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](../designers/codesnippet/VisualBasic/introduction-to-wpf_34.vb)]  
  
 Další příklad ukazuje XAML, který je potřeba začlenit uživatelského ovládacího prvku do <xref:System.Windows.Window>.  
  
 [!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](../designers/codesnippet/Xaml/introduction-to-wpf_37.xaml)]  
  
 Následující obrázek ukazuje `NumericUpDown` řízení hostované v <xref:System.Windows.Window>.  
  
 ![Vlastní UserControl](../designers/media/wpfintrofigure3.png "WPFIntroFigure3")  
  
 Další informace o vlastních ovládacích prvcích najdete v tématu [vytváření – Přehled ovládacího prvku](/dotnet/framework/wpf/controls/control-authoring-overview).  
  
##  <a name="WPF_Best_Practices"></a>Osvědčené postupy WPF  
 Stejně jako u jakékoli platformě vývoj WPF lze v různých způsobů, jak dosáhnout požadovaného výsledku. Jako způsob zajistit, aby vaše WPF aplikace zadejte požadované uživatelské prostředí a obecně splňovat požadavky na cílovou skupinu, jsou doporučené osvědčené postupy pro usnadnění, globalizace a lokalizace a výkonu. Najdete následující informace:  
  
-   [Usnadnění – doporučené postupy](/dotnet/framework/ui-automation/accessibility-best-practices)usnadnění – doporučené postupy  
  
-   [Přehled globalizace a lokalizace WPF](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview)  
  
-   [Optimalizace výkonu aplikace WPF](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)  
  
-   [Zabezpečení systému Windows Presentation Foundation](/dotnet/framework/wpf/security-wpf)  
  
##  <a name="Summary"></a>Souhrn  
 WPF je komplexní prezentace technologie pro vytváření širokou škálu vizuálně omráčení klientské aplikace. Tento úvod poskytl podívejte se na klíčové funkce WPF.  
  
 Dalším krokem je vytvoření aplikace WPF!  
  
 Při sestavování je, můžete se se vraťte k tento úvod pro aktualizační program na klíčové funkce a najít odkazy na podrobnější pokrytí funkcí zahrnuté v tento úvod.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme s WPF](../designers/getting-started-with-wpf.md)   
 [Vytvoření moderních aplikací klasické pracovní plochy s Windows Presentation Foundation](../designers/create-modern-desktop-applications-with-windows-presentation-foundation.md)   
 [Windows Presentation Foundation](/dotnet/framework/wpf/index)