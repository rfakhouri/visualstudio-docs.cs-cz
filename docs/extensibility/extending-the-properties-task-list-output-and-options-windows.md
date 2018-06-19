---
title: Rozšíření vlastnosti, seznam úkolů, výstupní a možnosti Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- properties pane
- task list
- output window
- properties window
- tutorials
- tool windows
ms.assetid: 06990510-5424-44b8-9fd9-6481acec5c76
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4db9bb9101bd06921814132856fab0335a4a2530
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135537"
---
# <a name="extending-the-properties-task-list-output-and-options-windows"></a>Rozšíření vlastnosti, seznam úkolů, výstupní a možnosti Windows
Žádné okno nástroje v sadě Visual Studio můžete přistupovat. Tento návod ukazuje, jak integrovat do nové informace o vaší okno nástroje **možnosti** stránky a nové nastavení na **vlastnosti** stránky a také jak k zápisu do **seznam úkolů** a **výstup** systému windows.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="create-an-extension-with-a-tool-window"></a>Vytvoření rozšíření s okno nástroje  
  
1.  Vytvoření projektu s názvem **TodoList** pomocí VSIX šablony a přidat vlastní nástroj šablonu položky okno s názvem **TodoWindow**.  
  
    > [!NOTE]
    >  Další informace o vytváření rozšíření s okno nástroje najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="set-up-the-tool-window"></a>Nastavit okno nástroje  
 Přidáte textové pole pro zadání nová položka ToDo, tlačítko Přidat novou položku do seznamu a ListBox k zobrazení položek v seznamu.  
  
1.  V TodoWindow.xaml odstraňte, textové pole a StackPanel ovládacích prvků z UserControl.  
  
    > [!NOTE]
    >  Tím nedojde k odstranění **button1_Click** obslužná rutina události, která bude používat v pozdější fázi.  
  
2.  Z **všech ovládacích prvků WPF** části **sada nástrojů**, přetáhněte **plátno** řízení k mřížce.  
  
3.  Přetáhněte **TextBox**, **tlačítko**a **ListBox** na plátno. Umožňuje uspořádejte prvky, aby do textového pole a tlačítko jsou na stejné úrovni, a ListBox vyplní zbytek okna uvedenou pod nimi, stejně jako na obrázku níže.  
  
     ![Dokončení okno nástroje](../extensibility/media/t5-toolwindow.png "okno T5 nástrojů")  
  
4.  V podokně XAML najít tlačítko a nastavte vlastnost obsahu na **přidat**. Znovu připojit tlačítko obslužné rutiny události pro ovládací prvek tlačítko přidáním `Click="button1_Click"` atribut. Blok plátno by měl vypadat takto:  
  
    ```xml  
    <Canvas HorizontalAlignment="Left" Width="306">  
        <TextBox x:Name="textBox" HorizontalAlignment="Left" Height="23" Margin="10,10,0,0" TextWrapping="Wrap" Text="TextBox" VerticalAlignment="Top" Width="208"/>  
            <Button x:Name="button" Content="Add" HorizontalAlignment="Left" Margin="236,13,0,0" VerticalAlignment="Top" Width="48" Click="button1_Click"/>  
            <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="222" Margin="10,56,0,0" VerticalAlignment="Top" Width="274"/>  
    </Canvas>  
    ```  
  
#### <a name="customize-the-constructor"></a>Přizpůsobení konstruktoru  
  
1.  V souboru TodoWindowControl.xaml.cs, přidejte následující příkaz using:  
  
    ```csharp  
    using System;  
    ```  
  
2.  Přidejte veřejný odkaz na TodoWindow a mít konstruktor TodoWindowControl přebírají parametr TodoWindow. Kód by měl vypadat takto:  
  
    ```csharp  
    public TodoWindow parent;  
  
    public TodoWindowControl(TodoWindow window)  
    {  
        InitializeComponent();  
        parent = window;  
    }  
    ```  
  
3.  V TodoWindow.cs změňte TodoWindowControl konstruktor zahrnout parametr TodoWindow. Kód by měl vypadat takto:  
  
    ```csharp  
    public TodoWindow() : base(null)  
    {  
        this.Caption = "TodoWindow";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
  
         this.Content = new TodoWindowControl(this);  
    }  
    ```  
  
## <a name="create-an-options-page"></a>Vytvořit stránku možnosti  
 Můžete zadat na stránce v nástroji **možnosti** dialogu tak, aby uživatelé mohou změnit nastavení pro panel nástrojů. Vytvoření stránku možnosti vyžaduje, aby obě třídu, která popisuje možnosti a položku v souboru TodoListPackage.cs nebo TodoListPackage.vb.  
  
1.  Přidejte třídu s názvem `ToolsOptions.cs`. Ujistěte se, dědí z třídy ToolsOptions <xref:Microsoft.VisualStudio.Shell.DialogPage>.  
  
    ```csharp  
    class ToolsOptions : DialogPage  
    {  
    }  
    ```  
  
2.  Přidejte následující příkaz using:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
3.  Na stránce Možnosti v tomto návodu obsahuje pouze jednu možnost s názvem DaysAhead. Přidejte soukromé pole s názvem **daysAhead** a vlastnost s názvem **DaysAhead** k třídě ToolsOptions:  
  
    ```csharp  
    private double daysAhead;  
  
    public double DaysAhead  
    {  
        get { return daysAhead; }  
        set { daysAhead = value; }  
    }  
    ```  
  
 Nyní je nutné provést projektu vědět, tato stránka Možnosti.  
  
#### <a name="make-the-options-page-available-to-users"></a>Na stránce Možnosti zpřístupnit uživatelům  
  
1.  V TodoWindowPackage.cs, přidejte <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> k třídě TodoWindowPackage:  
  
    ```csharp  
    [ProvideOptionPage(typeof(ToolsOptions), "ToDo", "General", 101, 106, true)]  
    ```  
  
2.  První parametr konstruktoru ProvideOptionPage je typ třídy ToolsOptions, který jste vytvořili dříve. Druhý parametr "ToDo", je název kategorie **možnosti** dialogové okno. Třetí parametr "Obecné", je název podkategorie **možnosti** dialogové, kde bude k dispozici na stránce Možnosti. Následující dva parametry jsou ID prostředku pro řetězce; Název kategorie je první a druhý je název podkategorie. Konečný parametr určuje, zda tato stránka je přístupná pomocí automatizace.  
  
     Když uživatel otevře stránka Možnosti, by měl vypadat podobně jako na následujícím obrázku.  
  
     ![Stránka Možnosti](../extensibility/media/t5optionspage.gif "T5OptionsPage")  
  
     Všimněte si, kategorii **ToDo** a podkategorii **Obecné**.  
  
## <a name="make-data-available-to-the-properties-window"></a>Zpřístupnit Data do okna vlastností  
 Chcete-li proveďte informace o seznamu můžete zpřístupnit vytvořením třídy s názvem úkolu, který obsahuje informace o jednotlivých položek v seznamu úkolů.  
  
1.  Přidejte třídu s názvem `TodoItem.cs`.  
  
     Pokud okno nástroje jsou k dispozici uživatelům, položky v seznamu budou odpovídat TodoItems. Když uživatel vybere jeden z těchto položek v ovládacím prvku rozevíracího seznamu, **vlastnosti** okně se zobrazí informace o položce.  
  
     Jak zpřístupnit data v **vlastnosti** okně zapnout data do veřejné vlastnosti, které mají dva speciální atributy `Description` a `Category`. `Description` je text, který se zobrazí v dolní části **vlastnosti** okno. `Category` Určuje, kde, vlastnost by se měla objevit, když **vlastnosti** okno se zobrazí v **Categorized** zobrazení. Na následujícím obrázku **vlastnosti** je okno **Categorized** zobrazení, **název** vlastnost v **ToDo pole** kategorie vybrané a popis **název** vlastnosti se zobrazí v dolní části okna.  
  
     ![Vlastnosti – okno](../extensibility/media/t5properties.png "T5Properties")  
  
2.  Přidejte následující příkazy using TodoItem.cs souboru.  
  
    ```csharp  
    using System.ComponentModel;  
    using System.Windows.Forms;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  Přidat `public` – modifikátor přístupu k deklaraci třídy.  
  
    ```csharp  
    public class TodoItem  
    {  
    }  
    ```  
  
     Přidáte dvě vlastnosti Name a DueDate. Provedeme UpdateList() a CheckForErrors() později.  
  
    ```csharp  
    public class TodoItem  
    {  
        private TodoWindowControl parent;  
        private string name;  
        [Description("Name of the ToDo item")]  
        [Category("ToDo Fields")]  
        public string Name  
        {  
            get { return name; }  
            set  
            {  
                name = value;  
                parent.UpdateList(this);  
            }  
        }  
  
        private DateTime dueDate;  
        [Description("Due date of the ToDo item")]  
        [Category("ToDo Fields")]  
        public DateTime DueDate  
        {  
            get { return dueDate; }  
            set  
            {  
                dueDate = value;  
                parent.UpdateList(this);  
                parent.CheckForErrors();  
            }  
        }  
    }  
    ```  
  
4.  Přidejte privátní odkaz na uživatelský ovládací prvek. Přidejte konstruktor, který přebírá název pro tuto položku úkolů a uživatelského ovládacího prvku. Najít hodnotu pro daysAhead, získá vlastnost stránka Možnosti.  
  
    ```csharp  
    private TodoWindowControl parent;  
  
    public TodoItem(TodoWindowControl control, string itemName)  
    {  
        parent = control;  
        name = itemName;  
        dueDate = DateTime.Now;  
  
        double daysAhead = 0;  
        IVsPackage package = parent.parent.Package as IVsPackage;  
        if (package != null)  
        {  
            object obj;  
            package.GetAutomationObject("ToDo.General", out obj);  
  
            ToolsOptions options = obj as ToolsOptions;  
            if (options != null)  
            {  
                daysAhead = options.DaysAhead;  
            }  
        }  
  
        dueDate = dueDate.AddDays(daysAhead);  
    }  
    ```  
  
5.  Protože instance `TodoItem` třída bude uložen v seznamu a ListBox zavolá `ToString` funkce, musí přetížení `ToString` funkce. Přidejte následující kód do TodoItem.cs, po konstruktoru a před ukončením třídy.  
  
    ```csharp  
    public override string ToString()  
    {  
        return name + " Due: " + dueDate.ToShortDateString();  
    }  
    ```  
  
6.  V TodoWindowControl.xaml.cs, přidejte do třídy TodoWindowControl pro metody se zakázaným inzerováním `CheckForError` a `UpdateList` metody. Umístěte je po ProcessDialogChar a před konec souboru.  
  
    ```csharp  
    public void CheckForErrors()  
    {  
    }  
    public void UpdateList(TodoItem item)  
    {  
    }  
    ```  
  
     `CheckForError` Metoda zavolá metodu, která má stejný název v nadřazeném objektu a dané metody bude zkontrolujte, jestli všechny chyby mít došlo k chybě a je správně zpracovat. `UpdateList` Metoda zaktualizuje ListBox v nadřazeného ovládacího prvku; metoda je volána, když `Name` a `DueDate` vlastnosti v této změně třídy. Budou prováděny později.  
  
## <a name="integrate-into-the-properties-window"></a>Integrovat do okna vlastností  
 Nyní napsat kód, který spravuje ListBox, které bude být vázáno **vlastnosti** okno.  
  
 Je nutné změnit tlačítko klikněte na obslužnou rutinu do textového pole číst, vytvářet úkolu a přidá ji do seznamu.  
  
1.  Nahradit existující `button1_Click` funkce s kódem, který vytvoří nový TodoItem a přidá ji do seznamu. Volá TrackSelection(), který bude později definovaný.  
  
    ```csharp  
    private void button1_Click(object sender, RoutedEventArgs e)  
    {  
        if (textBox.Text.Length > 0)  
        {  
            var item = new TodoItem(this, textBox.Text);  
            listBox.Items.Add(item);  
            TrackSelection();  
            CheckForErrors();  
        }  
    }  
    ```  
  
2.  V návrhovém zobrazení vyberte ListBox – ovládací prvek. V **vlastnosti** okno kliknutím **obslužné rutiny událostí** tlačítko a vyhledejte události SelectionChanged. Zadejte do textového pole s **listBox_SelectionChanged**. Díky tomuto přidá zástupnou proceduru pro obslužnou rutinu SelectionChanged a přiřadí ji k události.  
  
3.  Implementujte metodu TrackSelection(). Vzhledem k tomu, že budete muset získat <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> služby, je nutné provést <xref:Microsoft.VisualStudio.Shell.WindowPane.GetService%2A> přístupné TodoWindowControl. Přidejte následující metodu do třídy TodoWindow:  
  
    ```  
    internal object GetVsService(Type service)  
    {  
        return GetService(service);  
    }  
    ```  
  
4.  Přidejte následující příkazy using do TodoWindowControl.xaml.cs:  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  Obslužná rutina SelectionChanged vyplňte takto:  
  
    ```  
    private void listBox_SelectionChanged(object sender, SelectionChangedEventArgs e)  
    {  
        TrackSelection();  
    }  
    ```  
  
6.  Nyní, vyplňte TrackSelection funkce, který bude poskytovat integrace s **vlastnosti** okno. Tato funkce je volána, když uživatel přidá položku do seznamu, nebo kliknutím na položku v seznamu. Přidá obsah objektu ListBox SelectionContainer a předá SelectionContainer k **vlastnosti** uživatele systému Windows <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> obslužné rutiny události. Služba TrackSelection sleduje vybrané objekty v uživatelském rozhraní (UI) a zobrazí jejich vlastnosti  
  
    ```csharp  
    private SelectionContainer mySelContainer;  
    private System.Collections.ArrayList mySelItems;  
    private IVsWindowFrame frame = null;  
  
    private void TrackSelection()  
    {  
        if (frame == null)  
        {  
            var shell = parent.GetVsService(typeof(SVsUIShell)) as IVsUIShell;  
            if (shell != null)  
            {  
                var guidPropertyBrowser = new  
                Guid(ToolWindowGuids.PropertyBrowser);  
                shell.FindToolWindow((uint)__VSFINDTOOLWIN.FTW_fForceCreate,  
                ref guidPropertyBrowser, out frame);  
            }  
        }  
        if (frame != null)  
            {  
                frame.Show();  
            }  
        if (mySelContainer == null)  
        {  
            mySelContainer = new SelectionContainer();  
        }  
  
        mySelItems = new System.Collections.ArrayList();  
  
        var selected = listBox.SelectedItem as TodoItem;  
        if (selected != null)  
        {  
            mySelItems.Add(selected);  
        }  
  
        mySelContainer.SelectedObjects = mySelItems;  
  
        ITrackSelection track = parent.GetVsService(typeof(STrackSelection))  
                                as ITrackSelection;  
        if (track != null)  
        {  
            track.OnSelectChange(mySelContainer);  
        }  
    }  
    ```  
  
     Teď, když máte třídu, **vlastnosti** okno můžete použít, můžete integrovat **vlastnosti** okno s okno nástroje. Když uživatel klikne na položku v ovládacím prvku rozevíracího seznamu v okně nástroje **vlastnosti** okně by měly být aktualizovány odpovídajícím způsobem. Podobně platí, když uživatel změní položky ToDo v **vlastnosti** okna, je třeba aktualizovat související položku.  
  
7.  Nyní přidejte zbývající kód funkce UpdateList v TodoWindowControl.xaml.cs. Měl by vyřadit a znovu přidat upravené TodoItem ze seznamu.  
  
    ```csharp  
    public void UpdateList(TodoItem item)  
    {  
        var index = listBox.SelectedIndex;  
        listBox.Items.RemoveAt(index);  
        listBox.Items.Insert(index, item);  
        listBox.SelectedItem = index;  
    }  
    ```  
  
8.  Otestujte svůj kód. Sestavte projekt a spusťte ladění. Experimentální instanci by se zobrazit.  
  
9. Otevřete **Nástroje / možnosti** stránky. Měli byste vidět kategorii úkolů v levém podokně. Kategorie jsou uvedeny v abecedním, takže podívejte se do části Ts.  
  
10. Na stránce Možnosti Todo, měli byste vidět vlastnost nastavena na DaysAhead **0**. Změňte ho na **2**.  
  
11. V zobrazení nebo ostatní okna nabídce otevřete **TodoWindow**. Typ **koncovým datem** textového pole a klikněte na **přidat**.  
  
12. V seznamu byste měli vidět dva dny pozdější než dnešní datum.  
  
## <a name="add-text-to-the-output-window-and-items-to-the-task-list"></a>Přidat Text do okna výstupu a položky do seznamu úkolů  
 Pro **seznam úkolů**, vytvořit nový objekt typu úloh a poté přidejte tento objekt úlohy pro **seznam úkolů** voláním metody jeho přidat. Zapsat do **výstup** volat jeho getpane – metoda pro získání objektu podokně a potom volejte metodu OutputString objektu podokně.  
  
1.  V TodoWindowControl.xaml.cs v `button1_Click` metoda, přidat kód slouží k získání **Obecné** podokně **výstup** okno (což je výchozí nastavení) a zápis do. Metoda by měla vypadat takto:  
  
    ```csharp  
    private void button1_Click(object sender, EventArgs e)  
    {  
        if (textBox.Text.Length > 0)  
        {  
            var item = new TodoItem(this, textBox.Text);  
            listBox.Items.Add(item);  
  
            var outputWindow = parent.GetVsService(  
                typeof(SVsOutputWindow)) as IVsOutputWindow;  
            IVsOutputWindowPane pane;  
            Guid guidGeneralPane = VSConstants.GUID_OutWindowGeneralPane;  
            outputWindow.GetPane(ref guidGeneralPane, out pane);  
            if (pane != null)  
            {  
                 pane.OutputString(string.Format(  
                    "To Do item created: {0}\r\n",  
                 item.ToString()));  
        }  
            TrackSelection();  
            CheckForErrors();  
        }  
    }  
    ```  
  
2.  Chcete-li přidat položky do seznamu úkolů, musíte třídy TodoWindowControl přidat vnořené třídy. Vnořené třídy musí být odvozen z <xref:Microsoft.VisualStudio.Shell.TaskProvider>. Přidejte následující kód na konec TodoWindowControl třídy.  
  
    ```csharp  
    [Guid("72de1eAD-a00c-4f57-bff7-57edb162d0be")]  
    public class TodoWindowTaskProvider : TaskProvider  
    {  
        public TodoWindowTaskProvider(IServiceProvider sp)  
            : base(sp)  
        {  
        }  
    }  
    ```  
  
3.  Dále přidejte privátní odkaz na TodoTaskProvider a CreateProvider() metodu do třídy TodoWindowControl. Kód by měl vypadat takto:  
  
    ```csharp  
    private TodoWindowTaskProvider taskProvider;  
    private void CreateProvider()  
    {  
        if (taskProvider == null)  
        {  
            taskProvider = new TodoWindowTaskProvider(parent);  
            taskProvider.ProviderName = "To Do";  
        }  
    }  
    ```  
  
4.  Přidejte do třídy TodoWindowControl ClearError(), který vymaže seznamu úkolů, a ReportError(), který přidá položku do seznamu úkolů.  
  
    ```csharp  
    private void ClearError()  
    {  
        CreateProvider();  
        taskProvider.Tasks.Clear();  
    }  
    private void ReportError(string p)  
    {  
        CreateProvider();  
        var errorTask = new Task();  
        errorTask.CanDelete = false;  
        errorTask.Category = TaskCategory.Comments;  
        errorTask.Text = p;  
  
        taskProvider.Tasks.Add(errorTask);  
  
        taskProvider.Show();  
  
        var taskList = parent.GetVsService(typeof(SVsTaskList))  
            as IVsTaskList2;  
        if (taskList == null)  
        {  
            return;  
        }  
  
        var guidProvider = typeof(TodoWindowTaskProvider).GUID;  
         taskList.SetActiveProvider(ref guidProvider);  
    }  
    ```  
  
5.  Teď následujícím způsobem implementujte metodu CheckForErrors.  
  
    ```csharp  
    public void CheckForErrors()  
    {  
        foreach (TodoItem item in listBox.Items)  
        {  
            if (item.DueDate < DateTime.Now)  
            {  
                ReportError("To Do Item is out of date: "  
                    + item.ToString());  
            }  
        }  
    }  
    ```  
  
## <a name="trying-it-out"></a>Vyzkoušení ho  
  
1.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
2.  Otevřete TodoWindow (**zobrazení nebo jiných Windows nebo TodoWindow**).  
  
3.  Zadejte text do textového pole a pak klikněte na **přidat**.  
  
     Datum splatnosti 2 dní od dnešního dne se přidá do seznamu. Nebudou vygenerovány žádné chyby a **seznam úkolů** (**zobrazení / úloh seznamu**) by měl mít žádné položky.  
  
4.  Teď změňte nastavení na **nástroje / Možnosti / ToDo** stránku z **2** zpět na **0**.  
  
5.  Zadejte jiný v **TodoWindow** a pak klikněte na **přidat** znovu. Tím se spustí chybu a také položku v **seznam úkolů**.  
  
     Při přidávání položek, počáteční datum je nastaveno nyní plus dvou dnů.  
  
6.  Na **zobrazení** nabídky, klikněte na tlačítko **výstup** otevřete **výstup** okno.  
  
     Všimněte si, že vždy, že přidáte položku, zobrazí se zpráva v **seznam úkolů** podokně.  
  
7.  Klikněte na některou z položek v seznamu.  
  
     **Vlastnosti** zobrazují dvě vlastnosti pro položku.  
  
8.  Jedna z vlastností změňte a stiskněte klávesu ENTER.  
  
     Položka k aktualizaci v seznamu.