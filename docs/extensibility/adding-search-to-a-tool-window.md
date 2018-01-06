---
title: "Přidání hledání do okno nástroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tool windows, adding search
ms.assetid: f78c4892-8060-49c4-8ecd-4360f1b4d133
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d37956c01cbbebbe29d7506cf5eacd9456b3bbc1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="adding-search-to-a-tool-window"></a>Přidání vyhledávání okno nástroje
Při vytváření nebo aktualizujte okno nástroje ve vašem rozšíření, můžete přidat stejné funkce vyhledávání, který se zobrazí někde v sadě Visual Studio. Tato funkce zahrnuje následující funkce:  
  
-   Vyhledávací pole vždy umístěnou ve vlastní oblast panelu nástrojů.  
  
-   Indikátor průběhu, který je jako překryvný obrázek na vyhledávací pole samo.  
  
-   Umožňuje zobrazit výsledky při zadávání jednotlivých znaků (rychlé vyhledávání) nebo pouze po vybrání klávesy Enter (hledání na vyžádání).  
  
-   Seznam, který ukazuje podmínky, pro které dokončení naposledy hledání.  
  
-   Umožňuje filtrovat hledání podle konkrétních polí nebo aspektů cíle pro vyhledávání.  
  
 Podle tohoto návodu se dozvíte, jak provádět následující úlohy:  
  
1.  Vytvoření projektu VSPackage.  
  
2.  Vytvořte okno nástroje, který obsahuje UserControl s textové pole jen pro čtení.  
  
3.  Přidejte vyhledávacího pole v okně nástroje.  
  
4.  Přidání implementace hledání.  
  
5.  Povolte rychlé vyhledávání a zobrazení indikátor průběhu.  
  
6.  Přidat **malá a velká písmena** možnost.  
  
7.  Přidat **hledat pouze i řádky** filtru.  
  
## <a name="to-create-a-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Vytvoření projektu VSIX s názvem `TestToolWindowSearch` s okno nástroj s názvem **TestSearch**. Pokud potřebujete pomoc, to, najdete v části [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="to-create-a-tool-window"></a>Chcete-li vytvořit okno nástroje  
  
1.  V `TestToolWindowSearch` projektu, otevřete soubor TestSearchControl.xaml.  
  
2.  Nahradit existující `<StackPanel>` blok s následující blok, který přidá jen pro čtení <xref:System.Windows.Controls.TextBox> k <xref:System.Windows.Controls.UserControl> v okně nástroje.  
  
    ```xaml  
    <StackPanel Orientation="Vertical">  
        <TextBox Name="resultsTextBox" Height="800.0"  
            Width="800.0"  
            IsReadOnly="True">  
        </TextBox>  
    </StackPanel>  
    ```  
  
3.  V souboru TestSearchControl.xaml.cs, přidejte následující příkaz using:  
  
    ```csharp  
    using System.Text;  
    ```  
  
4.  Odeberte `button1_Click()` metoda.  
  
     V **TestSearchControl** třídy, přidejte následující kód.  
  
     Tento kód přidá veřejné <xref:System.Windows.Controls.TextBox> vlastnost s názvem **SearchResultsTextBox** a veřejné řetězec vlastnost s názvem **SearchContent**. V konstruktoru SearchResultsTextBox nastavena do textového pole a SearchContent je inicializováno sadu řetězce s položkami oddělenými nový řádek. Obsah textové pole je také inicializován sadu řetězce.  
  
    ```csharp  
    public partial class TestSearchControl : UserControl  
    {  
        public TextBox SearchResultsTextBox { get; set; }  
        public string SearchContent { get; set; }  
  
        public TestSearchControl()  
        {  
            InitializeComponent();  
  
            this.SearchResultsTextBox = resultsTextBox;  
            this.SearchContent = BuildContent();  
  
            this.SearchResultsTextBox.Text = this.SearchContent;  
        }  
  
        private string BuildContent()  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendLine("1 go");  
            sb.AppendLine("2 good");  
            sb.AppendLine("3 Go");  
            sb.AppendLine("4 Good");  
            sb.AppendLine("5 goodbye");  
            sb.AppendLine("6 Goodbye");  
  
            return sb.ToString();  
        }  
    }  
    ```  
  
     [!code-csharp[ToolWindowSearch#1](../extensibility/codesnippet/CSharp/adding-search-to-a-tool-window_1.cs)]
     [!code-vb[ToolWindowSearch#1](../extensibility/codesnippet/VisualBasic/adding-search-to-a-tool-window_1.vb)]  
  
5.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci sady Visual Studio.  
  
6.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **TestSearch**.  
  
     Zobrazí se okno nástroj, ale ještě ovládacího prvku hledání nezobrazí.  
  
## <a name="to-add-a-search-box-to-the-tool-window"></a>Chcete-li přidat vyhledávacího pole v okně nástroje  
  
1.  V souboru TestSearch.cs, přidejte následující kód, který `TestSearch` třídy. Kód přepíše <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> vlastnost tak, aby vrátil přistupující objekt get `true`.  
  
     Pokud chcete povolit vyhledávání, je nutné přepsat <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> vlastnost. <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> Třída implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch> a poskytuje výchozí implementaci, která neumožňuje vyhledávání.  
  
    ```csharp  
    public override bool SearchEnabled  
    {  
        get { return true; }  
    }  
    ```  
  
2.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
3.  V experimentální instanci sady Visual Studio, otevřete **TestSearch**.  
  
     V horní části okna nástroje, zobrazí se ovládacího prvku vyhledávání s **vyhledávání** ikona zvětšení, přehledné a vodoznak. Vyhledávání však není ještě fungovat, protože proces vyhledávání ještě nebyla implementována.  
  
## <a name="to-add-the-search-implementation"></a>Chcete-li přidat implementace hledání  
 Když povolíte vyhledávání na <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>, jako v předchozím postupu, vytvoří okno nástroje vyhledávání hostitele. Tento hostitel nastavit a spravovat vyhledávání procesů, které vždy odehrávat na vlákna na pozadí. Protože <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> třída spravuje vytváření vyhledávání hostitelů a nastavení hledání, třeba pouze vytvořit úlohu vyhledávání a zadejte metodu search. Proces vyhledávání proběhne vlákna na pozadí a volání do ovládacího prvku okno nástroj, ke kterým došlo u vlákna uživatelského rozhraní. Proto je nutné použít <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> metoda ke správě všech volání, které provedete v práci s ovládacím prvkem.  
  
1.  V souboru TestSearch.cs, přidejte následující `using` příkazy:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Runtime.InteropServices;  
    using System.Text;  
    using System.Windows.Controls;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
2.  V `TestSearch` třídy, přidejte následující kód, který provede následující akce:  
  
    -   Přepsání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> metodu pro vytvoření úlohy vyhledávání.  
  
    -   Přepsání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> metodou pro obnovení stav textového pole. Tato metoda je volána, když uživatel zruší úlohu vyhledávání a když uživatel nastaví nebo unsets možností nebo filtry. Obě <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> se nazývají ve vlákně UI. Proto nemusíte přístup textového pole prostřednictvím <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> metoda.  
  
    -   Vytvoří třídu, která je s názvem `TestSearchTask` který dědí z <xref:Microsoft.VisualStudio.Shell.VsSearchTask>, který poskytuje výchozí implementaci třídy <xref:Microsoft.VisualStudio.Shell.Interop.IVsSearchTask>.  
  
         V `TestSearchTask`, konstruktor nastaví soukromé pole, který odkazuje na panel nástrojů. Pokud chcete zadat metodu search, můžete přepsat <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> a <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStopSearch%2A> metody. <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> Metoda je, kde můžete implementovat proces vyhledávání. Tento proces zahrnuje provádění vyhledávání, zobrazování výsledků vyhledávání do textového pole a volání základní třída implementace této metody informuje, že po dokončení vyhledávání.  
  
    ```csharp  
    public override IVsSearchTask CreateSearch(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback)  
    {  
        if (pSearchQuery == null || pSearchCallback == null)  
            return null;  
         return new TestSearchTask(dwCookie, pSearchQuery, pSearchCallback, this);  
    }  
  
    public override void ClearSearch()  
    {  
        TestSearchControl control = (TestSearchControl)this.Content;  
        control.SearchResultsTextBox.Text = control.SearchContent;  
    }  
  
    internal class TestSearchTask : VsSearchTask  
    {  
        private TestSearch m_toolWindow;  
  
        public TestSearchTask(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback, TestSearch toolwindow)  
            : base(dwCookie, pSearchQuery, pSearchCallback)  
        {  
            m_toolWindow = toolwindow;  
        }  
  
        protected override void OnStartSearch()  
        {  
            // Use the original content of the text box as the target of the search.   
            var separator = new string[] { Environment.NewLine };  
            TestSearchControl control = (TestSearchControl)m_toolWindow.Content;  
            string[] contentArr = control.SearchContent.Split(separator, StringSplitOptions.None);  
  
            // Get the search option.   
            bool matchCase = false;  
            // matchCase = m_toolWindow.MatchCaseOption.Value;   
  
                // Set variables that are used in the finally block.  
                StringBuilder sb = new StringBuilder("");  
                uint resultCount = 0;  
                this.ErrorCode = VSConstants.S_OK;  
  
                try  
                {  
                    string searchString = this.SearchQuery.SearchString;  
  
                    // Determine the results.   
                    uint progress = 0;  
                    foreach (string line in contentArr)  
                    {  
                        if (matchCase == true)  
                        {  
                            if (line.Contains(searchString))  
                            {  
                                sb.AppendLine(line);  
                                resultCount++;  
                            }  
                        }  
                        else  
                            {  
                                if (line.ToLower().Contains(searchString.ToLower()))  
                                {  
                                    sb.AppendLine(line);  
                                    resultCount++;  
                                }  
                            }  
  
                            // SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));   
  
                            // Uncomment the following line to demonstrate the progress bar.   
                            // System.Threading.Thread.Sleep(100);  
                        }  
                    }  
                    catch (Exception e)  
                    {  
                        this.ErrorCode = VSConstants.E_FAIL;  
                    }  
                    finally  
                    {  
                        ThreadHelper.Generic.Invoke(() =>  
                        { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
                        this.SearchResults = resultCount;  
                    }  
  
            // Call the implementation of this method in the base class.   
            // This sets the task status to complete and reports task completion.   
            base.OnStartSearch();  
        }  
  
        protected override void OnStopSearch()  
        {  
            this.SearchResults = 0;  
        }  
    }  
    ```  
  
3.  Testování vaší implementace hledání podle následujících kroků:  
  
    1.  Projekt znovu sestavte a spusťte ladění.  
  
    2.  V experimentální instanci sady Visual Studio znovu otevřete okno nástroje, zadejte v okně hledání některé hledaný text a stiskněte ENTER.  
  
         By se zobrazit správné výsledky.  
  
## <a name="to-customize-the-search-behavior"></a>Chcete-li přizpůsobit chování vyhledávání  
 Změnou nastavení vyhledávání můžete nastavit různé změny v tom, jak se zobrazí ovládacího prvku vyhledávání a jak se provádí vyhledávání. Můžete například změnit vodoznak (výchozí text, který se do vyhledávacího pole), minimální a maximální šířku ovládacího prvku vyhledávání a zda se zobrazí indikátor průběhu. Můžete také změnit bod, ve které výsledky hledání spuštění (na vyžádání nebo okamžité hledání) a jestli se má zobrazit seznam termínů, pro které jste nedávno vyhledávat. Úplný seznam nastavení najdete <xref:Microsoft.VisualStudio.PlatformUI.SearchSettingsDataSource> třídy.  
  
1.  V souboru TestSearch.cs, přidejte následující kód, který `TestSearch` třídy. Tento kód umožňuje rychlé vyhledávání místo vyhledávání na vyžádání (což znamená, že uživatel nemá k klepněte na tlačítko zadat). Kód přepíše `ProvideSearchSettings` metoda v `TestSearch` třídy, která je potřeba změnit výchozí nastavení.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
            (uint)VSSEARCHSTARTTYPE.SST_INSTANT);}  
    ```  
  
2.  Testování nové nastavení znovu sestavit řešení a restartováním ladicího programu.  
  
     Výsledky hledání se zobrazí pokaždé, když zadáte znak do vyhledávacího pole.  
  
3.  V `ProvideSearchSettings` metoda, přidejte následující řádek, který umožňuje zobrazení indikátor průběhu.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
             (uint)VSSEARCHSTARTTYPE.SST_INSTANT);  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchProgressTypeProperty.Name,   
             (uint)VSSEARCHPROGRESSTYPE.SPT_DETERMINATE);  
    }  
    ```  
  
     U indikátor průběhu, který se zobrazí musí být uvedena průběh. Chcete-li hlášení průběhu, zrušte komentář u následující kód do `OnStartSearch` metodu `TestSearchTask` – třída:  
  
    ```csharp  
    SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
    ```  
  
4.  Zpomalit zpracování dostatek který průběh pruh je viditelná, zrušte komentář u následujícího řádku `OnStartSearch` metodu `TestSearchTask` třídy:  
  
    ```csharp  
    System.Threading.Thread.Sleep(100);  
    ```  
  
5.  Znovu sestavit řešení a spustit na debugb otestujte nové nastavení.  
  
     Indikátor průběhu se zobrazí v okně hledání (jako modré řádku pod textového pole pro vyhledávání) pokaždé, když provést vyhledávání.  
  
## <a name="to-enable-users-to-refine-their-searches"></a>Chcete-li povolit uživatelům upřesnit jejich hledání  
 Můžete povolit uživatelům upřesnit jejich hledání prostřednictvím možnosti, jako například **malá a velká písmena** nebo **celá slova**. Možnosti může být logická hodnota, která se zobrazí jako zaškrtávací políčka nebo příkazy, které se zobrazují jako tlačítka. V tomto návodu vytvoříte logickou možnost.  
  
1.  V souboru TestSearch.cs, přidejte následující kód, který `TestSearch` třídy. Kód přepíše `SearchOptionsEnum` metoda, která umožňuje vyhledávání implementace ke zjištění, zda je daný možnost zapnout nebo vypnout. Kód v `SearchOptionsEnum` přidá možnost malá a velká písmena k <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumWindowSearchOptions> enumerátor. Je také k dispozici jako možnost malá a velká písmena `MatchCaseOption` vlastnost.  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
        {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
2.  V `TestSearchTask` třída, zrušte komentář u matchCase řádku `OnStartSearch` metoda:  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
         {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
3.  Testovací možnost:  
  
    1.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
    2.  V okně nástroje zvolte šipka dolů na pravé straně textového pole.  
  
         **Malá a velká písmena** se zobrazí zaškrtávací políčko.  
  
    3.  Vyberte **malá a velká písmena** zaškrtněte políčko a potom proveďte některé hledání.  
  
## <a name="to-add-a-search-filter"></a>Chcete-li přidat vyhledávací filtr  
 Můžete přidat filtry hledání, které umožňují uživatelům upřesnit sadu hledání cíle. Například můžete filtrovat soubory v Průzkumníku souborů podle data, na kterých byly naposledy upraveny a jejich přípony názvů souborů. V tomto návodu přidáte filtr i pouze pro řádky. Když uživatel vybere tento filtr, přidá hostitele hledání řetězce, které zadáte do vyhledávací dotaz. Pak můžete identifikovat tyto řetězce uvnitř metodu vyhledávání a filtrování cíle pro vyhledávání odpovídajícím způsobem.  
  
1.  V souboru TestSearch.cs, přidejte následující kód, který `TestSearch` třídy. Kód implementuje `SearchFiltersEnum` přidáním <xref:Microsoft.VisualStudio.PlatformUI.WindowSearchSimpleFilter> určující filtrovat výsledky hledání tak, aby se zobrazí pouze i řádky.  
  
    ```csharp  
    public override IVsEnumWindowSearchFilters SearchFiltersEnum  
    {  
        get  
        {  
            List<IVsWindowSearchFilter> list = new List<IVsWindowSearchFilter>();  
            list.Add(new WindowSearchSimpleFilter("Search even lines only", "Search even lines only", "lines", "even"));  
            return new WindowSearchFilterEnumerator(list) as IVsEnumWindowSearchFilters;  
        }  
    }  
  
    ```  
  
     Teď ovládacího prvku vyhledávání zobrazí vyhledávací filtr `Search even lines only`. Když uživatel vybere filtru řetězec `lines:"even"` se zobrazí do vyhledávacího pole. Další kritéria vyhledávání se může zobrazit ve stejnou dobu jako filtr. Hledání řetězců se mohou objevit před filtru po filtr, nebo obojí.  
  
2.  V souboru TestSearch.cs, přidejte následující metody, které `TestSearchTask` třída, která je v `TestSearch` třídy. Tyto metody podporují `OnStartSearch` metodu, která budete upravovat v dalším kroku.  
  
    ```csharp  
    private string RemoveFromString(string origString, string stringToRemove)  
    {  
        int index = origString.IndexOf(stringToRemove);  
        if (index == -1)  
            return origString;  
        else   
             return (origString.Substring(0, index) + origString.Substring(index + stringToRemove.Length)).Trim();  
    }  
  
    private string[] GetEvenItems(string[] contentArr)  
    {  
        int length = contentArr.Length / 2;  
        string[] evenContentArr = new string[length];  
  
        int indexB = 0;  
        for (int index = 1; index < contentArr.Length; index += 2)  
        {  
            evenContentArr[indexB] = contentArr[index];  
            indexB++;  
        }  
  
        return evenContentArr;  
    }  
    ```  
  
3.  V `TestSearchTask` třídy, aktualizaci `OnStartSearch` metoda následujícím kódem. Tato změna aktualizuje kódu, které podporují filtru.  
  
    ```csharp  
    protected override void OnStartSearch()  
    {  
        // Use the original content of the text box as the target of the search.   
        var separator = new string[] { Environment.NewLine };  
        string[] contentArr = ((TestSearchControl)m_toolWindow.Content).SearchContent.Split(separator, StringSplitOptions.None);  
  
        // Get the search option.   
        bool matchCase = false;  
        matchCase = m_toolWindow.MatchCaseOption.Value;  
  
        // Set variables that are used in the finally block.  
        StringBuilder sb = new StringBuilder("");  
        uint resultCount = 0;  
        this.ErrorCode = VSConstants.S_OK;  
  
        try  
        {  
            string searchString = this.SearchQuery.SearchString;  
  
            // If the search string contains the filter string, filter the content array.   
            string filterString = "lines:\"even\"";  
  
            if (this.SearchQuery.SearchString.Contains(filterString))  
            {  
                // Retain only the even items in the array.  
                contentArr = GetEvenItems(contentArr);  
  
                // Remove 'lines:"even"' from the search string.  
                searchString = RemoveFromString(searchString, filterString);  
            }  
  
            // Determine the results.   
            uint progress = 0;  
            foreach (string line in contentArr)  
            {  
                if (matchCase == true)  
                {  
                    if (line.Contains(searchString))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
                else  
                {  
                    if (line.ToLower().Contains(searchString.ToLower()))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
  
                SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
  
                // Uncomment the following line to demonstrate the progress bar.   
                // System.Threading.Thread.Sleep(100);  
            }  
        }  
        catch (Exception e)  
        {  
            this.ErrorCode = VSConstants.E_FAIL;  
        }  
        finally  
        {  
            ThreadHelper.Generic.Invoke(() =>  
            { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
            this.SearchResults = resultCount;  
        }  
  
        // Call the implementation of this method in the base class.   
        // This sets the task status to complete and reports task completion.   
        base.OnStartSearch();  
    }  
    ```  
  
4.  Otestujte svůj kód.  
  
5.  Sestavte projekt a spusťte ladění. V experimentální instanci sady Visual Studio otevřete okno nástroje a klikněte na šipku dolů v prvku vyhledávání.  
  
     **Malá a velká písmena** zaškrtávací políčko a **hledat pouze i řádky** zobrazí filtru.  
  
6.  Vyberte filtr.  
  
     Do vyhledávacího pole obsahuje **řádky: "i"**, a zobrazí se následující výsledky:  
  
     Dobrý 2  
  
     4 dobré  
  
     6 dát sbohem všem  
  
7.  Odstranit `lines:"even"` do vyhledávacího pole, vyberte **malá a velká písmena** zaškrtněte políčko a potom zadejte `g` do vyhledávacího pole.  
  
     Zobrazí se následující výsledky:  
  
     přejděte 1  
  
     Dobrý 2  
  
     5 dát sbohem všem  
  
8.  Zvolte X na pravé straně vyhledávacího pole.  
  
     Hledání není zaškrtnuta, a původní obsah se zobrazí. Ale **malá a velká písmena** stále je zaškrtnuté políčko.