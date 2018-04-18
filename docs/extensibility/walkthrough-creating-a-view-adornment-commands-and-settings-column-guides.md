---
title: Vytvoření dalších úprav zobrazení, příkazy a nastavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 4a2df0a3-42da-4f7b-996f-ee16a35ac922
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 57a7696eae0da92d88babf64c580a4767775dffd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-view-adornment-commands-and-settings-column-guides"></a>Návod: Vytvoření dalších úprav zobrazení, příkazy a nastavení (vodítka sloupců)
Můžete rozšířit editor text/kódu Visual Studio s příkazy a zobrazit důsledky.  Toto téma ukazuje, jak začít pracovat s funkcí oblíbených rozšíření, vodítka sloupců.  Vodítka sloupce jsou vizuálně světla čáry vykreslené zobrazení textového editoru vám pomůžou spravovat svůj kód šířky konkrétní sloupců.  Konkrétně formátovaný kód může být důležité pro ukázky zahrnout v dokumentech, příspěvky blogu nebo chyb sestavy.  
  
 V tomto návodu budete:  
  
-   Vytvoření projektu VSIX  
  
-   Přidání dalších úprav editoru zobrazení  
  
-   Přidání podpory pro ukládání a načítání nastavení (kde pro kreslení vodítka sloupců a jejich barvu)  
  
-   Přidání příkazů (Přidat nebo odebrat sloupce příručky, změnit jejich barvu)  
  
-   Umístěte příkazy v nabídce Upravit a text dokumentu kontextové nabídky  
  
-   Přidání podpory pro vyvolání příkazů z příkazové okno Visual Studio  
  
 Můžete vyzkoušet verzi funkce vodítka sloupec s Tato galerie sady Visual Studio[rozšíření](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home).  
  
 **Poznámka:**: v tomto návodu můžete vložit velké množství kódu do několika souborů vygenerované šablony sady visual studio rozšíření, ale brzy bude Tento názorný postup odkazovat na dokončeného řešení na githubu s další příklady rozšíření.  Dokončený kód se mírně liší v tom, že má skutečné příkaz ikony místo použití generictemplate ikony.  
  
## <a name="getting-started"></a>Začínáme  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="setting-up-the-solution"></a>Nastavit řešení  
 Nejprve vytvořte projekt VSIX, přidáte dalších úprav editoru zobrazení a poté přidejte příkaz (který přidá VSPackage udělil příkaz).  Základní architektura vypadá takto:  
  
-   Máte naslouchací proces vytváření zobrazení textu, který vytvoří `ColumnGuideAdornment` objektu na zobrazení.  Tento objekt naslouchá událostem o změně zobrazení nebo změna nastavení, provede aktualizaci nebo překreslování sloupec podle potřeby.  
  
-   Došlo `GuidesSettingsManager` která zpracovává čtení a zápis z úložiště nastavení sady Visual Studio.  Správce nastavení také obsahuje operace pro aktualizaci nastavení, které podporují příkazy uživatele (sloupec přidat, odebrat sloupec, změnit barvu).  
  
-   Je VSIP balíček, který je nezbytný, pokud máte uživatele příkazy, ale je stejně často používaný kód, který inicializuje objekt implementace příkazy.  
  
-   Došlo `ColumnGuideCommands` objekt, který implementuje příkazy uživatele a zachytí až obslužné rutiny příkazů pro příkazy deklarován v souboru .vsct.  
  
 **VSIX**.  Použití **soubor &#124; nové...**  příkaz k vytvoření projektu.  V levém navigačním podokně vyberte uzel rozšiřitelnost v C# a zvolte **projektu VSIX** v pravém podokně.  Zadejte název ColumnGuides a zvolte **OK** a vytvořte tak projekt.  
  
 **Zobrazení dalších úprav**.  Klikněte na tlačítko správné ukazatel na uzel projektu v Průzkumníku řešení.  Vyberte **přidat &#124; novou položku...**  příkaz pro přidání nové položky zobrazení dalších úprav.  Zvolte **rozšiřitelnost &#124; Editor** v levém navigačním podokně a zvolte **dalších úprav editoru zobrazení** v pravém podokně.  Zadejte název ColumnGuideAdornment jako název položky a zvolte **přidat** ho přidejte.  
  
 Uvidíte, tato šablona položku Přidat do projektu (a také odkazy a tak dále) dva soubory: ColumnGuideAdornment.cs a ColumnGuideAdornmentTextViewCreationListener.cs.  Šablony právě kreslení fialové obdélníku v zobrazení.  Níže změníte pár řádků v naslouchací proces vytváření zobrazení a nahraďte jeho obsah ColumnGuideAdornment.cs.  
  
 **Příkazy**.  Klikněte na tlačítko správné ukazatel na uzel projektu v Průzkumníku řešení.  Vyberte **přidat &#124; novou položku...**  příkaz pro přidání nové položky zobrazení dalších úprav.  Zvolte **rozšiřitelnost &#124; VSPackage** v levém navigačním podokně a zvolte **vlastní příkaz** v pravém podokně.  Zadejte název ColumnGuideCommands jako název položky a zvolte **přidat** ho přidejte.  Kromě několik odkazů přidávání příkazů a balíček přidat ColumnGuideCommands.cs, ColumnGuideCommandsPackage.cs a ColumnGuideCommandsPackage.vsct.  Níže nahradíte obsah první a poslední souborů vymezit a provádět příkazy.  
  
## <a name="setting-up-the-text-view-creation-listener"></a>Nastavení naslouchacího procesu vytváření zobrazení textu  
 ColumnGuideAdornmentTextViewCreationListener.cs otevře v editoru.  Tento kód implementuje obslužnou rutinu pro vždy, když Visual Studio vytvoří zobrazení textu.  Existují atributy, které řídí, kdy se nazývá obslužná rutina v závislosti na vlastnosti zobrazení.  
  
 Kód také je třeba deklarovat s vrstvou dalších úprav.  Když editoru aktualizuje zobrazení, získá vrstvy dalších úprav pro zobrazení a od získá elementy dalších úprav.  Je možné deklarovat řazení vrstvě vůči ostatním s atributy.  Nahraďte tento řádek:  
  
```csharp  
[Order(After = PredefinedAdornmentLayers.Caret)]  
```  
  
 s tyto dva řádky:  
  
```csharp  
[Order(Before = PredefinedAdornmentLayers.Text)]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
```  
  
 Řádek, který můžete nahradit se nachází ve skupině atributů, které deklarovat vrstvu dalších úprav.   První řádek změnit pouze změny provedené, kde se zobrazí Průvodce řádky sloupce.  Kreslení čar "před" text v zobrazení znamená, že se objeví za nebo pod text.  Druhý řádek deklaruje, že vylepšení Průvodce sloupec se dají použít pro entity text, odpovídající vaší představu o dokument, ale může deklarovat dalších úprav, například k fungovat pouze pro upravovat text.  Další informace naleznete v [služba jazyka a body rozšíření editoru](../extensibility/language-service-and-editor-extension-points.md)  
  
## <a name="implementing-the-settings-manager"></a>Implementace nastavení správce  
 Obsah GuidesSettingsManager.cs nahraďte následujícím kódem (vysvětlení níže):  
  
```csharp  
using Microsoft.VisualStudio.Settings;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Settings;  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows.Media;  
  
namespace ColumnGuides  
{  
    internal static class GuidesSettingsManager  
    {  
        // Because my code is always called from the UI thred, this succeeds.  
        internal static SettingsManager VsManagedSettingsManager =  
            new ShellSettingsManager(ServiceProvider.GlobalProvider);  
  
        private const int _maxGuides = 5;  
        private const string _collectionSettingsName = "Text Editor";  
        private const string _settingName = "Guides";  
        // 1000 seems reasonable since primary scenario is long lines of code  
        private const int _maxColumn = 1000;   
  
        static internal bool AddGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column",  
                    "The paramenter must be between 1 and " + _maxGuides.ToString());  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            if (offsets.Count() >= _maxGuides)  
                return false;  
            // Check for duplicates  
            if (offsets.Contains(column))  
                return false;  
            offsets.Add(column);  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, offsets);  
            return true;  
        }  
  
        static internal bool RemoveGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column", "The paramenter must be between 1 and 10,000");  
            var columns = GuidesSettingsManager.GetColumnOffsets();  
            if (! columns.Remove(column))  
            {  
                // Not present.  Allow user to remove the last column   
                // even if they're not on the right column.  
                if (columns.Count != 1)  
                    return false;  
  
                columns.Clear();  
            }  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, columns);  
            return true;  
        }  
  
        static internal bool CanAddGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                return false;  
            var offsets = GetColumnOffsets();  
            if (offsets.Count >= _maxGuides)  
                return false;  
            return ! offsets.Contains(column);  
        }  
  
        static internal bool CanRemoveGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                return false;  
            // Allow user to remove the last guideline regardless of the column.  
            // Okay to call count, we limit the number of guides.  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            return offsets.Contains(column) || offsets.Count() == 1;  
        }  
  
        static internal void RemoveAllGuidelines()  
        {  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, new int[0]);  
        }  
  
        private static bool IsValidColumn(int column)  
        {  
            // zero is allowed (per user request)  
            return 0 <= column && column <= _maxColumn;  
        }  
  
        // This has format "RGB(<int>, <int>, <int>) <int> <int>...".  
        // There can be any number of ints following the RGB part,   
        // and each int is a column (char offset into line) where to draw.  
        static private string _guidelinesConfiguration;  
        static private string GuidelinesConfiguration  
        {  
            get  
            {  
                if (_guidelinesConfiguration == null)  
                {  
                    _guidelinesConfiguration =   
                        GetUserSettingsString(  
                            GuidesSettingsManager._collectionSettingsName,  
                            GuidesSettingsManager._settingName)  
                        .Trim();  
                }  
                return _guidelinesConfiguration;  
            }  
  
            set  
            {  
                if (value != _guidelinesConfiguration)  
                {  
                    _guidelinesConfiguration = value;  
                    WriteUserSettingsString(  
                        GuidesSettingsManager._collectionSettingsName,  
                        GuidesSettingsManager._settingName, value);  
                    // Notify ColumnGuideAdornments to update adornments in views.  
                    var handler = GuidesSettingsManager.SettingsChanged;  
                    if (handler != null)  
                        handler();  
                }  
            }  
        }  
  
        internal static string GetUserSettingsString(string collection, string setting)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetReadOnlySettingsStore(SettingsScope.UserSettings);  
            return store.GetString(collection, setting, "RGB(255,0,0) 80");  
        }  
  
        internal static void WriteUserSettingsString(string key, string propertyName,  
                                                     string value)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetWritableSettingsStore(SettingsScope.UserSettings);  
            store.CreateCollection(key);  
            store.SetString(key, propertyName, value);  
        }  
  
        // Persists settings and sets property with side effect of signaling  
        // ColumnGuideAdornments to update.  
        static private void WriteSettings(Color color, IEnumerable<int> columns)  
        {  
            string value = ComposeSettingsString(color, columns);  
            GuidelinesConfiguration = value;  
        }  
  
        private static string ComposeSettingsString(Color color,  
                                                    IEnumerable<int> columns)  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendFormat("RGB({0},{1},{2})", color.R, color.G, color.B);  
            IEnumerator<int> columnsEnumerator = columns.GetEnumerator();  
            if (columnsEnumerator.MoveNext())  
            {  
                sb.AppendFormat(" {0}", columnsEnumerator.Current);  
                while (columnsEnumerator.MoveNext())  
                {  
                    sb.AppendFormat(", {0}", columnsEnumerator.Current);  
                }  
            }  
            return sb.ToString();  
        }  
  
        // Parse a color out of a string that begins like "RGB(255,0,0)"  
        static internal Color GuidelinesColor  
        {  
            get  
            {  
                string config = GuidelinesConfiguration;  
                if (!String.IsNullOrEmpty(config) && config.StartsWith("RGB("))  
                {  
                    int lastParen = config.IndexOf(')');  
                    if (lastParen > 4)  
                    {  
                        string[] rgbs = config.Substring(4, lastParen - 4).Split(',');  
  
                        if (rgbs.Length >= 3)  
                        {  
                            byte r, g, b;  
                            if (byte.TryParse(rgbs[0], out r) &&  
                                byte.TryParse(rgbs[1], out g) &&  
                                byte.TryParse(rgbs[2], out b))  
                            {  
                                return Color.FromRgb(r, g, b);  
                            }  
                        }  
                    }  
                }  
                return Colors.DarkRed;  
            }  
  
            set  
            {  
                WriteSettings(value, GetColumnOffsets());  
            }  
        }  
  
        // Parse a list of integer values out of a string that looks like  
        // "RGB(255,0,0) 1, 5, 10, 80"  
        static internal List<int> GetColumnOffsets()  
        {  
            var result = new List<int>();  
            string settings = GuidesSettingsManager.GuidelinesConfiguration;  
            if (String.IsNullOrEmpty(settings))  
                return new List<int>();  
  
            if (!settings.StartsWith("RGB("))  
                return new List<int>();  
  
            int lastParen = settings.IndexOf(')');  
            if (lastParen <= 4)  
                return new List<int>();  
  
            string[] columns = settings.Substring(lastParen + 1).Split(',');  
  
            int columnCount = 0;  
            foreach (string columnText in columns)  
            {  
                int column = -1;  
                // VS 2008 gallery extension didn't allow zero, so per user request ...  
                if (int.TryParse(columnText, out column) && column >= 0)  
                {  
                    columnCount++;  
                    result.Add(column);  
                    if (columnCount >= _maxGuides)  
                        break;  
                }  
            }  
            return result;  
        }  
  
        // Delegate and Event to fire when settings change so that ColumnGuideAdornments   
        // can update.  We need nothing special in this event since the settings manager   
        // is statically available.  
        //  
        internal delegate void SettingsChangedHandler();  
        static internal event SettingsChangedHandler SettingsChanged;  
  
    }  
}  
  
```  
  
 Většina tento kód jenom vytvoří a analyzuje nastavení formátu: "RGB (\<int >,\<int >,\<int >) \<int >, \<int >,...".  Celá čísla na konci jsou základem jedna sloupců místo vodítka sloupců.  Rozšíření příručky sloupec zaznamená všechna nastavení v jednom nastavení řetězec.  
  
 Existují některé části kódu vhodné zvýraznění.  Následující kód získá sady Visual Studio spravovaná obálka pro nastavení úložiště.  Ve většině případů to abstrahuje přes registru systému Windows, ale toto rozhraní API je nezávislé na mechanismus úložiště.  
  
```csharp  
internal static SettingsManager VsManagedSettingsManager =  
    new ShellSettingsManager(ServiceProvider.GlobalProvider);  
```  
  
 Nastavení úložiště Visual Studio používá k jedinečné identifikaci všechna nastavení identifikátor kategorie a identifikátor nastavení:  
  
```csharp  
private const string _collectionSettingsName = "Text Editor";  
private const string _settingName = "Guides";  
```  
  
 Není nutné používat `"Text Editor"` jako kategorie název a můžete si vybrat jakkoli chcete.  
  
 První několik funkcí jsou vstupní body, chcete-li změnit nastavení.  Jejich zkontrolujte souhrnné omezení jako maximální počet příručky povoleny.  Potom volání `WriteSettings` který vytvoří řetězec nastavení a nastaví vlastnost `GuideLinesConfiguration`.  Nastavení této vlastnosti uloží hodnotu nastavení do sady Visual Studio nastavení úložiště a aktivuje se `SettingsChanged` na Aktualizovat všechny události `ColumnGuideAdornment` objekty, každý přidružený k zobrazení textu.  
  
 Existují dvě vstupní bod funkce, jako například `CanAddGuideline`, které se používají k implementaci příkazy, které mění nastavení.  Když Visual Studio zobrazí nabídky, vyžádá si implementace příkazu zobrazíte, pokud příkaz momentálně je zapnutá, co je jeho název, atd.  Níže se zobrazí postup spojit tyto vstupní body pro implementace příkazu.  V tématu [rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md) Další informace o příkazech.  
  
## <a name="implementing-the-columnguideadornment-class"></a>Implementace ColumnGuideAdornment – třída  
 `ColumnGuideAdornment` Vytvoření instance třídy pro každý textového zobrazení, která může mít vylepšení.  Tato třída naslouchá událostem o změně zobrazení nebo změna nastavení, provede aktualizaci nebo překreslování sloupec podle potřeby.  
  
 Obsah ColumnGuideAdornment.cs nahraďte následujícím kódem (vysvětlení níže):  
  
```csharp  
using System;  
using System.Windows.Media;  
using Microsoft.VisualStudio.Text.Editor;  
using System.Collections.Generic;  
using System.Windows.Shapes;  
using Microsoft.VisualStudio.Text.Formatting;  
using System.Windows;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Adornment class, one instance per text view that draws a guides on the viewport  
    /// </summary>  
    internal sealed class ColumnGuideAdornment  
    {  
        private const double _lineThickness = 1.0;  
        private IList<Line> _guidelines;  
        private IWpfTextView _view;  
        private double _baseIndentation;  
        private double _columnWidth;  
  
        /// <summary>  
        /// Creates editor column guidelines  
        /// </summary>  
        /// <param name="view">The <see cref="IWpfTextView"/> upon   
        /// which the adornment will be drawn</param>  
        public ColumnGuideAdornment(IWpfTextView view)  
        {  
            _view = view;  
            _guidelines = CreateGuidelines();  
            GuidesSettingsManager.SettingsChanged +=   
                new GuidesSettingsManager.SettingsChangedHandler(SettingsChanged);  
            view.LayoutChanged +=   
                new EventHandler<TextViewLayoutChangedEventArgs>(OnViewLayoutChanged);  
            _view.Closed += new EventHandler(OnViewClosed);  
        }  
  
        void SettingsChanged()  
        {  
            _guidelines = CreateGuidelines();  
            UpdatePositions();  
            AddGuidelinesToAdornmentLayer();  
        }  
  
        void OnViewClosed(object sender, EventArgs e)  
        {  
            _view.LayoutChanged -= OnViewLayoutChanged;  
            _view.Closed -= OnViewClosed;  
            GuidesSettingsManager.SettingsChanged -= SettingsChanged;  
        }  
  
        private bool _firstLayoutDone;  
  
        void OnViewLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
        {  
            bool fUpdatePositions = false;  
  
            IFormattedLineSource lineSource = _view.FormattedLineSource;  
            if (lineSource == null)  
            {  
                return;  
            }  
            if (_columnWidth != lineSource.ColumnWidth)  
            {  
                _columnWidth = lineSource.ColumnWidth;  
                fUpdatePositions = true;  
            }  
            if (_baseIndentation != lineSource.BaseIndentation)  
            {  
                _baseIndentation = lineSource.BaseIndentation;  
                fUpdatePositions = true;  
            }  
            if (fUpdatePositions ||  
                e.VerticalTranslation ||  
                e.NewViewState.ViewportTop != e.OldViewState.ViewportTop ||  
                e.NewViewState.ViewportBottom != e.OldViewState.ViewportBottom)  
            {  
                UpdatePositions();  
            }  
            if (!_firstLayoutDone)  
            {  
                AddGuidelinesToAdornmentLayer();  
                _firstLayoutDone = true;  
            }  
        }  
  
        private static IList<Line> CreateGuidelines()  
        {  
            Brush lineBrush = new SolidColorBrush(GuidesSettingsManager.GuidelinesColor);  
            DoubleCollection dashArray = new DoubleCollection(new double[] { 1.0, 3.0 });  
            IList<Line> result = new List<Line>();  
            foreach (int column in GuidesSettingsManager.GetColumnOffsets())  
            {  
                Line line = new Line()  
                {  
                    // Use the DataContext slot as a cookie to hold the column  
                    DataContext = column,  
                    Stroke = lineBrush,  
                    StrokeThickness = _lineThickness,  
                    StrokeDashArray = dashArray  
                };  
                result.Add(line);  
            }  
            return result;  
        }  
  
        void UpdatePositions()  
        {  
            foreach (Line line in _guidelines)  
            {  
                int column = (int)line.DataContext;  
                line.X2 = _baseIndentation + 0.5 + column * _columnWidth;  
                line.X1 = line.X2;  
                line.Y1 = _view.ViewportTop;  
                line.Y2 = _view.ViewportBottom;  
            }  
        }  
  
        void AddGuidelinesToAdornmentLayer()  
        {  
            // Grab a reference to the adornment layer that this adornment   
            // should be added to  
            // Must match exported name in ColumnGuideAdornmentTextViewCreationListener  
            IAdornmentLayer adornmentLayer =   
                _view.GetAdornmentLayer("ColumnGuideAdornment");  
            if (adornmentLayer == null)  
                return;  
            adornmentLayer.RemoveAllAdornments();  
            // Add the guidelines to the adornment layer and make them relative   
            // to the viewport  
            foreach (UIElement element in _guidelines)  
                adornmentLayer.AddAdornment(AdornmentPositioningBehavior.OwnerControlled,  
                                            null, null, element, null);  
        }  
    }  
  
}  
```  
  
 Instance této třídy uložení do přidruženého <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> a seznam `Line` objekty, které jsou vykreslovány v zobrazení.  
  
 V konstruktoru (volat z `ColumnGuideAdornmentTextViewCreationListener` když Visual Studio vytvoří nová zobrazení) vytvoří Průvodce sloupec `Line` objekty.  Konstruktor také přidá obslužné rutiny pro `SettingsChanged` událostí (definované v `GuidesSettingsManager`) a zobrazit události `LayoutChanged` a `Closed`.  
  
 `LayoutChanged` Aktivuje událost z důvodu několik druhů změny v zobrazení, včetně když Visual Studio vytvoří zobrazení.  `OnViewLayoutChanged` Volání obslužné rutiny `AddGuidelinesToAdornmentLayer` provést.  Kód v `OnViewLayoutChanged` Určuje, jestli je třeba aktualizovat pozice řádku na základě změn například změní velikost písma, zobrazení mezery, vodorovného posouvání a tak dále.  Kód v `UpdatePositions` způsobí, že průvodce řádky k vykreslení mezi znaky nebo bezprostředně za sloupec text, který je v posunu zadaný znak v řádku textu.  
  
 Vždy, když nastavení změnit `SettingsChanged` vytvoří všechny funkce jenom `Line` objekty se aktivují nové nastavení.  Po nastavení pozice řádku, odebere všechna předchozí kód `Line` objekty z `ColumnGuideAdornment` dalších úprav vrstvy a přidá nové.  
  
## <a name="defining-the-commands-menus-and-menu-placements"></a>Definování příkazy, nabídky a umísťováním nabídky  
 Může být mnohem deklarace příkazy a nabídky, umístěním skupin příkazy nebo nabídky na různých jiných nabídek a zapojování obslužné rutiny příkazů.  Tento názorný postup označuje, jak fungují příkazy v tomto rozšíření, ale pro podrobnější informace najdete v tématu [rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md).  
  
### <a name="introduction-to-the-code"></a>Úvod do kódu  
 Rozšíření příručky sloupec zobrazuje deklarace skupinu příkazů, které patří společně (sloupec přidat, odebrat sloupec, změnit barvu čáry) a pak uvedení této skupiny na dílčí nabídky editoru kontextové nabídky.  Rozšíření vodítka sloupců také přidá příkazy do hlavní **upravit** nabídky ale zajišťuje jejich neviditelná, jako běžný vzor níže popsané.  
  
 Existují tři části implementace příkazů: ColumnGuideCommandsPackage.cs, ColumnGuideCommandsPackage.vsct a ColumnGuideCommands.cs.  Kód vygenerovaný šablony příkaz umístí **nástroje** nabídce, která se objeví dialogové okno jako implementace.  Můžete si prohlédnout jak která je implementovaná v souborech ColumnGuideCommands.cs a .vsct vzhledem k tomu, že je poměrně jednoduché.  Nahradíte kód v těchto souborech níže.  
  
 Balíček kódu je často používaný deklarace, které jsou požadovány pro sadu Visual Studio ke zjištění, zda rozšíření nabízí příkazy a kam umístit příkazy.  Pokud balíček inicializuje, vytvoří instanci třída implementace příkazy.  Podívejte se na příkazy výše na odkaz Další informace o balíčcích týkající se příkazy.  
  
### <a name="a-common-commands-pattern"></a>Běžný vzor příkazy  
 Příkazy v rozšíření vodítka sloupců jsou příklad velmi běžný vzor v sadě Visual Studio.  Zadejte související příkazy do skupiny, a vložíte této skupiny na hlavní nabídky, často se "`<CommandFlag>CommandWellOnly</CommandFlag>`" nastavena na nastavit jako neviditelné příkaz.  Vložení příkazy na hlavní nabídky (, jako **upravit**) tímto způsobem jim poskytne dobrý názvy (například **Edit.AddColumnGuide**) které jsou užitečné pro vyhledávání příkazy při přiřazování znovu vazeb klíče v  **Možnosti nástrojů** a získání dokončení při vyvolání příkazů z **příkazové okno**.  
  
 Přidat skupinu příkazů do kontextové nabídky nebo sub nabídky kde očekáváte, může uživatel používat příkazy.  Visual Studio zpracuje `CommandWellOnly` jako neviditelnosti příznak pro pouze hlavní nabídky.  Při umístění na stejnou skupinu příkazů v místní nabídce nebo dílčí nabídky, příkazy jsou viditelné.  
  
 Rozšíření vodítka sloupců v rámci běžných vzor, vytvoří druhé skupiny, která obsahuje jednu odebíraného nabídky.  V nabídce dílčí zase obsahuje první skupinu pomocí Průvodce příkazů čtyři sloupce.  Druhé skupině, která obsahuje dílčí nabídky je opakovaně použitelné asset, který můžete umístit na různé kontextové nabídky, který převádí dílčí nabídky na tyto kontextové nabídky.  
  
### <a name="the-vsct-file"></a>Soubor .vsct  
 Soubor .vsct deklaruje příkazy a kde přejde, společně s ikony a tak dále.  Nahraďte obsah souboru .vsct následujícím kódem (vysvětlení níže):  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <!--  This is the file that defines the actual layout and type of the commands.  
        It is divided in different sections (e.g. command definition, command  
        placement, ...), with each defining a specific set of properties.  
        See the comment before each section for more details about how to  
        use it. -->  
  
  <!--  The VSCT compiler (the tool that translates this file into the binary  
        format that VisualStudio will consume) has the ability to run a preprocessor  
        on the vsct file; this preprocessor is (usually) the C++ preprocessor, so  
        it is possible to define includes and macros with the same syntax used  
        in C++ files. Using this ability of the compiler here, we include some files  
        defining some of the constants that we will use inside the file. -->  
  
  <!--This is the file that defines the IDs for all the commands exposed by   
      VisualStudio. -->  
  <Extern href="stdidcmd.h"/>  
  
  <!--This header contains the command ids for the menus provided by the shell. -->  
  <Extern href="vsshlids.h"/>  
  
  <!--The Commands section is where commands, menus, and menu groups are defined.  
      This section uses a Guid to identify the package that provides the command   
      defined inside it. -->  
  <Commands package="guidColumnGuideCommandsPkg">  
    <!-- Inside this section we have different sub-sections: one for the menus, another    
    for the menu groups, one for the buttons (the actual commands), one for the combos   
    and the last one for the bitmaps used. Each element is identified by a command id  
    that is a unique pair of guid and numeric identifier; the guid part of the identifier  
    is usually called "command set" and is used to group different command inside a  
    logically related group; your package should define its own command set in order to  
    avoid collisions with command ids defined by other packages. -->  
  
    <!-- In this section you can define new menu groups. A menu group is a container for   
         other menus or buttons (commands); from a visual point of view you can see the   
         group as the part of a menu contained between two lines. The parent of a group   
         must be a menu. -->  
    <Groups>  
  
      <!-- The main group is parented to the edit menu. All the buttons within the group  
           have the "CommandWellOnly" flag, so they're actually invisible, but it means  
           they get canonical names that begin with "Edit". Using placements, the group  
           is also placed in the GuidesSubMenu group. -->  
      <!-- The priority 0xB801 is chosen so it goes just after   
           IDG_VS_EDIT_COMMANDWELL -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
      <!-- Group for holding the "Guidelines" sub-menu anchor (the item on the menu that  
           drops the sub menu). The group is parented to  
           the context menu for code windows. That takes care of most editors, but it's  
           also placed in a couple of other windows using Placements -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_CTXT_CODEWIN" />  
      </Group>  
  
    </Groups>  
  
    <Menus>  
      <Menu guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" priority="0x1000"  
            type="Menu">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup" />  
        <Strings>  
          <ButtonText>&Column Guides</ButtonText>  
        </Strings>  
      </Menu>  
    </Menus>  
  
    <!--Buttons section. -->  
    <!--This section defines the elements the user can interact with, like a menu command or a button   
        or combo box in a toolbar. -->  
    <Buttons>  
      <!--To define a menu group you have to specify its ID, the parent menu and its   
          display priority.   
          The command is visible and enabled by default. If you need to change the   
          visibility, status, etc, you can use the CommandFlag node.  
          You can add more than one CommandFlag node e.g.:  
              <CommandFlag>DefaultInvisible</CommandFlag>  
              <CommandFlag>DynamicVisibility</CommandFlag>  
          If you do not want an image next to your command, remove the Icon node or   
          set it to <Icon guid="guidOfficeIcon" id="msotcidNoIcon" /> -->  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
              priority="0x0100" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicAddGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Add Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveColumnGuide"   
              priority="0x0101" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicRemoveGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Remove Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidChooseGuideColor"   
              priority="0x0103" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicChooseColor" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Column Guide &Color...</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveAllColumnGuides"   
              priority="0x0102" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Remove A&ll Columns</ButtonText>  
        </Strings>  
      </Button>  
    </Buttons>  
  
    <!--The bitmaps section is used to define the bitmaps that are used for the  
        commands.-->  
    <Bitmaps>  
      <!--  The bitmap id is defined in a way that is a little bit different from the  
            others:   
            the declaration starts with a guid for the bitmap strip, then there is the  
            resource id of the bitmap strip containing the bitmaps and then there are   
            the numeric ids of the elements used inside a button definition. An important  
            aspect of this declaration is that the element id   
            must be the actual index (1-based) of the bitmap inside the bitmap strip. -->  
      <Bitmap guid="guidImages" href="Resources\ColumnGuideCommands.png"   
              usedList="bmpPicAddGuide, bmpPicRemoveGuide, bmpPicChooseColor" />  
    </Bitmaps>  
  
  </Commands>  
  
  <CommandPlacements>  
  
    <!-- Define secondary placements for our groups -->  
  
    <!-- Place the group containing the three commands in the sub-menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                      priority="0x0100">  
      <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
    </CommandPlacement>  
  
    <!-- The HTML editor context menu, for some reason, redefines its own groups  
         so we need to place a copy of our context menu there too. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_HTML" />  
    </CommandPlacement>  
  
    <!-- The HTML context menu in Dev12 changed. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp_Dev12" id="IDMX_HTM_SOURCE_HTML_Dev12" />  
    </CommandPlacement>  
  
    <!-- Similarly for Script -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_SCRIPT" />  
    </CommandPlacement>  
  
    <!-- Similarly for ASPX  -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_ASPX" />  
    </CommandPlacement>  
  
    <!-- Similarly for the XAML editor context menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x0600">  
      <Parent guid="guidXamlUiCmds" id="IDM_XAML_EDITOR" />  
    </CommandPlacement>  
  
  </CommandPlacements>  
  
  <!-- This defines the identifiers and their values used above to index resources  
       and specify commands. -->  
  <Symbols>  
    <!-- This is the package guid. -->  
    <GuidSymbol name="guidColumnGuideCommandsPkg"   
                value="{e914e5de-0851-4904-b361-1a3a9d449704}" />  
  
    <!-- This is the guid used to group the menu commands together -->  
    <GuidSymbol name="guidColumnGuidesCommandSet"   
                value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
      <IDSymbol name="GuidesContextMenuGroup" value="0x1020" />  
      <IDSymbol name="GuidesMenuItemsGroup" value="0x1021" />  
      <IDSymbol name="GuidesSubMenu" value="0x1022" />  
      <IDSymbol name="cmdidAddColumnGuide" value="0x0100" />  
      <IDSymbol name="cmdidRemoveColumnGuide" value="0x0101" />  
      <IDSymbol name="cmdidChooseGuideColor" value="0x0102" />  
      <IDSymbol name="cmdidRemoveAllColumnGuides" value="0x0103" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
      <IDSymbol name="bmpPicAddGuide" value="1" />  
      <IDSymbol name="bmpPicRemoveGuide" value="2" />  
      <IDSymbol name="bmpPicChooseColor" value="3" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp_Dev12"   
                value="{78F03954-2FB8-4087-8CE7-59D71710B3BB}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML_Dev12" value="0x1" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp" value="{d7e8c5e1-bdb8-11d0-9c88-0000f8040a53}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML" value="0x33" />  
      <IDSymbol name="IDMX_HTM_SOURCE_SCRIPT" value="0x34" />  
      <IDSymbol name="IDMX_HTM_SOURCE_ASPX" value="0x35" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidXamlUiCmds" value="{4c87b692-1202-46aa-b64c-ef01faec53da}">  
      <IDSymbol name="IDM_XAML_EDITOR" value="0x103" />  
    </GuidSymbol>  
  </Symbols>  
  
</CommandTable>  
  
```  
  
 **IDENTIFIKÁTORY GUID**.  Pro sadu Visual Studio můžete najít vaší obslužné rutiny příkazů a je vyvolat je potřeba zajistit, že balíčku, který GUID deklarován v souboru ColumnGuideCommandsPackage.cs (vygenerovaná ze šablony položek projektu) odpovídá balíčku, který GUID deklarován v souboru .vsct (zkopírovat z výše ).  Pokud chcete znovu použít tento ukázkový kód, musí se zkontrolujte, zda že máte jiný identifikátor GUID tak, aby nedošlo ke konfliktu s nikým Nesdílet, kdo může zkopírovali tento kód.  
  
 Tento řádek v ColumnGuideCommandsPackage.cs najít a zkopírovat identifikátor GUID, které uvozovek:  
  
```csharp  
public const string PackageGuidString = "ef726849-5447-4f73-8de5-01b9e930f7cd";  
```  
  
 Vložte identifikátor GUID v souboru .vsct tak, aby měli následující řádek vaší `Symbols` deklarace:  
  
```xml  
<GuidSymbol name="guidColumnGuideCommandsPkg"   
            value="{ef726849-5447-4f73-8de5-01b9e930f7cd}" />  
```  
  
 Identifikátory GUID pro příkaz nastavit a rastrového obrázku musí být jedinečná pro rozšíření příliš:  
  
```xml  
<GuidSymbol name="guidColumnGuidesCommandSet"   
            value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
<GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
```  
  
 Není ale nutné změnit sadu příkazů nástroje a bitmap identifikátory GUID bitové kopie v tomto návodu získat kód pro práci.  Příkaz nastavit GUID musí odpovídat deklarace v souboru ColumnGuideCommands.cs, ale nahradí obsah tohoto souboru příliš; proto bude shodovat s identifikátory GUID.  
  
 Další identifikátory GUID v souboru .vsct identifikovány existující nabídky, do které jsou přidány sloupce Průvodce příkazy, nikdy nezmění.  
  
 **Soubor části**.  .vsct má tři části vnější: příkazy, umísťováním a symboly.  V části příkazy definuje příkaz skupin, nabídky, tlačítek nebo položek nabídky a rastrových obrázků pro ikony.  V části umísťováním deklaruje, kde skupiny přejděte na nabídky nebo další umísťováním do již existující nabídky.  V části symboly deklaruje identifikátory používané jinde v .vsct souboru, který umožňuje kód .vsct srozumitelnější než everywhere s identifikátory GUID a šestnáctkových číslic.  
  
 **Příkazy části, definice skupin**.  V části příkazy nejdřív definuje příkaz skupiny.  Příkazy, které se zobrazí v nabídkách mírné šedé řádků oddělení skupiny jsou skupiny příkazů.  Skupinu může také zadat hodnoty nabídce celý dílčí jako v následujícím příkladě a nevidíte na šedý symbol v tomto případě oddělení řádky.  Soubory .vsct deklaruje dvě skupiny, `GuidesMenuItemsGroup` , je nadřazena k `IDM_VS_MENU_EDIT` (hlavní **upravit** nabídky) a `GuidesContextMenuGroup` , je nadřazena k `IDM_VS_CTXT_CODEWIN` (editoru kódu Kontextová nabídka).  
  
 Má druhý deklarace skupiny `0x0600` priority:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
```  
  
 Cílem je uvést sloupec provede dílčí nabídky na konci z jakékoli kontextové nabídky, do které přidáme skupině dílčí nabídky.  Ale nesmí předpokládá vědět, co nejlépe a vynutit dílčí nabídky vždycky být poslední pomocí prioritu `0xFFFF`.  Máte k přehrání s tímto číslem zobrazíte, kde je dílčí nabídka na kontextové nabídky, kam umístit.  V takovém případě `0x0600` je dostatečně vysoký, uvést na konci v nabídkách jde uvidíme, ale ponechá prostor pro někdo návrhu svého rozšíření pro být nižší než rozšíření příručky sloupce, pokud je žádoucí.  
  
 **Příkazy nabídky definice části**.  Další příkaz oddíl definuje dílčí nabídky `GuidesSubMenu`, k nadřazeným prvkem `GuidesContextMenuGroup`.  `GuidesContextMenuGroup` Je skupina přidáme na všechny příslušné místní nabídky.  V části umísťováním kód umístí skupinu pomocí Průvodce příkazů čtyři sloupce v této nabídce sub.  
  
 **Příkazy části, tlačítka definice**.  V části příkazy pak definuje položky nabídky nebo provede příkazy tlačítek, které jsou čtyři sloupce.  `CommandWellOnly`, výše popsané, znamená příkazy jsou neviditelná po na hlavní nabídky.  Dvě položky nabídky tlačítko deklarace (Průvodce přidat a odebrat průvodce) také `AllowParams` příznak:  
  
```xml  
<CommandFlag>AllowParams</CommandFlag>  
```  
  
 Tento příznak umožňuje spolu s s umísťováním hlavní nabídky, příkaz příjmu argumenty, když Visual Studio vyvolá obslužná rutina příkazu.  Pokud uživatel spustí příkaz z příkazového řádku, argument předána do obslužná rutina události argumenty.  
  
 **Příkaz oddíly, rastrové obrázky definice**.  Nakonec části příkazy deklaruje Bitmap nebo ikony používané pro příkazy.  Toto je jednoduchá deklarace, který identifikuje prostředek projektu a uvádí na základě jedné indexy použité ikony.  V části symboly souboru .vsct deklaruje hodnoty identifikátorů použít jako indexy.  Tento návod používá pruhu rastrový obrázek součástí šablony položky vlastního příkazu k projektu nepřidají.  
  
 **Část umísťováním**.  Část po příkazech, které se v části umísťováním.  První z nich je, kde kód přidá první skupinu popsané výše, obsahuje čtyři sloupce Průvodce příkazy do dílčí nabídky kde se zobrazí příkazy:  
  
```xml  
<CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                  priority="0x0100">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
</CommandPlacement>  
```  
  
 Všechny ostatní umísťováním přidat `GuidesContextMenuGroup` (obsahující `GuidesSubMenu`) další editor místních nabídek.  Pokud kód deklarován `GuidesContextMenuGroup`, byl nadřazena do editoru kódu kontextové nabídky.  To je důvod, proč se v umístění místní nabídky editoru kódu nezobrazí.  
  
 **Symboly části**.  Jak jsme uvedli výše, deklaruje části symboly identifikátory používané jinde v .vsct souboru, který umožňuje kód .vsct srozumitelnější než everywhere s identifikátory GUID a šestnáctkových číslic.  Důležité body v této části jsou, že GUID balíčku, musíte souhlasit s deklarace v třídě balíček a sadu příkazů, že identifikátor GUID, musíte souhlasit s deklaraci ve třídě implementace příkazu.  
  
## <a name="implementing-the-commands"></a>Implementace příkazy  
 Soubor ColumnGuideCommands.cs implementuje příkazy a zachytí až obslužných rutin.  Když Visual Studio načte balíček a inicializuje ji, balíček volá `Initialize` na třída implementace příkazy.  Inicializace příkazy jednoduše vytvoří instanci třídy a konstruktoru zachytí až všechny obslužné rutiny příkazů.  
  
 Nahraďte obsah souboru ColumnGuideCommands.cs následujícím kódem (vysvětlení níže):  
  
```csharp  
using System;  
using System.ComponentModel.Design;  
using System.Globalization;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Interop;  
using Microsoft.VisualStudio.TextManager.Interop;  
using Microsoft.VisualStudio.Text.Editor;  
using Microsoft.VisualStudio;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Command handler  
    /// </summary>  
    internal sealed class ColumnGuideCommands  
    {  
  
        const int cmdidAddColumnGuide = 0x0100;  
        const int cmdidRemoveColumnGuide = 0x0101;  
        const int cmdidChooseGuideColor = 0x0102;  
        const int cmdidRemoveAllColumnGuides = 0x0103;  
  
        /// <summary>  
        /// Command menu group (command set GUID).  
        /// </summary>  
        static readonly Guid CommandSet =   
            new Guid("c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e");  
  
        /// <summary>  
        /// VS Package that provides this command, not null.  
        /// </summary>  
        private readonly Package package;  
  
        OleMenuCommand _addGuidelineCommand;  
        OleMenuCommand _removeGuidelineCommand;  
  
        /// <summary>  
        /// Initializes the singleton instance of the command.  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        public static void Initialize(Package package)  
        {  
            Instance = new ColumnGuideCommands(package);  
        }  
  
        /// <summary>  
        /// Gets the instance of the command.  
        /// </summary>  
        public static ColumnGuideCommands Instance  
        {  
            get;  
            private set;  
        }  
  
        /// <summary>  
        /// Initializes a new instance of the <see cref="ColumnGuideCommands"/> class.  
        /// Adds our command handlers for menu (commands must exist in the command   
        /// table file)  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        private ColumnGuideCommands(Package package)  
        {  
            if (package == null)  
            {  
                throw new ArgumentNullException("package");  
            }  
  
            this.package = package;  
  
            // Add our command handlers for menu (commands must exist in the .vsct file)  
  
            OleMenuCommandService commandService =  
                this.ServiceProvider.GetService(typeof(IMenuCommandService))  
                    as OleMenuCommandService;  
            if (commandService != null)  
            {  
                // Add guide  
                _addGuidelineCommand =   
                    new OleMenuCommand(AddColumnGuideExecuted, null,  
                                       AddColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidAddColumnGuide));  
                _addGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_addGuidelineCommand);  
                // Remove guide  
                _removeGuidelineCommand =  
                    new OleMenuCommand(RemoveColumnGuideExecuted, null,  
                                       RemoveColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidRemoveColumnGuide));  
                _removeGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_removeGuidelineCommand);  
                // Choose color  
                commandService.AddCommand(  
                    new MenuCommand(ChooseGuideColorExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidChooseGuideColor)));  
                // Remove all  
                commandService.AddCommand(  
                    new MenuCommand(RemoveAllGuidelinesExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidRemoveAllColumnGuides)));  
            }  
        }  
  
        /// <summary>  
        /// Gets the service provider from the owner package.  
        /// </summary>  
        private IServiceProvider ServiceProvider  
        {  
            get  
            {  
                return this.package;  
            }  
        }  
  
        private void AddColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _addGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanAddGuideline(currentColumn);  
        }  
  
        private void RemoveColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _removeGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanRemoveGuideline(currentColumn);  
        }  
  
        private int GetCurrentEditorColumn()  
        {  
            IVsTextView view = GetActiveTextView();  
            if (view == null)  
            {  
                return -1;  
            }  
  
            try  
            {  
                IWpfTextView textView = GetTextViewFromVsTextView(view);  
                int column = GetCaretColumn(textView);  
  
                // Note: GetCaretColumn returns 0-based positions. Guidelines are 1-based  
                // positions.  
                // However, do not subtract one here since the caret is positioned to the  
                // left of  
                // the given column and the guidelines are positioned to the right. We  
                // want the  
                // guideline to line up with the current caret position. e.g. When the  
                // caret is  
                // at position 1 (zero-based), the status bar says column 2. We want to  
                // add a  
                // guideline for column 1 since that will place the guideline where the  
                // caret is.  
                return column;  
            }  
            catch (InvalidOperationException)  
            {  
                return -1;  
            }  
        }  
  
        /// <summary>  
        /// Find the active text view (if any) in the active document.  
        /// </summary>  
        /// <returns>The IVsTextView of the active view, or null if there is no active  
        /// document or the  
        /// active view in the active document is not a text view.</returns>  
        private IVsTextView GetActiveTextView()  
        {  
            IVsMonitorSelection selection =  
                this.ServiceProvider.GetService(typeof(IVsMonitorSelection))  
                                                    as IVsMonitorSelection;  
            object frameObj = null;  
            ErrorHandler.ThrowOnFailure(  
                selection.GetCurrentElementValue(  
                    (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame, out frameObj));  
  
            IVsWindowFrame frame = frameObj as IVsWindowFrame;  
            if (frame == null)  
            {  
                return null;  
            }  
  
            return GetActiveView(frame);  
        }  
  
        private static IVsTextView GetActiveView(IVsWindowFrame windowFrame)  
        {  
            if (windowFrame == null)  
            {  
                throw new ArgumentException("windowFrame");  
            }  
  
            object pvar;  
            ErrorHandler.ThrowOnFailure(  
                windowFrame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView, out pvar));  
  
            IVsTextView textView = pvar as IVsTextView;  
            if (textView == null)  
            {  
                IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
                if (codeWin != null)  
                {  
                    ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
                }  
            }  
            return textView;  
        }  
  
        private static IWpfTextView GetTextViewFromVsTextView(IVsTextView view)  
        {  
  
            if (view == null)  
            {  
                throw new ArgumentNullException("view");  
            }  
  
            IVsUserData userData = view as IVsUserData;  
            if (userData == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            object objTextViewHost;  
            if (VSConstants.S_OK  
                   != userData.GetData(Microsoft.VisualStudio  
                                                .Editor  
                                                .DefGuidList.guidIWpfTextViewHost,  
                                       out objTextViewHost))  
            {  
                throw new InvalidOperationException();  
            }  
  
            IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
            if (textViewHost == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            return textViewHost.TextView;  
        }  
  
        /// <summary>  
        /// Given an IWpfTextView, find the position of the caret and report its column  
        /// number. The column number is 0-based  
        /// </summary>  
        /// <param name="textView">The text view containing the caret</param>  
        /// <returns>The column number of the caret's position. When the caret is at the  
        /// leftmost column, the return value is zero.</returns>  
        private static int GetCaretColumn(IWpfTextView textView)  
        {  
            // This is the code the editor uses to populate the status bar.  
            Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
                textView.Caret.ContainingTextViewLine;  
            double columnWidth = textView.FormattedLineSource.ColumnWidth;  
            return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                       / columnWidth));  
        }  
  
        /// <summary>  
        /// Determine the applicable column number for an add or remove command.  
        /// The column is parsed from command arguments, if present. Otherwise  
        /// the current position of the caret is used to determine the column.  
        /// </summary>  
        /// <param name="e">Event args passed to the command handler.</param>  
        /// <returns>The column number. May be negative to indicate the column number is  
        /// unavailable.</returns>  
        /// <exception cref="ArgumentException">The column number parsed from event args  
        /// was not a valid integer.</exception>  
        private int GetApplicableColumn(EventArgs e)  
        {  
            var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
            if (!string.IsNullOrEmpty(inValue))  
            {  
                int column;  
                if (!int.TryParse(inValue, out column) || column < 0)  
                    throw new ArgumentException("Invalid column");  
                return column;  
            }  
  
            return GetCurrentEditorColumn();  
        }  
  
        /// <summary>  
        /// This function is the callback used to execute a command when the a menu item  
        /// is clicked. See the Initialize method to see how the menu item is associated  
        /// to this function using the OleMenuCommandService service and the MenuCommand  
        /// class.  
        /// </summary>  
        private void AddColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.AddGuideline(column);  
            }  
        }  
  
        private void RemoveColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.RemoveGuideline(column);  
            }  
        }  
  
        private void RemoveAllGuidelinesExecuted(object sender, EventArgs e)  
        {  
            GuidesSettingsManager.RemoveAllGuidelines();  
        }  
  
        private void ChooseGuideColorExecuted(object sender, EventArgs e)  
        {  
            System.Windows.Media.Color color = GuidesSettingsManager.GuidelinesColor;  
  
            using (System.Windows.Forms.ColorDialog picker =   
                new System.Windows.Forms.ColorDialog())  
            {  
                picker.Color = System.Drawing.Color.FromArgb(255, color.R, color.G,  
                                                             color.B);  
                if (picker.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
                {  
                    GuidesSettingsManager.GuidelinesColor =   
                        System.Windows.Media.Color.FromRgb(picker.Color.R,  
                                                           picker.Color.G,   
                                                           picker.Color.B);  
                }  
            }  
        }  
  
    }  
}  
  
```  
  
 **Opravte odkazy**.  Chybí odkaz v tomto okamžiku.  Klikněte na tlačítko správné ukazatel na uzlu odkazy v Průzkumníku řešení.  Vyberte **přidat...**  příkaz.  **Přidat odkaz na** dialogové okno má vyhledávacího pole v pravém horním rohu.  Zadejte "editor" (bez dvojité uvozovky).  Vyberte **Microsoft.VisualStudio.Editor** položky (musí zaškrtnete políčko nalevo od položky, právě vyberte položku) a zvolte **OK** přidat odkaz.  
  
 **Inicializace**.  Inicializuje třídu balíčku, zavolá `Initialize` na třída implementace příkazy.  `ColumnGuideCommands` Inicializace vytvoří instanci třídy a členy třídy ukládá instance třídy a odkaz na balíček.  
  
 Podívejme se na jednu z ups háku obslužná rutina příkazu z konstruktoru třídy:  
  
```csharp  
_addGuidelineCommand =   
    new OleMenuCommand(AddColumnGuideExecuted, null,  
                       AddColumnGuideBeforeQueryStatus,  
                       new CommandID(ColumnGuideCommands.CommandSet,  
                                     cmdidAddColumnGuide));  
  
```  
  
 Vytvoříte `OleMenuCommand`.  Visual Studio použije příkaz systém Microsoft Office.  Při vytváření instancí OleMenuCommand je funkce, která implementuje příkaz klíče argumenty (`AddColumnGuideExecuted`), funkce se má volat při Visual Studio zobrazí nabídky pomocí příkazu (`AddColumnGuideBeforeQueryStatus`) a ID příkazu.  Visual studio volá funkci stav dotazu před zobrazením příkazu v nabídce tak, aby příkaz můžete provést samotný neviditelná nebo vyšedlé pro konkrétní zobrazení nabídky (třeba zakázání **kopie** Pokud neexistuje žádný výběr), změnit jeho ikonu, nebo dokonce změnit svůj název (například z přidat něco odebrat něco) a tak dále.  ID příkazu, který se musí shodovat ID příkazu, který je deklarován v souboru .vsct.  Nastavte řetězce pro příkaz a vodítka sloupců přidejte příkaz musí shodovat se mezi .vsct soubor a ColumnGuideCommands.cs.  
  
 Následující řádek naleznete pomoc při, pokud uživatelé vyvolat příkaz prostřednictvím příkazové okno (vysvětlení níže):  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
```  
  
 **Dotaz na stav**.  Funkce dotazování na stav `AddColumnGuideBeforeQueryStatus` a `RemoveColumnGuideBeforeQueryStatus` zkontrolujte některá nastavení (například maximální počet příruček a maximální počet sloupců) nebo pokud je sloupec příručka k odebrání.  Pokud jsou podmínky vpravo umožňují příkazy.  Funkce dotazování na stav musí být velmi efektivní, protože běží pokaždé, když Visual Studio zobrazí nabídku u každého příkazu v nabídce.  
  
 **Funkce AddColumnGuideExecuted**.  Přidání průvodce část zajímavé je přijít na to, aktuální umístění zobrazení a pomocí kurzoru editor.  První volání této funkce `GetApplicableColumn` které ověří, pokud je argumentem uživatelem zadané v argumentech obslužná rutina události, a pokud žádný neexistuje, pak funkce zkontroluje zobrazení editoru:  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
    return GetCurrentEditorColumn();  
}  
  
```  
  
 `GetCurrentEditorColumn` má prozkoumat malým získat <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> zobrazení kódu.  Pokud je trasování prostřednictvím `GetActiveTextView`, `GetActiveView`, a `GetTextViewFromVsTextView`, uvidíte, jak to provést.  Následuje odpovídající kód abstrahované, počínaje aktuální výběr a získávání rámce na výběr a potom vyberte získávání rámečku DocView jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>, potom <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> z IVsTextView a pak hostitele, zobrazení, získávání a Nakonec IWpfTextView:  
  
```csharp  
   IVsMonitorSelection selection =  
       this.ServiceProvider.GetService(typeof(IVsMonitorSelection))   
           as IVsMonitorSelection;  
   object frameObj = null;  
  
ErrorHandler.ThrowOnFailure(selection.GetCurrentElementValue(  
                                (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame,  
                                out frameObj));  
  
   IVsWindowFrame frame = frameObj as IVsWindowFrame;  
   if (frame == null)  
       <<do nothing>>;  
  
...  
   object pvar;  
   ErrorHandler.ThrowOnFailure(frame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView,  
                                                  out pvar));  
  
   IVsTextView textView = pvar as IVsTextView;  
   if (textView == null)  
   {  
       IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
       if (codeWin != null)  
       {  
           ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
       }  
   }  
  
...  
   if (textView == null)  
       <<do nothing>>  
  
   IVsUserData userData = textView as IVsUserData;  
   if (userData == null)  
       <<do nothing>>  
  
   object objTextViewHost;  
   if (VSConstants.S_OK   
           != userData.GetData(Microsoft.VisualStudio.Editor.DefGuidList  
                                                            .guidIWpfTextViewHost,  
                                out objTextViewHost))  
   {  
       <<do nothing>>  
   }  
  
   IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
   if (textViewHost == null)  
       <<do nothing>>  
  
   IWpfTextView textView = textViewHost.TextView;  
  
```  
  
 Až budete mít IWpfTextView, můžete získat sloupec, kde se nachází pomocí kurzoru:  
  
```csharp  
private static int GetCaretColumn(IWpfTextView textView)  
{  
    // This is the code the editor uses to populate the status bar.  
    Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
        textView.Caret.ContainingTextViewLine;  
    double columnWidth = textView.FormattedLineSource.ColumnWidth;  
    return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                / columnWidth));  
}  
  
```  
  
 S aktuální sloupec v ručně tam, kde uživatel klikne, kód právě volá správce nastavení, které chcete přidat nebo odebrat sloupce.  Správce nastavení aktivuje událost na kterém jsou všechny `ColumnGuideAdornment` objekty naslouchat.  Po událost se aktivuje, tyto objekty aktualizovat zobrazení jejich přidružené text nových nastavení Průvodce sloupců.  
  
## <a name="invoking-command-from-the-command-window"></a>Volajícím příkazu v příkazovém okně  
 Ukázka příručky sloupec umožňuje uživatelům vyvolání dva příkazy v příkazovém okně jako formulář rozšíření.  Pokud použijete **zobrazení &#124; ostatní okna &#124; příkazové okno** příkaz, může se zobrazit příkazové okno.  Můžete pracovat s příkazové okno zadáním "upravit" a název dokončení příkazu a poskytnutí argument 120, máte následující:  
  
```  
> Edit.AddColumnGuide 120  
>  
```  
  
 Částí vzorku, které umožňují Toto jsou v souboru deklarace .vsct, `ColumnGuideCommands` konstruktoru třídy, když ho zachytí obslužné rutiny příkazů a příkaz implementace obslužných rutin, které kontrolují argumenty událostí.  
  
 Už jste viděli "`<CommandFlag>CommandWellOnly</CommandFlag>`" v souboru .vsct, jakož i umísťováním v hlavní nabídce Upravit i když jsme nezobrazovat příkazy v **upravit** nabídce uživatelského rozhraní.  Toho, aby v hlavní nabídce Upravit jim poskytne názvy jako **Edit.AddColumnGuide**.  Příkazy skupiny deklarace, který obsahuje čtyři příkazy umístěno skupině v nabídce upravit přímo:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
```  
  
 Oddíl tlačítka později deklarovat příkazy `CommandWellOnly` zachovat neviditelná v hlavní nabídce a deklaruje je `AllowParams`:  
  
```xml  
<Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
        priority="0x0100" type="Button">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
  <Icon guid="guidImages" id="bmpPicAddGuide" />  
  <CommandFlag>CommandWellOnly</CommandFlag>  
  <CommandFlag>AllowParams</CommandFlag>  
  
```  
  
 Jste viděli obslužná rutina příkazu spojit kód `ColumnGuideCommands` konstruktoru třídy zadat popis povolené parametr:  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
  
```  
  
 Už jste viděli `GetApplicableColumn` funkce kontroly `OleMenuCmdEventArgs` pro hodnotu před zaškrtnutím zobrazení editoru pro aktuální sloupec:  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
```  
  
## <a name="trying-your-extension"></a>Při rozšíření  
 Nyní můžete stisknout **F5** provést rozšíření vodítka sloupců.  Otevřete textový soubor a pomocí místní nabídky editoru přidejte řádky Průvodce, je odebrat a změnit jejich barvu.  Je třeba kliknout na text (předán není prázdné znaky konce řádku) Chcete-li přidat sloupec průvodce nebo editoru přidá ji do posledního sloupce v řádku.  Pokud používáte příkazové okno a volat příkazy s parametrem, můžete přidat sloupec příručky kdekoli.  
  
 Pokud chcete zkuste jiný příkaz umísťováním, změňte názvy, změňte ikony a tak dále, a máte problémy s zobrazující nejnovější kód v nabídkách sady Visual Studio, můžete resetovat experimentální hive, ve kterém jsou ladění.  Zprovoznit **nabídce Start Windows** a zadejte "obnovit".  Vyhledejte a vyvolání příkazu **resetovat další Visual Studio experimentální instanci**.  Tím vyčistíte experimentální podregistru všech součástí rozšíření.  Tento název neexistuje vyčistit se nastavení ze součástí, takže všechny příručky jste měli při vypínání experimentální hive sady Visual Studio bude stále existovat při kód čte úložišti nastavení při dalším spuštění.  
  
## <a name="finished-code-project"></a>Dokončený kód projektu  
 Brzy bude projektu githubu ukázky rozšiřitelnosti Visual Studio a dokončený projekt bude existovat.  Toto téma tak, aby odkazoval došlo, pokud k tomu dojde bude aktualizován.  Dokončené ukázkový projekt může mít různé identifikátory GUID a bude mít jiné bitmap pruhu pro příkaz ikony.  
  
 Můžete vyzkoušet verzi funkce vodítka sloupec s Tato galerie sady Visual Studio[rozšíření](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home).  
  
## <a name="see-also"></a>Viz také  
 [V editoru](../extensibility/inside-the-editor.md)   
 [Rozšíření pro Editor a jazyk služby](../extensibility/extending-the-editor-and-language-services.md)   
 [Služba jazyka a body rozšíření editoru](../extensibility/language-service-and-editor-extension-points.md)   
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)   
 [Přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md)   
 [Vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)