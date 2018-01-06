---
title: Barvy a styly pro sadu Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 07/31/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e384ea1-4d9e-4307-8884-6e183900732c
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 40e795238e46885707cfd6eff715a27a5f53f85c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="colors-and-styling-for-visual-studio"></a>Barvy a styly pro sadu Visual Studio
## <a name="using-color-in-visual-studio"></a>Pomocí barev v sadě Visual Studio  
V sadě Visual Studio barva slouží především jako nástroj pro komunikaci, ne jenom jako dekorace. Použijte barva minimálně a rezervovat pro situace, ve které chcete:  
  
-   Komunikovat význam nebo přidružení (například platformy nebo jazyk modifikátory)  
  
-   Přitahují pozornost (například označující ke změně stavu)  
  
-   Zlepšení čitelnosti a poskytnout zajímavá navigace uživatelského rozhraní  
  
-   Je žádoucí zvýšení  
  
Existuje několik možností pro přiřazení barvy k elementům uživatelského rozhraní v sadě Visual Studio. V některých případech může být obtížné obrázek na možnosti, kterou se má použít, nebo způsobu jeho použití správně. Toto téma vám pomůže:  
  
1.  Seznámit s různými službami a systémy používá k definování barev v sadě Visual Studio.  
  
2.  Vyberte správný možnost pro daný element.  
  
3.  Správně použijte možnost, kterou jste vybrali.  
  
> **Poznámka:** nikdy používat pevné kódování šestnáctkově, RGB nebo barvy systému k vaší elementům uživatelského rozhraní. Použití služeb umožňuje flexibilitu při ladění hue. Kromě toho bez této služby nebude možné využívat výhod možností Přepnutí motivu [službu VSColor](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService).
  
### <a name="methods-for-assigning-color-to-visual-studio-interface-elements"></a>Prvky rozhraní metody pro přiřazení barev k sadě Visual Studio  
Zvolte metodu, která nejlépe odpovídá vaší prvky uživatelského rozhraní.  
  
| Uživatelské rozhraní | Metoda | Jaké jsou jejich? |  
| --- | --- | --- |  
| S vloženými nebo samostatné dialogových oken. | **Barvy systému** | Názvy systému, které umožňují definovat barva a zobrazení prvků uživatelského rozhraní operačního systému jako běžné ovládací prvky dialogového okna. |
| Máte vlastní uživatelské rozhraní, které mají být konzistentní s prostředím celkové VS a máte prvky uživatelského rozhraní, které splňují danou kategorii a význam sémantického sdílené tokenů. | **Běžné sdílené barvy** | Existující názvy tokenu předdefinované barvu pro konkrétní prvky uživatelského rozhraní |
| Máte jednotlivé funkce nebo skupiny funkcí a neexistuje žádný sdílený barvu pro podobné elementy. | **Vlastní barvy** | Barva tokenu názvy, které jsou specifické pro oblast a není určená ke sdílení s další uživatelského rozhraní |
| Chcete povolit koncového uživatele pro přizpůsobení uživatelského rozhraní nebo obsahu (například textové editory nebo specializované návrháře windows). | **Přizpůsobení koncového uživatele**<br /><br />**(Nástroje &gt; dialogovém okně Možnosti)** | Nastavení definované na stránce "Písma a barvy" **nástroje &gt; možnosti** dialogového nebo specializované specifické pro jeden funkce uživatelského rozhraní stránky. |
  
### <a name="visual-studio-themes"></a>Visual Studio motivů  
Visual Studio funkce tři různé barevné motivy: světla, tmavý a modré. Navíc rozpozná režimu vysokého kontrastu, která je určená pro usnadnění systémové barevný motiv.  
  
Uživatelé vyzváni k výběru motiv při jejich prvním použití sady Visual Studio a je možné přepnout motivy později tak, že přejdete do **nástroje &gt; možnosti &gt; prostředí &gt; Obecné** a vybrat nový motiv z rozevírací nabídky "barvu motivu".  
  
Uživatelé také pomocí ovládacího panelu můžete přepnout jejich celý systémy do jednoho z několika motivů vysoký kontrast. Pokud uživatel vybere motiv s vysokým kontrastem, pak modulu pro výběr barvu motivu sady Visual Studio už ovlivňuje barev v sadě Visual Studio, i když jsou změny motiv uložit při ukončení práce v režimu vysokého kontrastu. Další informace o režimu vysokého kontrastu najdete v tématu [výběr vysoký kontrast barvy](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ChoosingHighContrastColors).
  
### <a name="the-vscolor-service"></a>Službu VSColor  
Visual Studio poskytuje služby barva prostředí, označuje jako VSColor služby, která umožňuje vytvoření vazby na barvu vaší prvků uživatelského rozhraní s názvem záznam obsahující hodnoty barev pro každý motiv sady Visual Studio. Tím se zajistí, že vaše barvy se automaticky změní tak, aby odrážela aktuální vybrané uživatelem motiv nebo systém režimu vysokého kontrastu. Použití služby znamená, že implementace všechny změny barev motivů související se zpracovává na jednom místě, a pokud používáte společné sdílené barvy ze služby, uživatelské rozhraní se automaticky projeví nové motivy obsažené v budoucích verzích sady Visual Studio.  
  
### <a name="implementation"></a>Implementace  
Zdrojový kód sady Visual Studio obsahuje několik definiční soubory balíčků, které obsahují seznamy tokenu názvy a hodnoty odpovídající barvu pro každý motiv. Službu barva přečte VSColors definované v těchto definiční soubory balíčků. Tyto barvy se odkazuje v jazyce XAML kódu nebo v kódu a pak načten prostřednictvím buď `IVsUIShell5.GetThemedColor` metoda nebo DynamicResource mapování.  
  
### <a name="system-colors"></a>Barvy systému  
Běžné ovládací prvky odkazovat barvy systému ve výchozím nastavení. Pokud chcete, aby vaše uživatelské prostředí používat barvy systému, například při vytváření vložené nebo samostatné dialogu, nemusíte provádět žádné kroky.  
  
### <a name="common-shared-colors-in-the-vscolor-service"></a>Běžné sdílené barvy v rámci služby VSColor  
Prvky vaši rozhraní by měla odpovídat celkové prostředí Visual Studio. Opětovným použitím běžné sdílené barev, které jsou vhodné pro součást uživatelského rozhraní, který navrhujete, zkontrolujte, že vaše rozhraní je v souladu s dalších rozhraní sady Visual Studio a že vaše barvy bude automaticky aktualizovat při přidávání nebo aktualizaci motivů.  
  
Před použitím běžné sdílené barvy, ujistěte se, že rozumíte správně jejich použití. Nesprávné použití běžné sdílené barvy může mít za následek nekonzistentní, frustrující nebo matoucí prostředí pro uživatele.  
  
### <a name="user-customizable-colors"></a>Uživatel přizpůsobitelné barvy  
Přejděte na téma: [vystavení barvy pro koncové uživatele](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers)  
  
V některých případech budete chtít povolit koncovému uživateli umožňují přizpůsobit uživatelské rozhraní, například při vytváření editor kódu nebo návrhové ploše. Přizpůsobitelné součásti uživatelského rozhraní, které se nacházejí v **písma a barev** části **nástroje &gt; možnosti** dialogové okno, kde uživatelé mohou změnit barvu popředí, barva pozadí nebo obojí.  
  
![Nástroje pro &gt; dialogovém okně Možnosti](../../extensibility/ux-guidelines/media/0301-a_toolsoptionsdialog.png "0301 a_ToolsOptionsDialog")<br />Nástroje pro &gt; dialogové okno Možnosti
  
##  <a name="BKMK_TheVSColorService"></a>Službu VSColor  
Visual Studio poskytuje služby barva prostředí, označovaný taky jako služba VSColor nebo službu barva prostředí. Tato služba umožňuje svázání hodnoty barev vaše prvky uživatelského rozhraní pro název hodnota barvu nastavit obsahující barvy pro každý motiv. Službu VSColor musí použít pro všechny prvky uživatelského rozhraní, tak, aby barvy automaticky změnit tak, aby odrážela aktuální motiv vybrané uživatelem a tak, aby uživatelského rozhraní svázaná se službou barva prostředí bude integrovat nové motivy v budoucích verzí sady Visual Studio.  
  
### <a name="how-the-service-works"></a>Jak funguje služba  
Barva službu prostředí přečte že vscolors definované v .pkgdef pro součást uživatelského rozhraní. Tyto VSColors se pak odkazuje v XAML značek nebo kódu a jsou načteny prostřednictvím buď `IVsUIShell5.GetThemedColor` nebo `DynamicResource` mapování.  
  
![Architektura služby barva prostředí](../../extensibility/ux-guidelines/media/0302-a_environmentcolorservicearchitecture.png "0302 a_EnvironmentColorServiceArchitecture")<br />Architektura služby barva prostředí
  
### <a name="accessing-the-service"></a>Přístupu ke službě
Existuje několik různých způsobů, jak používáte službu VSColor, v závislosti na tom, jaký druh barva tokeny, můžete přístup a jaký druh kódu máte.  

#### <a name="predefined-environment-colors"></a>Předdefinované prostředí barvy  
  
##### <a name="from-native-code"></a>Z nativního kódu  
Prostředí poskytuje službu, která poskytuje přístup k `COLORREF` barev. Rozhraní služby nebo je:  
  
```  
IVsUIShell2::GetVSSysColorEx(VSSYSCOLOR dwSysColIndex, DWORD *pdwRGBval)  
```  
  
V souboru VSShell80.idl výčtu `__VSSYSCOLOREX` má prostředí barva konstanty. Pokud chcete použít, předat jako hodnotu indexu buď jednu z hodnot z `enum __VSSYSCOLOREX` regulární index, číslo, které rozhraní API systému Windows nebo zdokumentovaný v MSDN `GetSysColor`, přijímá. Díky tomuto získá zpět hodnoty RGB barvy, který se má použít v druhý parametr.  
  
Pokud ukládáte pera nebo štětce s novou barvu, je nutné `AdviseBroadcastMessages` (z prostředí sady Visual Studio) a naslouchat `WM_SYSCOLORCHANGE` a `WM_THEMECHANGED` zprávy.  
  
  
Přístup ke službě barev v nativním kódu, provedete volání, které vypadá takto: 

```
pUIShell2->GetVSSysColorEx(VSCOLOR_COLOR_NAME, &rgbLOCAL_COLOR);    
```  

> **Poznámka:** `COLORREF` hodnot vrácených `GetVSSysColorEx()` obsahovat pouze R, G, B součástí Barva motivu. Pokud položku motiv používá průhlednost, je před vrácením zahodí hodnotu alfa kanálu. Proto pokud barvu prostředí týkající se musí použít na místě, kde kanál průhlednost je důležité, abyste používali `IVsUIShell5.GetThemedColor` místo `IVsUIShell2::GetVSSysColorEx`, jak je popsáno dále v tomto tématu.  
  
##### <a name="from-managed-code"></a>Ze spravovaného kódu  
Přístup k službě VSColor prostřednictvím nativního kódu je poměrně jednoduché. Pokud pracujete pomocí spravovaného kódu, ale určení způsobu používání služby může být složité. Si uvědomit zde je C# fragmentu kódu demonstraci tento proces:  
  
```  
private void VSColorPaint(object sender, System.Windows.Forms.PaintEventArgs e)  
{  
    //getIVSUIShell2  
    IVsUIShell2 uiShell2 = Package.GetService(typeof(SVsUIShell)) as IVsUIShell2;  
    Debug.Assert (uiShell2 != null, "failed to get IVsUIShell2");  
  
    if (uiShell2 != null)  
    {  
        //get the COLORREF structure  
        uint win32Color;  
        uiShell.GetVSSysColorEx(VSSYSCOLOREX.VSCOLOR_SMARTTAG_HOVER_FILL, out win32Color);  
  
        //translate it to a managed Color structure  
        Color myColor = ColorTranslator.FromWin32((int)win32Color);  
        //use it  
        e.Graphics.FillRectangle(new SolidBrush(myColor), 0, 0, 100, 100);  
    }  
}  
```  
  
Pokud pracujete v jazyce Visual Basic, použijte:  
  
```  
Dim myColor As Color = ColorTranslator.FromWin32((Integer)win32Color)  
```  
  
##### <a name="from-wpf-ui"></a>Z uživatelského rozhraní grafického subsystému WPF  
Můžete vázat na Visual Studio barvy prostřednictvím hodnoty exportovali do aplikace `ResourceDictionary`. Dole je příklad použití prostředků z tabulky barev, stejně jako vytvoření vazby na data písma prostředí v jazyce XAML.  
  
```  
<Style TargetType="{x:Type Button}">  
    <Setter Property="TextBlock.FontFamily"  
            Value="{DynamicResource VsFont.EnvironmentFontFamily}" />  
    <Setter Property="TextBlock.FontSize"  
            Value="{DynamicResource VsFont.EnvironmentFontSize}" />  
    <Setter Property="Background"  
            Value="{DynamicResource VsBrush.EnvironmentBackgroundGradient}" />  
</Style>  
```  
  
#### <a name="helper-classes-and-methods-for-managed-code"></a>Pomocné třídy a metody pro spravovaný kód  
Pro spravovaný kód, knihovna spravované Framework balíček prostředí služby (`Microsoft.VisualStudio.Shell.12.0.dll`) obsahuje několik pomocných tříd, používá motivu barvy.  
  
Pomocné metody v `Microsoft.VisualStudio.Shell.VsColors` zahrnují třídy v MPF `GetThemedGDIColor()` a `GetThemedWPFColor()`. Tyto pomocné metody vrátit hodnotu barvu motivu položky jako `System.Drawing.Color` nebo `System.Windows.Media.Color`, který se má použít v WinForms nebo uživatelského rozhraní grafického subsystému WPF.  
  
```  
IVsUIShell5 shell5;  
Button button = new Button();  
button.BackColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemBrushKey);  
button.ForeColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemTextBrushKey);  
  
/// <summary>  
/// Gets a System.Drawing.Color value from the current theme for the given color key.  
/// </summary>  
/// <param name="vsUIShell">The IVsUIShell5 service, used to get the color's value.</param>  
/// <param name="themeResourceKey">The key to find the color for.</param>  
/// <returns>The current theme's value of the named color.</returns>  
public static System.Drawing.Color GetThemedGDIColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)  
{  
   Validate.IsNotNull(vsUIShell, "vsUIShell");  
   Validate.IsNotNull(themeResourceKey, "themeResourceKey");  
  
   byte[] colorComponents = GetThemedColorRgba(vsUIShell, themeResourceKey);  
  
   // Note: The Win32 color we get back from IVsUIShell5.GetThemedColor is ABGR  
   return System.Drawing.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]);  
}  
  
private static byte[] GetThemedColorRgba(IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)  
{  
   Guid category = themeResourceKey.Category;  
   __THEMEDCOLORTYPE colorType = __THEMEDCOLORTYPE.TCT_Foreground  
   if (themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundColor || themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundBrush)  
   {  
      colorType = __THEMEDCOLORTYPE.TCT_Background;  
   }  
  
   // This call will throw an exception if the color is not found  
   uint rgbaColor = vsUIShell.GetThemedColor(ref category, themeResourceKey.Name, (uint)colorType);  
   return BitConverter.GetBytes(rgbaColor);  
}  
public static System.Windows.Media.Color GetThemedWPFColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)  
{  
   Validate.IsNotNull(vsUIShell, "vsUIShell");  
   Validate.IsNotNull(themeResourceKey, "themeResourceKey");  
  
   byte[] colorComponents = GetThemedColorComponents(vsUIShell, themeResourceKey);  
  
    return System.Windows.Media.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]);  
}    
```  
  
Třídu lze také získat VSCOLOR identifikátory pro daný WPF barva klíč prostředků, nebo naopak.  
  
```  
public static string GetColorBaseKey(int vsSysColor);  
public static bool TryGetColorIDFromBaseKey(string baseKey, out int vsSysColor);  
```  
  
Metody `VsColors` třída zadat dotaz na službu VSColor vrátit pokaždé, když jsou vyvolány hodnoty barvy. K získání hodnoty barvy jako `System.Drawing.Color`, alternativou s lepším výkonem je místo toho používat metody třídy `Microsoft.VisualStudio.PlatformUI.VSThemeColor` třídy, která ukládá do mezipaměti získat ze služby VSColor hodnoty barev. Třída interně přihlásí k událostem zprávy všesměrového vysílání prostředí a zahodí hodnotu uloženou v mezipaměti, pokud se vyskytne událost změna motivu. Navíc poskytuje třídy. NET-friendly událost přihlásit k odběru změn motivu. Použít `ThemeChanged` událostí, které chcete přidat novou obslužnou rutinu a použít `GetThemedColor()` metoda získat barvy hodnoty pro `ThemeResourceKeys` zájmu. Ukázkový kód může vypadat například takto:  
  
```  
public MyWindowPanel()  
{  
    InitializeComponent();  
  
    // Subscribe to theme changes events so we can refresh the colors  
    VSColorTheme.ThemeChanged += VSColorTheme_ThemeChanged;  
  
    RefreshColors();  
}  
  
private void VSColorTheme_ThemeChanged(ThemeChangedEventArgs e)  
{  
    RefreshColors();  
  
    // Also post a message to all the children so they can apply the current theme appropriately  
    foreach (System.Windows.Forms.Control child in this.Controls)  
    {  
        NativeMethods.SendMessage(child.Handle, e.Message, IntPtr.Zero, IntPtr.Zero);  
    }  
}  
  
private void RefreshColors()  
{  
    this.BackColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowBackgroundColorKey);  
    this.ForeColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowTextColorKey);  
}  
  
protected override void Dispose(bool disposing)  
{  
    if (disposing)  
    {  
        VSColorTheme.ThemeChanged -= this.VSColorTheme_ThemeChanged;  
        base.Dispose(disposing);}  
}  
```  
  
##  <a name="BKMK_ChoosingHighContrastColors"></a>Výběr barvy vysoký kontrast  
  
### <a name="overview"></a>Přehled  
Windows používá několik motivy úrovni systému vysokého kontrastu, které zvýšit kontrast barvu textu, pozadí a bitové kopie, provedení elementy zobrazí více jedinečných na obrazovce. Usnadnění z důvodů je důležité, aby elementy rozhraní sady Visual Studio reagovat správně při uživatelé přepnout motiv s vysokým kontrastem.  
  
Jen někteří z nich barvy systému lze použít pro vysoký kontrast motivů. Při výběru systému názvy barev, mějte na paměti následující tipy:  
  
1.  **Výběr barvy systému, které mají stejný význam sémantického** jako elementu, který se zvýrazňování. Pokud zvolíte vysoký kontrast pro text v rámci časového období, použijte pro instanci WindowText a není ControlText.  
  
2.  **Zvolte popředí nebo pozadí páry** společně nebo nebudete jisti, že výběr barvy bude fungovat v všechny vysoký kontrast motivů.  
  
3.  **Určit, které části uživatelské rozhraní jsou nejdůležitější a ujistěte se, bude zvýraznění obsahu oblasti.** Velké množství podrobností, která by za normálních okolností rozlišit jemně lišit v odstín barvy, dojde ke ztrátě, takže použití silné ohraničení barev je běžné definovat oblasti obsahu, protože nejsou k dispozici žádné varianty barvu pro různé oblasti obsahu.  
  
### <a name="system-color-set"></a>Sada System barev  
Tabulky na [Blog týmu WPF: odkaz na SystemColors](http://blogs.msdn.com/b/wpf/archive/2010/11/30/systemcolors-reference.aspx) označuje kompletní sadu názvy barev systému a odpovídající odstíny zobrazí v každý motiv.  
  
Při použití to omezenou sadu barev a uživatelské rozhraní, *očekává se, že dojde ke ztrátě jemně podrobnosti, které byly součástí "normální" motivy*. Tady je příklad uživatelského rozhraní pomocí jemně šedé barev, které se používají k rozlišení oblasti v rámci okno nástroje. Při spárovaný s okně zobrazí v režimu vysokého kontrastu, uvidíte, že všechny pozadí jsou stejné hue a ohraničení z těchto oblastí, které jsou označeny ohraničení samostatně:  
  
![Příklad jak jemně podrobnosti jsou ztraceny s vysokým kontrastem](../../extensibility/ux-guidelines/media/030303-a_propertieswindow.png "030303 a_PropertiesWindow")<br />Příklad jak jemně podrobnosti jsou ztraceny, vysoký kontrast
  
#### <a name="choosing-text-colors-in-an-editor"></a>Výběr barvy textu v editoru  
Obarvené text se používá v editoru nebo návrhové ploše k označení význam, například povolení pro snazší identifikaci skupin podobné položky. V motiv s vysokým kontrastem ale nemáte možnost rozlišit mezi víc než třemi barvy textu. WindowText, GrayText a HotTrackText jsou k dispozici na povrchu WindowBackground pouze barvy. Vzhledem k tomu, že nemůžete použít víc než třemi barvy, pečlivě zvolte nejdůležitější rozdíly, které chcete zobrazit v režimu vysokého kontrastu.  
  
Odstíny pro každou z tokenu názvy povolené na povrchu editor, jak jsou v každém motiv s vysokým kontrastem:  
  
![Vysoký kontrast editor porovnání](../../extensibility/ux-guidelines/media/030303-b_hceditorcomparison.png "030303 b_HCEditorComparison")<br />Porovnání editor vysoký kontrast
  
Příklady editor plochy v motivu Blue:  
  
![Editor v motiv modrý](../../extensibility/ux-guidelines/media/030303-c_editorblue.png "030303 c_EditorBlue")<br />Editor v motiv modrý
  
![Editor v motivu Vysoký kontrast 1](../../extensibility/ux-guidelines/media/030303-d_editorhc1.png "030303 d_EditorHC1")<br />Editor v motivu Vysoký kontrast 1
  
### <a name="usage-patterns"></a>Vzorce používání
Barvy s vysokým kontrastem definované máte mnoho běžných prvků uživatelského rozhraní. Tyto vzory využití můžete odkazovat při výběru vlastní systému názvy barev, tak, aby vaše prvky uživatelského rozhraní jsou konzistentní s podobné součásti.  
  
| Barva systému | Použití |
| --- | --- |
| ActiveCaption | -Active IDE a glyfy tlačítko rafted okno na hover a stiskněte klávesu<br />-Pozadí panelu název pro rozhraní IDE a rafted windows<br />-Výchozí pozadí panelu stavu |
| ActiveCaptionText | -Active IDE a rafted windows pro název panelu popředí (text a glyfy)<br />-Na pozadí a ohraničení tlačítek aktivní okno na hover a stiskněte klávesu |
| Ovládací prvek | -Pole se seznamem, rozevíracího seznamu a hledání řídit výchozí a zakázané pozadí, včetně rozevírací tlačítko<br />-Ukotvení cíl tlačítko pozadí<br />– Pozadí panelu příkaz<br />– Pozadí okna nástroj |
| ControlDark | -Pozadí IDE<br />-Nabídek a příkazů panelu oddělovačů<br />– Ohraničení panelu příkaz<br />– Shadows nabídka<br />-Nástroj okno Karta výchozí a hover ohraničení a oddělovače<br />-Dokumentů a pozadí tlačítko přetečení<br />-Ukotvení cíl glyfy ohraničení |
| ControlDarkDark |-Karta nezaostřená, vybrané dokumentu – okno |
| ControlLight |-Automaticky skrýt karta ohraničení<br />-Pole se seznamem pole a v rozevíracím seznamu ohraničení<br />-Ukotvení ohraničení a pozadí cíl |
| ControlLightLight | -Vybraný, cílených předběžné ohraničení |
| ControlText | – Glyfy pole se seznamem pole a rozevírací seznam<br />– Text karty okno zrušit nástroj |
| GrayText |– Pole se seznamem a rozevíracího seznamu Zakázané ohraničení, glyfy rozevíracího seznamu, text a text položky nabídky<br />– Text zakázáno nabídky<br />-Text záhlaví 'možnosti vyhledávání' search ovládací prvek<br />-Oddělovač oddílu search ovládací prvek |
| Zvýrazněte | – Všechny hover a při stisknutí tlačítka pozadí a ohraničení, s výjimkou pole se seznamem rozevírací tlačítko pozadí a dokumentu dobře přetečení tlačítko okraj pole<br />-Pozadí vybranou položku |
| HighlightText | -Všechny hover a při stisknutí tlačítka foregrounds (text a glyfy)<br />-Cílených nástroj okno a dokumentu karta okna řízení popředí<br />-Cílených nástroj okno nadpis panelu ohraničení<br />-Cílených, vybrané předběžné karta popředí<br />-Document dobře přetečení tlačítko ohraničení na hover a stiskněte klávesu<br />-Vybrané ikony ohraničení|
| HotTrack | -Posuvník jezdec pozadí a ohraničení na stisknutím klávesy<br />-Posuvníku glyfy šipku na stisknutím klávesy |
| InactiveCaption | -Neaktivní IDE a glyfy tlačítko rafted okno při přechodu myší<br />-Pozadí panelu název pro rozhraní IDE a rafted windows<br />-Zakázaný vyhledávání pozadí ovládacího prvku |
| InactiveCaptionText | -Neaktivní IDE a rafted windows title panelu popředí (text a glyfy)<br />-Pozadí tlačítka neaktivní okna a ohraničení při přechodu myší<br />-Ohraničení a pozadí tlačítko okno nezaostřená nástroj<br />-Zakázaný vyhledávání řízení popředí |
| Nabídka | -Rozevírací nabídce pozadí<br />-Pozadí zaškrtnuté a zakázané značky zaškrtnutí |
| MenuText | -Rozevírací nabídce ohraničení<br />-Značky zaškrtnutí<br />-Glyfů nabídky<br />– Text rozevírací nabídky<br />-Vybrané ikony ohraničení |  
| ScrollBar | -Posuňte panelu a posuvník šipku pozadí, všechny stavy |
| Okno | Automaticky skrýt karta pozadí<br />-Nabídky panelu a příkaz police pozadí<br />-Pozadí karta okna dokumentu nezaostřená nebo nezaškrtnuté a ohraničení dokumentu pro otevřené a předběžná karty<br />-Pozadí panelu nadpis okna nezaostřená nástroj<br />-Nástroj okno Karta pozadí, vybrané i zrušit |
| Okenní rám | -IDE ohraničení |
| WindowText | -Automaticky skrýt karta popředí<br />-Vybraného nástroje okno Karta popředí<br />-Karta okna nezaostřená dokumentu a nezaostřená nebo nezaškrtnuté předběžné karta popředí<br />-Popředí výchozí zobrazení a strom hover přes nezaškrtnuté glyfy<br />– Okraj vybraná karta okna nástroj<br />-Posuvníku jezdec pozadí, ohraničení a glyfy |
  
##  <a name="BKMK_ExposingColorsForEndUsers"></a>Vystavení barvy pro koncové uživatele  
  
### <a name="overview"></a>Přehled  
Někdy budete chtít povolit koncovému uživateli umožňují přizpůsobit uživatelské rozhraní, například při vytváření editor kódu nebo návrhové ploše. Nejběžnější způsob k tomu je pomocí **nástroje &gt; možnosti** dialogové okno. Pokud používáte vysoce specializovaný uživatelské rozhraní, které vyžaduje speciální ovládací prvky, je nejjednodušší způsob, jak přizpůsobení k dispozici prostřednictvím **písma a barev** stránky v rámci **prostředí** části dialogového okna. Pro každý element, který vystavit pro vlastní nastavení můžete zvolit uživatele změnit barvu popředí, barva pozadí nebo obojí.

### <a name="building-a-vspackage-for-your-customizable-colors"></a>Vytváření VSPackage pro vaše přizpůsobitelná barvy  
VSPackage můžete řídit písma a barev prostřednictvím vlastních kategorií a zobrazení položek na stránce vlastností písma a barev. Pokud používáte tento mechanismus, musí implementovat VSPackages [IVsFontAndColorDefaultsProvider](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.aspx) rozhraní a jeho přidružené rozhraní.  
  
V zásadě tento mechanismus lze změnit všechna existující položky zobrazení a kategorie, které je obsahují. Však není vhodné jej použít k úpravě kategorie textového editoru nebo jeho položky zobrazení. Další informace o kategorii textový Editor, najdete v části [písma a barev přehled](../font-and-color-overview.md).  
  
Pokud chcete implementovat vlastní kategorie nebo zobrazit položky, musí VSPackage:  
  
-   **Vytvořte nebo Identifikujte kategorií v registru.** Implementace rozhraní IDE **písma a barev** stránka vlastností používá tuto informaci k správně dotaz pro službu podpora dané kategorii.  
  
-   **Vytvořte nebo Identifikujte skupiny v registru (volitelné).** Může to být užitečné pro definování skupiny, která představuje sjednocení dvou nebo více kategorií. Pokud je definována skupinu, rozhraní IDE automaticky sloučí podkategorie a distribuuje zobrazit položky v rámci skupiny.  
  
-   **Implementovat podpora rozhraní IDE.**  
  
-   **Zpracování změn písma a barvy.**  
  
#### <a name="to-create-or-identify-categories"></a>K vytvoření nebo určení kategorií  
Vytvořit zvláštní druh položky registru kategorie `[HKLM\SOFTWARE\Microsoft \Visual Studio\\<Visual Studio version\>\FontAndColors\\<Category\>]` kde `<Category>` je Nelokalizováno název kategorie.
  
Naplnění registr s využitím dvou hodnot:  

| Název | Typ | Data | Popis |
| --- | --- | --- | --- |
| Kategorie | REG_SZ | GUID | Identifikátor GUID vytvořit k identifikaci kategorie |
| Balíček | REG_SZ | GUID | Identifikátor GUID VSPackage služby, která podporuje kategorie |
  
 Službu uvedený v registru musí poskytovat implementace [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) pro odpovídající kategorii.  
  
#### <a name="to-create-or-identify-groups"></a>K vytvoření nebo určení skupiny  
Vytvořit zvláštní druh položky registru kategorie `[HKLM\SOFTWARE\Microsoft \Visual Studio\\<Visual Studio version\>\FontAndColors\\<group\>]` kde `<group>` je Nelokalizováno název skupiny.  
  
Naplnění registr s využitím dvou hodnot:

| Název | Typ | Data | Popis |
|--- | --- | --- | --- |
| Kategorie | REG_SZ | GUID | Identifikátor GUID vytvořit k identifikaci kategorie |
| Balíček | REG_SZ | GUID | Identifikátor GUID VSPackage služby, která podporuje kategorie |
  
Službu uvedený v registru musí poskytovat implementace `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` pro odpovídající skupinu.

![Implementace IVsFontAndColorGroup](../../extensibility/ux-guidelines/media/0304-a_fontandcolorgroup.png "0304 a_FontAndColorGroup")<br />Implementace`IVsFontAndColorGroup`
  
### <a name="to-implement-ide-support"></a>K implementaci podpora rozhraní IDE  
Implementace [GetObject](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.getobject.aspx), která vrací buď [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) rozhraní nebo `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` rozhraní IDE pro každou kategorii nebo skupinu identifikátorem GUID.  
  
Pro každou kategorii podporuje, VSPackage implementuje samostatnou instanci [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) rozhraní.  
  
Metody implementované pomocí [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) musíte zadat IDE se:  
  
-   Seznam zobrazení položek v kategorii  
  
-   Lokalizovatelný názvy pro zobrazení položek  
  
-   Zobrazení informací pro každého člena kategorie  
  
 > **Poznámka:** každé kategorie musí obsahovat alespoň jednu položku zobrazení.
  
Rozhraní IDE používá `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` rozhraní k definování spojení několika kategorií.

Jeho implementace poskytuje IDE se:

-   Seznam kategorií, které tvoří dané skupiny  
  
-   Přístup k instancím typu [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) podpora každou kategorii v rámci skupiny  
  
-   Názvy lokalizovatelný skupin  
  
#### <a name="updating-the-ide"></a>Aktualizace rozhraní IDE  
Prostředí IDE ukládá do mezipaměti informace o nastavení písma a barvy. Proto po všech změnách konfigurace IDE písma a barvy, zajistíte, že je aktuální mezipaměti osvědčeným postupem je.  
  
Aktualizace mezipaměti se provádí prostřednictvím [IvsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx) rozhraní a lze provádět globálně nebo jenom na vybrané položky.  
  
### <a name="handling-font-and-color-changes"></a>Zpracování změn písma a barev  
Pro podporu správně zabarvení text, který zobrazí VSPackage, službu zabarvení podpora VSPackage reagovat na uživatel spustil změny prostřednictvím stránku vlastností písma a barev.  
  
K tomuto účelu musí VSPackage:  
  
-   **zpracování událostí generovaných IDE** implementací [IVsFontAndColorEvents](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.aspx) rozhraní. Prostředí IDE volá metodu odpovídající následující uživatelské úpravy stránky písma a barev. Například volání [onfontchanged –](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.onfontchanged.aspx) metoda, pokud je vybrána nového písma.  
  
 **OR**  
  
-   **dotazování IDE pro změny**. To lze provést prostřednictvím systému implementovaná [IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx) rozhraní. I když především pro podporu trvalost, [GetItem](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.getitem.aspx) metoda můžete získat informace o písma a barev pro zobrazení položek. Další informace o nastavení písma a barvy, najdete v článku na webu MSDN [přístup k uložené písma a barev nastavení](../accessing-stored-font-and-color-settings.md).  
  
> **Poznámka:** k zajištění, zda jsou informace správné výsledky dotazování, použijte [IVsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx) rozhraní k určení, pokud se před voláním metody načtení potřebuje vyprázdnění mezipaměti a aktualizace [ IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx) rozhraní.
  
#### <a name="registering-custom-font-and-color-category-without-implementing-interfaces"></a>Registrace vlastní písma a barev kategorie bez implementace rozhraní  
Následující příklad kódu ukazuje, jak zaregistrovat vlastní písma a barevných kategorie bez implementace rozhraní:  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\FontAndColors\CSharp Tool Window]  
"Package"="{F5E7E71D-1401-11D1-883B-0000F87579D2}"  
"Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}"  
"ToolWindowPackage"="{7259e420-6241-4e0d-b535-5b820671d183}"  
  
    "NameID"=dword:00000064  
```  

Pro tento příklad kódu:   
-   `"NameID"`= Název lokalizované kategorie na balíček s ID prostředku
-   `"ToolWindowPackage"`= GUID balíčku
-   `"Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}"`Skutečná hodnota může být identifikátor GUID nového poskytované implementátor je jenom jako příklad.  
  
### <a name="set-the-font-and-color-property-category-guid"></a>Nastavte vlastnost kategorie písma a barev GUID  
Následující příklad kódu ukazuje nastavení identifikátory GUID kategorie.  
  
```  
// m_pView is your IVsTextView  
IVsTextEditorPropertyCategoryContainer spPropCatContainer =  
(IVsTextEditorPropertyCategoryContainer)m_pView;  
if (spPropCatContainer != null)  
{  
IVsTextEditorPropertyContainer spPropContainer;  
Guid GUID_EditPropCategory_View_MasterSettings =  
new Guid("{D1756E7C-B7FD-49a8-B48E-87B14A55655A}");  
hr = spPropCatContainer.GetPropertyCategory(  
ref GUID_EditPropCategory_View_MasterSettings,  
out spPropContainer);  
if(hr == 0)  
{  
hr =  
spPropContainer.SetProperty(  
VSEDITPROPID.VSEDITPROPID_ViewGeneral_FontCategory,  
catGUID);  
hr =  
spPropContainer.SetProperty(  
VSEDITPROPID.VSEDITPROPID_ViewGeneral_ColorCategory,  
catGUID);  
}  
}  
```  
