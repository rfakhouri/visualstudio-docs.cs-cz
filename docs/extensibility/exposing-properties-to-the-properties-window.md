---
title: Vystavení vlastností do okna vlastností | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- properties [Visual Studio SDK], exposing in Property Browser
- properties [Visual Studio SDK]
- Property Browser, exposing properties
ms.assetid: 47f295b5-1ca5-4e7b-bb52-7b926b136622
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 12dcb30374250ca7aa917cf19b3a01ba57862c6d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="exposing-properties-to-the-properties-window"></a>Vystavení vlastností do okna vlastností
Tento názorný postup zpřístupní veřejné vlastnosti objektu **vlastnosti** okno. Pro tyto vlastnosti provedené změny se projeví v **vlastnosti** okno.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="exposing-properties-to-the-properties-window"></a>Vystavení vlastností do okna vlastností  
 V této části vytvořit okno Vlastní nástroje a zobrazit veřejné vlastnosti objektu přidružené okno podokně ve **vlastnosti** okno.  
  
#### <a name="to-expose-properties-to-the-properties-window"></a>K vystavení vlastností do okna vlastností  
  
1.  Každé rozšíření sady Visual Studio začíná projekt nasazení VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projektu s názvem `MyObjectPropertiesExtension`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Přidat okno nástroje přidáním okno nástroje vlastní šablonu položka s názvem `MyToolWindow`. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **dialogové okno Přidat novou položku**, přejděte na **Visual C# položky nebo rozšíření** a vyberte **okno nástroje vlastní**. V **název** pole v dolní části dialogového okna, změňte název souboru `MyToolWindow.cs`. Další informace o tom, jak vytvořit vlastní nástroj okno najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
3.  Otevřete MyToolWindow.cs a přidejte následující příkaz using:  
  
    ```  
    using System.Collections;  
    using System.ComponentModel;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
4.  Nyní přidejte následující pole do `MyToolWindow` třídy.  
  
    ```csharp  
    private ITrackSelection trackSel;  
    private SelectionContainer selContainer;  
  
    ```  
  
5.  Přidejte následující kód do třídy MyToolWindow.  
  
    ```csharp  
    private ITrackSelection TrackSelection  
    {  
        get  
        {  
            if (trackSel == null)  
                trackSel =  
                   GetService(typeof(STrackSelection)) as ITrackSelection;  
            return trackSel;  
        }  
    }  
  
    public void UpdateSelection()  
    {  
        ITrackSelection track = TrackSelection;  
        if (track != null)  
            track.OnSelectChange((ISelectionContainer)selContainer);  
    }  
  
    public void SelectList(ArrayList list)  
    {  
        selContainer = new SelectionContainer(true, false);  
        selContainer.SelectableObjects = list;  
        selContainer.SelectedObjects = list;  
        UpdateSelection();  
    }  
  
    public override void OnToolWindowCreated()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(this);  
        SelectList(listObjects);  
    }  
    ```  
  
     `TrackSelection` Používá vlastnost `GetService` získat `STrackSelection` služba, která poskytuje <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> rozhraní. `OnToolWindowCreated` Obslužné rutiny události a `SelectList` metoda dohromady vytvoří seznam vybraných objektů, který obsahuje pouze nástroj okno podokně samotného objektu. `UpdateSelection` Metoda informuje **vlastnosti** okna zobrazte veřejné vlastnosti v podokně okna nástrojů.  
  
6.  Sestavte projekt a spusťte ladění. Experimentální instanci sady Visual Studio by se zobrazit.  
  
7.  Pokud **vlastnosti** okno není viditelný, otevřete stisknutím klávesy F4.  
  
8.  Otevřete **MyToolWindow** okno. Najdete ho v **zobrazení nebo ostatní okna**.  
  
     Otevře se okno a veřejné vlastnosti v podokně okna se zobrazí v **vlastnosti** okno.  
  
9. Změna **popisek** vlastnost v **vlastnosti** okna **Moje vlastnosti objektu**.  
  
     Titulek MyToolWindow okno změní odpovídajícím způsobem.  
  
## <a name="exposing-tool-window-properties"></a>Vystavení vlastností okna nástroje  
 V této části přidávat okno nástroje a zobrazit její vlastnosti. Změny vlastností se projeví v **vlastnosti** okno.  
  
#### <a name="to-expose-tool-window-properties"></a>Aby se zveřejnily vlastností okna nástroje  
  
1.  Otevřete MyToolWindow.cs a přidejte do třídy MyToolWindow veřejná vlastnost typu boolean IsChecked.  
  
    ```csharp  
    [Category("My Properties")]  
    [Description("MyToolWindowControl properties")]  
    public bool IsChecked  
    {  
        get {  
            if (base.Content == null)  return false;  
            return (bool)(( MyToolWindowControl) base.Content).checkBox.IsChecked;   
        }  
        set {  
            ((MyToolWindowControl) base.Content).checkBox.IsChecked = value;  
        }  
    }  
    ```  
  
     Tato vlastnost získá stav z grafického subsystému WPF políčko, které vytvoříte později.  
  
2.  Otevřete MyToolWindowControl.xaml.cs a konstruktoru MyToolWindowControl nahraďte následujícím kódem.  
  
    ```vb  
    private MyToolWindow pane;  
    public MyToolWindowControl(MyToolWindow pane)  
    {  
        InitializeComponent();  
        this.pane = pane;  
        checkBox.IsChecked = false;  
    }  
    ```  
  
     Díky tomu `MyToolWindowControl` přístup k `MyToolWindow` podokně.  
  
3.  MyToolWindow.cs, změňte `MyToolWindow` konstruktor následujícím způsobem:  
  
    ```csharp  
    base.Content = new MyToolWindowControl(this);  
    ```  
  
4.  Přejděte do zobrazení návrhu MyToolWindowControl.  
  
5.  Tlačítko Odstranit a přidejte zaškrtávací políčko z **sada nástrojů** na levém horním rohu.  
  
6.  Přidání události zaškrtnuto a nezaškrtnuto. Zaškrtněte políčko v zobrazení návrhu. V **vlastnosti** okně klikněte na tlačítko obslužné rutiny události (v horní části napravo od **vlastnosti** okno). Najít **Checked** a typ **checkbox_Checked** do textového pole, vyhledejte **Unchecked** a typ **checkbox_Unchecked** v textovém poli.  
  
7.  Přidání obslužných rutin událostí políčko:  
  
    ```csharp  
    private void checkbox_Checked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = true;  
        pane.UpdateSelection();  
    }  
    private void checkbox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = false;  
        pane.UpdateSelection();  
    }  
    ```  
  
8.  Sestavte projekt a spusťte ladění.  
  
9. V experimentální instance, otevřete **MyToolWindow** okno.  
  
     Vyhledejte okně Vlastnosti v **vlastnosti** okno. **IsChecked** vlastnost se zobrazí v dolní části okna, v části **vlastnosti mého** kategorie.  
  
10. Zaškrtnutím políčka **MyToolWindow** okno. **IsChecked** v **vlastnosti** okno změní na **True**. Zrušte zaškrtnutí políčka v **MyToolWindow** okno. **IsChecked** v **vlastnosti** okno změní na **False**. Změňte hodnotu **IsChecked** v **vlastnosti** okno. Zaškrtněte políčko v **MyToolWindow** změny okna tak, aby odpovídala nové hodnotě.  
  
    > [!NOTE]
    >  Pokud musí vyřazení objekt, který se zobrazí v **vlastnosti** okno, volání `OnSelectChange` s `null` výběr kontejneru první. Po uvolnění vlastnost nebo objekt, můžete změnit na výběr kontejner, který byl aktualizován <xref:Microsoft.VisualStudio.Shell.SelectionContainer.SelectableObjects%2A> a <xref:Microsoft.VisualStudio.Shell.SelectionContainer.SelectedObjects%2A> uvádí.  
  
## <a name="changing-selection-lists"></a>Změna seznamech výběru  
 V této části přidat seznam výběr vlastností základní třídy a vyberte, které výběr seznamu zobrazíte pomocí rozhraní okno nástroje.  
  
#### <a name="to-change-selection-lists"></a>Chcete-li změnit výběr seznamy  
  
1.  Otevřete MyToolWindow.cs a přidejte veřejnou třídu s názvem `Simple`.  
  
    ```csharp  
    public class Simple  
    {  
        private string someText = "";  
  
        [Category("My Properties")]  
        [Description("Simple Properties")]  
        [DisplayName("My Text")]  
        public string SomeText  
        {  
            get { return someText; }  
            set { someText = value; }  
        }  
  
        [Category("My Properties")]  
        [Description("Read-only property")]  
        public bool ReadOnly  
        {  
            get { return false; }  
        }  
    }  
    ```  
  
2.  Přidání vlastnosti SimpleObject na třídě MyToolWindow plus dvě metody přepnout **vlastnosti** okno Výběr mezi podokně okna a `Simple` objektu.  
  
    ```csharp  
    private Simple simpleObject = null;  
    public Simple SimpleObject  
    {  
        get  
        {  
            if (simpleObject == null) simpleObject = new Simple();  
            return simpleObject;  
        }  
    }  
  
    public void SelectSimpleList()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(SimpleObject);  
        SelectList(listObjects);  
    }  
  
    public void SelectThisList()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(this);  
        SelectList(listObjects);  
    }  
    ```  
  
3.  V MyToolWindowControl.cs nahraďte obslužné rutiny políčko tyto řádky kódu:  
  
    ```csharp  
    private void checkbox_Checked(object sender, RoutedEventArgs e)  
     {  
        pane.IsChecked = true;  
        pane.SelectSimpleList();  
        pane.UpdateSelection();  
    }  
    private void checkbox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = false;  
        pane.SelectThisList();  
        pane.UpdateSelection();  
    }  
    ```  
  
4.  Sestavte projekt a spusťte ladění.  
  
5.  V experimentální instance, otevřete **MyToolWindow** okno.  
  
6.  Toto políčko zaškrtněte v **MyToolWindow** okno. **Vlastnosti** v okně se zobrazí `Simple` vlastnosti, objektu **SomeText** a **jen pro čtení**. Zrušte zaškrtnutí políčka. Veřejné vlastnosti okna se zobrazí v **vlastnosti** okno.  
  
    > [!NOTE]
    >  Zobrazovaný název **SomeText** je **Moje Text**.  
  
## <a name="best-practice"></a>Osvědčený postup  
 V tomto návodu <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> je implementována tak, aby kolekce volitelný objektu a kolekce vybraný objekt jsou stejné kolekci. V seznamu vlastností prohlížeče se zobrazí pouze vybraný objekt. Pro podrobnější ISelectionContainer implementaci najdete v části Reference.ToolWindow ukázky.  
  
 Okna nástrojů Visual Studio zachovat mezi relacemi sady Visual Studio. Další informace o zachování stavu okno nástroje najdete v tématu <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření vlastností a okno Vlastnosti](../extensibility/extending-properties-and-the-property-window.md)