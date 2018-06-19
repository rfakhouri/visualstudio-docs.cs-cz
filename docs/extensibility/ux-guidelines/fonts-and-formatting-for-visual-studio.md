---
title: Písma a formátování pro sadu Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: c3c3df69-83b4-4fd0-b5b1-e18c33f39376
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 22e765916a19caeff643e25f97f4d0d4f91669c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148129"
---
# <a name="fonts-and-formatting-for-visual-studio"></a>Písma a formátování pro sadu Visual Studio
##  <a name="BKMK_TheEnvironmentFont"></a> Písmo prostředí
 Všechny písem v sadě Visual Studio, musí se zveřejnit pro uživatele pro přizpůsobení. Důvodem je primárně prostřednictvím **písma a barev** stránky v **nástroje > Možnosti** dialogové okno. Jsou tři hlavní kategorie nastavení písma:  
  
-   **Prostředí písma** -primární písmo rozhraní IDE (integrované vývojové prostředí), použité pro všechny prvky rozhraní, včetně dialogová okna, nabídek, nástroje systému windows a okna dokumentu. Ve výchozím nastavení je písmo prostředí vázaný na systém písmo, které se zobrazí jako 9 pt Segoe UI v aktuálních verzích Windows. Pomocí jednoho písma pro všechny prvky rozhraní pomáhá zajistit konzistentní písma vzhled v celém rozhraní IDE.  
  
-   **Textový editor** – elementy, prostor v kódu a další textové editory lze upravit v textovém editoru stránky v **nástroje > Možnosti**.  
  
-   **Konkrétní kolekce** -návrháře windows, které nabízejí uživatele přizpůsobení jejich prvky rozhraní může vystavit písma, které jsou specifické pro jejich návrh surface v vlastní nastavení na stránce **nástroje > Možnosti**.  
  
### <a name="editor-font-customization-and-resizing"></a>Přizpůsobení editoru písma a změna velikosti  
 Uživatelé se často zvětšit nebo zvětšení velikosti a barvy textu v editoru podle jejich předvoleb, nezávisle na obecné uživatelské rozhraní. Protože písmo prostředí se používá u elementů, které se mohou zobrazit v rámci nebo jako součást editor nebo návrháři, je důležité si uvědomit očekávané chování, pokud jeden z těchto klasifikací písma změněn.  
  
 Při vytváření prvky uživatelského rozhraní, které se zobrazují v editoru, ale jsou nejsou součástí *obsah*, je důležité použít prostředí písma a není písmo textu, aby předvídatelný způsobem změnit velikost elementů.  
  
1.  V editoru kódu text velikost s nastavením písmo textu kódu a reagují na úroveň přiblížení editoru textu.  
  
2.  Všechny prvky rozhraní by měl být vázáno nastavení písma prostředí a reagovat na změny globální v prostředí. To zahrnuje (ale není omezeno na):  
  
    -   Text v kontextové nabídky  
  
    -   Text v dalších úprav editoru jako text nabídky žárovky, rychle najít podokně editor a přejděte do podokna  
  
    -   Označení textu v dialogových oknech, jako je **hledání v souborech** nebo **Refaktorovat**  
  
### <a name="accessing-the-environment-font"></a>Přístup k prostředí písma  
 V kódu nativní nebo WinForms písmo prostředí je přístupná pomocí volání metody `IUIHostLocale::GetDialogFont` po dotazování rozhraní z `SID_SUIHostLocale` služby.  
  
 Pro Windows Presentation Foundation (WPF), vlastní třídy dialogového okna okno odvozena z prostředí nástroje `DialogWindow` třída místo na WPF `Window` třídy.  
  
 V jazyce XAML kód vypadat třeba takto:
  
```xaml
<ui:DialogWindow  
    x:Class"MyNameSpace.MyWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:s="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:ui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"  
    ShowInTaskbar="False"  
    WindowStartupLocation="CenterOwner"  
    Title="My Dialog">  
</ui:DialogWindow>  
```

kódu na pozadí:

```csharp
internal partial class WebConfigModificationWindow : DialogWindow  
{  
}  
```
  
 (Nahraďte `Microsoft.VisualStudio.Shell.11.0` s aktuální verzí sady MPF knihovny DLL.)  
  
 Pokud chcete zobrazit dialogové okno, volání "`ShowModal()`" k třídě přes `ShowDialog()`. `ShowModal()` Nastaví správné modální stav v prostředí, zajišťuje, aby se že dialogové okno je umístěn na střed v nadřazené okno a tak dále.  
  
 Kód je následující:  
  
```csharp
MyWindow window = new MyWindow();  
window.ShowModal()  
```
  
 `ShowModal` Vrátí bool? (s možnou hodnotou Null Boolean) s `DialogResult`, který může být použit v případě potřeby. Vrácená hodnota je true, pokud dialogové okno se zavřel s **OK**.  
  
 Pokud potřebujete zobrazit některé WPF uživatelské rozhraní, které není dialogové okno a je hostovaná v jeho vlastní `HwndSource`, jako je například automaticky otevíraném okně nebo podřízeného okna WPF okna Win32/WinForms nadřazené okno, budete muset nastavit `FontFamily` a `FontSize` v kořenovém elementu e WPF lementu. (Prostředí v hlavním okně nastaví vlastnosti, ale nebude možné Zdědit po `HWND`). Prostředí obsahuje prostředky, ke kterým může být vázaný vlastnosti, například takto:  
  
```xaml
<Setter Property="FontFamily" Value="{DynamicResource VsFont.EnvironmentFontFamily}" />  
<Setter Property="FontSize" Value="{DynamicResource VsFont.EnvironmentFontSize}" />  
```
  
###  <a name="BKMK_Formatting"></a> Formátování odkaz (škálování nebo tučné)  
 Některá dialogová okna vyžadují konkrétní text, který má být tučné nebo velikost než písmo prostředí. Dříve byly písem větší než písmo prostředí programového jako "`environment font +2`" nebo podobné. Používání fragmentů poskytnutý kód podporují vysokou hodnotou DPI monitorování a zajistit, aby zobrazovaný text se vždy na správnou velikost a váhu (například Světlý nebo Semilight).  
  
> **Poznámka: Před použitím formátování, ujistěte se, jsou následující pokyny v nalezen [styl textu](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).**  
  
 Škálování prostředí písmo, nastavte styl TextBlock nebo štítek, které je uvedené. Všechny tyto fragmenty kódu použít správně, bude generovat správné písmo, včetně odpovídající velikost a váhu variace.  
  
 Kde "`vsui`" je odkaz na obor názvů `Microsoft.VisualStudio.Shell`:  

```xaml
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0" 
```
  
#### <a name="375-environment-font--light"></a>Písmo prostředí 375 % + světlý  
 **Zobrazí se jako:** 34 pt Segoe UI světlý  
 **Použití:** (stane se výjimečně) jedinečný rámci uživatelského rozhraní, jako je třeba na stránce Start

 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku:  
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey);  
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je vidět.  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey}}">TextBlock: 375 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey}}">Label: 375 Percent Scaling</Label>  
```
  
#### <a name="310-environment-font--light"></a>Písmo prostředí 310 % + světlý  
 **Zobrazí se jako:** 28 pt Segoe UI světlý   
 **Použití:** velké podpis dialogové okno názvy, hlavní záhlaví v sestavách  
  
 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku:  
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey);    
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je vidět.  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey}}">TextBlock: 310 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey}}">Label: 310 Percent Scaling</Label>     
```
  
#### <a name="200-environment-font--semilight"></a>200 % prostředí písma + Semilight  
 **Zobrazí se jako:** 18 bodů Segoe UI Semilight    
 **Použití:** podpoložek, názvy v malé a střední dialogová okna  
  
 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku: 
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey);    
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je znázorněno:  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey}}">TextBlock: 200 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey}}">Label: 200 Percent Scaling</Label>    
```
  
#### <a name="155-environment-font"></a>155 % prostředí písma  
 **Zobrazí se jako:** 14 pt Segoe uživatelského rozhraní    
 **Použití:** část záhlaví v dokumentu i uživatelského rozhraní nebo sestavy  
  
 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku:  
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey);    
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je znázorněno:  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey}}">TextBlock: 155 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey}}">Label: 155 Percent Scaling</Label>  
```
  
#### <a name="133-environment-font"></a>133 % prostředí písma  
 **Zobrazí se jako:** 12 pt Segoe uživatelského rozhraní    
 **Použití:** menší podpoložek v dokumentu a dialogová okna podpis i uživatelského rozhraní  
  
 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku:  
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey);    
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je znázorněno:  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey}}">TextBlock: 133 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey}}">Label: 133 Percent Scaling</Label>    
```
  
#### <a name="122-environment-font"></a>122 % prostředí písma  
 **Zobrazí se jako:** 11 bodů Segoe uživatelského rozhraní    
 **Použití:** část záhlaví v dialozích podpisu, top uzlů v zobrazení stromu, vertikální tabulátor navigace  
  
 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku:  
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey);    
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je znázorněno:  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey}}">TextBlock: 122 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey}}">Label: 122 Percent Scaling</Label>    
```
  
#### <a name="environment-font--bold"></a>Prostředí písma + tučně  
 **Zobrazí se jako:** uveden tučně 9 pt Segoe uživatelského rozhraní    
 **Použití:** popisky a podnadpisy dialogová okna podpis, sestavy a dokumentu i uživatelského rozhraní  
  
 **Příklady kódu:** kde `textBlock` je dříve definovaný TextBlock a `label` je dříve definovaný štítku:  
  
```csharp
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironmentBoldStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironmentBoldStyleKey);    
```
  
 **XAML:** nastavit styl TextBlock nebo štítek, jak je znázorněno:  
  
```xaml
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironmentBoldStyleKey}}"> Bold TextBlock</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironmentBoldStyleKey}}"> Bold Label</Label>    
```
  
### <a name="localizable-styles"></a>Lokalizovatelný styly  
 V některých případech bude muset překladatelům při lokalizaci upravit styly písem pro různá národní prostředí, jako je například odebrání tučné z textu pro jazyky východní Asie. Chcete-li možné lokalizace styly písem, musí být tyto styly v rámci tohoto souboru RESX. Nejlepší způsob, jak dosáhnout a stále upravit styly písem v návrháři formuláře v sadě Visual Studio je explicitně nastavit styly písem v době návrhu. I když to vytvoří objekt úplné písma a může zdát, že přeruší dědičnost písma nadřazeného, pouze vlastnost FontStyle slouží k nastavení písma.  
  
 Řešení, které je formulář dialogové okno Připojit k `FontChanged` událostí. V `FontChanged` událostí, provede všechny ovládací prvky a zkontrolujte, pokud je nastavená jejich písma. Pokud je nastavena, změňte jej na nové písmo na základě formuláře písma a předchozí styl písma ovládacího prvku. Příklady v kódu je:  
  
```csharp
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
          SetFontStyles();  
}  
  
/// <summary>  
/// SetFontStyles - This function will iterate all controls on a page  
/// and recreate their font with the desired fontstyle.  
/// It should be called in the OnFontChanged handler (and also in the constructor  
/// in case the IUIService is not available so OnFontChange doesn't fire).  
/// This way, when the VS shell font is given to us the controls that have  
/// a different style for the font (bolded for example) will recreate their font  
/// and use the VS shell font but with a style variation (bolded ...).  
/// </summary>   
protected void SetFontStyles()  
{  
     SetFontStyles(this, this, this.Font);  
}  
  
protected static void SetFontStyles(Control topControl, Control parent, Font referenceFont)  
{  
     foreach(Control c in parent.Controls)  
     {  
          if (c.Controls != null && c.Controls.Count > 0) {  
               SetFontStyles(topControl, c, referenceFont);  
          }  
          if (c.Font != topControl.Font) {  
               c.Font = new Font(referenceFont, c.Font.Style);  
          }  
     }  
}  
```
  
 Pomocí tohoto kódu zaručuje, že při aktualizaci formuláře písma písem ovládacích prvků bude aktualizovat také. Tato metoda by měla být volána z konstruktoru formuláře také, protože dialogové okno se nemusí podařit získat instanci `IUIService` a `FontChanged` událostí se nikdy aktivují. Zapojování `FontChanged` vám umožní dialogových oknech se dynamicky vyzvednutí nové písmo, přestože dialogovém okně je již otevřeno.  
  
### <a name="testing-the-environment-font"></a>Testování písmo prostředí  
 Chcete-li zajistit, aby vaše uživatelské prostředí používá prostředí písma a respektuje nastavení velikosti, otevřete **nástroje > Možnosti > prostředí > písma a barev** a vyberte v části "Font prostředí" "Zobrazit nastavení pro:" rozevírací nabídky.  
  
 ![Nastavení písma a barev v nástrojích pro &gt; dialogovém okně Možnosti](../../extensibility/ux-guidelines/media/0201-a_optionsfonts.png "0201 a_OptionsFonts")<br />Nastavení písma a barev v nástrojích pro &gt; dialogové okno Možnosti
  
 Písmo hodnotu nastaveno něco velmi jiný než výchozí. Chcete-li zřejmé uživatelského rozhraní není aktualizace, zvolte písmo s patek (např. "Times New Roman") a nastavit velmi velké. Otestujte uživatelské rozhraní k zajištění, že ho respektuje prostředí. Tady je příklad pomocí dialogu licencí:  
  
 ![Příklad textu uživatelského rozhraní, který nesplňuje písmo prostředí](../../extensibility/ux-guidelines/media/0201-b_wrongfontdialog.png "0201 b_WrongFontDialog")<br />Příklad textu uživatelského rozhraní, který nesplňuje písmo prostředí
  
 V tomto případě "Uživatelské informace" a "Informace o produktu" nejsou respektováním písmo. V některých případech to může být na volbu explicitní návrhu, ale pokud explicitní písmo není zadané jako součást specifikace redline může být chyby.  
  
 Pokud chcete resetovat písma, klikněte na tlačítko "Použít výchozí hodnoty" v části **nástroje > Možnosti > prostředí > písma a barev**.  
  
##  <a name="BKMK_TextStyle"></a> Styl textu  
 Styl textu odkazuje na velikost písma, váha a velká a malá písmena. Implementace pokyny najdete v tématu [písmo prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
### <a name="text-casing"></a>Text velká a malá písmena  
  
#### <a name="all-caps"></a>Velká písmena  
 Nepoužívejte všechna velká pro názvy nebo popisky v sadě Visual Studio.  
  
#### <a name="all-lowercase"></a>Všechny malá  
 Nepoužívejte malá písmena. názvy nebo popisky v sadě Visual Studio.  
  
#### <a name="sentence-and-title-case"></a>Věty a název případu  
 Text v sadě Visual Studio by měl použít první písmeno velké nebo věty, v závislosti na situaci.  
  
|Případ použití názvu pro:|Případ použití větu pro:|  
|-------------------------|----------------------------|  
|Dialogové okno názvy|Popisky|  
|Skupinové rámečky|Zaškrtávací políčka|  
|Položky nabídky|Přepínací tlačítka|  
|Položek kontextové nabídky|Pole položky seznamu|  
|Tlačítka|Stavové řádky|  
|Tabulka popisky||  
|Záhlaví sloupců||  
|Popisy tlačítek||  
  
##### <a name="title-case"></a>První písmeno velké  
 První písmeno velké je styl, ve kterém jsou použita velká písmena první písmena většinu nebo všechny slova v rámci frázi. V sadě Visual Studio první písmeno velké slouží pro mnoho položek, včetně:  
  
-   **Popisy tlačítek.** Příklad: "Preview vybraných položek"  
  
-   **Záhlaví sloupců.** Příklad: "systému odpověď"  
  
-   **Položky nabídky.** Příklad: "uložit všechny"  
  
 Při použití první písmeno velké, jsou tyto pokyny pro při převedení slova na velká písmena a kdy je ponechte malá písmena:  
  
|Velká písmena|Komentáře a příklady|  
|---------------|---------------------------|  
|Všechny podstatná jména||  
|Všechny akce|Včetně "Je" a jiných forem "Chcete-li být"|  
|Všechny příslovcí|Včetně "Než" a "Data"|  
|Všechny přídavných jmen|Včetně "To" a ""|  
|Všechny zájmena|Včetně přivlastňovacího pádu "Jeho" také jako "Je," zmenšení zastupovat "jej" a příkaz "je"|  
|První a poslední slova, bez ohledu na části řeči||  
|Předložky, které jsou součástí příkaz fráze|"Zavírání na všechny systémy Windows" nebo "Vypnutí systému"|  
|Všechna písmena zkratka|HTML, XML, ADRESA URL, IDE, RGB|  
|Druhá aplikace word v složeného slova, pokud je to podstatné jméno nebo přídavných jmen správné, nebo pokud slova nemají stejnou hodnotu|Přístup pro čtení a zápis křížových odkazů, Software před společnosti Microsoft, běhu|  
  
|Malá|Příklady|  
|---------------|--------------|  
|Druhý slova v složené word, je-li jiný slovní nebo jiném čase či osobě, úprava první aplikace word|Postupy startu|  
|Články, není-li jeden první slova v názvu|a,,|  
|Koordinaci spojky|a, ale, ani, nebo|  
|Předložky s slova čtyři nebo méně písmena mimo příkaz fráze|do do, jako u mimo, v horní části|  
|"Do" při použití v nekonečná fráze|"Jak formátování pevného disku"|  
  
##### <a name="sentence-case"></a>Věty  
 Věty je metoda standardní použití velkých písmen pro zápis v první slovo věty je aktivována, spolu s žádné podstatná jména správné a zastupovat "I." Obecně platí věty je snazší pro čtení, zvlášť když obsah bude přeložit počítačem po celém světě cílovou skupinu. Případ použití větu pro:  
  
1.  **Zprávy stavového řádku.** Jsou jednoduchý, řečeno a zadat jenom informace o stavu. Příklad: "načítání projektu soubor"  
  
2.  **Všechny další prvky uživatelského rozhraní**, včetně popisky, zaškrtněte políčka, přepínače a pole položky seznamu. Příklad: "vyberte všechny položky v seznamu"  
  
### <a name="text-formatting"></a>Formátování textu  
 Výchozí text formátování ve Visual Studiu 2013 se řídí [písmo prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont). Tato služba pomáhá zajistit konzistentní písma vzhled v celém rozhraní IDE (integrované vývojové prostředí), a používejte zaručit konzistentního prostředí pro uživatele.  
  
 Výchozí velikost písma služba Visual Studio používá pochází ze systému Windows a zobrazí se jako 9 pt.  
  
 Můžete použít formátování pro prostředí písmo. Toto téma popisuje, jak a kde používat styly. Informace o implementaci, najdete v části [písmo prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
#### <a name="bold-text"></a>Tučně  
 Tučně se používá pouze v sadě Visual Studio a by se mělo vyhradit pro:  
  
-   Otázka popisky v průvodcích  
  
-   určení aktivní projekt v Průzkumníku řešení  
  
-   přepsat hodnoty v okně vlastností nástroje  
  
-   určité události v rozevíracích seznamech editoru jazyka Visual Basic  
  
-   generované serverem obsah Osnova dokumentu pro webové stránky  
  
-   část hlavičky v dialogovém okně komplexní nebo v Návrháři uživatelského rozhraní  
  
#### <a name="italics"></a>Italics  
 Visual Studio nepoužívá kurzíva nebo uveden tučně kurzíva text.  
  
#### <a name="color"></a>Barva  
  
-   Modrá je vyhrazeno pro hypertextové odkazy (navigační a tvorba příkazů) a musí být nikdy použit pro orientaci.  
  
-   Větší záhlaví (prostředí písma x 155 % nebo vyšší) může být označeno pro tyto účely:  
  
    -   K poskytování visual odvolání za podpis rozhraní Visual Studia  
  
    -   Chcete-li upoutat pozornost na určitou oblast  
  
    -   Nabídka pomoc od standardní tmavý prostředí šedé nebo černé barvy  
  
-   Barva v záhlaví by je měli využít existující sady Visual Studio brand barvy, především hlavní Fialová #FF68217A.  
  
-   Při použití barev v záhlaví, je nutné splnit [Windows barvu pokyny](https://msdn.microsoft.com/en-us/library/dn742482.aspx), včetně poměr kontrast a další důležité informace pro usnadnění přístupu.  
  
### <a name="font-size"></a>Velikost písma  
 Visual Studio uživatelského rozhraní návrhu funkce světlejší vzhled s další prázdné znaky. Kde je to možné, byly chrome a název řádky snížit nebo odebrat. Požadavek v sadě Visual Studio sice informace hustotu typografii nadále být důležité, s důrazem na více otevřete mezery mezi řádky a změnu velikosti písem a váhu.  
  
 Následující tabulky obsahuje podrobnosti o návrhu a visual příklady pro zobrazení písma použitá v sadě Visual Studio. Několik odchylek písma zobrazení mít velikost i váhy, jako je například Semilight nebo světlý, zakódovaný do jejich vzhled.  
  
 Fragmenty kódu implementace pro všechna zobrazení písma lze nalézt v [formátování (škálování nebo tučné) odkaz](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_Formatting).  
  
#### <a name="375-environment-font--light"></a>Písmo prostředí 375 % + světlý  
  
|||  
|-|-|  
|**Použití:** výjimečných. Jedinečný pouze rámci uživatelského rozhraní.<br /><br /> **Proveďte:**<br /><br /> -Větu případ použití<br />-Vždy používat lehká<br /><br /> **Ne:**<br /><br /> -Použijte uživatelské rozhraní než podpis uživatelského rozhraní, jako je například – úvodní stránka<br />-Tučné, kurzíva a tučné, kurzíva<br />-Použití pro základní text<br />-Použít v panelech nástrojů|**Zobrazí se jako:** 34 pt Segoe UI světlý<br /><br /> **Visual příklad:**<br /><br /> *Aktuálně nepoužívá. Lze na stránce Start.*|  
  
#### <a name="310-environment-font--light"></a>Písmo prostředí 310 % + světlý  
  
|||  
|-|-|  
|**Použití:**<br /><br /> -Větší záhlaví v dialozích podpisu<br />– Záhlaví hlavní části sestavy<br /><br /> **Proveďte:**<br /><br /> -Větu případ použití<br />-Vždy používat lehká<br /><br /> **Ne:**<br /><br /> -Použijte uživatelské rozhraní než podpis uživatelského rozhraní, jako je například – úvodní stránka<br />-Tučné, kurzíva a tučné, kurzíva<br />-Použití pro základní text<br />-Použít v panelech nástrojů|**Zobrazí se jako:** 28 pt Segoe UI světlý<br /><br /> **Visual příklad:**<br /><br /> ![Příklad 310 % prostředí písma &#43; světla záhlaví](../../extensibility/ux-guidelines/media/0202-a_ef310.png "0202 a_EF310")|  
  
#### <a name="200-environment-font--semilight"></a>200 % prostředí písma + Semilight  
  
|||  
|-|-|  
|**Použití:**<br /><br /> -Podpoložek<br />-Tituly malé a střední dialogová okna<br /><br /> **Proveďte:**<br /><br /> -Větu případ použití<br />-Vždy používat Semilight váhy<br /><br /> **Ne:**<br /><br /> -Tučné, kurzíva a tučné, kurzíva<br />-Použití pro základní text<br />-Použít v panelech nástrojů|**Zobrazí se jako:** 18 bodů Segoe UI Semillight<br /><br /> **Visual příklad:**<br /><br /> ![Příklad 200 % prostředí písma &#43; Semilight](../../extensibility/ux-guidelines/media/0202-b_ef200.png "0202 b_EF200")|  
  
#### <a name="155-environment-font"></a>155 % prostředí písma  
  
|||  
|-|-|  
|**Použití:**<br /><br /> -Section záhlaví v dokumentu i uživatelského rozhraní<br />-Sestavy<br /><br /> **Úkol:** větu případ použití<br /><br /> **Ne:**<br /><br /> -Tučné, kurzíva a tučné, kurzíva<br />-Použití pro základní text<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />-Použít v panelech nástrojů|**Zobrazí se jako:** 14 pt Segoe uživatelského rozhraní<br /><br /> **Visual příklad:**<br /><br /> ![Příklad 155 % prostředí písma nadpisu](../../extensibility/ux-guidelines/media/0202-c_ef155.png "0202 c_EF155")|  
  
#### <a name="133-environment-font"></a>133 % prostředí písma  
  
|||  
|-|-|  
|**Použití:**<br /><br /> -Menší podpoložek v dialozích podpisu<br />-Menší podpoložek v dokumentu i uživatelského rozhraní<br /><br /> **Úkol:** větu případ použití<br /><br /> **Ne:**<br /><br /> -Tučné, kurzíva a tučné, kurzíva<br />-Použití pro základní text<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />-Použít v panelech nástrojů|**Zobrazí se jako:** 12 pt Segoe uživatelského rozhraní<br /><br /> **Visual příklad:**<br /><br /> ![Příklad 133 % prostředí písma nadpisu](../../extensibility/ux-guidelines/media/0202-d_ef133.png "0202 d_EF133")|  
  
#### <a name="122-environment-font"></a>122 % prostředí písma  
  
|||  
|-|-|  
|**Použití:**<br /><br /> -Section záhlaví v dialozích podpisu<br />-Nejvyšší uzlů v zobrazení stromu<br />– Navigace vertikální tabulátor<br /><br /> **Úkol:** větu případ použití<br /><br /> **Ne:**<br /><br /> -Tučné, kurzíva a tučné, kurzíva<br />-Použití pro základní text<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />-Použít v panelech nástrojů|**Zobrazí se jako:** 11 bodů Segoe uživatelského rozhraní<br /><br /> **Visual příklad:**<br /><br /> ![Příklad 122 % prostředí písma nadpisu](../../extensibility/ux-guidelines/media/0202-e_ef122.png "0202 e_EF122")|  
  
#### <a name="environment-font--bold"></a>Prostředí písma + tučně  
  
|||  
|-|-|  
|**Použití:**<br /><br /> -Popisků a podnadpisy v dialozích podpisu<br />-Popisků a podnadpisy v sestavách<br />-Popisků a podnadpisy v dokumentu uživatelského rozhraní<br /><br /> **Proveďte:**<br /><br /> -Větu případ použití<br />-Použít tučné váhy<br /><br /> **Ne:**<br /><br /> -Výběr kurzívy nebo tučné, kurzíva<br />-Použití pro základní text<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />-Použít v panelech nástrojů|**Zobrazí se jako:** uveden tučně 9 pt Segoe uživatelského rozhraní<br /><br /> **Visual příklad:**<br /><br /> ![Příklad prostředí písma &#43; tučné záhlaví](../../extensibility/ux-guidelines/media/0202-f_efb.png "0202 f_EFB")|  
  
#### <a name="environment-font"></a>Prostředí písma  
  
|||  
|-|-|  
|**Použití:** část textu<br /><br /> **Úkol:** větu případ použití<br /><br /> **Nemáte:** kurzíva nebo tučné kurzíva|**Zobrazí se jako:** 9 pt Segoe uživatelského rozhraní<br /><br /> **Visual příklad:**<br /><br /> ![Příklad prostředí písma](../../extensibility/ux-guidelines/media/0202-g_ef.png "0202 g_EF")|  
  
### <a name="padding-and-spacing"></a>Odsazení a mezery  
 Záhlaví vyžadovat místa kolem, aby jim poskytnout příslušné zvýraznění. Tento prostor se liší v závislosti na velikosti bodů a co je téměř záhlaví, například vodorovné pravítko nebo na řádku textu v písmu k dispozici prostředí.  
  
-   Odsazení ideální pro nadpis samostatně by měl být 90 % prostoru výška kapitálové znak. Například na záhlaví Segoe UI Light 28 pt má výšku cap 26 pt a odsazení musí být přibližně 23 pt, nebo o 31 pixelů.  
  
-   Minimální místo kolem nadpisu by mělo být 50 % výška kapitálové znaků. Když na záhlaví je přiložena pravidlo nebo jiného elementu úzkou přizpůsobování lze méně místa.  
  
-   Uveden tučně prostředí písmo textu postupujte podle výšky výchozí velikost mezer a odsazením.  
  
## <a name="see-also"></a>Viz také  
 [MSDN: Písem (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742483\(v=vs.85\).aspx)   
 [MSDN: Text v uživatelském rozhraní (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx)