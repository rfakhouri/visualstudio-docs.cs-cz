---
title: Adresování DPI Problémy2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 359184aa-f5b6-4b6c-99fe-104655b3a494
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc0801d3fb43188ac3371ed7e5e7394b0e3aad72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="addressing-dpi-issues"></a>Řešení problémů DPI
Se zvyšující číslo zařízení se dodává s "s vysokým rozlišením" obrazovky. Tyto obrazovky obvykle mají více než 200 počet pixelů na palec (ICP). Práce s aplikací na těchto počítačích bude vyžadovat obsah tak, aby se rozšířit tak, aby vyhovovaly zobrazení obsah v normálním zobrazení vzdálenosti pro zařízení. Od verze 2014 je primární cíle pro s vysokou hustotou zobrazí mobilní zařízení (tablety, notebooky design a telefony) computing.  
  
 Windows 8.1 a vyšší obsahuje několik funkcí, aby tyto počítače pro práci s zobrazí a prostředí, kde je počítač připojen k i s vysokou hustotou standard hustotu zobrazí ve stejnou dobu.  
  
-   Windows může umožňují změní měřítko obsahu pro zařízení pomocí "Zkontrolujte text a další položky větší nebo menší" nastavení (dostupné od Windows XP).  
  
-   Windows 8.1 a vyšší se automaticky změní měřítko obsahu pro většinu aplikací, aby byla konzistentní při přesunu mezi zobrazí různé densities – pixelů. Když (200 % scaling) s vysokou hustotou je primární a sekundární zobrazení je standardní hustotu (100 %), Windows bude automaticky škálovat obsah okna aplikace na displeji sekundární (1 pixel zobrazí u každé 4 pixelů pro vykreslení aplikace).  
  
-   Právo škálování pro hustotě pixelů a zobrazení vzdálenost pro zobrazení (Windows 7 a vyšší, od výrobců OEM konfigurovat) je výchozí nastavení systému Windows.  
  
-   Windows může automaticky škálovat obsahu až 250 % na nová zařízení, které překračují 280 pixelů na palec (od verze Windows 8.1 s.14).  
  
 Systém Windows má způsob práci s vertikálním navýšení kapacity uživatelského rozhraní využívat výhod počty vyšší pixelů. Aplikace vyjádřit výslovný souhlas pro tento systém deklarováním sám sebe "systém DPI vědět." Aplikace, které neprovádějte tuto akci, jsou škálovat v systému. Výsledkem může být "přibližné" uživatelské prostředí, kde bude celá aplikace je jednotná roztažen tak pixelů. Příklad:  
  
 ![DPI problémy přibližné](../extensibility/media/dpi-issues-fuzzy.png "DPI problémy přibližné")  
  
 Visual Studio vyjádřit výslovný souhlas stal DPI škálování využívající technologii a proto není "virtualizované."  
  
 Windows (a Visual Studio) využívejte několik technologií uživatelského rozhraní, které mají různé způsoby nakládání s škálování faktorů nastaví ho systém. Příklad:  
  
-   WPF měří ovládací prvky způsobem nezávislé na zařízení (jednotky, není v pixelech). Uživatelské rozhraní WPF automaticky přizpůsobí pro aktuální DPI.  
  
-   Všech velikostí text bez ohledu na to uživatelského rozhraní framework jsou vyjádřeny v bodech a proto nakládá na systém jako nezávislé DPI. Text v Win32, WinForms a WPF již škálovat správně při kreslení do zobrazení zařízení.  
  
-   Win32/WinForms dialogová okna a windows mít prostředky pro povolení rozložení, které změní s textem – například prostřednictvím mřížky, toku a panelů rozložení tabulky. Tyto povolit zabraňující pevně pixelů umístění, které udávají, když jsou zvětšit velikost písma.  
  
-   Ikony poskytuje systém nebo prostředky v závislosti na metriky systému (například SM_CXICON a SM_CXSMICON) jsou již škálovat.  
  
## <a name="older-win32-gdi-gdi-and-winforms-based-ui"></a>Starší Win32 (GDI, GDI +) a na základě WinForms uživatelského rozhraní  
 Zatímco WPF již vysoké palec, většinu kódu založenými na systému Win32/GDI nebyl zapíše původně povědomí o DPI v paměti. Windows poskytl Škálování DPI rozhraní API. Opravy problémů Win32 by měl použít konzistentně napříč produktu. Visual Studio poskytl pomocné rutiny knihovny tříd předejdete duplikace funkce a zajištění konzistence napříč produktu.  
  
## <a name="high-resolution-images"></a>S vysokým rozlišením bitové kopie  
 Tato část je určen pro vývojáře v rozšíření sady Visual Studio 2013. Pro Visual Studio 2015 použijte službu bitovou kopii, která je integrována v sadě Visual Studio. Můžete také zjistit, že potřebujete podporu/cílový počet verzí sady Visual Studio a proto v 2015 pomocí bitové kopie služby není možné vzhledem k tomu, že není k dispozici v předchozích verzích. Tato část se také pro vás pak.  
  
## <a name="scaling-up-images-that-are-too-small"></a>Rozšiřování prostředků bitové kopie, které jsou příliš malé  
 Bitové kopie, které jsou příliš malé můžete "Rozšířená" a zobrazí na GDI a WPF pomocí některé běžné metody. Spravované DPI pomocné rutiny třídy jsou k dispozici pro Visual Studio integrátorem interní a externí adresu škálování ikony, rastrové obrázky, imagestrips a imagelists. Na základě Win32 nativní C / C ++ pomocné rutiny jsou dostupné pro škálování HICON, HBITMAP, HIMAGELIST a VsUI::GdiplusImage. Škálování bitmapy obvykle vyžaduje pouze jednořádkové změnu po zahrnutí odkazu na pomocné knihovny. Příklad:  
  
```cpp  
(Unmanaged)  VsUI::DpiHelper::LogicalToDeviceUnits(&hBitmap);  
```  
  
```csharp  
(WinForms) DpiHelper.LogicalToDeviceUnits(ref image);  
```  
  
 Škálování imagelist závisí na tom, zda položka imagelist skončí v okamžiku načtení, nebo se připojí za běhu. Pokud při načítání, dokončení volání LogicalToDeviceUnits() s položka imagelist stejně jako rastrový obrázek. Pokud kód potřebuje před skládání položka imagelist načtěte jednotlivých rastrového obrázku, ujistěte se, že jste škálování velikost bitové kopie položka imagelist:  
  
```csharp  
imagelist.ImageSize = DpiHelper.LogicalToDeviceUnits(imagelist.ImageSize);  
```  
  
 Dimenze v nativním kódu, je možné rozšířit při vytváření položka imagelist následujícím způsobem:  
  
```cpp  
ImageList_Create(VsUI::DpiHelper::LogicalToDeviceUnitsX(16),VsUI::DpiHelper::LogicalToDeviceUnitsY(16), ILC_COLOR32|ILC_MASK, nCount, 1);  
```  
  
 Funkce v knihovně povolit zadání algoritmu změny velikosti. Když škálování Image umístit do imagelists, nezapomeňte zadat barvu pozadí, který se používá pro průhlednost, nebo pomocí NearestNeighbor škálování (což způsobí narušení na 125 % a 150 %).  
  
 Obrátit <xref:Microsoft.VisualStudio.PlatformUI.DpiHelper> dokumentaci na webu MSDN.  
  
 V následující tabulce jsou uvedeny příklady, jak by měl být změněna bitové kopie na odpovídající DPI škálování faktory. Bitové kopie zeleně označují naše osvědčený postup od verze Visual Studio 2013 (100 % - 200 % Škálování DPI):  
  
 ![Problémy DPI škálování](../extensibility/media/dpi-issues-scaling.png "DPI problémy škálování")  
  
## <a name="layout-issues"></a>Problémy s rozložením  
 Běžné problémy s rozložením se vyhnout především udržováním body v uživatelském rozhraní škálovat a relativně k jinému, a nikoli pomocí absolutní umístění (konkrétně v pixelech jednotky). Příklad:  
  
-   Rozložení nebo textu pozice nutné upravit účet na bitové kopie vertikálním navýšením kapacity.  
  
-   Sloupce v mřížky musí být šířek přizpůsobené pro text vertikálním navýšením kapacity.  
  
-   Pevně velikosti nebo prostoru mezi elementy bude také muset možné škálovat. Velikosti, které jsou na základě pouze u dimenzí text jsou obvykle, protože písem automaticky škálovat.  
  
 Podpůrné funkce jsou k dispozici v <xref:Microsoft.VisualStudio.PlatformUI.DpiHelper> třídu, která umožňuje škálování na ose X a Y:  
  
-   LogicalToDeviceUnitsX/LogicalToDeviceUnitsY (Povolit funkce škálování na X nebo osy Y)  
  
-   int místo = DpiHelper.LogicalToDeviceUnitsX (10);  
  
-   Výška int = VsUI::DpiHelper::LogicalToDeviceUnitsY(5);  
  
 Existují přetížení LogicalToDeviceUnits umožňuje škálování objekty například Rect –, bod a velikost.  
  
## <a name="using-the-dpihelper-libraryclass-to-scale-images-and-layout"></a>Použití knihovny nebo třídy DPIHelper změna měřítka obrázků a rozložení  
 Visual Studio DPI pomocné knihovny je k dispozici ve formulářích nativní a spravovaná a mimo prostředí sady Visual Studio můžete použít jiné aplikace.  
  
 Na používání knihovny, přejděte na [Visual Studio – ukázky rozšiřitelnosti VSSDK](https://github.com/Microsoft/VSSDK-Extensibility-Samples) a klonování vysokou DPI_Images_Icons vzorku  
  
 Zdrojové soubory zahrnují VsUIDpiHelper.h a volání statické funkce VsUI::DpiHelper třídy:  
  
```cpp  
#include "VsUIDpiHelper.h"  
  
int cxScaled = VsUI::DpiHelper::LogicalToDeviceUnitsX(cx);  
VsUI::DpiHelper::LogicalToDeviceUnits(&hBitmap);  
  
```  
  
> [!NOTE]
>  Nepoužívejte podpůrné funkce v modulu úrovni nebo třídy statické proměnné. Statické objekty knihovny také používá pro přístup z více vláken synchronizace a může dojít k problémům pořadí inicializace. Buď převést tyto statické objekty nestatické členské proměnné nebo zabalit do funkce (takže se získat sestavený na první přístup).  
  
 Pro přístup k DPI pomocných funkcí ze spravovaného kódu, který se spustí v prostředí Visual Studio:  
  
-   Využívání projektu musí odkazovat na nejnovější verzi sady MPF prostředí. Příklad:  
  
    ```csharp  
    <Reference Include="Microsoft.VisualStudio.Shell.14.0.dll" />  
    ```  
  
-   Ujistěte se, obsahuje odkazy na projekt **System.Windows.Forms**, **PresentationCore**, a **PresentationUI**.  
  
-   V kódu pomocí **Microsoft.VisualStudio.PlatformUI** obor názvů a volání statické funkce DpiHelper třídy. U podporovaných typů (body, velikosti, obdélníků a tak dále) jsou poskytované škálovat rozšíření funkce, které vracejí nové objekty. Příklad:  
  
    ```csharp  
    using Microsoft.VisualStudio.PlatformUI;  
    double x = DpiHelper.LogicalToDeviceUnitsX(posX);  
    Point ptScaled = ptOriginal.LogicalToDeviceUnits();  
    DpiHelper.LogicalToDeviceUnits(ref bitmap);  
  
    ```  
  
## <a name="dealing-with-wpf-image-fuzziness-in-zoomable-ui"></a>Práci s tomu image grafického subsystému WPF v umožňujícím uživatelského rozhraní  
 V grafickém subsystému WPF, rastrové obrázky jsou po změně velikosti automaticky pomocí grafického subsystému WPF pro aktuální úroveň přiblížení DPI pomocí algoritmu vysoce kvalitní bikubické (výchozí), který funguje dobře pro obrázky nebo velké snímky obrazovky, ale není vhodný pro ikon položek nabídky, protože zavádí dosahovaný tomu .  
  
 Doporučení:  
  
-   Pro bitové kopie a hlaviček logo kresby, výchozí <xref:System.Windows.Media.BitmapScalingMode> Změna velikosti režimu by bylo možné použít.  
  
-   Položky nabídky a Image používá <xref:System.Windows.Media.BitmapScalingMode> by měl být použit při nezpůsobuje artefaktů narušení eliminovat tomu (v 200 % a 300 %).  
  
-   Pro velké přiblížení úrovně není násobky 100 % (například 250 % nebo 350 %), škálování používá obrázky s bikubické výsledkem přibližné, vybledle uživatelského rozhraní. Lepší výsledek se získá tak, že první zvětšení velikosti obrázku s NearestNeighbor na největší násobek 100 % (například 200 % nebo 300 %) a škálování s bikubické odtud. V tématu zvláštní případ: prescaling WPF Image pro velké DPI úrovně pro další informace.  
  
 DpiHelper třída v oboru názvů Microsoft.VisualStudio.PlatformUI poskytuje členem <xref:System.Windows.Media.BitmapScalingMode> který lze použít pro vazbu. Bude možné prostředí sady Visual Studio k řízení rastrový obrázek škálování režimu mezi produktu jednotně, v závislosti na zadané Měřítko DPI.  
  
 Chcete-li použít v jazyce XAML, přidejte:  
  
```xaml  
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
  
<Setter Property="RenderOptions.BitmapScalingMode" Value="{x:Static vs:DpiHelper.BitmapScalingMode}" />  
  
```  
  
 Prostředí sady Visual Studio už se tato vlastnost nastaví na nejvyšší úrovni windows a dialogová okna. Na základě WPF uživatelského rozhraní v sadě Visual Studio spuštěná zdědí už ho. Pokud nastavení nešířily na vaše konkrétní součásti uživatelského rozhraní, lze nastavit v kořenovém elementu uživatelského rozhraní jazyka XAML nebo WPF. Místa, kde se to stane zahrnují automaticky otevíraná okna u elementů s Win32 nadřazených objektů, a procesu návrháře systému windows, které spustit z, jako je například Blend.  
  
 Některé uživatelského rozhraní můžete škálovat nezávisle na úroveň přiblížení DPI sada systému, například Visual Studio textovém editoru a návrháři grafického subsystému WPF (WPF Desktop a Windows Store). V těchto případech by nemělo být použito DpiHelper.BitmapScalingMode. Chcete-li tento problém vyřešit v editoru, týmem IDE vytvořili vlastní vlastnost s názvem RenderOptions.BitmapScalingMode. Nastavte tuto hodnotu vlastnosti na HighQuality nebo NearestNeighbor v závislosti na úrovni kombinované přiblížení systému a uživatelské rozhraní.  
  
## <a name="special-case-prescaling-wpf-images-for-large-dpi-levels"></a>Zvláštní případ: prescaling WPF bitové kopie pro velké DPI úrovně  
 Pro velké přiblížení úrovně, které nejsou násobky 100 % (například 250 %, 350 % a tak dále) škálování používá obrázky s bikubické má za následek přibližné, vybledle uživatelského rozhraní. Dojem těchto bitových kopií podél zřetelný textu je velmi podobná, optické dojem. Bitové kopie se zdají být blíže oko a mimo fokus ve vztahu k text. Škálování výsledek při této velikosti oddálit lze vylepšit první zvětšení velikosti obrázku s NearestNeighbor na největší násobek 100 % (například 200 % nebo 300 %) a škálování s bikubické ke zbytku (Další 50 %).  
  
 Následující je příkladem rozdíly ve výsledcích, kde je první obrázku změněna s lepší škálování dvojitou algoritmem-100 % > 200 % -> 250 % a druhý právě s bikubické 100 % -> 250 %.  
  
 ![DPI problémy dvojité škálování příklad](../extensibility/media/dpi-issues-double-scaling-example.png "DPI problémy dvojité škálování příklad")  
  
 Chcete-li povolit uživatelského rozhraní používat tento dvojitou škálování, kód XAML pro zobrazení jednotlivých prvků Image bude nutné změnit. Následující příklady ukazují, jak používat dvojitou škálování v grafickém subsystému WPF v sadě Visual Studio pomocí knihovny DpiHelper a Shell.12/14.  
  
 Krok 1: Prescale bitovou kopii na 200 %, 300 % a tak dále pomocí NearestNeighbor.  
  
 Prescale bitovou kopii pomocí buď převaděč použít u vazby, nebo s příponou kód XAML. Příklad:  
  
```xaml  
<vsui:DpiPrescaleImageSourceConverter x:Key="DpiPrescaleImageSourceConverter" />  
  
<Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" Width="16" Height="16" />  
  
<Image Source="{vsui:DpiPrescaledImage Images/Help.png}" Width="16" Height="16" />  
  
```  
  
 Pokud také musí být motivu bitovou kopii (většina, pokud nejsou všechny, měli), kód můžete použít různé převaděč, který nejprve motivů bitové kopie a poté předem škálování. Kód můžete použít buď <xref:Microsoft.VisualStudio.PlatformUI.DpiPrescaleThemedImageConverter> nebo <xref:Microsoft.VisualStudio.PlatformUI.DpiPrescaleThemedImageSourceConverter>, v závislosti na požadované převod výstup.  
  
```xaml  
<vsui:DpiPrescaleThemedImageSourceConverter x:Key="DpiPrescaleThemedImageSourceConverter" />  
  
<Image Width="16" Height="16">  
  <Image.Source>  
    <MultiBinding Converter="{StaticResource DpiPrescaleThemedImageSourceConverter}">  
      <Binding Path="Icon" />  
      <Binding Path="(vsui:ImageThemingUtilities.ImageBackgroundColor)"    
               RelativeSource="{RelativeSource Self}" />  
      <Binding Source="{x:Static vsui:Boxes.BooleanTrue}" />  
    </MultiBinding>  
  </Image.Source>  
</Image>  
```  
  
 Krok 2: Ujistěte se, že je správný pro aktuální DPI konečné velikosti.  
  
 Protože WPF bude škálovat uživatelského rozhraní pro aktuální DPI pomocí vlastnosti BitmapScalingMode nastavte na prvků uživatelského rozhraní, by měl ovládacího prvku obrázek pomocí prescaled bitové kopie jako svůj zdroj bude vypadat větší než dvě nebo tři časy. Následuje několik způsobů, jak čítače tento vliv:  
  
-   Pokud znáte dimenzi původní bitové kopie na 100 %, můžete zadat přesný velikost ovládacího prvku obrázek. Tyto velikosti se projeví, že se použije velikost uživatelské rozhraní před škálování.  
  
    ```xaml  
    <Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" Width="16" Height="16" />  
    ```  
  
-   Pokud je velikost původní bitové kopie není znám, LayoutTransform slouží k snižovat objekt finální Image. Příklad:  
  
    ```xaml  
    <Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" >  
        <Image.LayoutTransform>  
         <ScaleTransform  
             ScaleX="{x:Static vsui:DpiHelper.PreScaledImageLayoutTransformScale}"  
             ScaleY="{x:Static vsui:DpiHelper.PreScaledImageLayoutTransformScale}" />  
        </Image.LayoutTransform>  
    </Image>  
    ```  
  
## <a name="enabling-hdpi-support-to-the-weboc"></a>Povolení podpory HDPI k WebOC  
 Ve výchozím nastavení ovládací prvky WebOC (například WebBrowser – ovládací prvek WPF nebo rozhraní rozhraní IWebBrowser2) nepovolíte HDPI detekce a podporu. Výsledkem bude vloženému ovládacímu prvku s obsahem zobrazení, který je příliš malá na zobrazení s vysokým rozlišením. Následující popisuje, jak povolit podporu vysokou hodnotou DPI v instanci WebOC konkrétní web.  
  
 Implementace rozhraní IDocHostUIHandler (najdete v článku na webu MSDN na [IDocHostUIHandler](http://msdn.microsoft.com/library/aa753260.aspx) rozhraní):  
  
```idl  
[ComImport, InterfaceType(ComInterfaceType.InterfaceIsIUnknown),  
 Guid("BD3F23C0-D43E-11CF-893B-00AA00BDCE1A")]  
public interface IDocHostUIHandler  
{  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ShowContextMenu(  
        [In, MarshalAs(UnmanagedType.U4)] int dwID,  
        [In] POINT pt,  
        [In, MarshalAs(UnmanagedType.Interface)] object pcmdtReserved,  
        [In, MarshalAs(UnmanagedType.IDispatch)] object pdispReserved);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetHostInfo([In, Out] DOCHOSTUIINFO info);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ShowUI(  
        [In, MarshalAs(UnmanagedType.I4)] int dwID,  
        [In, MarshalAs(UnmanagedType.Interface)] object activeObject,  
        [In, MarshalAs(UnmanagedType.Interface)] object commandTarget,  
        [In, MarshalAs(UnmanagedType.Interface)] object frame,  
        [In, MarshalAs(UnmanagedType.Interface)] object doc);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int HideUI();  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int UpdateUI();  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int EnableModeless([In, MarshalAs(UnmanagedType.Bool)] bool fEnable);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int OnDocWindowActivate([In, MarshalAs(UnmanagedType.Bool)] bool fActivate);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int OnFrameWindowActivate([In, MarshalAs(UnmanagedType.Bool)] bool fActivate);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ResizeBorder(  
        [In] COMRECT rect,  
        [In, MarshalAs(UnmanagedType.Interface)] object doc,  
        bool fFrameWindow);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int TranslateAccelerator(  
        [In] ref MSG msg,  
        [In] ref Guid group,  
        [In, MarshalAs(UnmanagedType.I4)] int nCmdID);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetOptionKeyPath(  
        [Out, MarshalAs(UnmanagedType.LPArray)] string[] pbstrKey,  
        [In, MarshalAs(UnmanagedType.U4)] int dw);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetDropTarget(  
        [In, MarshalAs(UnmanagedType.Interface)] IOleDropTarget pDropTarget,  
        [MarshalAs(UnmanagedType.Interface)] out IOleDropTarget ppDropTarget);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetExternal([MarshalAs(UnmanagedType.IDispatch)] out object ppDispatch);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int TranslateUrl(  
        [In, MarshalAs(UnmanagedType.U4)] int dwTranslate,  
        [In, MarshalAs(UnmanagedType.LPWStr)] string strURLIn,  
        [MarshalAs(UnmanagedType.LPWStr)] out string pstrURLOut);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int FilterDataObject(  
        IDataObject pDO,  
        out IDataObject ppDORet);  
    }   
```  
  
 Volitelně můžete implementovat rozhraní ICustomDoc (najdete v článku na webu MSDN na [ICustomDoc](http://msdn.microsoft.com/library/aa753272.aspx) rozhraní):  
  
```idl  
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown),  
 Guid("3050F3F0-98B5-11CF-BB82-00AA00BDCE0B")]  
public interface ICustomDoc  
{  
    void SetUIHandler(IDocHostUIHandler pUIHandler);  
}   
```  
  
 Přidružte třídu, která implementuje IDocHostUIHandler s WebOC dokumentu. Pokud jste implementovali rozhraní ICustomDoc výše, poté co nejrychleji WebOC dokumentu vlastnost je platná, převést na ICustomDoc a volání metody SetUIHandler, předávání třídu, která implementuje IDocHostUIHandler.  
  
```csharp  
// "this" references that class that owns the WebOC control and in this case also implements the IDocHostUIHandler interface  
ICustomDoc customDoc = (ICustomDoc)webBrowser.Document;  
customDoc.SetUIHandler(this);  
  
```  
  
 Pokud jste neimplementovala rozhraní ICustomDoc, pak také WebOC dokumentu vlastnost je platná, musíte převést na IOleObject a volat metodu SetClientSite předávání ve třídě, která implementuje IDocHostUIHandler. Nastavte příznak DOCHOSTUIFLAG_DPI_AWARE na DOCHOSTUIINFO předaný GetHostInfo volání metody:  
  
```csharp  
public int GetHostInfo(DOCHOSTUIINFO info)  
{  
    // This is what the default site provides.  
    info.dwFlags = (DOCHOSTUIFLAG)0x5a74012;  
    // Add the DPI flag to the defaults  
    info.dwFlags |=.DOCHOSTUIFLAG.DOCHOSTUIFLAG_DPI_AWARE;  
    return S_OK;  
}  
```  
  
 To by mělo být vše, které potřebujete získat WebOC ovládací prvek pro podporu HPDI.  
  
## <a name="tips"></a>Tipy  
  
1.  Pokud vlastnost dokumentu na ovládací prvek WebOC změní, můžete dokumentu přidružte IDocHostUIHandler třídy.  
  
2.  Pokud se výše nefunguje, není známý problém s WebOC není výběr změnu příznak DPI. Nejspolehlivější způsob stanovení to je k přepnutí optické přiblížení WebOC, význam dvě volání s dvě různé hodnoty pro procento přiblížení. Kromě toho pokud toto řešení je potřeba, může být nutné provést při každém volání přejděte.  
  
    ```csharp  
    // browser2 is a SHDocVw.IWebBrowser2 in this case  
    // EX: Call the Exec twice with DPI%-1 and then DPI% as the zoomPercent values  
    IOleCommandTarget cmdTarget = browser2.Document as IOleCommandTarget;  
    if (cmdTarget != null)  
    {  
        object commandInput = zoomPercent;  
        cmdTarget.Exec(IntPtr.Zero,  
                       OLECMDID_OPTICAL_ZOOM,  
                       OLECMDEXECOPT_DONTPROMPTUSER,  
                       ref commandInput,  
                       ref commandOutput);  
    }  
    ```