---
title: "Návod: Zobrazení žárovky návrhy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99e5566d-450e-4660-9bca-454e1c056a02
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 97ab32d4bfe0772d7b50ea1ca5a0b0ec143ed536
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-light-bulb-suggestions"></a>Návod: Zobrazení žárovky návrhy
Žárovek jsou ikony používané v editoru Visual Studio, které rozbalte zobrazíte sadu akcí, například opravy pro problémy se identifikovanou pomocí analyzátorů předdefinované kódu nebo refaktoring kódu.  
  
 Editorů jazyka Visual C# a Visual Basic můžete také použít kompilátoru platformu .NET ("Roslyn") k zápisu a balíček analyzátorů vlastního kódu s akcemi, které zobrazují žárovek automaticky. Další informace naleznete v tématu:  
  
-   [Postupy: Zápis C# Diagnostika a oprava kódu](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-C%23-Analyzer-and-Code-Fix)  
  
-   [Postupy: Zápis kódu oprava a Diagnostika jazyka Visual Basic](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-Visual-Basic-Analyzer-and-Code-Fix)  
  
 Další jazyky, jako je například C++ poskytují žárovek pro některé rychlé akce, jako je návrh vytvořit prázdnou implementaci této funkce.  
  
 Zde je, jak vypadá žárovky. V projektu jazyka Visual Basic a Visual C# červenou vlnovkou se zobrazí v části název proměnné při je neplatný. Když myší neplatný identifikátor, zobrazí se žárovky téměř kurzor.  
  
 ![žárovky](../extensibility/media/lightbulb.png "žárovek")  
  
 Pokud kliknete na šipku dolů ve žárovky, se zobrazí sada doporučované akce, společně s náhled vybrané akce. V tomto případě zobrazuje změny, které budou provedeny kódu, je-li provést akci.  
  
 ![žárovky preview](../extensibility/media/lightbulbpreview.png "LightBulbPreview")  
  
 Žárovek můžete zadat vlastní doporučované akce. Například je možné zadat akce, které chcete přesunout otevření složené závorky na nový řádek nebo je přesunout na konec předchozí řádek. Následující postup ukazuje, jak vytvořit žárovky, který se zobrazí na aktuální aplikace word a má dva doporučené postupy: **převést na velká písmena** a **převést na malá písmena**.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Vytvoření projektu spravovaných rozšíření Framework (MEF)  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `LightBulbTest`.  
  
2.  Přidat **Editor třídění** šablony položky do projektu. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
4.  Přidejte následující odkaz na projekt a nastavte **místní kopie** k `False`:  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
5.  Přidat nový soubor třídy a pojmenujte ji **LightBulbTest**.  
  
6.  Přidejte následující příkazy:  
  
    ```csharp  
    using System;  
    using System.Linq;  
    using System.Collections.Generic;  
    using System.Threading.Tasks;  
    using Microsoft.VisualStudio.Language.Intellisense;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Operations;  
    using Microsoft.VisualStudio.Utilities;  
    using System.ComponentModel.Composition;  
    using System.Threading;  
  
    ```  
  
## <a name="implementing-the-light-bulb-source-provider"></a>Implementace zprostředkovatele žárovky zdroje  
  
1.  V souboru třídy LightBulbTest.cs odstraní LightBulbTest třídu. Přidejte třídu s názvem **TestSuggestedActionsSourceProvider** , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>. Export s názvem **navrhované akce testu** a <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text".  
  
    ```csharp  
    [Export(typeof(ISuggestedActionsSourceProvider))]  
    [Name("Test Suggested Actions")]  
    [ContentType("text")]  
    internal class TestSuggestedActionsSourceProvider : ISuggestedActionsSourceProvider  
    ```  
  
2.  Do třídy zprostředkovatele zdroj importovat <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> a přidejte ji jako vlastnost.  
  
    ```csharp  
    [Import(typeof(ITextStructureNavigatorSelectorService))]  
    internal ITextStructureNavigatorSelectorService NavigatorService { get; set; }  
    ```  
  
3.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider.CreateSuggestedActionsSource%2A> metodu pro návrat <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource> objektu. Zdroj v další části se budeme zabývat.  
  
    ```csharp  
    public ISuggestedActionsSource CreateSuggestedActionsSource(ITextView textView, ITextBuffer textBuffer)  
    {  
        if (textBuffer == null && textView == null)  
        {  
            return null;  
        }  
        return new TestSuggestedActionsSource(this, textView, textBuffer);  
    }  
    ```  
  
## <a name="implementing-the-isuggestedactionsource"></a>Implementace ISuggestedActionSource  
 Navrhovaná akce zdroj je zodpovědná za shromažďování sadu doporučované akce a jejich přidáním v pravém kontextu. V takovém případě kontextu je aktuální aplikace word a doporučované akce jsou **UpperCaseSuggestedAction** a **LowerCaseSuggestedAction**, který se budeme zabývat v následující části.  
  
1.  Přidání třídy **TestSuggestedActionsSource** , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>.  
  
    ```csharp  
    internal class TestSuggestedActionsSource : ISuggestedActionsSource  
    ```  
  
2.  Přidejte soukromé pole jen pro čtení pro poskytovatele správy zdrojového navrhovanou akci, textovou vyrovnávací paměť a textového zobrazení.  
  
    ```csharp  
    private readonly TestSuggestedActionsSourceProvider m_factory;  
    private readonly ITextBuffer m_textBuffer;  
    private readonly ITextView m_textView;  
    ```  
  
3.  Přidejte konstruktor, který nastaví privátní pole.  
  
    ```csharp  
    public TestSuggestedActionsSource(TestSuggestedActionsSourceProvider testSuggestedActionsSourceProvider, ITextView textView, ITextBuffer textBuffer)  
    {  
        m_factory = testSuggestedActionsSourceProvider;  
        m_textBuffer = textBuffer;  
        m_textView = textView;  
    }  
    ```  
  
4.  Přidejte soukromá metoda, která vrátí word, který je aktuálně kurzor. Následující metodu vypadá na aktuální pozici kurzoru a požádá Navigátor struktura text pro rozsah aplikace word. Pokud je kurzor na slova, <xref:Microsoft.VisualStudio.Text.Operations.TextExtent> je vrácený v výstupní parametr; jinak hodnota `out` parametr `null` a vrátí metodu `false`.  
  
    ```csharp  
    private bool TryGetWordUnderCaret(out TextExtent wordExtent)  
    {  
        ITextCaret caret = m_textView.Caret;  
        SnapshotPoint point;  
  
        if (caret.Position.BufferPosition > 0)  
        {  
            point = caret.Position.BufferPosition - 1;  
        }  
        else  
        {  
            wordExtent = default(TextExtent);  
            return false;  
        }  
  
        ITextStructureNavigator navigator = m_factory.NavigatorService.GetTextStructureNavigator(m_textBuffer);  
  
        wordExtent = navigator.GetExtentOfWord(point);  
        return true;  
    }  
    ```  
  
5.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource.HasSuggestedActionsAsync%2A> metoda. Editor volá tuto metodu a zjistěte, jestli se má zobrazit žárovky. Toto volání přišla velmi často, například vždy, když ukazatel přesune z jeden řádek na jiný, nebo když ukazatel myši nachází vlnovku chyby. Je asynchronní, aby bylo možné povolit další operace uživatelského rozhraní pro přenos, když tato metoda funguje. Ve většině případů tuto metodu je potřeba provést některé analýzy a analýzy aktuálního řádku takže zpracování může trvat delší dobu.  
  
     V našem implementaci asynchronně získá <xref:Microsoft.VisualStudio.Text.Operations.TextExtent> a určuje, zda je v rozsahu tedy důležité, zda má nějaký text jiné než prázdné znaky.  
  
    ```csharp  
    public Task<bool> HasSuggestedActionsAsync(ISuggestedActionCategorySet requestedActionCategories, SnapshotSpan range, CancellationToken cancellationToken)  
    {  
        return Task.Factory.StartNew(() =>  
        {  
            TextExtent extent;  
            if (TryGetWordUnderCaret(out extent))  
            {  
                // don't display the action if the extent has whitespace  
                return extent.IsSignificant;  
              }  
            return false;  
        });  
    }  
    ```  
  
6.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource.GetSuggestedActions%2A> metoda, která vrátí hodnotu pole <xref:Microsoft.VisualStudio.Language.Intellisense.SuggestedActionSet> objekty, které obsahují různými <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction> objekty. Tato metoda je volána, když žárovky je rozšířena.  
  
    > [!WARNING]
    >  Ujistěte se, který implementace `HasSuggestedActionsAsync()` a `GetSuggestedActions()` jsou konzistentní; který je, pokud `HasSuggestedActionsAsync()` vrátí `true`, pak `GetSuggestedActions()` by měl mít některé akce pro zobrazení. V mnoha případech `HasSuggestedActionsAsync()` je volána těsně před `GetSuggestedActions()`, ale není to vždy. Například, pokud uživatel vyvolá akce žárovky stisknutím kombinace kláves (CTRL +.) pouze `GetSuggestedActions()` je volána.  
  
    ```csharp  
    public IEnumerable<SuggestedActionSet> GetSuggestedActions(ISuggestedActionCategorySet requestedActionCategories, SnapshotSpan range, CancellationToken cancellationToken)  
    {  
        TextExtent extent;  
        if (TryGetWordUnderCaret(out extent) && extent.IsSignificant)  
        {  
            ITrackingSpan trackingSpan = range.Snapshot.CreateTrackingSpan(extent.Span, SpanTrackingMode.EdgeInclusive);  
            var upperAction = new UpperCaseSuggestedAction(trackingSpan);  
            var lowerAction = new LowerCaseSuggestedAction(trackingSpan);  
            return new SuggestedActionSet[] { new SuggestedActionSet(new ISuggestedAction[] { upperAction, lowerAction }) };  
        }  
        return Enumerable.Empty<SuggestedActionSet>();  
    }   
    ```  
  
7.  Definování `SuggestedActionsChanged` událostí.  
  
    ```csharp  
    public event EventHandler<EventArgs> SuggestedActionsChanged;  
    ```  
  
8.  K dokončení implementace, přidání implementace pro `Dispose()` a `TryGetTelemetryId()` metody. Jsme nechcete, aby se telemetrie, tak, aby vrátí hodnotu false a nastavit na prázdný identifikátor GUID.  
  
    ```csharp  
    public void Dispose()  
    {  
    }  
  
    public bool TryGetTelemetryId(out Guid telemetryId)  
    {  
        // This is a sample provider and doesn't participate in LightBulb telemetry  
        telemetryId = Guid.Empty;  
        return false;  
    }  
    ```  
  
## <a name="implementing-light-bulb-actions"></a>Implementace žárovky akce  
  
1.  V projektu přidejte odkaz na Microsoft.VisualStudio.Imaging.Interop.14.0.DesignTime.dll a nastavte **místní kopie** k `False`.  
  
2.  Vytvořte dvě třídy s názvem první `UpperCaseSuggestedAction` a druhá s názvem `LowerCaseSuggestedAction`. Obě třídy implementovat <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction>.  
  
    ```csharp  
    internal class UpperCaseSuggestedAction : ISuggestedAction   
    internal class LowerCaseSuggestedAction : ISuggestedAction  
    ```  
  
     Obě třídy jsou agentem, s tím rozdílem, že jeden volá <xref:System.String.ToUpper%2A> a jiná volání <xref:System.String.ToLower%2A>. Tyto kroky zahrnují pouze třídu velká akce, ale je nutné implementovat obě třídy. Použijte kroky pro implementaci velká akce jako vzor pro implementaci malá akce.  
  
3.  Přidejte následující příkazy pro tyto třídy:  
  
    ```csharp  
    using Microsoft.VisualStudio.Imaging.Interop;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Documents;  
    using System.Windows.Media;  
  
    ```  
  
4.  Deklarujte sadu privátním polím.  
  
    ```csharp  
    private ITrackingSpan m_span;  
    private string m_upper;  
    private string m_display;  
    private ITextSnapshot m_snapshot;  
    ```  
  
5.  Přidejte konstruktor, který nastaví pole.  
  
    ```csharp  
    public UpperCaseSuggestedAction(ITrackingSpan span)  
    {  
        m_span = span;  
        m_snapshot = span.TextBuffer.CurrentSnapshot;  
        m_upper = span.GetText(m_snapshot).ToUpper();  
        m_display = string.Format("Convert '{0}' to upper case", span.GetText(m_snapshot));  
    }  
    ```  
  
6.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.GetPreviewAsync%2A> metody, které se zobrazí ve verzi preview akce.  
  
    ```csharp  
    public Task<object> GetPreviewAsync(CancellationToken cancellationToken)  
    {  
        var textBlock = new TextBlock();  
        textBlock.Padding = new Thickness(5);  
        textBlock.Inlines.Add(new Run() { Text = m_upper });  
        return Task.FromResult<object>(textBlock);  
    }  
    ```  
  
7.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.GetActionSetsAsync%2A> metody, které se vrátí prázdnou <xref:Microsoft.VisualStudio.Language.Intellisense.SuggestedActionSet> výčtu.  
  
    ```csharp  
    public Task<IEnumerable<SuggestedActionSet>> GetActionSetsAsync(CancellationToken cancellationToken)  
    {  
        return Task.FromResult<IEnumerable<SuggestedActionSet>>(null);  
    }  
    ```  
  
8.  Vlastnosti implementujte následujícím způsobem.  
  
    ```csharp  
    public bool HasActionSets  
    {  
        get { return false; }  
    }  
    public string DisplayText  
    {  
        get { return m_display; }  
    }  
    public ImageMoniker IconMoniker  
    {  
       get { return default(ImageMoniker); }  
    }  
    public string IconAutomationText  
    {  
        get  
        {  
            return null;  
        }  
    }  
    public string InputGestureText  
    {  
        get  
        {  
            return null;  
        }  
    }  
    public bool HasPreview  
    {  
        get { return true; }  
    }  
    ```  
  
9. Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.Invoke%2A> metoda nahrazením textu v rozpětí ekvivalentem velká písmena.  
  
    ```csharp  
    public void Invoke(CancellationToken cancellationToken)  
    {  
        m_span.TextBuffer.Replace(m_span.GetSpan(m_snapshot), m_upper);  
    }  
    ```  
  
    > [!WARNING]
    >  Akce žárovky **Invoke** metoda neočekává zobrazit uživatelské rozhraní.  Pokud vaše akce zprovoznit nové uživatelské rozhraní (například dialog preview nebo výběr), nejsou zobrazeny přímo v rámci uživatelského rozhraní **Invoke** metoda, ale místo toho naplánovat zobrazit uživatelské rozhraní po vrácení z **Invoke**.  
  
10. Chcete-li dokončit implementace, přidejte `Dispose()` a `TryGetTelemetryId()` metody.  
  
    ```csharp  
    public void Dispose()  
    {  
    }  
  
    public bool TryGetTelemetryId(out Guid telemetryId)  
    {  
        // This is a sample action and doesn't participate in LightBulb telemetry  
        telemetryId = Guid.Empty;  
        return false;  
    }  
    ```  
  
11. Nezapomeňte se stejnou věc udělat `LowerCaseSuggestedAction` změna zobrazovaný text na "Převést {0}' na malá písmena" a volání <xref:System.String.ToUpper%2A> k <xref:System.String.ToLower%2A>.  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení LightBulbTest a spusťte ji v experimentální instanci.  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvoření textového souboru a zadejte text. Měli byste vidět žárovky vlevo od textu.  
  
     ![testování žárovky](../extensibility/media/testlightbulb.png "TestLIghtBulb")  
  
4.  Přejděte na žárovky. Měli byste vidět šipku dolů.  
  
5.  Když kliknete žárovky, dvě navrhovaná akce má být zobrazena, společně s ve verzi preview vybrané akce.  
  
     ![testování žárovky rozšířit](../extensibility/media/testlightbulbexpanded.gif "TestLIghtBulbExpanded")  
  
6.  Pokud je první akcí kliknete, veškerý text v aktuální aplikaci word mají být převedeny na velká písmena. Pokud kliknete na druhou akci, mají být převedeny veškerý text na malá písmena.  
  