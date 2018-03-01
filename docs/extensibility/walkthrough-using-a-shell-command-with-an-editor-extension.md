---
title: "Návod: Použití příkazů prostředí s příponou Editor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - add a menu command
ms.assetid: 08526848-a442-4cd4-afa1-b2eac2005adb
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5a7f9426297ef28bdf4b829bd6697543f5aab55f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-using-a-shell-command-with-an-editor-extension"></a>Návod: Použití příkazů prostředí s příponou editoru
Z VSPackage můžete přidat funkce, jako je příkazy nabídky do editoru. Tento návod ukazuje, jak přidat dalších úprav do zobrazení textu v editoru vyvoláním příkazu nabídky.  
  
 Tento návod ukazuje použití VSPackage společně s součást Managed Extensibility Framework (MEF). VSPackage musíte použít při registraci příkaz nabídky s prostředí sady Visual Studio a můžete použít příkaz pro přístup k části MEF součásti.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-an-extension-with-a-menu-command"></a>Vytvoření rozšíření pomocí příkazu nabídky  
 Vytvořit VSPackage, který umísťuje příkazu nabídky s názvem **přidání dalších úprav** na **nástroje** nabídky.  
  
1.  Vytvoření projektu C# VSIX s názvem `MenuCommandTest`a přidejte název šablony položky příkaz vlastní **AddAdornment**. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Řešení s názvem MenuCommandTest, je otevřené. Soubor MenuCommandTestPackage obsahuje kód, který vytvoří příkaz nabídky a vloží ho **nástroje** nabídky. V tomto okamžiku příkaz právě způsobí, že se zprávou, který se má zobrazit. Novější kroky ukazují, jak chcete-li změnit toto k zobrazení dalších úprav komentář.  
  
3.  Otevřete soubor source.extension.vsixmanifest v editoru Manifest VSIX. `Assets` Karta by měl mít řádek pro Microsoft.VisualStudio.VsPackage s názvem MenuCommandTest.  
  
4.  Uložte a zavřete soubor Source.extension.vsixmanifest.  
  
## <a name="adding-a-mef-extension-to-the-command-extension"></a>Přidává se rozšíření MEF pro příkaz rozšíření  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení, klikněte na **přidat**a potom klikněte na **nový projekt**. V **přidat nový projekt** dialogové okno, klikněte na tlačítko **rozšiřitelnost** pod **Visual C#**, pak **projektu VSIX**. Název projektu `CommentAdornmentTest`.  
  
2.  Protože tento projekt bude komunikovat s VSPackage sestavení silným názvem, musíte se odhlásit sestavení. Soubor klíče, které jsou vytvořeny již pro sestavení VSPackage můžete znovu použít.  
  
    1.  Otevřete vlastnosti projektu a vyberte **podpisování** kartě.  
  
    2.  Vyberte **podepsání sestavení**.  
  
    3.  V části **vyberte soubor klíče se silným názvem**, vyberte soubor Key.snk, který byl vytvořen pro MenuCommandTest sestavení.  
  
## <a name="referring-to-the-mef-extension-in-the-vspackage-project"></a>Odkaz na rozšíření MEF v projektu VSPackage  
 Vzhledem k tomu, že přidáváte komponentu MEF do VSPackage, musíte zadat oba typy prostředků v manifestu.  
  
> [!NOTE]
>  Další informace o rozhraní MEF najdete v tématu [Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index).  
  
#### <a name="to-refer-to-the-mef-component-in-the-vspackage-project"></a>K odkazování na komponenty MEF v projektu VSPackage  
  
1.  V projektu MenuCommandTest otevřete soubor source.extension.vsixmanifest v editoru Manifest VSIX.  
  
2.  Na **prostředky** , klikněte na **nový**.  
  
3.  V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
4.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
5.  V **projektu** vyberte **CommentAdornmentTest**.  
  
6.  Uložte a zavřete soubor source.extension.vsixmanifest.  
  
7.  Ujistěte se, že MenuCommandTest projekt obsahuje odkaz na projekt CommentAdornmentTest.  
  
8.  V projektu CommentAdornmentTest nastavte projekt k vytvoření sestavení. V **Průzkumníku řešení**, vyberte projekt a hledat v **vlastnosti** okna pro **kopie sestavení výstup do Výstupnísložka** vlastnost a nastavte ji na **true**.  
  
## <a name="defining-a-comment-adornment"></a>Definování dalších úprav komentář  
 Komentář dalších úprav, samotné se skládá z <xref:Microsoft.VisualStudio.Text.ITrackingSpan> vybraný text a některé řetězců, které představují autora a popis text, který sleduje.  
  
#### <a name="to-define-a-comment-adornment"></a>Chcete-li definovat dalších úprav komentář  
  
1.  V projektu CommentAdornmentTest přidat nový soubor třídy a pojmenujte ji `CommentAdornment`.  
  
2.  Přidejte následující odkazy:  
  
    1.  Microsoft.VisualStudio.CoreUtility  
  
    2.  Microsoft.VisualStudio.Text.Data  
  
    3.  Microsoft.VisualStudio.Text.Logic  
  
    4.  Microsoft.VisualStudio.Text.UI  
  
    5.  Microsoft.VisualStudio.Text.UI.Wpf  
  
    6.  System.ComponentModel.Composition  
  
    7.  PresentationCore  
  
    8.  PresentationFramework  
  
    9. WindowsBase  
  
3.  Přidejte následující `using` příkaz.  
  
    ```vb  
    using Microsoft.VisualStudio.Text;  
    ```  
  
4.  Soubor musí obsahovat třídu s názvem `CommentAdornment`.  
  
    ```  
    internal class CommentAdornment  
    ```  
  
5.  Přidejte tři pole na `CommentAdornment` třídy pro <xref:Microsoft.VisualStudio.Text.ITrackingSpan>, autora a popis.  
  
    ```csharp  
    public readonly ITrackingSpan Span;  
    public readonly string Author;  
    public readonly string Text;  
    ```  
  
6.  Přidejte konstruktor, který inicializuje pole.  
  
    ```csharp  
    public CommentAdornment(SnapshotSpan span, string author, string text)  
    {  
        this.Span = span.Snapshot.CreateTrackingSpan(span, SpanTrackingMode.EdgeExclusive);  
        this.Author = author;  
        this.Text = text;  
    }  
    ```  
  
## <a name="creating-a-visual-element-for-the-adornment"></a>Vytváření vizuální prvek pro dalších úprav  
 Vizuální prvek musí definovat také pro vaše dalších úprav. V tomto návodu definování ovládacího prvku, který dědí z třídy Windows Presentation Foundation (WPF) <xref:System.Windows.Controls.Canvas>.  
  
1.  Vytvořte třídu do projektu CommentAdornmentTest a pojmenujte ji `CommentBlock`.  
  
2.  Přidejte následující `using` příkazy.  
  
    ```csharp  
    using Microsoft.VisualStudio.Text;  
    using System;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Media;  
    using System.Windows.Shapes;  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Utilities;  
    ```  
  
3.  Ujistěte se, `CommentBlock` třídy dědí <xref:System.Windows.Controls.Canvas>.  
  
    ```csharp  
    internal class CommentBlock : Canvas  
    { }  
    ```  
  
4.  Přidáte některá pole privátní k definování visual aspektů dalších úprav.  
  
    ```csharp  
    private Geometry textGeometry;  
    private Grid commentGrid;  
    private static Brush brush;  
    private static Pen solidPen;  
    private static Pen dashPen;  
    ```  
  
5.  Přidejte konstruktor, který definuje komentář dalších úprav a přidá příslušný text.  
  
    ```csharp  
    public CommentBlock(double textRightEdge, double viewRightEdge,   
            Geometry newTextGeometry, string author, string body)  
    {  
        if (brush == null)  
        {  
            brush = new SolidColorBrush(Color.FromArgb(0x20, 0x00, 0xff, 0x00));  
            brush.Freeze();  
            Brush penBrush = new SolidColorBrush(Colors.Green);  
            penBrush.Freeze();  
            solidPen = new Pen(penBrush, 0.5);  
            solidPen.Freeze();  
            dashPen = new Pen(penBrush, 0.5);  
            dashPen.DashStyle = DashStyles.Dash;  
            dashPen.Freeze();  
        }  
  
        this.textGeometry = newTextGeometry;  
  
        TextBlock tb1 = new TextBlock();  
        tb1.Text = author;  
        TextBlock tb2 = new TextBlock();  
        tb2.Text = body;  
  
        const int MarginWidth = 8;  
        this.commentGrid = new Grid();  
        this.commentGrid.RowDefinitions.Add(new RowDefinition());  
        this.commentGrid.RowDefinitions.Add(new RowDefinition());  
        ColumnDefinition cEdge = new ColumnDefinition();  
        cEdge.Width = new GridLength(MarginWidth);  
        ColumnDefinition cEdge2 = new ColumnDefinition();  
        cEdge2.Width = new GridLength(MarginWidth);  
        this.commentGrid.ColumnDefinitions.Add(cEdge);  
        this.commentGrid.ColumnDefinitions.Add(new ColumnDefinition());  
        this.commentGrid.ColumnDefinitions.Add(cEdge2);  
  
        System.Windows.Shapes.Rectangle rect = new System.Windows.Shapes.Rectangle();  
        rect.RadiusX = 6;  
        rect.RadiusY = 3;  
        rect.Fill = brush;  
        rect.Stroke = Brushes.Green;  
  
            Size inf = new Size(double.PositiveInfinity, double.PositiveInfinity);  
            tb1.Measure(inf);  
            tb2.Measure(inf);  
            double middleWidth = Math.Max(tb1.DesiredSize.Width, tb2.DesiredSize.Width);  
            this.commentGrid.Width = middleWidth + 2 * MarginWidth;  
  
        Grid.SetColumn(rect, 0);  
        Grid.SetRow(rect, 0);  
         Grid.SetRowSpan(rect, 2);  
        Grid.SetColumnSpan(rect, 3);  
        Grid.SetRow(tb1, 0);  
        Grid.SetColumn(tb1, 1);  
        Grid.SetRow(tb2, 1);  
        Grid.SetColumn(tb2, 1);  
        this.commentGrid.Children.Add(rect);  
        this.commentGrid.Children.Add(tb1);  
        this.commentGrid.Children.Add(tb2);  
  
        Canvas.SetLeft(this.commentGrid, Math.Max(viewRightEdge - this.commentGrid.Width - 20.0, textRightEdge + 20.0));  
         Canvas.SetTop(this.commentGrid, textGeometry.GetRenderBounds(solidPen).Top);  
  
        this.Children.Add(this.commentGrid);  
    }  
    ```  
  
6.  Taky implementovat <xref:System.Windows.Controls.Panel.OnRender%2A> obslužné rutiny události, který se vykreslí dalších úprav.  
  
    ```csharp  
    protected override void OnRender(DrawingContext dc)  
    {  
        base.OnRender(dc);  
        if (this.textGeometry != null)  
        {  
            dc.DrawGeometry(brush, solidPen, this.textGeometry);  
            Rect textBounds = this.textGeometry.GetRenderBounds(solidPen);  
            Point p1 = new Point(textBounds.Right, textBounds.Bottom);  
            Point p2 = new Point(Math.Max(Canvas.GetLeft(this.commentGrid) - 20.0, p1.X), p1.Y);  
            Point p3 = new Point(Math.Max(Canvas.GetLeft(this.commentGrid), p1.X), (Canvas.GetTop(this.commentGrid) + p1.Y) * 0.5);  
            dc.DrawLine(dashPen, p1, p2);  
            dc.DrawLine(dashPen, p2, p3);  
        }  
    }  
    ```  
  
## <a name="adding-an-iwpftextviewcreationlistener"></a>Přidání IWpfTextViewCreationListener  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> Je část MEF součást, kterou můžete použít pro naslouchání na zobrazení událostí vytváření.  
  
1.  Přidejte soubor třídu do projektu CommentAdornmentTest a pojmenujte ji `Connector`.  
  
2.  Přidejte následující `using` příkazy.  
  
    ```csharp  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Utilities;  
    ```  
  
3.  Deklarace třídy, která implementuje <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text" a <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> z <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document>. Atribut typu obsahu určuje typ obsahu, na které se vztahuje komponentu. Text typ je základním typem pro všechny typy souborů není binární. Proto téměř každé textového zobrazení, která je vytvořena bude tohoto typu. Atribut text zobrazení role určuje druh textového zobrazení, pro kterou platí komponentu. Role zobrazení textového dokumentu obecně zobrazit text, který se skládá z čar a je uložen v souboru.  
  
     [!code-vb[VSSDKMenuCommandTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_1.vb)]
     [!code-csharp[VSSDKMenuCommandTest#11](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_1.cs)]  
  
4.  Implementace <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> metody, které volá statických `Create()` události `CommentAdornmentManager`.  
  
    ```csharp  
    public void TextViewCreated(IWpfTextView textView)  
    {  
        CommentAdornmentManager.Create(textView);  
    }  
    ```  
  
5.  Přidejte metodu, která můžete použít k provedení příkazu.  
  
    ```csharp  
    static public void Execute(IWpfTextViewHost host)  
    {  
        IWpfTextView view = host.TextView;  
        //Add a comment on the selected text.   
        if (!view.Selection.IsEmpty)  
        {  
            //Get the provider for the comment adornments in the property bag of the view.  
            CommentAdornmentProvider provider = view.Properties.GetProperty<CommentAdornmentProvider>(typeof(CommentAdornmentProvider));  
  
            //Add some arbitrary author and comment text.   
            string author = System.Security.Principal.WindowsIdentity.GetCurrent().Name;  
            string comment = "Four score....";  
  
            //Add the comment adornment using the provider.  
            provider.Add(view.Selection.SelectedSpans[0], author, comment);  
        }  
    }  
    ```  
  
## <a name="defining-an-adornment-layer"></a>Definování vrstvu dalších úprav  
 Pokud chcete přidat nový dalších úprav, je nutné zadat vrstvu dalších úprav.  
  
#### <a name="to-define-an-adornment-layer"></a>Chcete-li definovat vrstvu dalších úprav  
  
1.  V `Connector` třídy, deklarovat veřejné pole typu <xref:Microsoft.VisualStudio.Text.Editor.AdornmentLayerDefinition>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.NameAttribute> , určuje jedinečný název pro vrstvu dalších úprav a <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> , který definuje pořadí Z-order relace této vrstvy dalších úprav na další text Zobrazit vrstvy (text, pomocí kurzoru a výběr).  
  
    ```csharp  
    [Export(typeof(AdornmentLayerDefinition))]  
    [Name("CommentAdornmentLayer")]  
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
    public AdornmentLayerDefinition commentLayerDefinition;  
  
    ```  
  
## <a name="providing-comment-adornments"></a>Poskytnutí vylepšení komentář  
 Když definujete dalších úprav, také implementujte zprostředkovatele komentář dalších úprav a dalších úprav manažera komentář. Zprostředkovatel dalších úprav komentář udržuje seznam vylepšení komentář, naslouchá <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> události na základní textovou vyrovnávací paměť a vylepšení komentář odstraní při odstranění bude text.  
  
1.  Přidat nový soubor třídu do projektu CommentAdornmentTest a pojmenujte ji `CommentAdornmentProvider`.  
  
2.  Přidejte následující `using` příkazy.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.ObjectModel;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    ```  
  
3.  Přidejte třídu s názvem `CommentAdornmentProvider`.  
  
    ```csharp  
    internal class CommentAdornmentProvider  
    {  
    }  
    ```  
  
4.  Přidejte privátní pole pro textovou vyrovnávací paměť a seznam komentář vylepšení související do vyrovnávací paměti.  
  
    ```csharp  
    private ITextBuffer buffer;  
    private IList<CommentAdornment> comments = new List<CommentAdornment>();  
  
    ```  
  
5.  Přidejte konstruktor pro `CommentAdornmentProvider`. Tento konstruktor by měl mít privátní přístup, protože je mohl vytvořit jeho instanci zprostředkovatele `Create()` metoda. Přidá konstruktoru `OnBufferChanged` obslužná rutina události <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> událostí.  
  
    ```csharp  
    private CommentAdornmentProvider(ITextBuffer buffer)  
    {  
        this.buffer = buffer;  
        //listen to the Changed event so we can react to deletions.   
        this.buffer.Changed += OnBufferChanged;  
    }  
  
    ```  
  
6.  Přidat `Create()` metoda.  
  
    ```csharp  
    public static CommentAdornmentProvider Create(IWpfTextView view)  
    {  
        return view.Properties.GetOrCreateSingletonProperty<CommentAdornmentProvider>(delegate { return new CommentAdornmentProvider(view.TextBuffer); });  
    }  
  
    ```  
  
7.  Přidat `Detach()` metoda.  
  
    ```csharp  
    public void Detach()  
    {  
        if (this.buffer != null)  
        {  
            //remove the Changed listener   
            this.buffer.Changed -= OnBufferChanged;  
            this.buffer = null;  
        }  
    }  
    ```  
  
8.  Přidat `OnBufferChanged` obslužné rutiny události.  
  
    ```csharp  
    private void OnBufferChanged(object sender, TextContentChangedEventArgs e)  
    {  
        //Make a list of all comments that have a span of at least one character after applying the change. There is no need to raise a changed event for the deleted adornments. The adornments are deleted only if a text change would cause the view to reformat the line and discard the adornments.  
        IList<CommentAdornment> keptComments = new List<CommentAdornment>(this.comments.Count);  
  
        foreach (CommentAdornment comment in this.comments)  
        {  
            Span span = comment.Span.GetSpan(e.After);  
            //if a comment does not span at least one character, its text was deleted.   
            if (span.Length != 0)  
            {  
                keptComments.Add(comment);  
            }  
        }  
  
        this.comments = keptComments;  
    }  
  
    ```  
  
     [!code-csharp[VSSDKMenuCommandTest#21](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_2.cs)]
     [!code-vb[VSSDKMenuCommandTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_2.vb)]  
  
9. Přidejte deklaraci pro `CommentsChanged` událostí.  
  
    ```csharp  
    public event EventHandler<CommentsChangedEventArgs> CommentsChanged;  
    ```  
  
10. Vytvoření `Add()` metody přidat dalších úprav.  
  
    ```csharp  
    public void Add(SnapshotSpan span, string author, string text)  
    {  
        if (span.Length == 0)  
            throw new ArgumentOutOfRangeException("span");  
        if (author == null)  
            throw new ArgumentNullException("author");  
        if (text == null)  
            throw new ArgumentNullException("text");  
  
        //Create a comment adornment given the span, author and text.  
        CommentAdornment comment = new CommentAdornment(span, author, text);  
  
        //Add it to the list of comments.   
        this.comments.Add(comment);  
  
        //Raise the changed event.  
        EventHandler<CommentsChangedEventArgs> commentsChanged = this.CommentsChanged;  
        if (commentsChanged != null)  
            commentsChanged(this, new CommentsChangedEventArgs(comment, null));  
    }  
  
    ```  
  
11. Přidat `RemoveComments()` metoda.  
  
    ```csharp  
    public void RemoveComments(SnapshotSpan span)  
    {  
        EventHandler<CommentsChangedEventArgs> commentsChanged = this.CommentsChanged;  
  
        //Get a list of all the comments that are being kept   
        IList<CommentAdornment> keptComments = new List<CommentAdornment>(this.comments.Count);  
  
        foreach (CommentAdornment comment in this.comments)  
        {  
            //find out if the given span overlaps with the comment text span. If two spans are adjacent, they do not overlap. To consider adjacent spans, use IntersectsWith.   
            if (comment.Span.GetSpan(span.Snapshot).OverlapsWith(span))  
            {  
                //Raise the change event to delete this comment.   
                if (commentsChanged != null)  
                    commentsChanged(this, new CommentsChangedEventArgs(null, comment));  
            }  
            else  
                keptComments.Add(comment);  
        }  
  
        this.comments = keptComments;  
    }  
    ```  
  
12. Přidat `GetComments()` metodu, která vrátí všechny komentáře v daném snímku rozpětí.  
  
    ```csharp  
    public Collection<CommentAdornment> GetComments(SnapshotSpan span)  
    {  
        IList<CommentAdornment> overlappingComments = new List<CommentAdornment>();  
        foreach (CommentAdornment comment in this.comments)  
        {  
            if (comment.Span.GetSpan(span.Snapshot).OverlapsWith(span))  
                overlappingComments.Add(comment);  
        }  
  
        return new Collection<CommentAdornment>(overlappingComments);  
    }  
    ```  
  
13. Přidejte třídu s názvem `CommentsChangedEventArgs`, a to takto.  
  
    ```csharp  
    internal class CommentsChangedEventArgs : EventArgs  
    {  
        public readonly CommentAdornment CommentAdded;  
  
        public readonly CommentAdornment CommentRemoved;  
  
        public CommentsChangedEventArgs(CommentAdornment added, CommentAdornment removed)  
        {  
            this.CommentAdded = added;  
            this.CommentRemoved = removed;  
        }  
    }  
    ```  
  
## <a name="managing-comment-adornments"></a>Vylepšení správy komentář  
 Správce dalších úprav komentář vytvoří dalších úprav a přidává ji k vrstvě dalších úprav. Ho naslouchá <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> a <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> události, které se můžete přesunout nebo odstranit dalších úprav. Je také naslouchá `CommentsChanged` událost, která je spouštěna dalších úprav zprostředkovatelem komentář při přidávání nebo odebírání komentáře.  
  
1.  Přidejte soubor třídu do projektu CommentAdornmentTest a pojmenujte ji `CommentAdornmentManager`.  
  
2.  Přidejte následující `using` příkazy.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Windows.Media;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Formatting;  
    ```  
  
3.  Přidejte třídu s názvem `CommentAdornmentManager`.  
  
    ```csharp  
    internal class CommentAdornmentManager  
        {  
        }  
    ```  
  
4.  Přidejte do něj privátní pole.  
  
    ```csharp  
    private readonly IWpfTextView view;  
    private readonly IAdornmentLayer layer;  
    private readonly CommentAdornmentProvider provider;  
    ```  
  
5.  Přidejte konstruktor, která si předplatí správce k <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> a <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> události a také `CommentsChanged` událostí. Konstruktor je privátní, protože správce je vytvořena instance statickou `Create()` metoda.  
  
    ```csharp  
    private CommentAdornmentManager(IWpfTextView view)  
    {  
        this.view = view;  
        this.view.LayoutChanged += OnLayoutChanged;  
        this.view.Closed += OnClosed;  
  
        this.layer = view.GetAdornmentLayer("CommentAdornmentLayer");  
  
        this.provider = CommentAdornmentProvider.Create(view);  
        this.provider.CommentsChanged += OnCommentsChanged;  
    }  
    ```  
  
6.  Přidat `Create()` metoda, která načte zprostředkovatele nebo vytvoří jednu v případě potřeby.  
  
    ```csharp  
    public static CommentAdornmentManager Create(IWpfTextView view)  
    {  
        return view.Properties.GetOrCreateSingletonProperty<CommentAdornmentManager>(delegate { return new CommentAdornmentManager(view); });  
    }  
    ```  
  
7.  Přidat `CommentsChanged` obslužné rutiny.  
  
    ```csharp  
    private void OnCommentsChanged(object sender, CommentsChangedEventArgs e)  
    {  
        //Remove the comment (when the adornment was added, the comment adornment was used as the tag).   
        if (e.CommentRemoved != null)  
            this.layer.RemoveAdornmentsByTag(e.CommentRemoved);  
  
        //Draw the newly added comment (this will appear immediately: the view does not need to do a layout).   
        if (e.CommentAdded != null)  
            this.DrawComment(e.CommentAdded);  
    }  
    ```  
  
8.  Přidat <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> obslužné rutiny.  
  
    ```csharp  
    private void OnClosed(object sender, EventArgs e)  
    {  
        this.provider.Detach();  
        this.view.LayoutChanged -= OnLayoutChanged;  
        this.view.Closed -= OnClosed;  
    }  
    ```  
  
9. Přidat <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> obslužné rutiny.  
  
    ```csharp  
    private void OnLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
    {  
        //Get all of the comments that intersect any of the new or reformatted lines of text.  
        List<CommentAdornment> newComments = new List<CommentAdornment>();  
  
        //The event args contain a list of modified lines and a NormalizedSpanCollection of the spans of the modified lines.    
        //Use the latter to find the comments that intersect the new or reformatted lines of text.   
        foreach (Span span in e.NewOrReformattedSpans)  
        {  
            newComments.AddRange(this.provider.GetComments(new SnapshotSpan(this.view.TextSnapshot, span)));  
        }  
  
        //It is possible to get duplicates in this list if a comment spanned 3 lines, and the first and last lines were modified but the middle line was not.   
        //Sort the list and skip duplicates.  
        newComments.Sort(delegate(CommentAdornment a, CommentAdornment b) { return a.GetHashCode().CompareTo(b.GetHashCode()); });  
  
        CommentAdornment lastComment = null;  
        foreach (CommentAdornment comment in newComments)  
        {  
            if (comment != lastComment)  
            {  
                lastComment = comment;  
                this.DrawComment(comment);  
            }  
        }  
    }  
    ```  
  
10. Přidejte soukromá metoda, která nevykresluje komentář.  
  
     [!code-csharp[VSSDKMenuCommandTest#35](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_3.cs)]
     [!code-vb[VSSDKMenuCommandTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_3.vb)]  
  
## <a name="using-the-menu-command-to-add-the-comment-adornment"></a>Použitím příkazu nabídky pro přidání dalších úprav komentář  
 Můžete použít příkaz nabídky k vytvoření dalších úprav komentář implementací `MenuItemCallback` metoda VSPackage.  
  
1.  Přidejte následující odkazy na projekt MenuCommandTest:  
  
    -   Microsoft.VisualStudio.TextManager.Interop  
  
    -   Microsoft.VisualStudio.Editor  
  
    -   Microsoft.VisualStudio.Text.UI.Wpf  
  
2.  Otevřete soubor AddAdornment.cs a přidejte následující `using` příkazy.  
  
    ```csharp  
    using Microsoft.VisualStudio.TextManager.Interop;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Editor;  
    using CommentAdornmentTest;  
    ```  
  
3.  Delete – metoda ShowMessageBox() a přidejte následující obslužná rutina příkazu.  
  
    ```csharp  
    private void AddAdornmentHandler(object sender, EventArgs e)  
    {  
    }  
    ```  
  
4.  Přidejte kód slouží k získání aktivního zobrazení. Musíte získat `SVsTextManager` z prostředí sady Visual Studio získat aktivní `IVsTextView`.  
  
    ```csharp  
    private void AddAdornmentHandler(object sender, EventArgs e)  
    {  
        IVsTextManager txtMgr = (IVsTextManager)ServiceProvider.GetService(typeof(SVsTextManager));  
        IVsTextView vTextView = null;  
        int mustHaveFocus = 1;  
        txtMgr.GetActiveView(mustHaveFocus, null, out vTextView);  
    }  
    ```  
  
5.  Pokud toto zobrazení textu je instance zobrazení textového editoru, můžete jej do přetypovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> rozhraní a potom získat <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> a jeho přidružených <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>. Použití <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> k volání `Connector.Execute()` metoda, která získá zprostředkovatele komentář dalších úprav a přidá dalších úprav. Obslužná rutina příkazu by měl nyní vypadat takto:  
  
    ```csharp  
    private void AddAdornmentHandler(object sender, EventArgs e)  
    {  
        IVsTextManager txtMgr = (IVsTextManager)ServiceProvider.GetService(typeof(SVsTextManager));  
        IVsTextView vTextView = null;  
        int mustHaveFocus = 1;  
        txtMgr.GetActiveView(mustHaveFocus, null, out vTextView);  
        IVsUserData userData = vTextView as IVsUserData;  
         if (userData == null)  
        {  
            Console.WriteLine("No text view is currently open");  
                            return;  
        }  
        IWpfTextViewHost viewHost;  
        object holder;  
        Guid guidViewHost = DefGuidList.guidIWpfTextViewHost;  
        userData.GetData(ref guidViewHost, out holder);  
        viewHost = (IWpfTextViewHost)holder;  
        Connector.Execute(viewHost);  
    }  
    ```  
  
6.  Nastavte jako metodu AddAdornmentHandler jako obslužná rutina pro příkaz AddAdornment v konstruktoru AddAdornment.  
  
    ```csharp  
    private AddAdornment(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.AddAdornmentHandler;  
            MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
  
1.  Sestavte řešení a spuštění ladění. Experimentální instanci by se zobrazit.  
  
2.  Vytvořte textový soubor. Zadejte text a pak ho vyberte.  
  
3.  Na **nástroje** nabídky, klikněte na tlačítko **vyvolání přidání dalších úprav**. Bublina má být zobrazena na pravé straně okna text a musí obsahovat text, který vypadá takto.  
  
     Uživatelské_jméno  
  
     Fourscore...  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)