---
title: Služba jazyka a body rozšíření editoru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extension points
ms.assetid: 91a6417e-a6fe-4bc2-9d9f-5173c634a99b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d3c253ba52da1fd6bb9133e44ba6858e8f1a4151
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="language-service-and-editor-extension-points"></a>Služba jazyka a body rozšíření editoru
Editor poskytuje rozšíření body, které můžete rozšířit jako součásti Managed Extensibility Framework (MEF), včetně většinu funkcí služby jazyk. Toto jsou hlavní rozšíření bodu kategorií:  
  
-   Typy obsahu  
  
-   Klasifikace typy a formáty klasifikace  
  
-   Okraje a posuvníky  
  
-   Značky  
  
-   Vylepšení  
  
-   Myš procesorů  
  
-   Vyřaďte obslužné rutiny  
  
-   Možnosti  
  
-   IntelliSense  
  
## <a name="extending-content-types"></a>Rozšíření typů obsahu  
 Typy obsahu jsou definice druhy textového editoru, například zpracovávaných, "text", "kód" nebo "CSharp". Zadejte nový typ obsahu pomocí deklarace proměnné typu <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> a poskytnete jedinečný název nového typu obsahu. Chcete-li zaregistrovat typ obsahu pomocí editoru, ho exportujte společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute> je název typu obsahu.  
  
-   <xref:Microsoft.VisualStudio.Utilities.BaseDefinitionAttribute> je název typu obsahu, ze kterého je odvozen tento typ obsahu. Typ obsahu. může dědit z více jiné typy obsahu.  
  
 Protože <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> třída je zapečetěná, můžete ho exportovat s žádný parametr typu.  
  
 Následující příklad ukazuje export atributy v definici typu obsahu.  
  
```  
[Export]  
[Name("test")]  
[BaseDefinition("code")]  
[BaseDefinition("projection")]  
internal static ContentTypeDefinition TestContentTypeDefinition;  
```  
  
 Typy obsahu, může být založen na počtu nula či více typy existující obsahu. Toto jsou předdefinované typy:  
  
-   Žádné: základní typ obsahu. Nadřazené všechny ostatní typy obsahu.  
  
-   Text: základní typ pro jiných projekci obsahu. Dědit z "žádný".  
  
-   Ve formátu prostého textu: pro text jiný kód. Dědit z "text".  
  
-   Kód: pro kód všechny typy. Dědit z "text".  
  
-   Inertním: vyloučí text z jakéhokoli druhu zpracování. Text tento typ obsahu bude mít nikdy všechna rozšíření, použije na ni.  
  
-   Projekce: pro obsah projekce vyrovnávací paměti. Dědit z "žádný".  
  
-   IntelliSense: pro obsah IntelliSense. Dědit z "text".  
  
-   Sighelp: Nápověda podpis. Dědit z "intellisense".  
  
-   Sighelp-doc: podpis nápovědě. Dědit z "intellisense".  
  
 Toto jsou některé typy obsahu, které jsou definované v sadě Visual Studio a některých jazyků, které jsou hostované v sadě Visual Studio:  
  
-   Základní  
  
-   C/C++  
  
-   ConsoleOutput  
  
-   CSharp  
  
-   CSS  
  
-   ŠIF  
  
-   FindResults  
  
-   F#  
  
-   HTML  
  
-   JScript  
  
-   XAML  
  
-   XML  
  
 Chcete-li zjistit seznam dostupných typů obsahu, importujte <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>, která udržuje kolekci typů obsahu pro editor. Následující kód importuje této služby jako vlastnost.  
  
```  
[Import]  
internal IContentTypeRegistryService ContentTypeRegistryService { get; set; }  
```  
  
 Chcete-li přidružit příponu názvu souboru, typu obsahu, použijte <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition>.  
  
> [!NOTE]
>  V sadě Visual Studio jsou registrované přípony názvů souborů pomocí <xref:Microsoft.VisualStudio.Shell.ProvideLanguageExtensionAttribute> na balíček služby jazyk. <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> Přidruží typ obsahu MEF příponu názvu souboru, který byl zaregistrován tímto způsobem.  
  
 Pokud chcete exportovat příponu názvu souboru do definice typu obsahu, musí zahrnovat následující atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.FileExtensionAttribute>: Určuje příponu názvu souboru.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: Určuje typ obsahu.  
  
 Protože <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> třída je zapečetěná, můžete ho exportovat s žádný parametr typu.  
  
 Následující příklad ukazuje atributy export na příponu názvu souboru do definice typu obsahu.  
  
```  
[Export]  
[FileExtension(".test")]  
[ContentType("test")]  
internal static FileExtensionToContentTypeDefinition TestFileExtensionDefinition;  
```  
  
 <xref:Microsoft.VisualStudio.Utilities.IFileExtensionRegistryService> Spravuje přidružení mezi přípony názvů souborů a typy obsahu.  
  
## <a name="extending-classification-types-and-classification-formats"></a>Rozšíření typů klasifikaci a klasifikaci formáty  
 Typy klasifikaci můžete definovat typy text, pro který chcete zadat jinou zpracování (například zvýrazňování modrý text "– klíčové slovo" a "komentář" text zelená). Definujte nový typ klasifikace deklarace proměnné typu <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeDefinition> a předá jedinečný název.  
  
 Chcete-li zaregistrovat typ klasifikace pomocí editoru, ho exportujte společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název typu klasifikace.  
  
-   <xref:Microsoft.VisualStudio.Utilities.BaseDefinitionAttribute>: název typu klasifikace, ze kterého tento typ klasifikace dědí. Všechny typy klasifikace dědit z "text" a typu klasifikace mohou dědit z několika dalších typů klasifikace.  
  
 Protože <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeDefinition> třída je zapečetěná, můžete ho exportovat s žádný parametr typu.  
  
 Následující příklad ukazuje export atributy v definici typu klasifikace.  
  
```  
[Export]  
[Name("csharp.test")]  
[BaseDefinition("test")]  
internal static ClassificationTypeDefinition CSharpTestDefinition;  
```  
  
 <xref:Microsoft.VisualStudio.Language.StandardClassification.IStandardClassificationService> Poskytuje přístup k standardní klasifikace. Mezi tyto typy předdefinované klasifikace patří:  
  
-   "text"  
  
-   "přirozený jazyk" (odvozená z "text")  
  
-   "formální jazyk" (odvozená z "text")  
  
-   "řetězec" (odvozená z "literál")  
  
-   "znak" (odvozená z "literál")  
  
-   "číselné" (odvozená z "literál")  
  
 Sadu typů různých chyb dědí <xref:Microsoft.VisualStudio.Text.Adornments.ErrorTypeDefinition>. Tato nastavení zahrnují následující typy chyb:  
  
-   "Chyba syntaxe"  
  
-   "Chyba kompilátoru"  
  
-   "jiné error.  
  
-   "upozornění"  
  
 Chcete-li zjistit, seznamu dostupných typů klasifikace, importujte <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>, která udržuje kolekci typů klasifikace pro editor. Následující kód importuje této služby jako vlastnost.  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationTypeRegistryService { get; set; }  
```  
  
 Definice formátu klasifikaci můžete definovat nového typu klasifikace. Odvození třídy z <xref:Microsoft.VisualStudio.Text.Classification.ClassificationFormatDefinition> a exportovat je s typem <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition>, společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název formátu.  
  
-   <xref:Microsoft.VisualStudio.Utilities.DisplayNameAttribute>: Zobrazovaný název formátu.  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: Určuje, zda se zobrazí ve formátu na **písma a barev** stránky **možnosti** dialogové okno.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: prioritu formátu. Platné hodnoty jsou z <xref:Microsoft.VisualStudio.Text.Classification.Priority>.  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeAttribute>: název klasifikace typ, který má tento formát je namapovaný.  
  
 Následující příklad ukazuje atributy export na definici formátu klasifikace.  
  
```  
[Export(typeof(EditorFormatDefinition))]  
[ClassificationType(ClassificationTypeNames = "test")]  
[Name("test")]  
[DisplayName("Test")]  
[UserVisible(true)]  
[Order(After = Priority.Default, Before = Priority.High)]  
internal sealed class TestFormat : ClassificationFormatDefinition  
```  
  
 Chcete-li zjistit seznam dostupných formátů, importujte <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>, která udržuje kolekci formátů pro editor. Následující kód importuje této služby jako vlastnost.  
  
```  
[Import]  
internal IEditorFormatMapService FormatMapService { get; set; }  
```  
  
## <a name="extending-margins-and-scrollbars"></a>Rozšíření okraje a posuvníky  
 Okraje a posuvníky jsou hlavní zobrazení prvků editoru kromě samotném zobrazení textu. Můžete zadat libovolný počet okraje kromě standardní okraje, které jsou kolem textového zobrazení.  
  
 Implementace <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMargin> rozhraní k definování okraj. Musíte také implementovat <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> rozhraní pro vytváření okraj.  
  
 K registraci poskytovatele okraj pomocí editoru, musíte exportovat zprostředkovatele společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název rozpětí.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: pořadí, ve kterém se zobrazí okraj, vzhledem k jiné stránky.  
  
     Toto jsou předdefinované okraje:  
  
    -   "Wpf vodorovných Scrollbar"  
  
    -   "Wpf Vertical Scrollbar"  
  
    -   "Číslo okraj řádku Wpf"  
  
     Vodorovné okraje, které mají atribut pořadí `After="Wpf Horizontal Scrollbar"` níže předdefinované okraj a vodorovné okraje, které mají atribut pořadí se zobrazují `Before ="Wpf Horizontal Scrollbar"` jsou zobrazeny výše předdefinované okraj. Pravým svislé okraje, které mají atribut pořadí `After="Wpf Vertical Scrollbar"` se zobrazí vpravo od posuvník. Levé svislé okraje, které mají atribut pořadí `After="Wpf Line Number Margin"` (Pokud je zobrazen) se zobrazí vlevo číslo okraj řádku.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.MarginContainerAttribute>: druh okraj (levé, pravé, top a bottom).  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: druh obsah (například "text" nebo "kódu"), pro který je platný vaší okraj.  
  
 Následující příklad ukazuje atributy export na okraj poskytovatele pro okraj, který se zobrazí vpravo od číslo okraj řádku.  
  
```  
[Export(typeof(IWpfTextViewMarginProvider))]  
[Name("TestMargin")]  
[Order(Before = "Wpf Line Number Margin")]  
[MarginContainer(PredefinedMarginNames.Left)]  
[ContentType("text")]   
```  
  
## <a name="extending-tags"></a>Rozšíření značek  
 Značky jsou způsob přiřazení dat s různými druhy textu. V mnoha případech související data se zobrazí jako vizuální efekt, ale ne všechny značky mít vizuální prezentaci. Můžete definovat vlastní typ značky implementací <xref:Microsoft.VisualStudio.Text.Tagging.ITag>. Musíte také implementovat <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> zajistit značek pro danou sadu rozpětí textu a <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider> zajistit tagger. Je nutné exportovat zprostředkovatele tagger společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: druh obsah (například "text" nebo "kódu"), pro který je vaše značky platný.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute>: typ značky.  
  
 Následující příklad ukazuje na zprostředkovateli tagger export atributy.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 Následující typy značky jsou předdefinované:  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.ClassificationTag>: přidružené <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>: přidružené typy chyb.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>: přidružené dalších úprav.  
  
    > [!NOTE]
    >  Příklad <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>, viz definice HighlightWordTag v [návod: zvýraznění textu](../extensibility/walkthrough-highlighting-text.md).  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag>: přidružené k oblasti, které můžete rozbalit nebo sbalit v osnovy.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>: definuje prostor zabírá dalších úprav v zobrazení textu. Další informace o vylepšení vyjednávání místa najdete v následující části.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.IntraTextAdornmentTag>: poskytuje automatické mezery a velikosti dalších úprav.  
  
 Chcete-li najít a používat značky pro vyrovnávací paměti a zobrazení, importujte <xref:Microsoft.VisualStudio.Text.Tagging.IViewTagAggregatorFactoryService> nebo <xref:Microsoft.VisualStudio.Text.Tagging.IBufferTagAggregatorFactoryService>, které získáte <xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601> požadovaného typu. Následující kód importuje této služby jako vlastnost.  
  
```  
[Import]  
internal IViewTagAggregatorFactoryService ViewTagAggregatorFactoryService { get; set; }  
```  
  
#### <a name="tags-and-markerformatdefinitions"></a>Značky a MarkerFormatDefinitions  
 Můžete rozšířit <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition> třída definujte vzhled značku. Je nutné exportovat vlastní třídy (jako <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition>) s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název slouží k odkazování tento formát  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: To způsobí, že formát, který se zobrazí v uživatelském rozhraní  
  
 V konstruktoru zadejte zobrazovaný název a vzhled značky. <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.BackgroundColor%2A> Určuje barvu výplně a <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.ForegroundColor%2A> definuje barvu ohraničení. <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.DisplayName%2A> Je lokalizovatelný název definice formátu.  
  
 Následuje příklad definicí formátu:  
  
```  
[Export(typeof(EditorFormatDefinition))]  
[Name("MarkerFormatDefinition/HighlightWordFormatDefinition")]  
[UserVisible(true)]  
internal class HighlightWordFormatDefinition : MarkerFormatDefinition  
{  
    public HighlightWordFormatDefinition()  
    {  
        this.BackgroundColor = Colors.LightBlue;  
        this.ForegroundColor = Colors.DarkBlue;  
        this.DisplayName = "Highlight Word";   
        this.ZOrder = 5;  
    }  
}  
  
```  
  
 Pokud chcete použít tuto definici formátu značku, odkazovat na název, který nastavíte v atributu název třídy (ne zobrazovaný název).  
  
> [!NOTE]
>  Příklad <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition>, viz třídu HighlightWordFormatDefinition v [návod: zvýraznění textu](../extensibility/walkthrough-highlighting-text.md).  
  
## <a name="extending-adornments"></a>Rozšíření vylepšení  
 Vylepšení definovat vizuálních efektů, které můžete přidat buď na text, který se zobrazí v zobrazení textu nebo na text zobrazit sám sebe. Můžete definovat vlastní dalších úprav jako jakýkoli typ <xref:System.Windows.UIElement>.  
  
 Ve třídě dalších úprav musíte deklarovat <xref:Microsoft.VisualStudio.Text.Editor.AdornmentLayerDefinition>. Chcete-li zaregistrovat vrstvě dalších úprav, ho exportujte společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název dalších úprav.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: řazení dalších úprav s ohledem na ostatní vrstvy dalších úprav. Třída <xref:Microsoft.VisualStudio.Text.Editor.PredefinedAdornmentLayers> definuje čtyři vrstvy výchozí: výběr, osnova, pomocí kurzoru a Text.  
  
 Následující příklad ukazuje atributy export na definici vrstvy dalších úprav.  
  
```  
[Export]  
[Name("TestEmbeddedAdornment")]  
[Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
internal AdornmentLayerDefinition testLayerDefinition;  
```  
  
 Je nutné vytvořit druhou třídu, která implementuje <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> a zpracovává jeho <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> událostí po vytvoření instance dalších úprav. Je nutné exportovat tato třída společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: typ obsahu (například "text" nebo "kódu"), pro který je platný dalších úprav.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>: druh textového zobrazení, pro který je platný tento dalších úprav. Třída <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles> obsahuje sadu předdefinovaných text zobrazit role. Například <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> slouží především pro zobrazení textových souborů. <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> slouží k zobrazení textu, uživatel může upravit nebo přejít pomocí myši a klávesnice. Příklady <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> zobrazení jsou zobrazení textového editoru a **výstup** okno.  
  
 Následující příklad ukazuje atributy export na poskytovateli dalších úprav.  
  
```  
[Export(typeof(IWpfTextViewCreationListener))]  
[ContentType("csharp")]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
internal sealed class TestAdornmentProvider : IWpfTextViewCreationListener  
```  
  
 Dalších úprav vyjednávání místa je ten, který bude zabírat místo na stejné úrovni jako text. Chcete-li vytvořit tento druh dalších úprav, je třeba definovat značky třídu, která dědí z <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, která definuje množství místa sídlí dalších úprav.  
  
 Stejně jako u všech vylepšení, je nutné exportovat definici vrstvy dalších úprav.  
  
```  
[Export]  
[Name("TestAdornment")]  
[Order(After = DefaultAdornmentLayers.Text)]  
internal AdornmentLayerDefinition testAdornmentLayer;  
```  
  
 K vytvoření instance dalších úprav vyjednávání místo, je nutné vytvořit třídu, která implementuje <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>, kromě třídu, která implementuje <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> (stejně jako u jiných typů vylepšení).  
  
 K registraci poskytovatele tagger, je nutné jej exportovat společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: typ obsahu (například "text" nebo "kódu"), pro který je platný vaší dalších úprav.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>: druh textového zobrazení, pro které bude tato značka nebo dalších úprav je platný. Třída <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles> obsahuje sadu předdefinovaných text zobrazit role. Například <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> slouží především pro zobrazení textových souborů. <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> slouží k zobrazení textu, uživatel může upravit nebo přejít pomocí myši a klávesnice. Příklady <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> zobrazení jsou zobrazení textového editoru a **výstup** okno.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute>: typ značky nebo dalších úprav, který jste definovali. Je nutné přidat druhý <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> pro <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>.  
  
 Následující příklad ukazuje atributy export na poskytovateli tagger pro značku vyjednávání místo dalších úprav.  
  
```  
[Export(typeof(ITaggerProvider))]  
[ContentType("text")]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
[TagType(typeof(SpaceNegotiatingAdornmentTag))]  
[TagType(typeof(TestSpaceNegotiatingTag))]  
internal sealed class TestTaggerProvider : ITaggerProvider  
```  
  
## <a name="extending-mouse-processors"></a>Rozšíření myši procesorů  
 Můžete přidat zvláštní zpracování pro vstup z myši. Vytvořte třídu, která dědí z <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase> a přepsat události myši pro vstup chcete zpracovat. Musíte také implementovat <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider> v třídě sekundu a exportovat je společně s <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> , který určuje typ obsahu (například "text" nebo "kódu"), pro který je platný vaší obslužné rutiny myši.  
  
 Následující příklad ukazuje atributy export na zprostředkovatele procesoru myši.  
  
```  
[Export(typeof(IMouseProcessorProvider))]  
[Name("test mouse processor")]  
[ContentType("text")]  
[TextViewRole(PredefinedTextViewRoles.Interactive)]   
internal sealed class TestMouseProcessorProvider : IMouseProcessorProvider  
```  
  
## <a name="extending-drop-handlers"></a>Rozšíření obslužné rutiny rozevírací  
 Chování rozevírací obslužné rutiny pro specifické druhy text můžete přizpůsobit tak, že vytvoříte třídu, která implementuje <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.IDropHandler> a druhou třídu, která implementuje <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.IDropHandlerProvider> k vytvoření obslužné rutiny vyřaďte. Je nutné exportovat obslužná rutina rozevírací společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.DropFormatAttribute>: v textovém formátu, pro který je tato obslužná rutina rozevírací platný. Následující formáty jsou zpracovávány v pořadí podle priority od nejvyšší po nejnižší:  
  
    1.  Všechny vlastní formát  
  
    2.  FileDrop  
  
    3.  EnhancedMetafile  
  
    4.  WaveAudio  
  
    5.  RIFF  
  
    6.  DIF  
  
    7.  Národní prostředí  
  
    8.  Palety  
  
    9. PenData  
  
    10. Serializovatelné  
  
    11. SymbolicLink  
  
    12. XAML  
  
    13. XamlPackage  
  
    14. TIFF  
  
    15. Rastrový obrázek  
  
    16. DIB  
  
    17. MetafilePicture  
  
    18. SDÍLENÝ SVAZEK CLUSTERU  
  
    19. System.String  
  
    20. Formát HTML  
  
    21. UnicodeText  
  
    22. OEMText  
  
    23. Text  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název rozevíracího obslužné rutiny.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: řazení obslužná rutina rozevírací před nebo po vyřazení výchozí obslužnou rutinu. Vyřaďte výchozí obslužnou rutinu pro sadu Visual Studio je s názvem "DefaultFileDropHandler".  
  
 Následující příklad ukazuje atributy export na zprostředkovatele rozevírací obslužné rutiny.  
  
```  
[Export(typeof(IDropHandlerProvider))]  
[DropFormat("Text")]   
[Name("TestDropHandler")]  
[Order(Before="DefaultFileDropHandler")]   
internal class TestDropHandlerProvider : IDropHandlerProvider  
```  
  
## <a name="extending-editor-options"></a>Rozšíření možností editoru  
 Můžete definovat možnosti platná pouze v určitých oboru, například v textovém zobrazení. Tato sada předdefinované možnosti nabízí editor: Možnosti editoru, možnosti zobrazení a možnosti zobrazení Windows Presentation Foundation (WPF). Tyto možnosti lze nalézt v <xref:Microsoft.VisualStudio.Text.Editor.DefaultOptions>, <xref:Microsoft.VisualStudio.Text.Editor.DefaultTextViewOptions>, a <xref:Microsoft.VisualStudio.Text.Editor.DefaultWpfViewOptions>.  
  
 Pokud chcete přidat novou možnost, odvození třídy z jedné z těchto možností definice tříd:  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.EditorOptionDefinition%601>  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.ViewOptionDefinition%601>  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.WpfViewOptionDefinition%601>  
  
 Následující příklad ukazuje, jak exportovat definice možnosti, která má jako logická hodnota.  
  
```  
[Export(typeof(EditorOptionDefinition))]  
internal sealed class TestOption : EditorOptionDefinition<bool>  
```  
  
## <a name="extending-intellisense"></a>Rozšíření IntelliSense  
 IntelliSense je obecný termín pro skupinu součástí, které obsahují informace o strukturovaných textových a dokončování pro ni. Tyto funkce patří dokončování příkazů, podpis Nápověda, rychlé informace a žárovek. Dokončování pomáhá uživatelům, zadejte název jazyka – klíčové slovo nebo člen správně. Podpis help Zobrazí podpis nebo podpisy pro metodu, která má uživatel právě zadali. Rychlé informace zobrazí úplný podpis pro typ nebo člen název při přesunutí myši na ho. Žárovky poskytuje další akce pro určité identifikátory v některých kontextech, například přejmenování všechny výskyty proměnné po jeden výskyt byl přejmenován.  
  
 Návrh o funkci IntelliSense je podobný ve všech případech:  
  
-   IntelliSense *zprostředkovatele* je zodpovědný za celý proces.  
  
-   IntelliSense *relace* představuje posloupnost událostí mezi na aktivaci komponentě přednášejícího a committal nebo zrušení výběru. Relace je obvykle aktivovány některé gesto uživatele.  
  
-   IntelliSense *řadič* zodpovídá za rozhodování, kdy relaci by měl začínat a končit. Také rozhodne, pokud by měl být informace potvrdí a když by měla být zrušena relace.  
  
-   IntelliSense *zdroj* poskytuje obsah a rozhodne nejlepší shodu.  
  
-   IntelliSense *přednášejícího* zodpovídá za zobrazení obsahu.  
  
 Ve většině případů doporučujeme zadat aspoň zdrojem a řadiči. Pokud chcete přizpůsobit zobrazení, můžete zadat taky přednášejícího.  
  
### <a name="implementing-an-intellisense-source"></a>Implementace zdroje IntelliSense  
 Chcete-li přizpůsobit zdroj, musí implementovat jednu (nebo více) rozhraní následující zdroje:  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>  
  
> [!IMPORTANT]
>  <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagSource> se už nepoužívá pro <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>.  
  
 Kromě toho musí implementovat zprostředkovatele stejného druhu:  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>  
  
> [!IMPORTANT]
>  <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagSourceProvider> se už nepoužívá pro <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>.  
  
 Je nutné exportovat zprostředkovatele společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název zdroje.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: druh obsah (například "text" nebo "kódu"), na které se vztahuje zdroji.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: pořadí, ve kterém by se měla objevit zdroji (s ohledem na jiných zdrojů).  
  
-   Následující příklad ukazuje atributy export na dokončení zdroj zprostředkovatele.  
  
```  
Export(typeof(ICompletionSourceProvider))]  
[Name(" Test Statement Completion Provider")]  
[Order(Before = "default")]  
[ContentType("text")]  
internal class TestCompletionSourceProvider : ICompletionSourceProvider  
```  
  
 Další informace o implementaci zdroje IntelliSense viz následující kurzy:  
  
 [Návod: Zobrazení popisů tlačítek s rychlými informacemi](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)  
  
 [Návod: Zobrazení vyhrazené nápovědy](../extensibility/walkthrough-displaying-signature-help.md)  
  
 [Návod: Zobrazení dokončování příkazů](../extensibility/walkthrough-displaying-statement-completion.md)  
  
### <a name="implementing-an-intellisense-controller"></a>Implementace řadič IntelliSense  
 Chcete-li přizpůsobit řadič, je nutné implementovat <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController> rozhraní. Kromě toho musí implementovat zprostředkovatele kontroleru společně s následujícími atributy:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: název kontroleru.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: typ obsahu (například "text" nebo "kódu"), na které se vztahuje na řadič.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: pořadí, ve kterém by se měla objevit řadičem (s ohledem na ostatní řadiče).  
  
 Následující příklad ukazuje atributy export na dokončení řadiče zprostředkovatele.  
  
```  
Export(typeof(IIntellisenseControllerProvider))]  
[Name(" Test Controller Provider")]  
[Order(Before = "default")]  
[ContentType("text")]  
internal class TestIntellisenseControllerProvider : IIntellisenseControllerProvider  
```  
  
 Další informace o používání řadiče IntelliSense najdete v následující kurzy:  
  
 [Návod: Zobrazení popisů tlačítek s rychlými informacemi](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)