---
title: "Návod: Zvýraznění textu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - highlight text
ms.assetid: 64b772ad-4392-42e9-a237-5137f0384bf0
caps.latest.revision: "42"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b54dabbe00b0df920655b595cab32ed21126415b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-highlighting-text"></a>Návod: Zvýraznění textu
Různých vizuálních efektů můžete přidat do editoru vytvořením součásti Managed Extensibility Framework (MEF). Tento návod ukazuje, jak chcete zvýraznit všechny výskyty aktuální slova v textovém souboru. Pokud slovo dojde k více než jednou v textovém souboru a umístit pomocí kurzoru v jeden výskyt, každý výskyt zvýrazní.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `HighlightWordTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
## <a name="defining-a-textmarkertag"></a>Definování TextMarkerTag  
 Prvním krokem při zvýraznění textu je podtřídou <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> a definovat její vzhled.  
  
#### <a name="to-define-a-textmarkertag-and-a-markerformatdefinition"></a>K definování TextMarkerTag a MarkerFormatDefinition  
  
1.  Přidejte soubor třídy a pojmenujte ji **HighlightWordTag**.  
  
2.  Přidejte následující odkazy:  
  
    1.  Microsoft.VisualStudio.CoreUtility  
  
    2.  Microsoft.VisualStudio.Text.Data  
  
    3.  Microsoft.VisualStudio.Text.Logic  
  
    4.  Microsoft.VisualStudio.Text.UI  
  
    5.  Microsoft.VisualStudio.Text.UI.Wpf  
  
    6.  System.ComponentModel.Composition  
  
    7.  Presentation.Core  
  
    8.  Presentation.Framework  
  
3.  Importujte následující obory názvů.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using System.Linq;  
    using System.Threading;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Operations;  
    using Microsoft.VisualStudio.Text.Tagging;  
    using Microsoft.VisualStudio.Utilities;  
    using System.Windows.Media;  
    ```  
  
4.  Vytvořte třídu, která dědí z <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> a pojmenujte ji `HighlightWordTag`.  
  
    ```csharp  
    internal class HighlightWordTag : TextMarkerTag  
    {  
  
    }  
    ```  
  
5.  Vytvořte druhou třídu, která dědí z <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition>a pojmenujte ji HighlightWordFormatDefinition. Chcete-li použít tuto definici formátu vaše značky, je nutné ho exportovat s následujícími atributy:  
  
    -   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: značky použít tak, aby odkazovaly tento formát  
  
    -   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: To způsobí, že formát, který se zobrazí v uživatelském rozhraní  
  
    ```csharp  
  
    [Export(typeof(EditorFormatDefinition))]  
    [Name("MarkerFormatDefinition/HighlightWordFormatDefinition")]  
    [UserVisible(true)]  
    internal class HighlightWordFormatDefinition : MarkerFormatDefinition  
    {  
  
    }  
    ```  
  
6.  V konstruktoru pro HighlightWordFormatDefinition zadejte jeho zobrazovaný název a vzhled. Vlastnost pozadí definuje barvu výplně při vlastnost popředí definuje barvu ohraničení.  
  
    ```csharp  
    public HighlightWordFormatDefinition()  
    {  
                this.BackgroundColor = Colors.LightBlue;  
        this.ForegroundColor = Colors.DarkBlue;  
        this.DisplayName = "Highlight Word";  
        this.ZOrder = 5;  
    }  
    ```  
  
7.  V konstruktoru pro HighlightWordTag předejte názvu definicí formátu, který jste právě vytvořili.  
  
    ```  
    public HighlightWordTag() : base("MarkerFormatDefinition/HighlightWordFormatDefinition") { }  
    ```  
  
## <a name="implementing-an-itagger"></a>Implementace ITagger  
 Dalším krokem je implementace <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> rozhraní. Toto rozhraní přiřadí k dané textovou vyrovnávací paměť, značky, které poskytují zvýraznění textu a jiných vizuálních efektů.  
  
#### <a name="to-implement-a-tagger"></a>K implementaci tagger  
  
1.  Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> typu `HighlightWordTag`a pojmenujte ji `HighlightWordTagger`.  
  
    ```csharp  
    internal class HighlightWordTagger : ITagger<HighlightWordTag>  
    {  
  
    }  
    ```  
  
2.  Přidejte následující soukromé pole a vlastnosti do třídy:  
  
    -   <xref:Microsoft.VisualStudio.Text.Editor.ITextView>, Která odpovídá aktuální zobrazení textu.  
  
    -   <xref:Microsoft.VisualStudio.Text.ITextBuffer>, Která odpovídá textovou vyrovnávací paměť, který je základem textového zobrazení.  
  
    -   <xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService>, Který se používá k hledání textu.  
  
    -   <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>, Která obsahuje metody pro navigace v rámci textu rozpětí.  
  
    -   A <xref:Microsoft.VisualStudio.Text.NormalizedSnapshotSpanCollection>, který obsahuje sadu slova, abyste měli na očích.  
  
    -   A <xref:Microsoft.VisualStudio.Text.SnapshotSpan>, která odpovídá aktuální aplikace word.  
  
    -   A <xref:Microsoft.VisualStudio.Text.SnapshotPoint>, která odpovídá na aktuální pozici pomocí kurzoru.  
  
    -   Zámek objektu.  
  
    ```csharp  
    ITextView View { get; set; }  
    ITextBuffer SourceBuffer { get; set; }  
    ITextSearchService TextSearchService { get; set; }  
    ITextStructureNavigator TextStructureNavigator { get; set; }  
    NormalizedSnapshotSpanCollection WordSpans { get; set; }  
    SnapshotSpan? CurrentWord { get; set; }  
    SnapshotPoint RequestedPoint { get; set; }  
    object updateLock = new object();  
  
    ```  
  
3.  Přidejte konstruktor, který inicializuje vlastnosti uvedena i výše a přidá <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> a <xref:Microsoft.VisualStudio.Text.Editor.ITextCaret.PositionChanged> obslužné rutiny událostí.  
  
    ```csharp  
    public HighlightWordTagger(ITextView view, ITextBuffer sourceBuffer, ITextSearchService textSearchService,  
    ITextStructureNavigator textStructureNavigator)  
    {  
        this.View = view;  
        this.SourceBuffer = sourceBuffer;  
        this.TextSearchService = textSearchService;  
        this.TextStructureNavigator = textStructureNavigator;  
        this.WordSpans = new NormalizedSnapshotSpanCollection();  
        this.CurrentWord = null;  
        this.View.Caret.PositionChanged += CaretPositionChanged;  
        this.View.LayoutChanged += ViewLayoutChanged;  
    }  
  
    ```  
  
4.  Obslužné rutiny událostí obě volání `UpdateAtCaretPosition` metoda.  
  
    ```csharp  
    void ViewLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
    {  
        // If a new snapshot wasn't generated, then skip this layout   
        if (e.NewSnapshot != e.OldSnapshot)  
        {  
            UpdateAtCaretPosition(View.Caret.Position);  
        }  
    }  
  
    void CaretPositionChanged(object sender, CaretPositionChangedEventArgs e)  
    {  
        UpdateAtCaretPosition(e.NewPosition);  
    }  
    ```  
  
5.  Musíte taky přidat `TagsChanged` událost, která bude volat metodu aktualizace.  
  
     [!code-csharp[VSSDKHighlightWordTest#10](../extensibility/codesnippet/CSharp/walkthrough-highlighting-text_1.cs)]
     [!code-vb[VSSDKHighlightWordTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-highlighting-text_1.vb)]  
  
6.  `UpdateAtCaretPosition()` Metoda vyhledá všechny aplikace word ve vyrovnávací paměti text, který je stejný jako word, kde je umístěn kurzor a vytvoří seznam <xref:Microsoft.VisualStudio.Text.SnapshotSpan> objekty, které odpovídají výskytů slova. Potom zavolá `SynchronousUpdate`, kterou vyvolá `TagsChanged` událostí.  
  
    ```csharp  
    void UpdateAtCaretPosition(CaretPosition caretPosition)  
    {  
        SnapshotPoint? point = caretPosition.Point.GetPoint(SourceBuffer, caretPosition.Affinity);  
  
        if (!point.HasValue)  
            return;  
  
        // If the new caret position is still within the current word (and on the same snapshot), we don't need to check it   
        if (CurrentWord.HasValue  
            && CurrentWord.Value.Snapshot == View.TextSnapshot  
            && point.Value >= CurrentWord.Value.Start  
            && point.Value <= CurrentWord.Value.End)  
        {  
            return;  
        }  
  
        RequestedPoint = point.Value;  
        UpdateWordAdornments();  
    }  
  
    void UpdateWordAdornments()  
    {  
        SnapshotPoint currentRequest = RequestedPoint;  
        List<SnapshotSpan> wordSpans = new List<SnapshotSpan>();  
        //Find all words in the buffer like the one the caret is on  
        TextExtent word = TextStructureNavigator.GetExtentOfWord(currentRequest);  
        bool foundWord = true;  
        //If we've selected something not worth highlighting, we might have missed a "word" by a little bit  
        if (!WordExtentIsValid(currentRequest, word))  
        {  
            //Before we retry, make sure it is worthwhile   
            if (word.Span.Start != currentRequest  
                 || currentRequest == currentRequest.GetContainingLine().Start  
                 || char.IsWhiteSpace((currentRequest - 1).GetChar()))  
            {  
                foundWord = false;  
            }  
            else  
            {  
                // Try again, one character previous.    
                //If the caret is at the end of a word, pick up the word.  
                word = TextStructureNavigator.GetExtentOfWord(currentRequest - 1);  
  
                //If the word still isn't valid, we're done   
                if (!WordExtentIsValid(currentRequest, word))  
                    foundWord = false;  
            }  
        }  
  
        if (!foundWord)  
        {  
            //If we couldn't find a word, clear out the existing markers  
            SynchronousUpdate(currentRequest, new NormalizedSnapshotSpanCollection(), null);  
            return;  
        }  
  
        SnapshotSpan currentWord = word.Span;  
        //If this is the current word, and the caret moved within a word, we're done.   
        if (CurrentWord.HasValue && currentWord == CurrentWord)  
            return;  
  
        //Find the new spans  
        FindData findData = new FindData(currentWord.GetText(), currentWord.Snapshot);  
        findData.FindOptions = FindOptions.WholeWord | FindOptions.MatchCase;  
  
        wordSpans.AddRange(TextSearchService.FindAll(findData));  
  
        //If another change hasn't happened, do a real update   
        if (currentRequest == RequestedPoint)  
            SynchronousUpdate(currentRequest, new NormalizedSnapshotSpanCollection(wordSpans), currentWord);  
    }  
    static bool WordExtentIsValid(SnapshotPoint currentRequest, TextExtent word)  
    {  
        return word.IsSignificant  
            && currentRequest.Snapshot.GetText(word.Span).Any(c => char.IsLetter(c));  
    }  
  
    ```  
  
7.  `SynchronousUpdate` Provádí synchronní aktualizace `WordSpans` a `CurrentWord` vlastnosti a vyvolá `TagsChanged` událostí.  
  
    ```vb  
    void SynchronousUpdate(SnapshotPoint currentRequest, NormalizedSnapshotSpanCollection newSpans, SnapshotSpan? newCurrentWord)  
    {  
        lock (updateLock)  
        {  
            if (currentRequest != RequestedPoint)  
                return;  
  
            WordSpans = newSpans;  
            CurrentWord = newCurrentWord;  
  
            var tempEvent = TagsChanged;  
            if (tempEvent != null)  
                tempEvent(this, new SnapshotSpanEventArgs(new SnapshotSpan(SourceBuffer.CurrentSnapshot, 0, SourceBuffer.CurrentSnapshot.Length)));  
        }  
    }  
    ```  
  
8.  Musí implementovat <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> metoda. Tato metoda přebírá kolekce <xref:Microsoft.VisualStudio.Text.SnapshotSpan> objekty a vrátí výčet značky rozpětí.  
  
     V jazyce C# Implementujte tuto metodu, jako iterator upozornění, která umožňuje opožděné vyhodnocení (tedy zkušební sady jenom v případě, že jednotlivé položky ke kterým se přistupuje) z uvedených značek. V jazyce Visual Basic přidat značky do seznamu a vrátí seznam.  
  
     Zde metoda vrátí <xref:Microsoft.VisualStudio.Text.Tagging.TagSpan%601> objekt, který má "blue" <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>, který poskytuje modré pozadí.  
  
    ```csharp  
    public IEnumerable<ITagSpan<HighlightWordTag>> GetTags(NormalizedSnapshotSpanCollection spans)  
    {  
        if (CurrentWord == null)  
            yield break;  
  
        // Hold on to a "snapshot" of the word spans and current word, so that we maintain the same  
        // collection throughout  
        SnapshotSpan currentWord = CurrentWord.Value;  
        NormalizedSnapshotSpanCollection wordSpans = WordSpans;  
  
        if (spans.Count == 0 || wordSpans.Count == 0)  
            yield break;  
  
        // If the requested snapshot isn't the same as the one our words are on, translate our spans to the expected snapshot   
        if (spans[0].Snapshot != wordSpans[0].Snapshot)  
        {  
            wordSpans = new NormalizedSnapshotSpanCollection(  
                wordSpans.Select(span => span.TranslateTo(spans[0].Snapshot, SpanTrackingMode.EdgeExclusive)));  
  
            currentWord = currentWord.TranslateTo(spans[0].Snapshot, SpanTrackingMode.EdgeExclusive);  
        }  
  
        // First, yield back the word the cursor is under (if it overlaps)   
        // Note that we'll yield back the same word again in the wordspans collection;   
        // the duplication here is expected.   
        if (spans.OverlapsWith(new NormalizedSnapshotSpanCollection(currentWord)))  
            yield return new TagSpan<HighlightWordTag>(currentWord, new HighlightWordTag());  
  
        // Second, yield all the other words in the file   
        foreach (SnapshotSpan span in NormalizedSnapshotSpanCollection.Overlap(spans, wordSpans))  
        {  
            yield return new TagSpan<HighlightWordTag>(span, new HighlightWordTag());  
        }  
    }  
    ```  
  
## <a name="creating-a-tagger-provider"></a>Vytvoření zprostředkovatele Tagger  
 K vytvoření vašeho tagger, je nutné implementovat <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>. Tato třída je součást MEF, takže správné atributy je třeba nastavit tak, aby toto rozšíření je rozpoznán.  
  
> [!NOTE]
>  Další informace o rozhraní MEF najdete v tématu [Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index).  
  
#### <a name="to-create-a-tagger-provider"></a>Chcete-li vytvořit poskytovatele tagger  
  
1.  Vytvoření třídy s názvem `HighlightWordTaggerProvider` , která implementuje <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text" a <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> z <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>.  
  
    ```csharp  
    [Export(typeof(IViewTaggerProvider))]  
    [ContentType("text")]  
    [TagType(typeof(TextMarkerTag))]  
    internal class HighlightWordTaggerProvider : IViewTaggerProvider  
    { }  
    ```  
  
2.  Je nutné naimportovat dvě editor služby, <xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService> a <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, k vytvoření instance tagger.  
  
    ```csharp  
    [Import]  
    internal ITextSearchService TextSearchService { get; set; }  
  
    [Import]  
    internal ITextStructureNavigatorSelectorService TextStructureNavigatorSelector { get; set; }  
  
    ```  
  
3.  Implementace <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> metoda vrátí instanci `HighlightWordTagger`.  
  
    ```csharp  
    public ITagger<T> CreateTagger<T>(ITextView textView, ITextBuffer buffer) where T : ITag  
    {  
        //provide highlighting only on the top buffer   
        if (textView.TextBuffer != buffer)  
            return null;  
  
        ITextStructureNavigator textStructureNavigator =  
            TextStructureNavigatorSelector.GetTextStructureNavigator(buffer);  
  
        return new HighlightWordTagger(textView, buffer, TextSearchService, textStructureNavigator) as ITagger<T>;  
    }  
    ```  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení HighlightWordTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-the-highlightwordtest-solution"></a>Pro sestavení a otestování HighlightWordTest řešení  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvoření textového souboru a zadejte nějaký text, ve které se opakují slova, například "hello hello hello".  
  
4.  Umístěte kurzor v jednom z výskytů text "hello". Každý výskyt by měl být modře zvýrazněný.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)