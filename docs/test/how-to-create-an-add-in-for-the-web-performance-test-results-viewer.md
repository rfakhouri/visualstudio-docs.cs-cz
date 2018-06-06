---
title: Vytvoření doplňku sady Visual Studio pro prohlížeč výsledků testu výkonnosti webu
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, Visual Studio Add-in
- Visual Studio Add-in, Web performance tests
ms.assetid: 1118c604-4b1b-4b21-a04e-45995b676fa8
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2d3f0ec5108d077346eb69f1fb1236a7ecee56d5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751673"
---
# <a name="how-to-create-a-visual-studio-add-in-for-the-web-performance-test-results-viewer"></a>Postupy: Vytvoření doplňku sady Visual Studio pro prohlížeč výsledků testu výkonnosti webu

Uživatelské rozhraní pro prohlížeč výsledků testu výkonnosti webu můžete rozšířit pomocí následujících oborů názvů:

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting>

-   <xref:Microsoft.VisualStudio.TestTools.WebTesting>

Kromě toho budete muset přidat odkaz na knihovnu DLL LoadTestPackage, který je umístěný ve *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies* složky.

-   Pokud chcete rozšířit webový prohlížeč výsledků testu výkonnosti pro uživatelské rozhraní, musíte vytvořit přidat v sadě Visual Studio a uživatelského ovládacího prvku. Následující postupy popisují, jak vytvořit doplněk, uživatelského ovládacího prvku a implementaci tříd, které jsou nezbytné rozšířit webový prohlížeč výsledků testu výkonnosti pro uživatelské rozhraní.

## <a name="create-or-open-a-solution-that-contains-an-aspnet-web-application-and-a-web-performance-and-load-test-project"></a>Vytvořte nebo otevřete řešení obsahující webové aplikace ASP.NET a výkonu webu a zatížení testovacího projektu

### <a name="to-prepare-for-extending-the-web-performance-test-results-viewer"></a>Příprava pro rozšíření prohlížeč výsledků testu výkonnosti webu

Umožňuje vytvořit nebo otevřít mimo produkční řešení, můžete experimentovat s obsahující webové aplikace ASP.NET a výkonu webu a zatížení testování projektu pomocí jeden nebo více testů výkonu webové aplikace ASP.NET Web.

> [!NOTE]
> Můžete vytvořit webovou aplikaci ASP.NET a výkonu webu a zatížení testování projekt, který obsahuje testy výkonnosti webu pomocí postupů uvedených v [postupy: vytvoření služby Webový Test](../test/how-to-create-a-web-service-test.md) a [generování a spuštění programového webu test výkonnosti](../test/generate-and-run-a-coded-web-performance-test.md).

## <a name="create-a-visual-studio-add-in"></a>Vytvoření doplňku sady Visual Studio

Doplněk je kompilovanou knihovnu DLL, který je spuštěn v sadě Visual Studio integrované vývojové prostředí (IDE). Kompilace pomáhá chránit duševní vlastnictví a zvyšuje výkon. I když můžete vytvořit doplňky ručně, může být snazší použít průvodce Add-In. Tento průvodce vytvoří funkčnosti, ale základní doplňku můžete spustit okamžitě po jejím vytvoření. Po průvodce Add-In generuje základní program, můžete do ní přidejte kód a přizpůsobit.

 Průvodce Add-In umožňuje zadat zobrazovaný název a popis tohoto doplňku. Jak se objeví v **Add-In správce**. Volitelně může mít průvodce generovat kód, který přidá **nástroje** nabídky příkaz Otevřít doplněk. Můžete také zobrazit vlastní **o** dialogové okno pro vaše add-in. Po dokončení průvodce máte nový projekt, který obsahuje pouze jednu třídu, která implementuje doplněk. Třídy je název připojení.

 Budete používat **Add-In správce** na konci tohoto tématu.

### <a name="to-create-an-add-in-by-using-the-add-in-wizard"></a>Chcete-li vytvořit v pomocí průvodce Add-In

1.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení, zvolte **přidat** a pak vyberte **nový projekt**.

     Zobrazí se dialogové okno Nový projekt.

2.  V části **nainstalovaných šablonách**, rozbalte položku **jiné typy projektů** a vyberte **rozšiřitelnost**.

3.  V seznamu šablon, vyberte **Visual Studio Add-in**.

4.  Pod názvem zadejte název pro doplněk. Například **WebPerfTestResultsViewerAddin**.

5.  Zvolte **OK**.

     Spustí se průvodce Visual Studio Add-in.

6.  Zvolte **Další**.

7.  Na **vyberte programovací jazyk** vyberte programovací jazyk, který chcete použít k zápisu v doplňku.

    > [!NOTE]
    > Toto téma používá Visual C# pro ukázkový kód.

8.  Na **vyberte hostitele aplikací** vyberte **Visual Studio** a zrušte zaškrtnutí **Visual Studio makra**.

9. Zvolte **Další**.

10. Zadejte název a popis tohoto doplňku na **zadejte název a popis** stránky.

     Po doplněk je vytvořen, jeho název a popis se zobrazí v **Add-in k dispozici** seznamu v **Add-In správce**. Přidejte dostatek podrobností, které se popis tohoto doplňku tak, aby uživatelé můžete zjistit, jaké vaše doplňku neobsahuje, jak funguje a tak dále.

11. Zvolte **Další**.

12. Na **výběr Add-In možností** vyberte **nastavit jako můj Add-in načíst při spuštění aplikace hostitele**.

13. Zrušte zaškrtnutí políčka zbývající.

14. Na **výběr pomůže o informace** můžete zadat, jestli chcete získat informace o vaší doplňku pro zobrazení v **o** dialogové okno. Pokud chcete zobrazit informace, vyberte **Ano, chci Moje Add-in a nabídnout pole informace o** zaškrtávací políčko.

     Informace, které lze přidat do sady Visual Studio **o** dialogové okno obsahuje číslo verze, podrobnosti o podpoře, data o licenci a tak dále.

15. Zvolte **Další**.

16. Možnosti, které jste vybrali, se zobrazí na **Souhrn** stránky pro vás k posouzení. Pokud budete spokojeni, zvolte **Dokončit** vytvořit doplněk. Pokud chcete něco změnit, vyberte **zpět** tlačítko.

     Vytvoří se nové řešení a projektu a soubor Connect.cs pro nové doplněk se zobrazí v editoru kódu.

     Soubor Connect.cs přidáte kód, po následující postup, který vytvoří uživatelský ovládací prvek, který se odkazuje tento projekt WebPerfTestResultsViewerAddin.

 Po doplňku vytvoření, je nutné zaregistrovat ji pomocí sady Visual Studio před aktivací v **Add-In správce**. Můžete to provést pomocí souboru XML, který má příponu názvu souboru .addin.

 Soubor .addin popisuje informace, které sada Visual Studio vyžaduje zobrazíte doplněk v **Add-In správce**. Při spuštění sady Visual Studio se hledá v umístění souboru .addin pro všechny soubory k dispozici .addin. Když najde některý, načte soubor XML a poskytuje **Add-In správce** informace, které vyžaduje spuštění v doplňku po klepnutí.

 Při vytváření v pomocí průvodce Add-In, vytvoří se soubor .addin automaticky.

### <a name="add-in-file-locations"></a>Umístění souborů doplňku

Dvě kopie souboru .addin automaticky vytváří průvodce Add-In následujícím způsobem:

|**. Umístění souboru doplněk**|**Popis**|
|------------------------------|----------------------------|---------------------|
|Kořenové složce projektu|Použít pro nasazení projektu doplňku. Zahrnutý v projektu pro snadné úpravy a má místní cestu pro nasazení XCopy stylu.|
|Složky doplňků|Používá pro spuštění v doplňku v prostředí ladění. Vždy by měla odkazovat na výstupní cesta aktuální konfigurace sestavení.|

## <a name="create-a-windows-form-control-library-project"></a>Vytvoření projektu knihovny ovládacího prvku formuláře Windows

Doplněk sady Visual Studio vytvořili v předchozím postupu odkazuje na projekt knihovny ovládacích prvků Windows Forms k vytvoření instance <xref:System.Windows.Forms.UserControl> třídy.

### <a name="to-create-a-control-to-be-used-in-the-web-test-results-viewer"></a>Vytvoření ovládacího prvku pro použití v prohlížeč výsledků testu webu

1.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení, zvolte **přidat** a pak vyberte **nový projekt**.

     **Nový projekt** se zobrazí dialogové okno.

2.  V části **nainstalovaných šablonách**, rozbalte položku **buď jazyka Visual Basic** nebo **Visual C#** a vyberte **Windows**.

    > [!NOTE]
    > Toto téma používá Visual C# pro ukázkový kód.

3.  V seznamu šablon, vyberte **knihovny ovládacích prvků Windows Forms**.

4.  V části **název**, zadejte název pro doplněk. Například **WebPerfTestResultsViewerControl**.

5.  Zvolte **OK**.

     Windows forms ovládací prvek knihovna projekt, který WebPerfTestResultsViewerControl je přidaný do Průzkumníka řešení a UserControl1.cs se zobrazí v režimu návrhu.

6.  Ze sady nástrojů, přetáhněte <xref:System.Windows.Forms.DataGridView> na plochu userControl1.

7.  Klikněte na tlačítko glyfy značky akce (![inteligentní značky glyfy](../test/media/vs_winformsmttagglyph.gif)) v pravém horním rohu <xref:System.Windows.Forms.DataGridView> a postupujte podle těchto kroků:

    1.  Zvolte **ukotvení v nadřazený kontejner**.

    2.  Zrušte zaškrtnutí políček u **povolit přidání**, **povolit úpravy**, **Povolit odstraňování** a **povolení změny pořadí sloupců**.

    3.  Zvolte **přidat sloupec**.

         **Přidat sloupec** se zobrazí dialogové okno.

    4.  V **typ** rozevíracího seznamu vyberte **DataGridViewTextBoxColumn**.

    5.  Odstraňte text "Column1" v **text záhlaví**.

    6.  Zvolte **přidat**.

    7.  Zvolte **Zavřít**.

8.  V okně vlastností změňte **(název)** vlastnost <xref:System.Windows.Forms.DataGridView> k **resultControlDataGridView**.

9. Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **kód zobrazení**.

     Soubor UserControl1.cs se zobrazí v editoru kódu.

10. Změňte název vytvořenou instanci <xref:System.Windows.Forms.UserControl> třídy z UserContro1 resultControl:

    ```csharp
    namespace WebPerfTestResultsViewerControl
    {
        public partial class resultControl : UserControl
        {
            public resultControl()
            {
                InitializeComponent();
            }
    ```

     V dalším postupu přidáte kód do souboru Connect.cs WebPerfTestResultsViewerAddin projektu, který bude odkazovat na třídu resultControl.

     Budete přidávat další kód do souboru Connect.cs později.

## <a name="add-code-to-the-webperftestresultsvieweraddin"></a>Přidejte do WebPerfTestResultsViewerAddin kód

### <a name="to-add-code-to-the-visual-studio-add-in-to-extend-the-web-test-results-viewer"></a>Chcete-li přidat kód pro Visual Studio Add-in rozšířit prohlížeč výsledků testu webu

1.  V Průzkumníku řešení klikněte pravým tlačítkem myši **odkazy** uzlu v WebPerfTestResultsViewerAddin projekt a vyberte **přidat odkaz na**.

2.  V **přidat odkaz na** dialogovém okně vyberte **.NET** kartě.

3.  Přejděte dolů a vyberte **Microsoft.VisualStudio.QualityTools.WebTestFramework** a **System.Windows.Forms**.

4.  Zvolte **OK**.

5.  Klikněte pravým tlačítkem myši **odkazy** uzel znovu a vyberte možnost **přidat odkaz na**.

6.  V **přidat odkaz na** dialogovém okně vyberte **Procházet** kartě.

7.  Vyberte z rozevírací nabídky pro **Hledat v** , přejděte na % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies, vyberte Microsoft.VisualStudio.QualityTools.LoadTestPackage.dll soubor.

8.  Zvolte **OK**.

9. Klikněte pravým tlačítkem na uzel projektu WebPerfTestResultsViewerAddin a vyberte **přidat odkaz na**.

10. V **přidat odkaz na** dialogovém okně vyberte **projekty** kartě.

11. V části **název projektu**, vyberte **WebPerfTestResultsViewerControl** projektu a zvolte **OK**.

12. Pokud není soubor Connect.cs stále otevřen v Průzkumníku řešení, klikněte pravým tlačítkem **Connect.cs** v projektu WebPerfTestResultsViewerAddin soubor a vyberte **kód zobrazení**.

13. V souboru Connect.cs přidejte následující příkazy Using:

    ```csharp
    using System.IO;
    using System.Windows.Forms;
    using System.Collections.Generic;
    using Microsoft.VisualStudio.TestTools.LoadTesting;
    using Microsoft.VisualStudio.TestTools.WebTesting;
    using WebPerfTestResultsViewerControl;
    ```

14. Posuňte se dolů Connect.cs souboru. Je nutné přidat seznam identifikátory GUID pro <xref:System.Windows.Forms.UserControl> v případě, že více než jednu instanci prohlížeč výsledků testu výkonnosti webu je otevřený. Přidáte později kód, který používá tento seznam.

     Druhý seznam řetězec se používá v metodě OnDiscconection, který bude později kódu.

    ```csharp
    private DTE2 _applicationObject;
    private AddIn _addInInstance;

    private Dictionary<Guid, List<UserControl>> m_controls = new Dictionary<Guid, List<UserControl>>();        private List<string> temporaryFilePaths = new List<string>();
    ```

15. Soubor Connect.cs vytvoří instanci třídy s názvem připojení z <xref:Extensibility.IDTExtensibility2> třídy a také obsahuje některé metody pro implementaci doplňku pro Visual Studio. Jednu z metod je OnConnection metodu, která obdrží oznámení, že doplněk je právě načítán. Třída LoadTestPackageExt v metodě OnConnection, použije k vytvoření vašeho balíčku rozšíření pro prohlížeč výsledků testu výkonnosti webu. Přidejte následující kód do metody OnConnection:

    ```csharp
    public void OnConnection(object application, ext_ConnectMode connectMode, object addInInst, ref Array custom)
                {
                _applicationObject = (DTE2)application;
                _addInInstance = (AddIn)addInInst;

                // Create a load test packge extensibility class.            LoadTestPackageExt loadTestPackageExt = _applicationObject.GetObject("Microsoft.VisualStudio.TestTools.LoadTesting.LoadTestPackageExt") as LoadTestPackageExt;            // Process open windows.            foreach (WebTestResultViewer webTestResultViewer in loadTestPackageExt.WebTestResultViewerExt.ResultWindows)            {                WindowCreated(webTestResultViewer);            }            // Create event handlers.            loadTestPackageExt.WebTestResultViewerExt.WindowCreated += new EventHandler<WebTestResultViewerExt.WindowCreatedEventArgs>(WebTestResultViewerExt_WindowCreated);            loadTestPackageExt.WebTestResultViewerExt.WindowClosed += new EventHandler<WebTestResultViewerExt.WindowClosedEventArgs>(WebTesResultViewer_WindowClosed);            loadTestPackageExt.WebTestResultViewerExt.SelectionChanged += new EventHandler<WebTestResultViewerExt.SelectionChangedEventArgs>(WebTestResultViewer_SelectedChanged);
            }
    ```

16. Přidejte následující kód do třídy připojit k vytvoření metodu WebTestResultViewerExt_WindowCreated pro obslužné rutiny události loadTestPackageExt.WebTestResultViewerExt.WindowCreated jste přidali v metodě OnConnection a metodu WindowCreated, volání metody WebTestResultViewerExt_WindowCreated.

    ```csharp
            void WebTestResultViewerExt_WindowCreated(object sender, WebTestResultViewerExt.WindowCreatedEventArgs e)
            {
                // New control added to new result viewer window.
                WindowCreated(e.WebTestResultViewer);
            }

    private void WindowCreated(WebTestResultViewer viewer)        {            // Instantiate an instance of the resultControl referenced in the WebPerfTestResultsViewerControl project.
                resultControl resultControl = new resultControl();            // Add to the dictionary of open playback windows.            System.Diagnostics.Debug.Assert(!m_controls.ContainsKey(viewer.TestResultId));            List<UserControl> userControls = new List<UserControl>();            userControls.Add(resultControl);            // Add Guid to the m_control List to manage Result viewers and controls.            m_controls.Add(viewer.TestResultId, userControls);            // Add tabs to the playback control.            resultControl.Dock = DockStyle.Fill;            viewer.AddResultPage(new Guid(), "Sample", resultControl);        }
    ```

17. Přidejte následující kód do třídy připojit k vytvoření metodu WebTestResultViewer_SelectedChanged pro obslužné rutiny události loadTestPackageExt.WebTestResultViewerExt.SelectionChanged, které jste přidali v metodě OnConnection:

    ```csharp
    void WebTestResultViewer_SelectedChanged(object sender, WebTestResultViewerExt.SelectionChangedEventArgs e)
    {
        foreach (UserControl userControl in m_controls[e.TestResultId])            {                // Update the userControl in each result viewer.                resultControl resultControl = userControl as resultControl;                if (resultControl != null)                    // Call the resultControl's Update method (This will be added in the next procedure).                    resultControl.Update(e.WebTestRequestResult);            }
    }
    ```

18. Přidejte následující kód do třídy připojit k vytvoření metodu WebTesResultViewer_WindowClosed pro obslužnou rutinu události pro loadTestPackageExt.WebTestResultViewerExt.WindowClosed, které jste přidali v metodě OnConnection:

    ```csharp
    void WebTesResultViewer_WindowClosed(object sender, WebTestResultViewerExt.WindowClosedEventArgs e)
    {
        if (m_controls.ContainsKey(e.WebTestResultViewer.TestResultId))
        {
            m_controls.Remove(e.WebTestResultViewer.TestResultId);
        }
    }
    ```

     Teď, když kód dokončení pro sadě Visual Studio add-in, je nutné přidat metodu aktualizace pro resultControl v v WebPerfTestResultsViewerControl projektu.

## <a name="add-code-to-the-webperftestresultsviewercontrol"></a>Přidejte do WebPerfTestResultsViewerControl kód

### <a name="to-add-code-to-the-user-control"></a>Přidání kódu do uživatelského ovládacího prvku

1.  V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu WebPerfTestResultsViewerControl a vyberte **vlastnosti**.

2.  Vyberte **aplikace** a pak klikněte na příkaz **cílové rozhraní** rozevíracího seznamu a vyberte **rozhraní .NET Framework 4** a zavřete vlastnosti.

     Je to vyžadováno kvůli podpoře odkazy na knihovnu DLL, které jsou potřebné pro rozšíření prohlížeč výsledků testu výkonnosti webu.

3.  V Průzkumníku řešení v projektu WebPerfTestResultsViewerControl, klikněte pravým tlačítkem myši **odkazy** uzel a vyberte možnost **přidat odkaz na**.

4.  V **přidat odkaz na** dialogové okno, klikněte na tlačítko **.NET** kartě.

5.  Přejděte dolů a vyberte **Microsoft.VisualStudio.QualityTools.WebTestFramework**.

6.  Zvolte **OK**.

7.  V souboru UserControl1.cs přidejte následující příkazy Using:

    ```csharp
    using Microsoft.VisualStudio.TestTools.WebTesting;
    using Microsoft.VisualStudio.TestTools.WebTesting.Rules;
    ```

8.  Přidejte metodu aktualizace, která je volána a předat WebTestRequestResult z metody WebPerfTestResultsViewerAddin WebTestResultViewer_SelectedChanged v souboru Connect.cs. Metoda aktualizace naplní ovládacího prvku DataGridView s různé vlastnosti do ní předán v WebTestRequestResult.

    ```csharp
    public void Update(WebTestRequestResult WebTestResults)
            {
                // Clear the DataGridView when a request is selected.
                resultControlDataGridView.Rows.Clear();
                // Populate the DataGridControl with properties from the WebTestResults.
                this.resultControlDataGridView.Rows.Add("Request: " + WebTestResults.Request.Url.ToString());
                this.resultControlDataGridView.Rows.Add("Response: " + WebTestResults.Response.ResponseUri.ToString());
                foreach (RuleResult ruleResult in WebTestResults.ExtractionRuleResults)
                {
                    this.resultControlDataGridView.Rows.Add("Extraction rule results: " + ruleResult.Message.ToString());
                }
                foreach (RuleResult ruleResult in WebTestResults.ValidationRuleResults)
                {
                    this.resultControlDataGridView.Rows.Add("Validation rule results: " + ruleResult.Message.ToString());
                }
                foreach (WebTestError webTestError in WebTestResults.Errors)
                {
                    this.resultControlDataGridView.Rows.Add("Error: " + webTestError.ErrorType.ToString() + " " + webTestError.ErrorSubtype.ToString() + " " + webTestError.ExceptionText.ToString());
                }
            }
    ```

## <a name="build-the-webperftestresultsvieweraddin-solution"></a>Sestavte řešení WebPerfTestResultsViewerAddin

### <a name="to-build-the-solution"></a>K sestavení řešení

-   Na **sestavení** nabídce vyberte možnost **sestavit řešení**.

## <a name="register-the-webperftestresultsvieweraddin-add-in"></a>Zaregistrujte doplněk WebPerfTestResultsViewerAddin

### <a name="to-register-the-add-in-using-the-add-in-manager"></a>Zaregistrujte doplněk správci Add-in

1.  Na **nástroje** nabídce vyberte možnost **Add-in správce**.

2.  **Add-in správce** se zobrazí dialogové okno.

3.  Zaškrtněte políčko pro doplněk WebPerfTestResultsViewerAddin v **Add in k dispozici** sloupce a zrušte zaškrtnutí políček pod **spuštění** a **příkazového řádku**sloupce.

4.  Zvolte **OK**.

## <a name="run-the-web-performance-test-using-the-build-the-webperftestresultsvieweraddin-add-in"></a>Spuštění testu výkonnosti webu pomocí doplňku WebPerfTestResultsViewerAddin sestavení

### <a name="to-run-the-new-vs-add-in-for-the-web-test-results-viewer"></a>Spuštění nového VS doplněk pro prohlížeč výsledků testu webu

1.  Spuštění testu výkonnosti webu a zobrazí se WebPerfTestResultsViewerAddin doplňku novou kartu s názvem Ukázka zobrazí v prohlížeč pro výsledky testů výkonnosti webu.

2.  Vyberte kartu zobrazíte vlastnosti uvedené v ovládacím prvku DataGridView.

## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework

Pro zlepšení zabezpečení tak, že zabrání automaticky aktivace škodlivý doplňky Visual Studio poskytuje nastavení v **možnosti nástrojů** stránku s názvem **přidat/makra zabezpečení**.

Kromě toho tato stránka Možnosti můžete zadat složky, ve kterých vyhledává Visual Studio. Doplněk registrační soubory. To zvyšuje zabezpečení, protože umožňuje omezit umístění kde. Doplněk registrace soubory mohou být čteny. To pomáhá zabránit škodlivý. Doplněk soubory z neúmyslně používá.

 **Nastavení zabezpečení doplňku**

 Nastavení na stránce Možnosti pro doplněk zabezpečení jsou následující:

-   **Umožňuje přidat součásti načíst.** Ve výchozím nastavení je zaškrtnuto. Při výběru doplňky mohou načíst v sadě Visual Studio. Pokud není vybrána, doplňky nesmějí načítání v sadě Visual Studio.

-   **Umožňuje přidat součásti načíst z adresy URL.** Není vybrán ve výchozím nastavení. Při výběru doplňky mohou být načten z externích webových stránek. Pokud není vybrána, vzdálené doplňky nesmějí načítání v sadě Visual Studio. Pokud z nějakého důvodu nelze načíst doplněk, pak ho nelze načíst z webu. Toto nastavení řídí pouze načítání knihovnu DLL. Na. Doplněk registrační soubory musí být vždy umístěny v místním systému.

## <a name="see-also"></a>Viz také:

- <xref:System.Windows.Forms.UserControl>
- <xref:Microsoft.VisualStudio.TestTools.LoadTesting>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules>
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.DataGrid>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)