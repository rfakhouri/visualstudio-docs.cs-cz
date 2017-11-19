---
title: "Bitové kopie služby a katalog | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34990c37-ae98-4140-9b1e-a91c192220d9
caps.latest.revision: "37"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f5813788834a7a5a99c10fe6dafc35a300bac007
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="image-service-and-catalog"></a>Bitové kopie služby a katalog
Tato kuchařka obsahuje pokyny a osvědčené postupy pro přijetí Visual Studio Service bitovou kopii a bitovou kopii katalogu byla zavedená v sadě Visual Studio 2015.  
  
 Službu image byla zavedená v sadě Visual Studio 2015 umožňuje vývojářům získat nejlepší obrázky pro zařízení a uživatele zvolený motiv zobrazíte bitovou kopii, včetně správné motivů pro kontext, ve kterém jsou zobrazeny. Přijmutí služby bitové kopie se vyhnout hlavní problémové body týkající se údržby asset, HDPI škálování a motivů.  
  
|||  
|-|-|  
|**Problémy ještě dnes**|**Řešení**|  
|Prolnutí barvy pozadí|Předdefinované prolnutí alfa|  
|Obrázky motivů (některé)|Metadata motiv|  
|V režimu Vysoký kontrast|Alternativní prostředky vysoký kontrast|  
|Pro různé režimy DPI potřebovat víc zdrojů|Vybrat prostředky s vektorové záložního|  
|Duplicitní bitové kopie|Jeden identifikátor za koncept bitové kopie|  
  
 Proč přijmout službu image?  
  
-   Vždycky získáte nejnovější "pixelů dokonalou" image ze sady Visual Studio  
  
-   Můžete odeslat a používat vlastní Image  
  
-   Není nutné k testování obrázků se při Windows přidá nový Škálování DPI  
  
-   Adresa staré architektury překážek, se kterými v vaší implementace  
  
 Nástrojů Visual Studio shell, před a po pomocí bitové kopie služby:  
  
 ![Bitové kopie služby před a po](../extensibility/media/image-service-before-and-after.png "bitové kopie služby před a po")  
  
## <a name="how-it-works"></a>Jak to funguje  
 Službu bitové kopie můžete zadat rastrové image, která je vhodná pro všechny podporované uživatelského rozhraní framework:  
  
-   WPF: BitmapSource  
  
-   WinForms: System.Drawing.Bitmap  
  
-   Win32: HBITMAP  
  
 Vývojový diagram bitové kopie služby  
  
 ![Bitové kopie služby vývojový Diagram](../extensibility/media/image-service-flow-diagram.png "bitové kopie služby vývojový Diagram")  
  
 **Monikery bitové kopie**  
  
 Obrázek Přezdívka (nebo Přezdívka pro zkrácení) je pár GUID nebo ID, který jednoznačně identifikuje prostředek bitové kopie nebo bitové kopie seznamu prostředek v knihovně.  
  
 **Známé monikery**  
  
 Sada monikery bitové kopie, které jsou obsažené v katalogu bitové kopie Visual Studio a veřejně consumable všechny součásti sady Visual Studio nebo rozšíření.  
  
 **Soubory manifestu obrázků**  
  
 Soubory manifestu (.imagemanifest) bitové kopie jsou soubory XML, které definují sadu prostředků bitové kopie, zástupných názvů, které představují tyto prostředky a skutečné bitové kopie nebo bitové kopie, které představují každý prostředek. Manifesty bitové kopie můžete definovat samostatné bitové kopie nebo bitové kopie jsou uvedené pro starší verze podpora uživatelského rozhraní. Kromě toho jsou atributy, které lze nastavit na prostředku nebo na jednotlivé bitové kopie za každý prostředek změnit, kdy a jak se zobrazují tyto prostředky.  
  
 **Schéma manifestu bitové kopie**  
  
 Manifest dokončení obrázek vypadá takto:  
  
```xml  
<ImageManifest>  
      <!-- zero or one Symbols elements -->  
      <Symbols>  
        <!-- zero or more Import, Guid, ID, or String elements -->  
      </Symbols>  
      <!-- zero or one Images elements -->  
      <Images>  
        <!-- zero or more Image elements -->  
      </Images>  
      <!-- zero or one ImageLists elements -->  
      <ImageLists>  
        <!-- zero or more ImageList elements -->  
      </ImageLists>  
</ImageManifest>  
```  
  
 **Symboly**  
  
 Jak docílit přehlednosti a údržby, manifest bitové kopie můžete použít symboly pro hodnoty atributu. Symboly jsou definovány takto:  
  
```xml  
<Symbols>  
      <Import Manifest="manifest" />  
      <Guid Name="ShellCommandGuid" Value="8ee4f65d-bab4-4cde-b8e7-ac412abbda8a" />  
      <ID Name="cmdidSaveAll" Value="1000" />  
      <String Name="AssemblyName" Value="Microsoft.VisualStudio.Shell.UI.Internal" />  
</Symbols>  
```  
  
|||  
|-|-|  
|**Dílčí element**|**Definice**|  
|Import|Importuje symboly daném souboru manifestu pro použití v aktuální manifestu|  
|Identifikátor GUID|Symbol reprezentuje identifikátor GUID a musí odpovídat identifikátoru GUID formátování|  
|ID|Symbol reprezentuje ID a musí být nezáporné celé číslo|  
|String|Symbol představuje hodnotu libovolný řetězec|  
  
 Symboly jsou velká a malá písmena a odkazované pomocí $(symbol-name) syntaxe:  
  
```xml  
<Image Guid="$(ShellCommandGuid)" ID="$(cmdidSaveAll)" >  
      <Source Uri="/$(AssemblyName);Component/Resources/image.xaml" />  
</Image>  
```  
  
 Některé symboly jsou předdefinovány pro všechny manifesty. Ty mohou být použity v identifikátoru Uri atributu \<zdroje > nebo \<Import > elementu, který chcete cesty odkazů v místním počítači.  
  
|||  
|-|-|  
|**Symbol**|**Popis**|  
|CommonProgramFiles|Hodnota proměnné prostředí % CommonProgramFiles %|  
|LocalAppData|Hodnota proměnné prostředí % LocalAppData %|  
|ManifestFolder|Ve složce obsahující soubor manifestu|  
|MyDocuments|Úplná cesta ke složce Dokumenty aktuálního uživatele|  
|ProgramFiles|Hodnota proměnné prostředí % ProgramFiles %|  
|Systém|Složky Windows\System32|  
|WinDir|Hodnota proměnné prostředí % WinDir %|  
  
 **Bitové kopie**  
  
 \<Image > element definuje obrázek, který může odkazovat přezdívka. Identifikátor GUID a ID, které dohromady tvoří Přezdívka bitové kopie. Přezdívka pro bitovou kopii musí být jedinečný v rámci celého obrázku knihovny. Pokud má více než jeden obrázek dané přezdívka, první z nich došlo při vytváření knihovny je ten, který je zachován.  
  
 Musí obsahovat alespoň jeden zdroj. Velikost jazykově neutrální zdroje získáte nejlepších výsledků napříč širokým spektrem velikostí, ale se nevyžadují. Pokud služby se zobrazí výzva pro bitovou kopii velikosti není definovaná v \<Image > elementu a neexistuje žádný zdroj velikost jazykově neutrální, služba zvolit nejlepší velikost konkrétní zdroj a škálování na požadovanou velikost.  
  
```xml  
<Image Guid="guid" ID="int" AllowColorInversion="true/false">  
      <Source ... />  
      <!-- optional additional Source elements -->  
</Image>  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|Identifikátor GUID|[Vyžaduje] Část GUID Přezdívka bitové kopie|  
|ID|[Vyžaduje] Část ID Přezdívka bitové kopie|  
|AllowColorInversion|[Volitelné, výchozí true] Určuje, jestli bitovou kopii můžete mít jeho barvy prostřednictvím kódu programu obrácený při použití na tmavý pozadí.|  
  
 **Zdroj**  
  
 \<Zdroje > element definuje jediný zdroj zdroj obrázku (XAML a PNG).  
  
```xml  
<Source Uri="uri" Background="background">  
      <!-- optional NativeResource element -->  
 </Source>  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|identifikátor URI|[Vyžaduje] Identifikátor URI, který definuje, kde lze načíst obrázek z. Může být jeden z následujících akcí:<br /><br /> -A [Pack URI](http://msdn.microsoft.com/en-US/library/aa970069\(v=vs.100\).aspx) pomocí aplikace: / / / autority<br />– Odkaz na absolutní součásti prostředků<br />– Cesta k souboru, který obsahuje nativní prostředků|  
|Pozadí|[Nepovinné] Určuje, co na druhu pozadí, které zdroj je určena k použití.<br /><br /> Může být jeden z následujících akcí:<br /><br /> *Lehký:* zdroji lze použít na světle pozadí.<br /><br /> *Světlý:*zdroji lze použít v tmavý pozadí.<br /><br /> *Funkce Vysoký kontrast:* zdroji lze použít na všechny pozadí v režimu vysokého kontrastu.<br /><br /> *HighContrastLight:* zdroji lze použít na světle pozadí v režimu vysokého kontrastu.<br /><br /> *HighContrastDark:* zdroji lze použít na tmavý pozadí v režimu vysokého kontrastu.<br /><br /> Pokud je vynechán atribut pozadí, zdroji lze použít v jakékoli pozadí.<br /><br /> Pokud je pozadí *Light*, *tmavý*, *HighContrastLight*, nebo *HighContrastDark*, jsou nikdy Invertovat barvy zdroj. Pokud je tento parametr vynechán nebo nastavte na pozadí *funkce Vysoký kontrast*, řídí inverzi barev zdroj obrázku **AllowColorInversion** atribut.|  
|||  
  
 A \<zdroje > element může obsahovat právě jeden z následujících volitelné dílčí prvky:  
  
||||  
|-|-|-|  
|**Element**|**Atributy (všechna požadovaná)**|**Definice**|  
|\<Velikost >|Hodnota|Zdroj se použije pro bitové kopie na danou velikost (v jednotkách zařízení). Image bude čtvereček.|  
|\<SizeRange >|MinSize, MaxSize|Zdroj se použije pro obrázky z MinSize k MaxSize (v jednotkách zařízení) (včetně). Image bude čtvereček.|  
|\<Dimenze >|Šířky, výšky|Zdroj se použije pro Image dané šířky a výšky (v jednotkách zařízení).|  
|\<DimensionRange >|Hodnota MinWidth, MinHeight,<br /><br /> MaxWidth MaxHeight|Zdroj se použije pro bitové kopie z minimální šířky a výšky maximální šířky a výšky (v jednotkách zařízení) (včetně).|  
  
 A \<zdroje > element může obsahovat také volitelný \<NativeResource > dílčí element, který definuje \<zdroje > načtené z nativní sestavení namísto spravované sestavení.  
  
```xml  
<NativeResource Type="type" ID="int" />  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|Typ|[Vyžaduje] Typ nativní prostředku, XAML nebo PNG|  
|ID|[Vyžaduje] Celočíselnou část ID nativní prostředků|  
  
 **ImageList**  
  
 \<ImageList > element definuje kolekci bitové kopie, které mohou být vráceny v jednom pruhů. Pruh je založen na vyžádání, podle potřeby.  
  
```xml  
<ImageList>  
      <ContainedImage Guid="guid" ID="int" External="true/false" />  
      <!-- optional additional ContainedImage elements -->  
 </ImageList>  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|Identifikátor GUID|[Vyžaduje] Část GUID Přezdívka bitové kopie|  
|ID|[Vyžaduje] Část ID Přezdívka bitové kopie|  
|Externí|[Volitelné, výchozí hodnota je false] Určuje, zda obrázek Přezdívka odkazuje na obrázek v aktuální manifestu.|  
  
 Chcete-li obrázek definované v aktuální manifestu nemá Přezdívka pro bitovou kopii obsažené. Pokud nelze nalézt bitovou kopii obsažené v knihovně bitovou kopii, bitovou kopii prázdné zástupný symbol se použije na příslušné místo.  
  
## <a name="using-the-image-service"></a>Pomocí služby bitové kopie  
  
### <a name="first-steps-managed"></a>První kroky (spravované)  
 Chcete-li používat službu, image, do projektu přidejte odkazy na některé nebo všechny následující sestavení:  
  
-   **Microsoft.VisualStudio.ImageCatalog.dll**  
  
    -   Vyžaduje, pokud používáte integrované image katalogu KnownMonikers  
  
-   **Microsoft.VisualStudio.Imaging.dll**  
  
    -   Vyžaduje, pokud použijete **CrispImage** a **ImageThemingUtilities** v uživatelském rozhraní WPF  
  
-   **Microsoft.VisualStudio.Imaging.Interop.14.0.DesignTime.dll**  
  
    -   Vyžaduje, pokud použijete **ImageMoniker** a **ImageAttributes** typy  
  
    -   **EmbedInteropTypes** by měla být nastavena na hodnotu true  
  
-   **Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime**  
  
    -   Vyžaduje, pokud použijete **IVsImageService2** typu  
  
    -   **EmbedInteropTypes** by měla být nastavena na hodnotu true  
  
-   **Microsoft.VisualStudio.Utilities.dll**  
  
    -   Vyžaduje, pokud použijete **BrushToColorConverter** pro ImageThemingUtilities. **ImageBackgroundColor** v uživatelském rozhraní WPF  
  
-   **Microsoft.VisualStudio.Shell. \<VSVersion >.0**  
  
    -   Vyžaduje, pokud použijete **IVsUIObject** typu  
  
-   **Microsoft.VisualStudio.Shell.Interop.10.0.dll**  
  
    -   Vyžaduje, pokud použijete pomocné rutiny související s WinForms uživatelského rozhraní  
  
    -   **EmbedInteropTypes** by měla být nastavena na hodnotu true  
  
### <a name="first-steps-native"></a>První kroky (nativní)  
 Chcete-li používat službu, image, obsahovat některé nebo všechny následující hlavičky do projektu:  
  
-   **KnownImageIds.h**  
  
    -   Vyžaduje, pokud použijete katalogu předdefinované image **KnownMonikers**, ale nemůžete použít **ImageMoniker** typu, například při vrácení hodnot z **IVsHierarchy GetGuidProperty**nebo **GetProperty** volání.  
  
-   **KnownMonikers.h**  
  
    -   Vyžaduje, pokud použijete katalogu předdefinované image **KnownMonikers**.  
  
-   **ImageParameters140.h**  
  
    -   Vyžaduje, pokud použijete **ImageMoniker** a **ImageAttributes** typy.  
  
-   **VSShell140.h**  
  
    -   Vyžaduje, pokud použijete **IVsImageService2** typu.  
  
-   **ImageThemingUtilities.h**  
  
    -   Vyžaduje, pokud se nepodařilo zpracovat motivů můžete službu bitové kopie.  
  
    -   Pokud službu image může zpracovat váš obrázek motivů, nepoužívejte tuto hlavičku.  
  
-   **VSUIDPIHelper.h**  
  
    -   Vyžaduje, pokud použijete Pomocníci DPI získat aktuální DPI.  
  
## <a name="how-do-i-write-new-wpf-ui"></a>Jak lze napsat nové uživatelské rozhraní WPF?  
  
1.  Spuštění tak, že přidáte odkazy na sestavení, které jsou potřebné v výše nejdřív kroky části do projektu. Nemusíte přidejte všechny z nich, proto přidejte odkazy, které potřebujete. (Poznámka: Pokud používáte nebo mít přístup k **barvy** místo **štětce**, můžete přejít odkaz na **nástroje**, protože převaděč nebude nutné.)  
  
2.  Vybrat požadovanou image a získat jeho přezdívka. Použít **KnownMoniker**, nebo použít vlastní, pokud máte vlastní vlastních bitových kopií a zástupných názvů.  
  
3.  Přidat **CrispImages** do vaší jazyka XAML. (Viz následující příklad).  
  
4.  Nastavte **ImageThemingUtilities.ImageBackgroundColor** vlastnost ve vaší hierarchii uživatelského rozhraní. (Měla by být nastavena v umístění, kde barvu pozadí se označuje, nikoli nutně na **CrispImage**.) (Viz následující příklad).  
  
```xaml  
<Window  
  x:Class="WpfApplication.MainWindow"  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:imaging="clr-namespace:Microsoft.VisualStudio.Imaging;assembly=Microsoft.VisualStudio.Imaging"  
  xmlns:theming="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Imaging"  
  xmlns:utilities="clr-namespace:Microsoft.Internal.VisualStudio.Imaging;assembly=Microsoft.VisualStudio.Imaging"  
  xmlns:catalog="clr-namespace:Microsoft.VisualStudio.Imaging;assembly=Microsoft.VisualStudio.ImageCatalog"  
  Title="MainWindow" Height="350" Width="525" UseLayoutRounding="True">  
  <Window.Resources>  
    <utilities:BrushToColorConverter x:Key="BrushToColorConverter"/>  
  </Window.Resources>  
  <StackPanel Background="White" VerticalAlignment="Center"   
    theming:ImageThemingUtilities.ImageBackgroundColor="{Binding Background, RelativeSource={RelativeSource Self}, Converter={StaticResource BrushToColorConverter}}">  
    <imaging:CrispImage Width="16" Height="16" Moniker="{x:Static catalog:KnownMonikers.MoveUp}" />  
  </StackPanel>  
</Window>  
```  
  
 **Jak aktualizovat existující uživatelského rozhraní grafického subsystému WPF**  
  
 Aktualizace stávající uživatelského rozhraní grafického subsystému WPF je poměrně jednoduché proces, který se skládá z tři základní kroky:  
  
1.  Nahraďte všechny \<Image > prvky v uživatelském rozhraní s \<CrispImage > elementy  
  
2.  Změňte všechny atributy zdroje Přezdívka atributy  
  
    -   Pokud nikdy změny bitovou kopii a používáte **KnownMonikers**, staticky vazby pro tuto vlastnost **KnownMoniker**. (Viz výše uvedeném příkladu).  
  
    -   Pokud nikdy změní bitovou kopii a používáte svoji vlastní image, pak staticky vytvořte vazbu s vlastními přezdívka.  
  
    -   Pokud můžete změnit obrázek, vazbu atribut Přezdívka kód vlastnosti, která upozorní na změny vlastností.  
  
3.  Někde v hierarchii uživatelského rozhraní, nastavte **ImageThemingUtilities.ImageBackgroundColor** k Ujistěte se, že inverze barev funguje správně.  
  
    -   To může vyžadovat použití **BrushToColorConverter** třídy. (Viz výše uvedeném příkladu).  
  
## <a name="how-do-i-update-win32-ui"></a>Jak aktualizovat uživatelského rozhraní Win32?  
 Přidejte následující kód bez ohledu na vhodné nahradit nezpracovaná načítání obrázků. Přepnout hodnoty pro vrácení HBITMAPs versus HICONs versus HIMAGELIST podle potřeby.  
  
 **Získat služby bitové kopie**  
  
```cpp  
CComPtr<IVsImageService2> spImgSvc;  
CGlobalServiceProvider::HrQueryService(SID_SVsImageService, &spImgSvc);  
```  
  
 **Požaduje bitovou kopii**  
  
```cpp  
ImageAttributes attr = { 0 };  
attr.StructSize      = sizeof(attributes);  
attr.Format          = DF_Win32;  
// IT_Bitmap for HBITMAP, IT_Icon for HICON, IT_ImageList for HIMAGELIST  
attr.ImageType       = IT_Bitmap;  
attr.LogicalWidth    = 16;  
attr.LogicalHeight   = 16;  
attr.Dpi             = VsUI::DpiHelper::GetDeviceDpiX();  
attr.Background      = 0xFFFFFFFF;  
// Desired RGBA color, if you don't use this, don't set IAF_Background below  
attr.Flags           = IAF_RequiredFlags | IAF_Background;  
  
CComPtr<IVsUIObject> spImg;  
// Replace this KnownMoniker with your desired ImageMoniker  
spImgSvc->GetImage(KnownMonikers::Blank, attributes, &spImg);  
  
```  
  
## <a name="how-do-i-update-winforms-ui"></a>Jak aktualizovat WinForms uživatelského rozhraní  
 Přidejte následující kód bez ohledu na vhodné nahradit nezpracovaná načítání obrázků. Přepnout hodnoty pro vrácení rastrové obrázky a ikony, podle potřeby.  
  
 **Užitečné using – příkaz**  
  
```csharp  
using GelUtilities = Microsoft.Internal.VisualStudio.PlatformUI.Utilities;  
```  
  
 **Získat služby bitové kopie**  
  
```csharp  
// This or your preferred way of querying for Visual Studio services  
IVsImageService2 imageService = (IVsImageService2)Package.GetGlobalService(typeof(SVsImageService));  
  
```  
  
 **Požadují bitovou kopii**  
  
```csharp  
ImageAttributes attributes = new ImageAttributes  
{  
    StructSize    = Marshal.SizeOf(typeof(ImageAttributes)),  
    // IT_Bitmap for Bitmap, IT_Icon for Icon  
    ImageType     = (uint)_UIImageType.IT_Bitmap,  
    Format        = (uint)_UIDataFormat.DF_WinForms,  
    LogicalWidth  = 16,  
    LogicalHeight = 16,  
    // Desired RGBA color, if you don't use this, don't set IAF_Background below  
    Background    = 0xFFFFFFFF,  
    Flags = (uint)_ImageAttributesFlags.IAF_RequiredFlags | _ImageAttributesFlags.IAF_Background,  
};  
  
// Replace this KnownMoniker with your desired ImageMoniker  
IVsUIObject uIObj = imageService.GetImage(KnownMonikers.Blank, attributes);  
  
Bitmap bitmap = (Bitmap)GelUtilities.GetObjectData(uiObj); // Use this if you need a bitmap  
// Icon icon = (Icon)GelUtilities.GetObjectData(uiObj); // Use this if you need an icon  
  
```  
  
## <a name="how-do-i-use-image-monikers-in-a-new-tool-window"></a>Použití zástupných názvů bitové kopie v novém okně nástroje  
 Šablona projektu balíčku VSIX byl aktualizovaný pro Visual Studio 2015. Chcete-li vytvořit nové okno nástroje, klikněte pravým tlačítkem na projekt VSIX a vyberte "Přidat novou položku..." (Ctrl + Shift + A). V uzlu rozšíření pro jazyk projektu vyberte "Vlastní nástroj okno," pojmenujte panel nástrojů a klikněte na tlačítko "Přidat".  
  
 Toto jsou klíčové místech použití zástupných názvů v okně nástroje. Postupujte podle pokynů pro každou:  
  
1.  Na kartě okno nástroj při karty získat malé dostatek (používat i v přepínač okna Ctrl + Tab).  
  
     Přidejte tento řádek do konstruktoru pro třídu, která je odvozena z **ToolWindowPane** typu:  
  
    ```csharp  
    // Replace this KnownMoniker with your desired ImageMoniker  
    this.BitmapImageMoniker = KnownMonikers.Blank;  
    ```  
  
2.  Příkaz otevřete okno nástroje.  
  
     V souboru .vsct pro balíček upravte panel nástrojů příkazového tlačítka:  
  
    ```xml  
    <Button guid="guidPackageCmdSet" id="CommandId" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <!-- Replace this KnownMoniker with your desired ImageMoniker -->  
      <Icon guid="ImageCatalogGuid" id="Blank" />  
      <!-- Add this -->  
      <CommandFlag>IconIsMoniker</CommandFlag>  
      <Strings>  
        <ButtonText>MyToolWindow</ButtonText>  
      </Strings>  
    </Button>  
    ```  
  
 **Použití zástupných názvů bitové kopie v existujícím okně nástroje**  
  
 Aktualizace existujícího okna nástroj používat monikery bitové kopie je podobná kroky pro vytvoření nové okno nástroje.  
  
 Toto jsou klíčové místech použití zástupných názvů v okně nástroje. Postupujte podle pokynů pro každou:  
  
1.  Na kartě okno nástroj při karty získat malé dostatek (používat i v přepínač okna Ctrl + Tab).  
  
    1.  Odeberte tyto řádky (pokud existují) v konstruktoru pro třídu, která je odvozena z **ToolWindowPane** typu:  
  
        ```csharp  
        this.BitmapResourceID = <Value>;  
        this.BitmapIndex = <Value>;  
        ```  
  
    2.  Viz krok #1 "Jak se dá použít bitovou kopii Monikery v novém okně nástroje?" část výše.  
  
2.  Příkaz otevřete okno nástroje.  
  
    -   Viz krok #2 "Jak se dá použít bitovou kopii Monikery v novém okně nástroje?" část výše.  
  
## <a name="how-do-i-use-image-monikers-in-a-vsct-file"></a>Použití zástupných názvů image v souboru .vsct  
 Aktualizujte si soubor .vsct označené řádky komentářů níže:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <!--  Include the definitions for images included in the VS image catalog -->  
  <Include href="KnownImageIds.vsct"/>  
  <Commands package="guidMyPackage">  
    <Buttons>  
      <Button guid="guidMyCommandSet" id="cmdidMyCommand" priority="0x0000" type="Button">  
        <!-- Add an Icon element, changing the attributes to match the image moniker you want to use.  
             In this case, we're using the Guid for the VS image catalog.  
             Change the id attribute to be the ID of the desired image moniker. -->  
        <Icon guid="ImageCatalogGuid" id="OpenFolder" />  
        <CommandFlag>DynamicVisibility</CommandFlag>  
        <CommandFlag>DefaultInvisible</CommandFlag>  
        <CommandFlag>DefaultDisabled</CommandFlag>  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>IconAndText</CommandFlag>  
        <!-- Add the IconIsMoniker CommandFlag -->  
        <CommandFlag>IconIsMoniker</CommandFlag>  
        <Strings>  
          <ButtonText>Quick Fixes...</ButtonText>  
          <CommandName>Show Quick Fixes</CommandName>  
          <CanonicalName>ShowQuickFixes</CanonicalName>  
          <LocCanonicalName>ShowQuickFixes</LocCanonicalName>  
        </Strings>  
      </Button>  
    </Buttons>  
  </Commands>  
  <!-- It is recommended that you remove <Bitmap> elements that are no longer used in the vsct file -->  
  <Symbols>  
    <GuidSymbol name="guidMyPackage"    value="{1491e936-6ffe-474e-8371-30e5920d8fdd}" />  
    <GuidSymbol name="guidMyCommandSet" value="{10347de4-69a9-47f4-a950-d3301f6d2bc7}">  
      <IDSymbol name="cmdidMyCommand" value="0x9437" />  
    </GuidSymbol>  
  </Symbols>  
</CommandTable>  
```  
  
 **Co když můj .vsct také třeba soubor číst starší verze sady Visual Studio?**  
  
 Nelze rozpoznat starší verze sady Visual Studio **IconIsMoniker** příkaz příznak. Obrázky ze služby bitové kopie můžete použít ve verzích sady Visual Studio, které ji podporují, ale pokračovat v používání starého bitové kopie na starší verze sady Visual Studio. Uděláte to tak, by tento soubor .vsct nechat beze změny (a proto kompatibilní se staršími verzemi sady Visual Studio) a vytvoření souboru CSV (hodnoty oddělené čárkami), který mapuje z dvojice hodnot GUID nebo ID definované v souboru .vsct \<bitmap > element do bitové kopie identifikátor GUID nebo ID páry přezdívka.  
  
 Formát souboru CSV mapování je:  
  
```  
Icon guid, Icon id, Moniker guid, Moniker id  
b714fcf7-855e-4e4c-802a-1fd87144ccad,1,fda30684-682d-421c-8be4-650a2967058e,100  
b714fcf7-855e-4e4c-802a-1fd87144ccad,2,fda30684-682d-421c-8be4-650a2967058e,200  
```  
  
 Soubor CSV je nasazená s tímto balíčkem a je zadána jeho umístění **IconMappingFilename** vlastnost **ProvideMenuResource** atribut balíčku:  
  
```csharp  
[ProvideMenuResource("MyPackage.ctmenu", 1, IconMappingFilename="IconMappings.csv")]  
```  
  
 **IconMappingFilename** je relativní cesta implicitně root na $PackageFolder$ (jako v příkladu výše) nebo absolutní cesta na adresář definované proměnné prostředí, jako je například @"%UserProfile%\ explicitně root. dir1\dir2\MyMappingFile.csv".  
  
## <a name="how-do-i-port-a-project-system"></a>Jak portu systému projektu?  
 **Jak dodávat ImageMonikers pro projekt**  
  
1.  Implementace **VSHPROPID_SupportsIconMonikers** na projektu **IVsHierarchy**a vrátí hodnotu PRAVDA.  
  
2.  Implementovat buď **VSHPROPID_IconMonikerImageList** (pokud použili původní projekt **VSHPROPID_IconImgList**) nebo **VSHPROPID_IconMonikerGuid**,  **VSHPROPID_IconMonikerId**, **VSHPROPID_OpenFolderIconMonikerGuid**, **VSHPROPID_OpenFolderIconMonikerId** (pokud použili původní projekt  **VSHPROPID_IconHandle** a **VSHPROPID_OpenFolderIconHandle**).  
  
3.  Změňte implementaci původní VSHPROPIDs pro ikony pro vytvoření "starší" verzích ikony, pokud body rozšíření žádosti je. **IVsImageService2** poskytuje funkce, které jsou potřebné k získání těchto ikony  
  
 **Další požadavky pro VB / digitálních projektu C#**  
  
 Pouze implementovat **VSHPROPID_SupportsIconMonikers** Pokud zjistíte, že je váš projekt **nejkrajnější příchuť**. Jinak skutečné nejkrajnější příchuť nemusí podporovat monikery bitové kopie ve skutečnosti a vaše základní příchuť může efektivně "schovat" přizpůsobené Image.  
  
 **Použití zástupných názvů bitové kopie v systému CPS**  
  
 Nastavení vlastních bitových kopií v systému CPS (běžné systému projektu) lze provést ručně nebo pomocí šablony položky, která se dodává s SDK rozšíření systému projektu.  
  
 **Pomocí rozšíření systému projektu sady SDK**  
  
 Postupujte podle pokynů v [zadejte vlastní ikony pro typ projektu typu/položky](https://github.com/Microsoft/VSProjectSystem/blob/master/doc/scenario/provide_custom_icons_for_the_project_or_item_type.md) můžete přizpůsobit prohlášení CPS. Další informace o prohlášení CPS lze najít na [dokumentaci projektu rozšíření systému Visual Studio](https://github.com/Microsoft/VSProjectSystem)  
  
 **Ručně pomocí ImageMonikers**  
  
1.  Implementace a exportovat **IProjectTreeModifier** rozhraní ve vašem projektu systému.  
  
2.  Určete, který **KnownMoniker** nebo Přezdívka vlastní image, kterou chcete použít.  
  
3.  V **ApplyModifications** metoda, proveďte následující někde v metodě před vrácením novou větev, podobně jako následujícím příkladu:  
  
    ```csharp  
    // Replace this KnownMoniker with your desired ImageMoniker  
    tree = tree.SetIcon(KnownMonikers.Blank.ToProjectSystemType());  
    ```  
  
4.  Pokud vytváříte novou větev, můžete nastavit vlastní Image pomocí předávání požadované monikery do metody NewTree, podobně jako následujícím příkladu:  
  
    ```csharp  
    // Replace this KnownMoniker with your desired ImageMoniker  
    ProjectImageMoniker icon         = KnownMonikers.FolderClosed.ToProjectSystemType();  
    ProjectImageMoniker expandedIcon = KnownMonikers.FolderOpened.ToProjectSystemType();  
  
    return this.ProjectTreeFactory.Value.NewTree(/*caption*/<value>,  
                                                 /*filePath*/<value>,  
                                                 /*browseObjectProperties*/<value>,  
                                                 icon,  
                                                 expandedIcon);  
    ```  
  
## <a name="how-do-i-convert-from-a-real-image-strip-to-a-moniker-based-image-strip"></a>Jak převést pruhu skutečné bitové kopie na pruhu bitové kopie založené na přezdívku?  
 **Je nutné podporovat HIMAGELISTs**  
  
 Pokud dojde už existující pruhu bitové kopie pro váš kód, který chcete aktualizovat pomocí této bitové kopie služby, ale jsou omezeny rozhraní API, které vyžadují předávání kolem seznamů obrázků, stále můžete získat výhody služby bitové kopie. K vytvoření bitové kopie založené na Přezdívka pruhu, použijte následující postup k vytvoření manifestu z existující zástupných názvů.  
  
1.  Spustit **ManifestFromResources** nástroj, předání pruhu bitové kopie. Tím se vygeneruje manifestu pro pruh.  
  
    -   Doporučená: Zadejte název jiného výchozího manifest tak, aby vyhovovala jeho použití.  
  
2.  Pokud používáte pouze **KnownMonikers**, proveďte následující kroky:  
  
    -   Nahraďte \<bitové kopie > oddílu manifest s \<bitové kopie / >.  
  
    -   Odeberte všechny subimage ID (cokoli s \<imagestrip name > _ ##).  
  
    -   Doporučená: přejmenujte AssetsGuid symbolů a symbol pruhu obrázku tak, aby vyhovovala jeho použití.  
  
    -   Nahraďte každý **ContainedImage**na identifikátor GUID s $(ImageCatalogGuid), nahraďte každý **ContainedImage**na ID s $(\<Přezdívka >) a do každé Přidatatributexterní="true"**ContainedImage**  
  
        -   \<Přezdívka > by měla být nahrazená s **KnownMoniker** odpovídající bitovou kopii, ale s "KnownMonikers." Název odeberou.  
  
    -   Přidat < Import Manifest="$(ManifestFolder)\\< nainstalovat relativní cestu k domovskému adresáři na\>\Microsoft.VisualStudio.ImageCatalog.imagemanifest" /\> do horní části \<symboly > části.  
  
        -   Relativní cesta je určen podle umístění nasazení, které jsou definované v nastavení vytváření obsahu pro manifest.  
  
3.  Spustit **ManifestToCode** nástroj ke generování obálky tak, aby existující kód má Přezdívka můžete použít k dotazování služby pruhu bitovou kopii, bitovou kopii.  
  
    -   Doporučená: Zadejte jiný než výchozí názvy pro obálky a obory názvů tak, aby vyhovovala jejich využití.  
  
4.  Udělejte všechny přidá, vytváření instalaci a nasazení a jiné změny kódu pro práci s službu bitové kopie a nové soubory.  
  
 Ukázka manifest včetně interních i externích obrázků, které chcete zobrazit, co by měl vypadat jako:  
  
```xml  
<?xml version="1.0"?>  
<ImageManifest  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
  xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">  
  
  <Symbols>  
    <!-- This needs to be the relative path from your manifest to the ImageCatalog's manifest  
         where $(ManifestFolder) is the deployed location of this manifest. -->  
    <Import Manifest="$(ManifestFolder)\<RelPath>\Microsoft.VisualStudio.ImageCatalog.imagemanifest" />  
  
    <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/ImageStrip" />  
    <Guid Name="ImageGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" />  
    <Guid Name="ImageStripGuid" Value="{9c84a570-d9a7-4052-a340-188fb276f973}" />  
    <ID Name="MyImage_0" Value="100" />  
    <ID Name="MyImage_1" Value="101" />  
    <ID Name="InternalList" Value="1001" />  
    <ID Name="ExternalList" Value="1002" />  
  </Symbols>  
  
  <Images>  
    <Image Guid="$(ImageGuid)" ID="$(MyImage_0)">  
      <Source Uri="$(Resources)/MyImage_0.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
    <Image Guid="$(ImageGuid)" ID="$(MyImage_1)">  
      <Source Uri="$(Resources)/MyImage_1.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
  </Images>  
  
  <ImageLists>  
    <ImageList Guid="$(ImageStripGuid)" ID="$(InternalList)">  
      <ContainedImage Guid="$(ImageGuid)" ID="$(MyImage_0)" />  
      <ContainedImage Guid="$(ImageGuid)" ID="$(MyImage_1)" />  
    </ImageList>  
    <ImageList Guid="$(ImageStripGuid)" ID="$(ExternalList)">  
      <ContainedImage Guid="$(ImageCatalogGuid)" ID="$(StatusError)" External="true" />  
      <ContainedImage Guid="$(ImageCatalogGuid)" ID="$(StatusWarning)" External="true" />  
      <ContainedImage Guid="$(ImageCatalogGuid)" ID="$(StatusInformation)" External="true" />  
    </ImageList>  
  </ImageLists>  
  
</ImageManifest>  
```  
  
 **Nemusíte podporovat HIMAGELISTs**  
  
1.  Určení sady **KnownMonikers** odpovídat Image ve vašem pruhů bitové kopie, nebo vytvořit vlastní zástupných názvů pro Image ve vašem pruhů bitové kopie.  
  
2.  Aktualizujte jakoukoli mapování, které jste použili k získání požadovaných indexem v pruhu bitové kopie monikery místo toho použít bitovou kopii.  
  
3.  Aktualizace kódu pomocí bitové kopie služby k vyžádání monikery prostřednictvím aktualizované mapování. (To může znamenat, aktualizace až po **CrispImages** pro spravovaný kód, nebo požaduje HBITMAPs nebo HICONs ze služby bitové kopie a předání je kolem pro nativní kód.)  
  
## <a name="testing-your-images"></a>Testování obrázků  
 Nástroj Image Viewer knihovna slouží k testování vašich manifestů bitové kopie a ujistěte se, že všechno správně vytvořena. Nástroj v naleznete [Visual Studio 2015 SDK](http://msdn.microsoft.com/library/bb166441.aspx). Dokumentace pro tento nástroj a ostatní naleznete [zde](http://aka.ms/VSImageThemeTools).  
  
## <a name="additional-resources"></a>Další zdroje  
  
### <a name="samples"></a>Ukázky kódu  
 Některé Visual Studio – ukázky na webu GitHub se aktualizovaly v rámci ukazují, jak používat službu bitové kopie v rámci různých bodů rozšiřitelnosti Visual Studio.  
  
 Zkontrolujte [http://github.com/Microsoft/VSSDK-Extensibility-Samples](http://github.com/Microsoft/VSSDK-Extensibility-Samples) nejnovější ukázek.  
  
### <a name="tooling"></a>Nástrojů  
 Sadu nástrojů podpory pro službu bitové kopie byl vytvořen, které pomáhají při vytváření nebo aktualizace uživatelského rozhraní, která spolupracuje se službou bitové kopie. Další informace o nástroji pro každý naleznete v dokumentaci, která se dodává s nástroje. Nástroje, které jsou součástí [Visual Studio 2015 SDK.](http://msdn.microsoft.com/library/bb166441.aspx)  
  
 **ManifestFromResources**  
  
 Manifest z prostředků nástroje přebírá seznam prostředky obrázků (PNG nebo XAML) a vygeneruje soubor obrázku manifestu pro použití se službou image tyto bitové kopie.  
  
 **ManifestToCode**  
  
 Manifest do kódu – nástroj trvá soubor manifestu obrázku a vygeneruje soubor obálku pro odkazování na manifestu hodnoty v kódu (C++, C# a VB) nebo .vsct soubory.  
  
 **ImageLibraryViewer**  
  
 Nástroj Prohlížeč bitové kopie knihovny můžete načítat manifesty bitové kopie a umožňuje uživatelům s nimi manipulovat stejným způsobem, který by Visual Studio a ujistěte se, že manifest správně vytvořena. Uživatel může změnit pozadí, velikosti, nastavení DPI, vysoký kontrast a další nastavení. Také zobrazuje načítání informací o hledání chyb v manifestech a zobrazí informace o zdroji každé bitové kopie v manifestu.  
  
## <a name="faq"></a>Nejčastější dotazy  
  
-   Existují všechny závislosti, které je nutné zahrnout při načítání \<Include="Microsoft.VisualStudio.* odkaz. Interop.14.0.DesignTime"/ >?  
  
    -   Nastavit EmbedInteropTypes = "true" na všechny knihovny DLL zprostředkovatele komunikace s objekty.  
  
-   Nasazení manifest bitové kopie s Moje rozšíření  
  
    -   Přidejte soubor .imagemanifest do projektu.  
  
    -   "Zahrnout VSIX" nastavena na hodnotu True.  
  
-   Mě Probíhá aktualizace můj systém projektu prohlášení CPS. Co se stalo s **ImageName** a **StockIconService**?  
  
    -   o, které tyto byly odstraněny při CPS byl upraven k použití zástupných názvů. Už je třeba volat **StockIconService**, stačí předat požadovanou **KnownMoniker** metody nebo vlastnosti pomocí **ToProjectSystemType()** metoda rozšíření v prohlášení CPS nástrojů. Můžete najít mapování z **ImageName** k **KnownMonikers** níže:  
  
        |||  
        |-|-|  
        |**ImageName**|**KnownMoniker**|  
        |ImageName.OfflineWebApp|KnownImageIds.Web|  
        |ImageName.WebReferencesFolder|KnownImageIds.Web|  
        |ImageName.OpenReferenceFolder|KnownImageIds.FolderOpened|  
        |ImageName.ReferenceFolder|KnownImageIds.Reference|  
        |ImageName.Reference|KnownImageIds.Reference|  
        |ImageName.SdlWebReference|KnownImageIds.WebReferenceFolder|  
        |ImageName.DiscoWebReference|KnownImageIds.DynamicDiscoveryDocument|  
        |ImageName.Folder|KnownImageIds.FolderClosed|  
        |ImageName.OpenFolder|KnownImageIds.FolderOpened|  
        |ImageName.ExcludedFolder|KnownImageIds.HiddenFolderClosed|  
        |ImageName.OpenExcludedFolder|KnownImageIds.HiddenFolderOpened|  
        |ImageName.ExcludedFile|KnownImageIds.HiddenFile|  
        |ImageName.DependentFile|KnownImageIds.GenerateFile|  
        |ImageName.MissingFile|KnownImageIds.DocumentWarning|  
        |ImageName.WindowsForm|KnownImageIds.WindowsForm|  
        |ImageName.WindowsUserControl|KnownImageIds.UserControl|  
        |ImageName.WindowsComponent|KnownImageIds.ComponentFile|  
        |ImageName.XmlSchema|KnownImageIds.XMLSchema|  
        |ImageName.XmlFile|KnownImageIds.XMLFile|  
        |ImageName.WebForm|KnownImageIds.Web|  
        |ImageName.WebService|KnownImageIds.WebService|  
        |ImageName.WebUserControl|KnownImageIds.WebUserControl|  
        |ImageName.WebCustomUserControl|KnownImageIds.WebCustomControl|  
        |ImageName.AspPage|KnownImageIds.ASPFile|  
        |ImageName.GlobalApplicationClass|KnownImageIds.SettingsFile|  
        |ImageName.WebConfig|KnownImageIds.ConfigurationFile|  
        |ImageName.HtmlPage|KnownImageIds.HTMLFile|  
        |ImageName.StyleSheet|KnownImageIds.StyleSheet|  
        |ImageName.ScriptFile|KnownImageIds.JSScript|  
        |ImageName.TextFile|KnownImageIds.Document|  
        |ImageName.SettingsFile|KnownImageIds.Settings|  
        |ImageName.Resources|KnownImageIds.DocumentGroup|  
        |ImageName.Bitmap|KnownImageIds.Image|  
        |ImageName.Icon|KnownImageIds.IconFile|  
        |ImageName.Image|KnownImageIds.Image|  
        |ImageName.ImageMap|KnownImageIds.ImageMapFile|  
        |ImageName.XWorld|KnownImageIds.XWorldFile|  
        |ImageName.Audio|KnownImageIds.Sound|  
        |ImageName.Video|KnownImageIds.Media|  
        |ImageName.Cab|KnownImageIds.CABProject|  
        |ImageName.Jar|KnownImageIds.JARFile|  
        |ImageName.DataEnvironment|KnownImageIds.DataTable|  
        |ImageName.PreviewFile|KnownImageIds.Report|  
        |ImageName.DanglingReference|KnownImageIds.ReferenceWarning|  
        |ImageName.XsltFile|KnownImageIds.XSLTransform|  
        |ImageName.Cursor|KnownImageIds.CursorFile|  
        |ImageName.AppDesignerFolder|KnownImageIds.Property|  
        |ImageName.Data|KnownImageIds.Database|  
        |ImageName.Application|KnownImageIds.Application|  
        |ImageName.DataSet|KnownImageIds.DatabaseGroup|  
        |ImageName.Pfx|KnownImageIds.Certificate|  
        |ImageName.Snk|KnownImageIds.Rule|  
        |ImageName.VisualBasicProject|KnownImageIds.VBProjectNode|  
        |ImageName.CSharpProject|KnownImageIds.CSProjectNode|  
        |ImageName.Empty|KnownImageIds.Blank|  
        |ImageName.MissingFolder|KnownImageIds.FolderOffline|  
        |ImageName.SharedImportReference|KnownImageIds.SharedProject|  
        |ImageName.SharedProjectCs|KnownImageIds.CSSharedProject|  
        |ImageName.SharedProjectVc|KnownImageIds.CPPSharedProject|  
        |ImageName.SharedProjectJs|KnownImageIds.JSSharedProject|  
        |ImageName.CSharpCodeFile|KnownImageIds.CSFileNode|  
        |ImageName.VisualBasicCodeFile|KnownImageIds.VBFileNode|  
  
    -   Mě Probíhá aktualizace mého poskytovatele seznamu dokončení. Co **KnownMonikers** shodovat starý **StandardGlyphGroup** a **StandardGlyph** hodnoty?  
  
        ||||  
        |-|-|-|  
        |GlyphGroupClass|GlyphItemPublic|ClassPublic|  
        |GlyphGroupClass|GlyphItemInternal|ClassInternal|  
        |GlyphGroupClass|GlyphItemFriend|ClassInternal|  
        |GlyphGroupClass|GlyphItemProtected|ClassProtected|  
        |GlyphGroupClass|GlyphItemPrivate|ClassPrivate|  
        |GlyphGroupClass|GlyphItemShortcut|ClassShortcut|  
        |GlyphGroupConstant|GlyphItemPublic|ClassPublic|  
        |GlyphGroupConstant|GlyphItemInternal|ClassInternal|  
        |GlyphGroupConstant|GlyphItemFriend|ClassInternal|  
        |GlyphGroupConstant|GlyphItemProtected|ClassProtected|  
        |GlyphGroupConstant|GlyphItemPrivate|ClassPrivate|  
        |GlyphGroupConstant|GlyphItemShortcut|ClassShortcut|  
        |GlyphGroupDelegate|GlyphItemPublic|DelegatePublic|  
        |GlyphGroupDelegate|GlyphItemInternal|DelegateInternal|  
        |GlyphGroupDelegate|GlyphItemFriend|DelegateInternal|  
        |GlyphGroupDelegate|GlyphItemProtected|DelegateProtected|  
        |GlyphGroupDelegate|GlyphItemPrivate|DelegatePrivate|  
        |GlyphGroupDelegate|GlyphItemShortcut|DelegateShortcut|  
        |GlyphGroupEnum|GlyphItemPublic|EnumerationPublic|  
        |GlyphGroupEnum|GlyphItemInternal|EnumerationInternal|  
        |GlyphGroupEnum|GlyphItemFriend|EnumerationInternal|  
        |GlyphGroupEnum|GlyphItemProtected|EnumerationProtected|  
        |GlyphGroupEnum|GlyphItemPrivate|EnumerationPrivate|  
        |GlyphGroupEnum|GlyphItemShortcut|EnumerationShortcut|  
        |GlyphGroupEnumMember|GlyphItemPublic|EnumerationMemberPublic|  
        |GlyphGroupEnumMember|GlyphItemInternal|EnumerationMemberInternal|  
        |GlyphGroupEnumMember|GlyphItemFriend|EnumerationMemberInternal|  
        |GlyphGroupEnumMember|GlyphItemProtected|EnumerationMemberProtected|  
        |GlyphGroupEnumMember|GlyphItemPrivate|EnumerationMemberPrivate|  
        |GlyphGroupEnumMember|GlyphItemShortcut|EnumerationMemberShortcut|  
        |GlyphGroupEvent|GlyphItemPublic|EventPublic|  
        |GlyphGroupEvent|GlyphItemInternal|EventInternal|  
        |GlyphGroupEvent|GlyphItemFriend|EventInternal|  
        |GlyphGroupEvent|GlyphItemProtected|EventProtected|  
        |GlyphGroupEvent|GlyphItemPrivate|EventPrivate|  
        |GlyphGroupEvent|GlyphItemShortcut|EventShortcut|  
        |GlyphGroupException|GlyphItemPublic|ExceptionPublic|  
        |GlyphGroupException|GlyphItemInternal|ExceptionInternal|  
        |GlyphGroupException|GlyphItemFriend|ExceptionInternal|  
        |GlyphGroupException|GlyphItemProtected|ExceptionProtected|  
        |GlyphGroupException|GlyphItemPrivate|ExceptionPrivate|  
        |GlyphGroupException|GlyphItemShortcut|ExceptionShortcut|  
        |GlyphGroupField|GlyphItemPublic|FieldPublic|  
        |GlyphGroupField|GlyphItemInternal|FieldInternal|  
        |GlyphGroupField|GlyphItemFriend|FieldInternal|  
        |GlyphGroupField|GlyphItemProtected|FieldProtected|  
        |GlyphGroupField|GlyphItemPrivate|FieldPrivate|  
        |GlyphGroupField|GlyphItemShortcut|FieldShortcut|  
        |GlyphGroupInterface|GlyphItemPublic|InterfacePublic|  
        |GlyphGroupInterface|GlyphItemInternal|InterfaceInternal|  
        |GlyphGroupInterface|GlyphItemFriend|InterfaceInternal|  
        |GlyphGroupInterface|GlyphItemProtected|InterfaceProtected|  
        |GlyphGroupInterface|GlyphItemPrivate|InterfacePrivate|  
        |GlyphGroupInterface|GlyphItemShortcut|InterfaceShortcut|  
        |GlyphGroupMacro|GlyphItemPublic|MacroPublic|  
        |GlyphGroupMacro|GlyphItemInternal|MacroInternal|  
        |GlyphGroupMacro|GlyphItemFriend|MacroInternal|  
        |GlyphGroupMacro|GlyphItemProtected|MacroProtected|  
        |GlyphGroupMacro|GlyphItemPrivate|MacroPrivate|  
        |GlyphGroupMacro|GlyphItemShortcut|MacroShortcut|  
        |GlyphGroupMap|GlyphItemPublic|MapPublic|  
        |GlyphGroupMap|GlyphItemInternal|MapInternal|  
        |GlyphGroupMap|GlyphItemFriend|MapInternal|  
        |GlyphGroupMap|GlyphItemProtected|MapProtected|  
        |GlyphGroupMap|GlyphItemPrivate|MapPrivate|  
        |GlyphGroupMap|GlyphItemShortcut|MapShortcut|  
        |GlyphGroupMapItem|GlyphItemPublic|MapItemPublic|  
        |GlyphGroupMapItem|GlyphItemInternal|MapItemInternal|  
        |GlyphGroupMapItem|GlyphItemFriend|MapItemInternal|  
        |GlyphGroupMapItem|GlyphItemProtected|MapItemProtected|  
        |GlyphGroupMapItem|GlyphItemPrivate|MapItemPrivate|  
        |GlyphGroupMapItem|GlyphItemShortcut|MapItemShortcut|  
        |GlyphGroupMethod|GlyphItemPublic|MethodPublic|  
        |GlyphGroupMethod|GlyphItemInternal|MethodInternal|  
        |GlyphGroupMethod|GlyphItemFriend|MethodInternal|  
        |GlyphGroupMethod|GlyphItemProtected|MethodProtected|  
        |GlyphGroupMethod|GlyphItemPrivate|MethodPrivate|  
        |GlyphGroupMethod|GlyphItemShortcut|MethodShortcut|  
        |GlyphGroupOverload|GlyphItemPublic|MethodPublic|  
        |GlyphGroupOverload|GlyphItemInternal|MethodInternal|  
        |GlyphGroupOverload|GlyphItemFriend|MethodInternal|  
        |GlyphGroupOverload|GlyphItemProtected|MethodProtected|  
        |GlyphGroupOverload|GlyphItemPrivate|MethodPrivate|  
        |GlyphGroupOverload|GlyphItemShortcut|MethodShortcut|  
        |GlyphGroupModule|GlyphItemPublic|ModulePublic|  
        |GlyphGroupModule|GlyphItemInternal|ModuleInternal|  
        |GlyphGroupModule|GlyphItemFriend|ModuleInternal|  
        |GlyphGroupModule|GlyphItemProtected|ModuleProtected|  
        |GlyphGroupModule|GlyphItemPrivate|ModulePrivate|  
        |GlyphGroupModule|GlyphItemShortcut|ModuleShortcut|  
        |GlyphGroupNamespace|GlyphItemPublic|NamespacePublic|  
        |GlyphGroupNamespace|GlyphItemInternal|NamespaceInternal|  
        |GlyphGroupNamespace|GlyphItemFriend|NamespaceInternal|  
        |GlyphGroupNamespace|GlyphItemProtected|NamespaceProtected|  
        |GlyphGroupNamespace|GlyphItemPrivate|NamespacePrivate|  
        |GlyphGroupNamespace|GlyphItemShortcut|NamespaceShortcut|  
        |GlyphGroupOperator|GlyphItemPublic|OperatorPublic|  
        |GlyphGroupOperator|GlyphItemInternal|OperatorInternal|  
        |GlyphGroupOperator|GlyphItemFriend|OperatorInternal|  
        |GlyphGroupOperator|GlyphItemProtected|OperatorProtected|  
        |GlyphGroupOperator|GlyphItemPrivate|OperatorPrivate|  
        |GlyphGroupOperator|GlyphItemShortcut|OperatorShortcut|  
        |GlyphGroupProperty|GlyphItemPublic|PropertyPublic|  
        |GlyphGroupProperty|GlyphItemInternal|PropertyInternal|  
        |GlyphGroupProperty|GlyphItemFriend|PropertyInternal|  
        |GlyphGroupProperty|GlyphItemProtected|PropertyProtected|  
        |GlyphGroupProperty|GlyphItemPrivate|PropertyPrivate|  
        |GlyphGroupProperty|GlyphItemShortcut|PropertyShortcut|  
        |GlyphGroupStruct|GlyphItemPublic|StructurePublic|  
        |GlyphGroupStruct|GlyphItemInternal|StructureInternal|  
        |GlyphGroupStruct|GlyphItemFriend|StructureInternal|  
        |GlyphGroupStruct|GlyphItemProtected|StructureProtected|  
        |GlyphGroupStruct|GlyphItemPrivate|StructurePrivate|  
        |GlyphGroupStruct|GlyphItemShortcut|StructureShortcut|  
        |GlyphGroupTemplate|GlyphItemPublic|TemplatePublic|  
        |GlyphGroupTemplate|GlyphItemInternal|TemplateInternal|  
        |GlyphGroupTemplate|GlyphItemFriend|TemplateInternal|  
        |GlyphGroupTemplate|GlyphItemProtected|TemplateProtected|  
        |GlyphGroupTemplate|GlyphItemPrivate|TemplatePrivate|  
        |GlyphGroupTemplate|GlyphItemShortcut|TemplateShortcut|  
        |GlyphGroupTypedef|GlyphItemPublic|TypeDefinitionPublic|  
        |GlyphGroupTypedef|GlyphItemInternal|TypeDefinitionInternal|  
        |GlyphGroupTypedef|GlyphItemFriend|TypeDefinitionInternal|  
        |GlyphGroupTypedef|GlyphItemProtected|TypeDefinitionProtected|  
        |GlyphGroupTypedef|GlyphItemPrivate|TypeDefinitionPrivate|  
        |GlyphGroupTypedef|GlyphItemShortcut|TypeDefinitionShortcut|  
        |GlyphGroupType|GlyphItemPublic|TypePublic|  
        |GlyphGroupType|GlyphItemInternal|TypeInternal|  
        |GlyphGroupType|GlyphItemFriend|TypeInternal|  
        |GlyphGroupType|GlyphItemProtected|TypeProtected|  
        |GlyphGroupType|GlyphItemPrivate|TypePrivate|  
        |GlyphGroupType|GlyphItemShortcut|TypeShortcut|  
        |GlyphGroupUnion|GlyphItemPublic|UnionPublic|  
        |GlyphGroupUnion|GlyphItemInternal|UnionInternal|  
        |GlyphGroupUnion|GlyphItemFriend|UnionInternal|  
        |GlyphGroupUnion|GlyphItemProtected|UnionProtected|  
        |GlyphGroupUnion|GlyphItemPrivate|UnionPrivate|  
        |GlyphGroupUnion|GlyphItemShortcut|UnionShortcut|  
        |GlyphGroupVariable|GlyphItemPublic|FieldPublic|  
        |GlyphGroupVariable|GlyphItemInternal|FieldInternal|  
        |GlyphGroupVariable|GlyphItemFriend|FieldInternal|  
        |GlyphGroupVariable|GlyphItemProtected|FieldProtected|  
        |GlyphGroupVariable|GlyphItemPrivate|FieldPrivate|  
        |GlyphGroupVariable|GlyphItemShortcut|FieldShortcut|  
        |GlyphGroupValueType|GlyphItemPublic|ValueTypePublic|  
        |GlyphGroupValueType|GlyphItemInternal|ValueTypeInternal|  
        |GlyphGroupValueType|GlyphItemFriend|ValueTypeInternal|  
        |GlyphGroupValueType|GlyphItemProtected|ValueTypeProtected|  
        |GlyphGroupValueType|GlyphItemPrivate|ValueTypePrivate|  
        |GlyphGroupValueType|GlyphItemShortcut|ValueTypeShortcut|  
        |GlyphGroupIntrinsic|GlyphItemPublic|ObjectPublic|  
        |GlyphGroupIntrinsic|GlyphItemInternal|ObjectInternal|  
        |GlyphGroupIntrinsic|GlyphItemFriend|ObjectInternal|  
        |GlyphGroupIntrinsic|GlyphItemProtected|ObjectProtected|  
        |GlyphGroupIntrinsic|GlyphItemPrivate|ObjectPrivate|  
        |GlyphGroupIntrinsic|GlyphItemShortcut|ObjectShortcut|  
        |GlyphGroupJSharpMethod|GlyphItemPublic|MethodPublic|  
        |GlyphGroupJSharpMethod|GlyphItemInternal|MethodInternal|  
        |GlyphGroupJSharpMethod|GlyphItemFriend|MethodInternal|  
        |GlyphGroupJSharpMethod|GlyphItemProtected|MethodProtected|  
        |GlyphGroupJSharpMethod|GlyphItemPrivate|MethodPrivate|  
        |GlyphGroupJSharpMethod|GlyphItemShortcut|MethodShortcut|  
        |GlyphGroupJSharpField|GlyphItemPublic|FieldPublic|  
        |GlyphGroupJSharpField|GlyphItemInternal|FieldInternal|  
        |GlyphGroupJSharpField|GlyphItemFriend|FieldInternal|  
        |GlyphGroupJSharpField|GlyphItemProtected|FieldProtected|  
        |GlyphGroupJSharpField|GlyphItemPrivate|FieldPrivate|  
        |GlyphGroupJSharpField|GlyphItemShortcut|FieldShortcut|  
        |GlyphGroupJSharpClass|GlyphItemPublic|ClassPublic|  
        |GlyphGroupJSharpClass|GlyphItemInternal|ClassInternal|  
        |GlyphGroupJSharpClass|GlyphItemFriend|ClassInternal|  
        |GlyphGroupJSharpClass|GlyphItemProtected|ClassProtected|  
        |GlyphGroupJSharpClass|GlyphItemPrivate|ClassPrivate|  
        |GlyphGroupJSharpClass|GlyphItemShortcut|ClassShortcut|  
        |GlyphGroupJSharpNamespace|GlyphItemPublic|NamespacePublic|  
        |GlyphGroupJSharpNamespace|GlyphItemInternal|NamespaceInternal|  
        |GlyphGroupJSharpNamespace|GlyphItemFriend|NamespaceInternal|  
        |GlyphGroupJSharpNamespace|GlyphItemProtected|NamespaceProtected|  
        |GlyphGroupJSharpNamespace|GlyphItemPrivate|NamespacePrivate|  
        |GlyphGroupJSharpNamespace|GlyphItemShortcut|NamespaceShortcut|  
        |GlyphGroupJSharpInterface|GlyphItemPublic|InterfacePublic|  
        |GlyphGroupJSharpInterface|GlyphItemInternal|InterfaceInternal|  
        |GlyphGroupJSharpInterface|GlyphItemFriend|InterfaceInternal|  
        |GlyphGroupJSharpInterface|GlyphItemProtected|InterfaceProtected|  
        |GlyphGroupJSharpInterface|GlyphItemPrivate|InterfacePrivate|  
        |GlyphGroupJSharpInterface|GlyphItemShortcut|InterfaceShortcut|  
        |GlyphGroupError||StatusError|  
        |GlyphBscFile||ClassFile|  
        |GlyphAssembly||Odkaz|  
        |GlyphLibrary||Knihovna|  
        |GlyphVBProject||VBProjectNode|  
        |GlyphCoolProject||CSProjectNode|  
        |GlyphCppProject||CPPProjectNode|  
        |GlyphDialogId||Dialogové okno|  
        |GlyphOpenFolder||FolderOpened|  
        |GlyphClosedFolder||FolderClosed|  
        |GlyphArrow||Přejít na další|  
        |GlyphCSharpFile||CSFileNode|  
        |GlyphCSharpExpansion||fragment kódu|  
        |GlyphKeyword||IntellisenseKeyword|  
        |GlyphInformation||StatusInformation|  
        |GlyphReference||ClassMethodReference|  
        |GlyphRecursion||Rekurze|  
        |GlyphXmlItem||Značka|  
        |GlyphJSharpProject||DocumentCollection|  
        |GlyphJSharpDocument||Dokument|  
        |GlyphForwardType||Přejít na další|  
        |GlyphCallersGraph||CallTo|  
        |GlyphCallGraph||CallFrom|  
        |GlyphWarning||StatusWarning|  
        |GlyphMaybeReference||QuestionMark|  
        |GlyphMaybeCaller||CallTo|  
        |GlyphMaybeCall||CallFrom|  
        |GlyphExtensionMethod||ExtensionMethod|  
        |GlyphExtensionMethodInternal||ExtensionMethod|  
        |GlyphExtensionMethodFriend||ExtensionMethod|  
        |GlyphExtensionMethodProtected||ExtensionMethod|  
        |GlyphExtensionMethodPrivate||ExtensionMethod|  
        |GlyphExtensionMethodShortcut||ExtensionMethod|  
        |GlyphXmlAttribute||XmlAttribute|  
        |GlyphXmlChild||XmlElement.|  
        |GlyphXmlDescendant||XmlDescendant|  
        |GlyphXmlNamespace||XmlNamespace|  
        |GlyphXmlAttributeQuestion||XmlAttributeLowConfidence|  
        |GlyphXmlAttributeCheck||XmlAttributeHighConfidence|  
        |GlyphXmlChildQuestion||XmlElementLowConfidence|  
        |GlyphXmlChildCheck||XmlElementHighConfidence|  
        |GlyphXmlDescendantQuestion||XmlDescendantLowConfidence|  
        |GlyphXmlDescendantCheck||XmlDescendantHighConfidence|  
        |GlyphCompletionWarning||IntellisenseWarning|