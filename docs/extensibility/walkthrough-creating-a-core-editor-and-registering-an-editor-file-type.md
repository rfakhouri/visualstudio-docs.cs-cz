---
title: "Vytvoření základní editoru a registrace typ souboru Editor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - walkthrough
ms.assetid: 24d2bffd-a35c-46db-8515-fd60b884b7fb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ace475cb94920a5c0470c1d16265349edfa441f4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-core-editor-and-registering-an-editor-file-type"></a>Návod: Vytvoření základní editoru a registraci typu souboru editoru
Tento návod ukazuje, jak vytvořit VSPackage začínající [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor, pokud soubor, který má příponu názvu souboru .myext je načíst.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Umístění pro šablony projektu balíček Visual Studio  
 Šablona projektu balíček Visual Studio najdete ve třech různých umístěních v **nový projekt** dialogové okno:  
  
1.  V části rozšiřitelnosti jazyka Visual Basic. Je výchozí jazyk projektu jazyka Visual Basic.  
  
2.  V části C# – rozšiřitelnost. Je výchozí jazyk projektu C#.  
  
3.  V části Další typy rozšiřitelnost projektů. Výchozí jazyk projektu je C++.  
  
### <a name="to-create-the-vspackage"></a>Chcete-li vytvořit VSPackage  
  
-   Spustit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vytvořte [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] VSPackage s názvem `MyPackage`, jak je uvedeno v [návod: vytváření VSPackage příkaz nabídky](http://msdn.microsoft.com/en-us/d699c149-5d1e-47ff-94c7-e1222af02c32).  
  
### <a name="to-add-the-editor-factory"></a>Chcete-li přidat objekt factory editoru  
  
1.  Klikněte pravým tlačítkem myši **MyPackage** projektu, přejděte na **přidat** a pak klikněte na **třída**.  
  
2.  V **přidat novou položku** dialogové okno zkontrolujte, zda **– třída** je vybraná šablona, typ `EditorFactory.cs` pro název a pak klikněte na tlačítko **přidat** přidat třídu do projektu.  
  
     Soubor EditorFactory.cs musí být automaticky otevřen.  
  
3.  Následující sestavení odkazovat z vašeho kódu.  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    Imports Microsoft.VisualStudio  
    Imports Microsoft.VisualStudio.Shell  
    Imports Microsoft.VisualStudio.Shell.Interop  
    Imports Microsoft.VisualStudio.OLE.Interop  
    Imports Microsoft.VisualStudio.TextManager.Interop  
    Imports IOleServiceProvider = Microsoft.VisualStudio.OLE.Interop.IServiceProvider  
    ```  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio.TextManager.Interop;  
    using IOleServiceProvider = Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
  
    ```  
  
4.  Přidejte identifikátor GUID `EditorFactory` třída přidáním `Guid` atribut bezprostředně před deklaraci třídy.  
  
     Nový identifikátor GUID můžete vygenerovat pomocí programu guidgen.exe [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku, nebo kliknutím na **vytvořit GUID** na **nástroje** nabídky. Identifikátor GUID použít zde je pouze příklad; Nepoužívejte ho ve vašem projektu.  
  
    ```vb  
    <Guid("0eea3187-c5fa-48d4-aa72-b5eecd3b17b1")> _  
    ```  
  
    ```csharp  
    [Guid("0eea3187-c5fa-48d4-aa72-b5eecd3b17b1")]   
    ```  
  
5.  V definici třídy přidejte dva privátní proměnné tak, aby obsahovala balíček nadřazené a poskytovatele služeb.  
  
    ```vb  
    Class EditorFactory  
        Private parentPackage As Package  
        Private serviceProvider As IOleServiceProvider  
    ```  
  
    ```csharp  
    class EditorFactory  
    {  
        private Package parentPackage;  
        private IOleServiceProvider serviceProvider;  
    }  
  
    ```  
  
6.  Přidejte veřejnou třídu konstruktor, který přijímá jeden parametr typu <xref:Microsoft.VisualStudio.Shell.Package>:  
  
    ```vb  
    Public Sub New(ByVal parentPackage As Package)  
        Me.parentPackage = parentPackage  
    End Sub  
    ```  
  
    ```csharp  
    public EditorFactory(Package parentPackage)  
    {  
        this.parentPackage = parentPackage;  
    }  
    ```  
  
7.  Změnit `EditorFactory` deklarace k odvozování z třídy <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní.  
  
    ```vb  
    Class EditorFactory Implements IVsEditorFacto  
    ```  
  
    ```csharp  
    class EditorFactory : IVsEditorFactory  
  
    ```  
  
8.  Klikněte pravým tlačítkem na <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>, klikněte na tlačítko **implementovat rozhraní**a potom klikněte na **implementace rozhraní explicitně**.  
  
     Tento postup přidá čtyři metody, které musí být implementován v <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní.  
  
9. Nahraďte obsah `IVsEditorFactory.Close` metoda následujícím kódem.  
  
    ```vb  
    Return VSConstants.S_OK  
    ```  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
10. Nahraďte obsah `IVsEditorFactory.SetSite` následujícím kódem.  
  
    ```vb  
    Me.serviceProvider = psp  
    Return VSConstants.S_OK  
    ```  
  
    ```csharp  
    this.serviceProvider = psp;  
    return VSConstants.S_OK;  
    ```  
  
11. Nahraďte obsah `IVsEditorFactory.MapLogicalView` metoda následujícím kódem.  
  
    ```vb  
    Dim retval As Integer = VSConstants.E_NOTIMPL  
    pbstrPhysicalView = Nothing ' We support only one view.  
    If rguidLogicalView.Equals(VSConstants.LOGVIEWID_Designer)OrElse _  
    rguidLogicalView.Equals(VSConstants.LOGVIEWID_Primary) Then  
        retval = VSConstants.S_OK  
    End If  
    Return retval  
    ```  
  
    ```csharp  
    int retval = VSConstants.E_NOTIMPL;  
    pbstrPhysicalView = null;   // We support only one view.  
    if (rguidLogicalView.Equals(VSConstants.LOGVIEWID_Designer) ||  
    rguidLogicalView.Equals(VSConstants.LOGVIEWID_Primary))  
    {  
        retval = VSConstants.S_OK;  
    }  
    return retval;  
    ```  
  
12. Nahraďte obsah `IVsEditorFactory.CreateEditorInstance` metoda následujícím kódem.  
  
    ```vb  
    Dim retval As Integer = VSConstants.E_FAIL          
  
    ' Initialize these to empty to start with   
    ppunkDocView = IntPtr.Zero  
    ppunkDocData = IntPtr.Zero  
    pbstrEditorCaption = ""  
    pguidCmdUI = Guid.Empty  
    pgrfCDW = 0  
  
    If (grfCreateDoc And (VSConstants.CEF_OPENFILE Or _  
    VSConstants.CEF_SILENT)) = 0 Then  
        Throw New ArgumentException("Only Open or Silent is valid")  
    End If  
    If punkDocDataExisting <> IntPtr.Zero Then  
        Return VSConstants.VS_E_INCOMPATIBLEDOCDATA  
    End If  
  
    ' Instantiate a text buffer of type VsTextBuffer.   
    ' Note: we only need an IUnknown (object) interface for   
    ' this invocation.   
    Dim clsidTextBuffer As Guid = GetType(VsTextBufferClass).GUID  
    Dim iidTextBuffer As Guid = VSConstants.IID_IUnknown  
    Dim pTextBuffer As Object = pTextBuffer = _  
    parentPackage.CreateInstance(clsidTextBuffer, iidTextBuffer, _  
    GetType(Object))  
  
    If Not pTextBuffer Is Nothing Then  
        ' "Site" the text buffer with the service provider we were   
        ' provided.   
        Dim textBufferSite As IObjectWithSite = TryCast(pTextBuffer, _  
        IObjectWithSite)  
        If Not textBufferSite Is Nothing Then  
            textBufferSite.SetSite(Me.serviceProvider)  
        End If  
  
        ' Instantiate a code window of type IVsCodeWindow.   
        Dim clsidCodeWindow As Guid = GetType(VsCodeWindowClass).GUID  
        Dim iidCodeWindow As Guid = GetType(IVsCodeWindow).GUID  
        Dim pCodeWindow As IVsCodeWindow = _  
        CType(Me.parentPackage.CreateInstance(clsidCodeWindow, _  
        iidCodeWindow, GetType(IVsCodeWindow)), IVsCodeWindow)  
        If Not pCodeWindow Is Nothing Then  
            ' Give the text buffer to the code window.   
            ' We are giving up ownership of the text buffer!   
            pCodeWindow.SetBuffer(CType(pTextBuffer, IVsTextLines))  
  
            ' Now tell the caller about all this new stuff   
            ' that has been created.   
            ppunkDocView = Marshal.GetIUnknownForObject(pCodeWindow)  
            ppunkDocData = Marshal.GetIUnknownForObject(pTextBuffer)  
  
            ' Specify the command UI to use so keypresses are   
            ' automatically dealt with.   
            pguidCmdUI = VSConstants.GUID_TextEditorFactory  
  
            ' This caption is appended to the filename and   
            ' lets us know our invocation of the core editor   
            ' is up and running.   
            pbstrEditorCaption = " [MyPackage]"  
  
            retval = VSConstants.S_OK  
        End If  
    End If  
    Return retval  
    ```  
  
    ```csharp  
    int retval = VSConstants.E_FAIL;  
  
    // Initialize these to empty to start with  
    ppunkDocView       = IntPtr.Zero;  
    ppunkDocData       = IntPtr.Zero;  
    pbstrEditorCaption = "";  
    pguidCmdUI         = Guid.Empty;   
    pgrfCDW            = 0;  
  
    if ((grfCreateDoc & (VSConstants.CEF_OPENFILE |   
          VSConstants.CEF_SILENT)) == 0)  
    {   
        throw new ArgumentException("Only Open or Silent is valid");  
    }  
    if (punkDocDataExisting != IntPtr.Zero)  
    {  
        return VSConstants.VS_E_INCOMPATIBLEDOCDATA;  
    }  
  
    // Instantiate a text buffer of type VsTextBuffer.  
    // Note: we only need an IUnknown (object) interface for   
    // this invocation.  
    Guid clsidTextBuffer = typeof(VsTextBufferClass).GUID;  
    Guid iidTextBuffer   = VSConstants.IID_IUnknown;  
    object pTextBuffer   = pTextBuffer = parentPackage.CreateInstance(  
          ref clsidTextBuffer,  
          ref iidTextBuffer,  
          typeof(object));  
  
    if (pTextBuffer != null)  
    {  
        // "Site" the text buffer with the service provider we were  
        // provided.  
        IObjectWithSite textBufferSite = pTextBuffer as IObjectWithSite;  
        if (textBufferSite != null)  
        {  
            textBufferSite.SetSite(this.serviceProvider);  
        }  
  
        // Instantiate a code window of type IVsCodeWindow.  
        Guid clsidCodeWindow = typeof(VsCodeWindowClass).GUID;  
        Guid iidCodeWindow   = typeof(IVsCodeWindow).GUID;  
        IVsCodeWindow pCodeWindow =  
        (IVsCodeWindow)this.parentPackage.CreateInstance(   
              ref clsidCodeWindow,  
              ref iidCodeWindow,  
              typeof(IVsCodeWindow));  
        if (pCodeWindow != null)  
        {  
            // Give the text buffer to the code window.  
            // We are giving up ownership of the text buffer!  
            pCodeWindow.SetBuffer((IVsTextLines)pTextBuffer);  
  
            // Now tell the caller about all this new stuff   
            // that has been created.  
            ppunkDocView = Marshal.GetIUnknownForObject(pCodeWindow);  
            ppunkDocData = Marshal.GetIUnknownForObject(pTextBuffer);  
  
            // Specify the command UI to use so keypresses are   
            // automatically dealt with.  
            pguidCmdUI = VSConstants.GUID_TextEditorFactory;  
  
            // This caption is appended to the filename and  
            // lets us know our invocation of the core editor   
            // is up and running.  
            pbstrEditorCaption = " [MyPackage]";  
  
            retval = VSConstants.S_OK;  
        }   
    }   
    return retval;   
    ```  
  
13. Kompilace projektu a ujistěte se, že nejsou žádné chyby.  
  
### <a name="to-register-the-editor-factory"></a>K registraci objekt factory editoru  
  
1.  V **Průzkumníku řešení**, poklikejte na soubor Resources.resx a otevře se v tabulce řetězec, ve kterém položka **řetězec1 je** vybrané.  
  
2.  Změna názvu identifikátor, který `IDS_EDITORNAME` a text, který se **MyPackage Editor.** Jako název vašeho editoru, zobrazí se tento řetězec.  
  
3.  Otevřete soubor VSPackage.resx a přidejte nový řetězce, nastavte na název **101** a hodnota, která má `IDS_EDITORNAME`. To poskytuje balíček s ID prostředku pro přístup k řetězec, který jste právě vytvořili.  
  
    > [!NOTE]
    >  Pokud soubor VSPackage.resx obsahuje jiný řetězec, který `name` atribut nastaven na **101**, nahraďte jinou jedinečný, číselnou hodnotu, sem a v následujících krocích.  
  
4.  V **Průzkumníku**, otevřete soubor MyPackagePackage.cs.  
  
     Toto je soubor hlavní balíčku.  
  
5.  Přidejte následující atributy uživatele těsně před `Guid` atribut.  
  
    ```vb  
    <ProvideEditorFactoryAttribute(GetType(EditorFactory), 101)> _  
    <ProvideEditorExtensionAttribute(GetType(EditorFactory), _  
          ".myext", 32, NameResourceID:=101 )> _  
    ```  
  
    ```csharp  
    [ProvideEditorFactory(typeof(EditorFactory), 101)]  
    [ProvideEditorExtension(typeof(EditorFactory),   
          ".myext", 32, NameResourceID = 101)]   
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute> Atribut přidruží přípona souboru .myext vaše objekt factory editoru tak, aby vždycky, když soubor, který má, rozšíření je načtena, je vyvolána vaší objekt factory editoru.  
  
6.  Přidat privátní proměnnou, která `MyPackage` třídy těsně před konstruktoru a dejte mu typ `EditorFactory`.  
  
    ```vb  
    Private editorFactory As EditorFactory  
    ```  
  
    ```csharp  
    private EditorFactory editorFactory;  
    ```  
  
7.  Najít `Initialize` – metoda (možná budete muset otevřít `Package Members` Skrytá oblast) a přidejte následující kód po volání `base.Initialize()`.  
  
    ```vb  
    'Create our editor factory and register it.   
    Me.editorFactory = New EditorFactory(Me)  
    MyBase.RegisterEditorFactory(Me.editorFactory)  
    ```  
  
    ```csharp  
    // Create our editor factory and register it.  
    this.editorFactory = new EditorFactory(this);  
    base.RegisterEditorFactory(this.editorFactory);  
  
    ```  
  
8.  Kompilace programu a ujistěte se, že nejsou žádné chyby.  
  
     Tento krok zaregistruje objekt factory editoru experimentální podregistru pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pokud se zobrazí výzva k přepsání souboru resource.h, klikněte na tlačítko **OK**.  
  
9. Vytvoření ukázkového souboru s názvem TextFile1.myext.  
  
10. Stiskněte klávesu **F5** otevřete instanci experimentální [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
11. V experimentální [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]na **soubor** nabídky, přejděte na příkaz **otevřete** a pak klikněte na **soubor**.  
  
12. Najít TextFile1.myext a pak klikněte na tlačítko **otevřete**.  
  
     Soubor by měl nyní načíst.  
  
## <a name="robust-programming"></a>Robustní programování  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Základní editor zpracovává širokou škálu typy textový soubor a spolupracuje úzce s jazyk služeb nabízejí bohatou sadu funkcí, jako je například zvýraznění syntaxe závorky a seznamy dokončení slova a člen dokončení IntelliSense. Pokud pracujete s textové soubory, můžete použít editor základní spolu s vlastní jazyk služba, která podporuje vaše konkrétní typy souborů.  
  
 Vyvolat VSPackage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor zadáním objekt factory editoru. Tento objekt factory editoru se používá, když je načten soubor, který je k ní přidružena. Pokud soubor je součástí projektu, pak editoru základní se automaticky vyvolá, pokud vaše VSPackage přepsat. Ale pokud je soubor načten mimo projekt, pak editoru základní musí explicitně vyvolat vaší VSPackage.  
  
 Další informace o editoru jádra najdete v tématu [v editoru v základní](../extensibility/inside-the-core-editor.md).  
  
## <a name="see-also"></a>Viz také  
 [V editoru jádra](../extensibility/inside-the-core-editor.md)   
 [Vytváření instancí editoru základní pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)