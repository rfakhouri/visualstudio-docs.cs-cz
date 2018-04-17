---
title: Přidání okno nástroje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tutorials
- tool windows
ms.assetid: 8e16c381-03c8-404e-92ef-3614cdf3150a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: db06bebd700fa229685d6b79ffcfb014ef301994
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-tool-window"></a>Přidání okno nástroje
V tomto návodu jste Naučte se vytvořit okno nástroje a integrovat do sady Visual Studio následujícími způsoby:  
  
-   Přidání ovládacího prvku na panel nástrojů.  
  
-   Přidání panelu nástrojů na okno nástroje.  
  
-   Přidáte příkaz na panelu nástrojů.  
  
-   Implementujte příkazy.  
  
-   Nastavte výchozí umístění pro panel nástrojů.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-tool-window"></a>Vytváření okno nástroje  
  
1.  Vytvoření projektu s názvem **FirstToolWin** pomocí VSIX šablony a přidat vlastní nástroj šablonu položky okno s názvem **FirstToolWindow**.  
  
    > [!NOTE]
    >  Další informace o vytváření rozšíření s okno nástroje najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="add-a-control-to-the-tool-window"></a>Přidání ovládacího prvku na panel nástrojů  
  
1.  Odebrání ovládacího prvku výchozí. Otevřete FirstToolWindowControl.xaml a odstraňte **klikněte na tlačítko mi!** tlačítko.  
  
2.  V **sada nástrojů**, rozbalte **všech ovládacích prvků WPF** části a přetáhněte ji **média Element** řídit k **FirstToolWindowControl** formuláře. Vyberte ovládací prvek a v **vlastnosti** období, název tohoto elementu **mediaElement1**.  
  
## <a name="add-a-toolbar-to-the-tool-window"></a>Přidat panel nástrojů panel nástrojů  
 Přidáním panelu nástrojů následujícím způsobem zaručit, že jsou konzistentní se zbytkem prostředí IDE jeho přechody a barvy.  
  
1.  V **Průzkumníku**, otevřete FirstToolWindowPackage.vsct. Soubor .vsct definuje elementy grafické uživatelské rozhraní (GUI) v okně nástroje pomocí XML.  
  
2.  V `<Symbols>` část, vyhledejte `<GuidSymbol>` uzlu jejichž `name` atribut je `guidFirstToolWindowPackageCmdSet`. Přidejte následující dva `<IDSymbol>` elementy do seznamu `<IDSymbol>` elementy v tomto uzlu můžete definovat panelu nástrojů a nástrojů skupinu.  
  
    ```xml  
    <IDSymbol name="ToolbarID" value="0x1000" />  
    <IDSymbol name="ToolbarGroupID" value="0x1001" />  
    ```  
  
3.  Právě vyšší `<Buttons>` , vytvořte `<Menus>` oddíl, který vypadá takto:  
  
    ```xml  
    <Menus>  
        <Menu guid="guidFirstToolWindowPackageCmdSet" id="ToolbarID" priority="0x0000" type="ToolWindowToolbar">  
            <Parent guid="guidFirstToolWindowPackageCmdSet" id="ToolbarID" />  
            <Strings>  
                <ButtonText>Tool Window Toolbar</ButtonText>  
                <CommandName>Tool Window Toolbar</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     Existují různé druhy nabídky. Tato nabídka je panelu nástrojů v okně nástroje definované jeho `type` atribut. `guid` a `id` nastavení tvoří plně kvalifikovaný ID panelu nástrojů. Obvykle `<Parent>` nabídky je obsahující skupiny. Panel nástrojů je však definován jako vlastní nadřazený. Proto se používá stejný identifikátor pro `<Menu>` a `<Parent>` elementy. `priority` Atribut je právě ' 0'.  
  
4.  Panely nástrojů podobat nabídky mnoha způsoby. Například stejně jako nabídky může mít skupiny příkazů, panely nástrojů může také mít skupiny. (V nabídkách, příkaz skupiny jsou odděleny vodorovné čáry. Na panely nástrojů skupiny nejsou oddělených visual rozdělení.)  
  
     Přidat `<Groups>` oddíl, který obsahuje `<Group>` elementu. To definuje skupinu, jejíž ID deklarované v `<Symbols>` oddílu. Přidat `<Groups>` části právě po `<Menus>` oddílu.  
  
    ```xml  
    <Groups>  
       <Group guid="guidFirstToolWindowPackageCmdSet" id="ToolbarGroupID" priority="0x0000">  
           <Parent guid="guidFirstToolWindowPackageCmdSet" id="ToolbarID" />  
       </Group>  
    </Groups>  
    ```  
  
     Nastavením nadřazený identifikátor GUID a ID na identifikátor GUID a ID panelu nástrojů, přidejte skupinu na panelu nástrojů.  
  
## <a name="add-a-command-to-the-toolbar"></a>Přidání příkazu na panelu nástrojů  
 Na panelu nástrojů, který se zobrazí jako tlačítko přidáte příkaz.  
  
1.  V `<Symbols>` část, deklarovat následující prvky IDSymbol bezprostředně za panelu nástrojů a nástrojů deklarace skupiny.  
  
    ```xml  
    <IDSymbol name="cmdidWindowsMedia" value="0x0100" />  
    <IDSymbol name="cmdidWindowsMediaOpen" value="0x132" />  
    ```  
  
2.  Přidá prvek tlačítko uvnitř `<Buttons>` oddílu. Tento prvek se zobrazí na panelu nástrojů v okně nástroje s ikonou vyhledávání (s ikonou lupy).  
  
    ```xml  
    <Button guid="guidFirstToolWindowPackageCmdSet" id="cmdidWindowsMediaOpen" priority="0x0101" type="Button">  
        <Parent guid="guidFirstToolWindowPackageCmdSet" id="ToolbarGroupID"/>  
        <Icon guid="guidImages" id="bmpPicSearch" />  
        <Strings>  
            <CommandName>cmdidWindowsMediaOpen</CommandName>  
            <ButtonText>Load File</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
3.  Otevřete FirstToolWindowCommand.cs a přidejte následující řádky v třídě bezprostředně za existující pole.  
  
    ```csharp  
    public const string guidFirstToolWindowPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const uint cmdidWindowsMedia =        0x100;   
    public const int cmdidWindowsMediaOpen = 0x132;  
    public const int ToolbarID = 0x1000;  
    ```  
  
     Tato funkce zpřístupňuje příkazech v kódu.  
  
## <a name="add-a-mediaplayer-property-to-firsttoolwindowcontrol"></a>Přidání vlastnosti Media Player FirstToolWindowControl  
 Z obslužné rutiny události pro ovládací prvky panelu nástrojů musí být schopen řízení přehrávač médií, která je podřízená třídy FirstToolWindowControl přístupu vašeho kódu.  
  
 V **Průzkumníku řešení**, klikněte pravým tlačítkem na FirstToolWindowControl.xaml, klikněte na **kód zobrazení**a přidejte následující kód do třídy FirstToolWindowControl.  
  
```csharp  
public System.Windows.Controls.MediaElement MediaPlayer  
{  
    get { return mediaElement1; }  
}  
```  
  
## <a name="instantiate-the-tool-window-and-toolbar"></a>Vytvořit okno nástroje a panelu nástrojů  
 Přidání panelu nástrojů a příkaz nabídky, která volá **otevření souboru** dialogové okno a přehraje vybraného mediálního souboru.  
  
1.  Otevřete FirstToolWindow.cs a přidejte následující `using` příkazy.  
  
    ```csharp  
    using System.ComponentModel.Design;  
    using System.Windows.Forms;  
    using Microsoft.VisualStudio.Shell.Interop;   
    ```  
  
2.  Ve třídě FirstToolWindow přidejte veřejný odkaz do ovládacího prvku FirstToolWindowControl.  
  
    ```csharp  
    public FirstToolWindowControl control;  
    ```  
  
3.  Na konci tohoto konstruktoru nastavte tuto proměnnou ovládacího prvku do ovládacího prvku nově vytvořený.  
  
    ```csharp  
    control = new FirstToolWindowControl();   
    base.Content = control;  
    ```  
  
4.  Vytvoří instanci panelu nástrojů v konstruktoru.  
  
    ```csharp  
    this.ToolBar = new CommandID(new Guid(FirstToolWindowCommand.guidFirstToolWindowPackageCmdSet),   
        FirstToolWindowCommand.ToolbarID);  
    this.ToolBarLocation = (int)VSTWT_LOCATION.VSTWT_TOP;  
    ```  
  
5.  V tomto okamžiku konstruktor FirstToolWindow by měl vypadat takto:  
  
    ```csharp  
    public FirstToolWindow() : base(null)  
    {  
        this.Caption = "FirstToolWindow";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
        control = new FirstToolWindowControl();  
        base.Content = control;  
        this.ToolBar = new CommandID(new Guid(FirstToolWindowCommand.guidFirstToolWindowPackageCmdSet),   
            FirstToolWindowCommand.ToolbarID);  
            this.ToolBarLocation = (int)VSTWT_LOCATION.VSTWT_TOP;  
    }  
    ```  
  
6.  Přidejte příkaz nabídky panelu nástrojů. Ve třídě FirstToolWindowCommand.cs přidejte následující příkaz using  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
7.  Ve třídě FirstToolWindowCommand přidejte následující kód na konci metodu ShowToolWindow(). Příkaz ButtonHandler budou prováděny v další části.  
  
    ```csharp  
    // Create the handles for the toolbar command.   
    var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
    var toolbarbtnCmdID = new CommandID(new Guid(FirstToolWindowCommand.guidFirstToolWindowPackageCmdSet),  
        FirstToolWindowCommand.cmdidWindowsMediaOpen);  
    var menuItem = new MenuCommand(new EventHandler(  
        ButtonHandler), toolbarbtnCmdID);  
    mcs.AddCommand(menuItem);  
    ```  
  
#### <a name="to-implement-a-menu-command-in-the-tool-window"></a>K implementaci příkazu nabídky v okně nástroje  
  
1.  Ve třídě FirstToolWindowCommand přidat ButtonHandler metoda, která volá **otevření souboru** dialogové okno. Pokud soubor nebyl vybraný, hraje souboru média.  
  
2.  Ve třídě FirstToolWindowCommand přidejte privátní odkaz na okno FirstToolWindow, která je vytvořena v metodě FindToolWindow().  
  
    ```csharp  
    private FirstToolWindow window;  
    ```  
  
3.  Změnit metodu ShowToolWindow() nastavit na okno, které jste definovali výše, (, aby obslužná rutina ButtonHandler přístup ovládacího prvku okno. Zde je kompletní metoda ShowToolWindow().  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        window = (FirstToolWindow) this.package.FindToolWindow(typeof(FirstToolWindow), 0, true);  
        if ((null == window) || (null == window.Frame))  
        {  
                            throw new NotSupportedException("Cannot create tool window");  
        }  
  
        IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
  
         var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        var toolbarbtnCmdID = new CommandID(new Guid(FirstToolWindowCommandguidFirstToolWindowPackageCmdSet),  
            FirstToolWindowCommand.cmdidWindowsMediaOpen);  
        var menuItem = new MenuCommand(new EventHandler(  
            ButtonHandler), toolbarbtnCmdID);  
        mcs.AddCommand(menuItem);  
    }  
    ```  
  
4.  Přidejte metodu ButtonHandler. Vytvoří OpenFileDialog pro uživatele k určení souboru média k přehrání, a pak hraje vybraného souboru.  
  
    ```csharp  
    private void ButtonHandler(object sender, EventArgs arguments)  
    {  
        OpenFileDialog openFileDialog = new OpenFileDialog();  
        DialogResult result = openFileDialog.ShowDialog();  
        if (result == DialogResult.OK)  
        {  
            window.control.MediaPlayer.Source = new System.Uri(openFileDialog.FileName);  
        }  
    }  
    ```  
  
## <a name="set-the-default-position-for-the-tool-window"></a>Nastaví výchozí pozici pro panel nástrojů  
 Potom zadejte výchozí umístění v integrovaném vývojovém prostředí pro panel nástrojů. Informace o konfiguraci pro panel nástrojů je v souboru FirstToolWindowPackage.cs.  
  
1.  V FirstToolWindowPackage.cs, najdete <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> atributu u `FirstToolWindowPackage` třídy, která předá typ FirstToolWindow konstruktoru. Chcete-li určit výchozí umístění, je nutné přidat další parametry konstruktoru následující ukázka.  
  
    ```csharp  
    [ProvideToolWindow(typeof(FirstToolWindow),  
        Style = Microsoft.VisualStudio.Shell.VsDockStyle.Tabbed,  
        Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")]  
    ```  
  
     První parametr s názvem je `Style` a jeho hodnota může být `Tabbed`, což znamená, že okno bude na kartě v existujícím okně. Je zadána pozici ukotvení `Window` parametr, v tomto případě n identifikátor GUID **Průzkumníku řešení**.  
  
    > [!NOTE]
    >  Další informace o typech windows v prostředí IDE najdete v tématu <xref:EnvDTE.vsWindowType>.  
  
## <a name="testing-the-tool-window"></a>Testování panel nástrojů  
  
1.  Stisknutím klávesy F5 otevřete novou instanci třídy sadě Visual Studio experimentální sestavení.  
  
2.  Na **zobrazení** nabídky, přejděte na příkaz **ostatní okna** a pak klikněte na **první okno nástroje**.  
  
     Ve stejné pozici, jako by měla otevřít okno nástroje přehrávač médií **Průzkumníku řešení**. Pokud stále zobrazuje v stejně jako při před, obnovit rozložení okna (**okno nebo resetovat rozložení okna**).  
  
3.  Klikněte na tlačítko (má ikonu hledání) v okně nástroje. Vyberte podporované zvuk nebo video souboru, například C:\windows\media\chimes.wav, stiskněte **otevřete**.  
  
     Měli byste slyšet zvuk gongu.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)