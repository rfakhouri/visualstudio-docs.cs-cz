---
title: Podpora sledování na sledování pro rozšíření sady Visual Studio
titleSuffix: ''
description: Další informace o novou podporu zařízení extender pro za monitorování – sledování k dispozici v aplikaci Visual Studio 2019.
ms.date: 04/10/2019
helpviewer_keywords:
- Visual Studio, PMA, per-monitor-awareness, extenders, Windows Forms
- Per-Monitor Awareness support for extenders
ms.assetid: ''
author: rub8n
ms.author: rurios
manager: anthc
ms.prod: visual-studio-windows
monikerRange: vs-2019
ms.technology: vs-ide-general
ms.topic: reference
ms.workload:
- multiple
ms.openlocfilehash: 44938c5753491521702867398a514f770cf831fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62793633"
---
# <a name="per-monitor-awareness-support-for-visual-studio-extenders"></a>Podpora sledování na sledování pro rozšíření sady Visual Studio
Verze starší než Visual Studio 2019 měl svým kontextem povědomí o DPI nastavena na systém vědět, spíše než za sledování DPI vědět (PMA). Spouštění v systému sledování je v degradovaném stavu vizuálu pokaždé, když Visual Studio došlo k vykreslení na monitorech s jinou měřítko nebo vzdálené do počítačů s jiným zobrazením konfigurací např (jiné prostředí (například fuzzy písma nebo ikony) Windows škálování).

Kontext povědomí o DPI. 2019 Visual Studio je nastaven jako PMA, když prostředí podporuje proces v2v, umožní sadě Visual Studio k vykreslení závislosti na konfiguraci zobrazení, kde se hostuje místo jediného systému definované konfigurace. Takže v konečném důsledku překládá na vždy zřetelný uživatelského rozhraní pro plochy, které podporují režim PMA.

Odkazovat [vysoké rozlišení DPI Desktop Application Development na Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) dokumentaci pro další informace o podmínkách a celkové scénáře popsané v tomto dokumentu.

## <a name="quickstart"></a>Rychlý start
- Zkontrolujte, Visual Studio běží v režimu PMA (naleznete v tématu **povolení PMA**)

- Byly správně ověřeny vaše rozšíření funguje mezi sadu běžné scénáře (viz **testování rozšíření pro problémy PMA**)

- Pokud narazíte na problémy, můžete k diagnostikování a odstranění těchto problémů strategie/doporučení popsaných v tomto dokumentu. Také budete muset přidat nové [Microsoft.VisualStudio.DpiAwareness](https://www.nuget.org/packages/Microsoft.VisualStudio.DpiAwareness/) balíček NuGet do projektu pro přístup k požadované rozhraní API.

## <a name="enabling-pma"></a>Povolení PMA
Pokud chcete povolit PMA v sadě Visual Studio, musí být splněny následující požadavky:
1) Windows 10. dubna 2018 Update (v1803 RS4) nebo novější
2) Rozhraní .NET framework 4.8 RTM nebo novější
3) Visual Studio 2019 s ["Optimalizace vykreslování obrazovky s jinou hustoty"](https://docs.microsoft.com/visualstudio/ide/reference/general-environment-options-dialog-box?view=vs-2019) povolenou možnost

Jakmile jsou splněny tyto požadavky, Visual Studio automaticky povolí režim PMA celém procesu.

> [!NOTE]
> Obsah Windows Forms v sadě Visual Studio (například prohlížeč vlastností) budou podporovat PMA pouze v případě, že máte Visual Studio. 2019 aktualizace č. 1.

## <a name="testing-your-extensions-for-pma-issues"></a>Testování rozšíření PMA problémů

Visual Studio oficiálně podporuje rozhraní WPF, Windows Forms, Win32 a HTML/JS uživatelského rozhraní. Když Visual Studio přejde do režimu PMA, každý zásobník uživatelského rozhraní se chová odlišně. Bez ohledu na architekturu uživatelského rozhraní, proto doporučujeme, že průchodu testů se provádí za účelem Ujistěte se, že je kompatibilní s režimem PMA všechny uživatelské rozhraní.

Doporučuje se, že ověříte následující běžné scénáře:

1. Změna faktoru škálovací sady jednoho monitoru prostředí, když je aplikace spuštěná *
    - V tomto scénáři pomáhá otestovat, zda uživatelské rozhraní reaguje na dynamické změny Windows DPI

2. Ukotvení/vyjímání přenosném počítači, kde připojené monitorování změní na primární a připojené monitorování má jiný měřítko než přenosný počítač, když je spuštěná aplikace.
    - V tomto scénáři pomáhá otestovat, zda reaguje uživatelského rozhraní zobrazení změnit DPI, jakož i dynamicky zpracování zobrazí přidávání nebo odebírání

3. S více monitorů s jinou měřítko a přesun aplikace mezi nimi.
    - V tomto scénáři pomáhá otestovat, zda uživatelské rozhraní reaguje na změnu zobrazení DPI
    
4. Vzdálená komunikace k počítači, když místní a vzdálené počítače mají různé měřítko pro primární monitorování.
    - V tomto scénáři pomáhá otestovat, zda uživatelské rozhraní reaguje na dynamické změny Windows DPI

Vhodný předběžný test pro Určuje, zda vaše uživatelské rozhraní může mít problémy se určuje, zda kód využívá *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper*, *Microsoft.VisualStudio.PlatformUI.DpiHelper*, nebo *VsUI::CDpiHelper* třídy. Tyto třídy staré DpiHelper podporují jenom systému rozpoznání nastavení dpi a nebude vždy fungovat správně, když je proces PMA.

Typické použití těchto DpiHelpers bude vypadat takto:

```cs
Point screenTopRight = logicalBounds.TopRight.LogicalToDeviceUnits();

POINT screenIntTopRight = new POINT
{
    x = (int)screenTopRIght.X,
    y = (int)screenTopRIght.Y
}

// Declared via P/Invoke
IntPtr monitor = MonitorFromPoint(screenIntTopRight, MONITOR_DEFAULTTONEARST);
```

V předchozím příkladu obdélník představující logické hranice okna je převedena na jednotky zařízení tak, aby může být předán do nativní metody MonitorFromPoint, která očekává souřadnice zařízení, aby bylo možné vrátit zpět ukazatel přesné monitorování.

### <a name="classes-of-issues"></a>Třídy problémů
Když je povolený režim PMA pro sadu Visual Studio, uživatelské rozhraní může replikovat problémy běžné způsoby. Většina. Pokud ne, z těchto problémů může dojít v některém z podporovaných architektury uživatelského rozhraní sady Visual Studio. Kromě toho těchto problémů může také dojít, když část uživatelského rozhraní je hostovaná v kombinovaném režimu DPI škálování scénáře (odkazovat Windows [dokumentaci](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) Další). 

#### <a name="win32-window-creation"></a>Vytváření oken Win32
Při vytváření oken s CreateWindow() nebo CreateWindowEx(), běžným postupem je vytvoření okna na souřadnicích (0,0) (/ levého horního rohu primárního), přesuňte ho do konečného umístění. Díky tomu může způsobit okno k aktivaci DPI však změnit zprávy nebo událost, která můžete znovu aktivovat neúspěšnou dalších zpráv uživatelského rozhraní nebo události a nakonec vést k nežádoucímu chování nebo vykreslování.

#### <a name="wpf-element-placement"></a>Umístění prvku WPF
Při přesouvání elementů WPF pomocí staré Microsoft.VisualStudio.Utilities.Dpi.DpiHelper, souřadnice levého horního rohu nemusí být nevypočte správně pokaždé, když se elementy jsou v jiné než primární DPI.

#### <a name="serialization-of-ui-element-sizes-or-positions"></a>Serializace velikosti prvku uživatelského rozhraní nebo umístění
Po obnovení uživatelského rozhraní velikosti nebo pozice (Pokud je uložen jako jednotky zařízení) v jiném kontextu DPI než co byl uložen v bude umístěn a velikosti nesprávně. K tomu dochází, protože zařízení jednotky jsou vlastní relaci DPI.

#### <a name="incorrect-scaling"></a>Nesprávné měřítko
Prvky uživatelského rozhraní vytvářené na primární DPI škálovaly správně, ale když přesune na monitor s jinou DPI, není měřítko a díky tomu se jejich obsah končí nebuďte příliš velký či příliš malý.

#### <a name="incorrect-bounding"></a>Nesprávný ohraničující
Podobně škálování problému prvky uživatelského rozhraní bude počítat jejich rozsah správně v daném kontextu se primární DPI, ale při přesunu na neprimární DPI, jejich nových mezí nevypočte správně. V důsledku toho okno obsahu končí je příliš malá nebo příliš velké ve srovnání s hostování uživatelského rozhraní, jehož výsledkem je prázdný nebo oříznutí.

#### <a name="drag--drop"></a>Přetažením
Vždy, když ve scénářích DPI ve smíšeném režimu (například různé prvky uživatelského rozhraní vykreslování v různých režimech povědomí o DPI), přetáhněte souřadnice může být nesprávně vypočteny, výsledkem je konečné rozevírací koncové pozici nahoru nesprávné.

#### <a name="out-of-process-ui"></a>Uživatelského rozhraní na více instancí procesu
Některé uživatelské rozhraní se vytvoří na více instancí procesu a pokud vytvoření externího procesu je v jiném režimu povědomí o DPI než Visual Studio, což může představovat všechny předchozí problémů vykreslování.

#### <a name="windows-forms-controls-images-or-layouts-rendered-incorrectly"></a>Ovládací prvky Windows Forms, Image nebo rozložení vykreslen nesprávně
Obsah Windows Forms nepodporují PMA režimu. V důsledku toho se může zobrazit vykreslování problém s nesprávnou rozložení nebo škálování. V tomto případě je možné řešení explicitně vykreslení obsahu Windows Forms v "Systému upozornit" DpiAwarenessContext (odkazovat [vynucení ovládacího prvku do konkrétní DpiAwarenessContext](#forcing-a-control-into-a-specific-dpiawarenesscontext)).

#### <a name="windows-forms-controls-or-windows-not-displaying"></a>Ovládací prvky Windows Forms nebo windows nejsou zobrazena
Jedním z hlavní příčiny tohoto problému je vývojáři, chcete-li změnit nadřazenou položku pro ovládací prvek nebo okno s jeden DpiAwarenessContext do okna s jinou DpiAwarenessContext.

Následující obrázky ukazují aktuální **výchozí** omezení operačního systému Windows v systému windows nadřazenosti:

![Snímek obrazovky vztahy k nadřazeným položkám správné chování](../../extensibility/ux-guidelines/media/PMA-parenting-behavior.PNG)

> [!Note]
> Toto chování můžete změnit nastavením chování vlákna hostování (odkazovat [DpiHostinBehaviour](https://docs.microsoft.com/windows/desktop/api/windef/ne-windef-dpi_hosting_behavior)).

V důsledku toho pokud je nastavit vztah nadřazenosti a podřízenosti mezi nepodporované režimy, se nezdaří a okna ovládacího prvku nebo nemusí být vykreslen podle očekávání.

### <a name="diagnosing-issues"></a>Diagnostika problémů
Existuje celá řada faktorů, které je třeba zvážit při identifikaci problémů souvisejících se PMA: 

1. Fakturuje se u uživatelského rozhraní nebo rozhraní API očekávat logické nebo hodnoty zařízení.
    - Rozhraní API a rozhraní WPF obvykle používají logické hodnoty (ale ne vždy)
    - Uživatelského rozhraní Win32 API se obvykle používá hodnoty zařízení

2. Pokud jsou hodnoty pocházející z?
    - Pokud se zobrazuje hodnoty z jiných uživatelského rozhraní nebo rozhraní API, je to zařízení předávání nebo logické hodnoty.
    - Pokud se zobrazuje hodnoty z více zdrojů, všechny použijte/očekávají stejné typy hodnot nebo převody nemusíte být smíšený a odpovídající?

3. Jsou konstanty uživatelské rozhraní používá a jaké formuláře jsou v?

4. Vlákno je ve správném kontextu pro hodnoty DPI přijímá?
    - Změny umožňují hostování smíšené DPI by měly obecně put cesty kódu ve správném kontextu, však může spustit práce mimo hlavní zprávy smyčky nebo událost toku v chybném kontextu DPI.

5. Hodnoty překračují hranice kontextu DPI?
    - Přetáhnout je běžné situace, ve kterém můžete souřadnice napříč kontexty DPI. Okno se pokouší provést správnou věc, ale v některých případech možná muset práci převod zajistit odpovídající hranice kontext hostitele uživatelského rozhraní.

### <a name="pma-nuget-package"></a>Balíček PMA NuGet
Nové knihovny DpiAwarness můžete najít na [Microsoft.VisualStudio.DpiAwareness](https://www.nuget.org/packages/Microsoft.VisualStudio.DpiAwareness/) balíček NuGet.

### <a name="recommended-tools"></a>Doporučené nástroje
Následující nástroje vám mohou pomoci ladit problémy související s PMA v některé z různých zásobníky uživatelské rozhraní nepodporuje sady Visual Studio.

#### <a name="snoop"></a>Sledování
Sledování je nástroj ladění XAML, který má některé další funkce, která nemá integrované nástroje Visual Studio XAML. Kromě toho stará není potřeba aktivně ladění sady Visual Studio, abyste mohli zobrazit a upravit jeho uživatelské rozhraní WPF. Dva hlavní způsoby sledování může být užitečné při diagnostikování potíží PMA je pro ověření souřadnice logické umístění nebo velikost hranice a pro ověření rozhraní má správné DPI.
 
#### <a name="visual-studio-xaml-tools"></a>Nástroje sady Visual Studio XAML
Třeba sledování můžete nástroje XAML v sadě Visual Studio usnadnění diagnostiky potíží se PMA. Po nalezení pravděpodobnou můžete nastavit zarážky a použít ke kontrole hranice uživatelského rozhraní a aktuální DPI Live Visual Tree okna, jakož i ladicích oknech.

## <a name="strategies-for-fixing-pma-issues"></a>Strategie pro řešení problémů PMA
### <a name="replacing-dpihelper-calls"></a>Nahrazení DpiHelper volání
Ve většině případů opravit problémy uživatelského rozhraní v režimu PMA boils na nahrazení volání ve spravovaném kódu starého *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper* a *Microsoft.VisualStudio.PlatformUI.DpiHelper*tříd pomocí volání do nového *Microsoft.VisualStudio.Utilities.DpiAwareness* pomocná třída. 

```cs
// Remove this kind of use:
Point deviceTopLeft = new Point(window.Left, window.Top).LogicalToDeviceUnits();

// Replace with this use:
Point deviceTopLeft = window.LogicalToDevicePoint(new Point(window.Left, window.Top));
```

Pro nativní kód, bude mít nahrazení volání do starého *VsUI::CDpiHelper* třídy pomocí volání do nového *VsUI::CDpiAwareness* třídy. 

```cpp
// Remove this kind of use:
int cx = VsUI::DpiHelper::LogicalToDeviceUnitsX(m_cxS);
int cy = VsUI::DpiHelper::LogicalToDeviceUnitsY(m_cyS);

// Replace with this use:
int cx = m_cxS;
int cy = m_cyS;
VsUI::CDpiAwareness::LogicalToDeviceUnitsX(m_hwnd, &cx);
VsUI::CDpiAwareness::LogicalToDeviceUnitsY(m_hwnd, &cy);
```

Nové třídy DpiAwareness a CDpiAwareness nabízí stejné jednotce převodu pomocné rutiny třídy DpiHelper ale vyžadovat další vstupní parametr: prvku uživatelského rozhraní, který chcete použít jako referenci pro operaci převodu. Je důležité si uvědomit, že pomocné rutiny pro škálování image neexistuje v nové DpiAwareness/CDpiAwareness pomocné rutiny a v případě potřeby [ImageService](https://docs.microsoft.com/visualstudio/extensibility/image-service-and-catalog?view=vs-2019) by místo toho používat.

Spravované třídy DpiAwareness nabízí pomocné rutiny pro Vizuály WPF, ovládacích prvků Windows Forms a Win32 HWND a HMONITORs (i ve formě IntPtrs), při nativní CDpiAwareness nabídky HWND a HMONITOR pomocné rutiny třídy.

### <a name="windows-forms-dialogs-windows-or-controls-displayed-in-the-wrong-dpiawarenesscontext"></a>Dialogová okna Windows Forms, windows nebo ovládací prvky zobrazují v chybě DpiAwarenessContext
I potom, co úspěšném vztahy k nadřazeným položkám systému windows s jinou DpiAwarenessContexts (z důvodu výchozí chování Windows), může stále uvidí škálování problémy jako windows pomocí jiné DpiAwarenessContexts měřítko odlišně. Díky tomu uživatelé uvidí fuzzy/zarovnání textu nebo obrázků problémy v Uživatelském rozhraní.

Řešením je nastavit správný obor DpiAwarenessContext pro všechna okna a ovládací prvky v aplikaci.

### <a name="top-level-mixed-mode-tlmm-dialogs"></a>Dialogová okna nejvyšší úrovně ve smíšeném režimu (TLMM)
Při vytváření oknům nejvyšší úrovně, jako je například modální dialogová okna, je důležité zajistit, aby že vlákno je ve správném stavu před okna (a jeho popisovač) vytváří. Vlákno můžou být přepnuté do systému povědomí o použití pomocné rutiny CDpiScope v nativní nebo spravovaný DpiAwareness.EnterDpiScope pomocné rutiny v. (TLMM doporučujeme používat pro jiné WPF dialogů/windows.)

### <a name="child-level-mixed-mode-clmm"></a>Podřízená úroveň ve smíšeném režimu (CLMM)
Ve výchozím nastavení podřízená okna přijímat povědomí o DPI aktuální vlákno kontext Pokud vytvořen bez nadřazených nebo nadřazeného objektu DPI povědomí o kontextu při vytvoření s nadřazenou položku. Pokud chcete vytvořit podřízenou pomocí jiného kontextu povědomí o DPI než jeho nadřazený objekt, vlákno můžou být přepnuté do požadovaného kontextu povědomí o DPI. Potom podřízené se dají vytvářet bez nadřazených a ručně potomkům do nadřazeného okna.

#### <a name="clmm-issues"></a>CLMM problémy
Většina práce výpočtu uživatelského rozhraní, ke které dochází jako součást hlavní zasílání zpráv smyčky nebo událost řetězce by již být spuštěné ve správném kontextu povědomí o DPI. Nicméně pokud souřadnice nebo výpočty velikosti dokončení mimo tyto hlavní pracovní postupy (např. během úlohu dobu nečinnosti, nebo mimo vlákno uživatelského rozhraní, může být nesprávný, což vede k misplacement uživatelského rozhraní nebo chybně velikosti problémy s aktuálním kontextu povědomí o DPI. Uvedení vlákna do správného stavu pro uživatelské rozhraní pracovní obecně vyřeší daný problém.
 
#### <a name="opting-out-of-clmm"></a>Výslovné odhlášení z CLMM
Pokud okno nástroje bez WPF se migruje pro úplnou podporu PMA, ji budou muset vyjádřit výslovný nesouhlas CLMM. Uděláte to tak, je potřeba implementovat nové rozhraní: IVsDpiAware.

C#:

```cs
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
public interface IVsDpiAeware
{
    [ComAliasName("Microsoft.VisualStudio.Shell.Interop.VSDPIMode")]
    uint Mode {get;}
}
```
 
C++:

```cpp
IVsDpiAware : public IUnknown
{
    public:
        HRRESULT STDMETHODCALLTYPE get_Mode(__RCP__out VSDPIMODE *dwMode);
};
```

Pro spravované jazyky, je nejlepším místem pro toto rozhraní implementují ve stejné třídě, která je odvozena z *Microsoft.VisualStudio.Shell.ToolWindowPane*. Pro C++, je nejlepším místem pro toto rozhraní implementují ve stejné třídě, která implementuje *IVsWindowPane* z vsshell.h.

Hodnota vrácená vlastností režimu rozhraní je __VSDPIMODE (a spravovat přetypování na uint v):

```cs
enum __VSDPIMODE
{
    VSDM_Unaware    = 0x01,
    VSDM_System     = 0x02,
    VSDM_PerMonitor = 0x03,
}
```

- Neví, znamená, že panel nástrojů je potřeba zpracovat 96 DPI, Windows bude zpracovávat vertikální snížení jeho kapacity pro všechny ostatní dpi. Výsledné na obsah se mírně rozmazaný.
- Systém znamená, že panel nástrojů je potřeba zpracovat DPI pro primární zobrazení DPI. Žádné zobrazení s odpovídající DPI bude vypadat zřetelný, ale pokud DPI se liší nebo změny během relace, Windows bude zpracovávat škálování a bude mírně rozmazaný.
- PerMonitor znamená, že panel nástrojů je potřeba zpracovat všechny DPI na všech obrazovkách a vždy, když se změní DPI.

> [!NOTE]
> Visual Studio podporuje pouze PerMonitorV2 povědomí, tak hodnota výčtu PerMonitor překládá na hodnotu Windows DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2.

#### <a name="forcing-a-control-into-a-specific-dpiawarenesscontext"></a>Vynucení ovládacího prvku do konkrétní DpiAwarenessContext
Starší verze uživatelského rozhraní, která není aktualizován pro podporu PMA režimu, může dále potřebovat menší vylepšení pro práci v režimu PMA je spuštěna sada Visual Studio. Jeden takový oprava zahrnuje, ujistěte se, že probíhá vytváření uživatelského rozhraní v pravém DpiAwarenessContext. Přinutit uživatelské rozhraní do konkrétní DpiAwarenessContext můžete zadat rozsah DPI následujícím kódem:

C#:

```cs
using (DpiAwareness.EnterDpiScope(DpiAwarenessContext.SystemAware))
{
    Form form = new MyForm();
    form.ShowDialog();
}
```

C++:

```cpp
void MyClass::ShowDialog()
{
    VsUI::CDpiScope dpiScope(DPI_AWARENESS_CONTEXT_SYSTEM_AWARE);
    HWND hwnd = ::CreateWindow(...);
}
```

> [!NOTE]
> Vynucení DpiAwarenessContext funguje pouze na rozhraní WPF a nejvyšší úrovně dialogů WPF. Po vytvoření uživatelského rozhraní WPF, která se zajistit také jejich hostování v oknech nástrojů nebo návrháři, jakmile obsah je vložen do stromu rozhraní WPF získá převést na aktuální proces DpiAwarenessContext.

## <a name="known-issues"></a>Známé problémy
### <a name="windows-forms"></a>Windows Forms

Optimalizovat pro nové scénáře ve smíšeném režimu, Windows Forms změnit způsob, jak ho vytvořit ovládací prvky a windows pokaždé, když se jejich nadřazené nebyl explicitně nastaven. Ovládací prvky bez explicitní nadřazené dříve, použít interní "parkovací oknem" jako dočasné nadřazený ovládací prvek nebo vytváří okno. 

Před .NET 4.8 byl jednoho "parkovací okna", který získá jeho DpiAwarenessContext z aktuálního kontextu povědomí o DPI vláken v okamžiku vytvoření okna. Všechny ovládací prvky bez nadřazených položek dědí stejné DpiAwarenessContext jako okno parkovací při popisovač tohoto ovládacího prvku se vytvoří a bude potomkům nadřazený koncový/očekávanímu vývojářem aplikace. Pokud "Parkovací okno" vyšší DpiAwarenessContext než poslední nadřazené okno by způsobily selhání na základě časování.

Od .NET 4.8 je nyní "Parkovací okno" pro každý DpiAwarenessContext, který je zjištěn. Hlavní rozdíl je, že DpiAwarenessContext pro ovládací prvek je do mezipaměti při vytvoření ovládacího prvku, ne v případě, že je vytvořen popisovač. To znamená, že celkové chování end je stejný, ale můžete vypnout, co dříve problém na základě časování do konzistentního problém. Také poskytuje vývojář aplikace další deterministické chování pro psaní kódu jejich uživatelského rozhraní a oborů správně.
