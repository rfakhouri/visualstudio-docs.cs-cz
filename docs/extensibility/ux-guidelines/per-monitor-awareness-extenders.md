---
title: Podpora sledování na sledování pro rozšíření sady Visual Studio
titleSuffix: ''
description: Další informace o novou podporu zařízení extender pro za monitorování – sledování k dispozici v aplikaci Visual Studio 2019.
ms.date: 04/09/2019
helpviewer_keywords:
- Visual Studio, PMA, per-monitor-awareness, extenders, Windows Forms
- Per-Monitor Awareness support for extenders
ms.assetid: ''
author: rub8n
ms.author: rurios
manager: anthc
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: reference
ms.workload:
- multiple
ms.openlocfilehash: 42de73a29e053066c0fbeca72ca3511b58b2fa7e
ms.sourcegitcommit: 0a2fdc23faee77187e10a1c19665ba5a1ac68e72
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477807"
---
# <a name="per-monitor-awareness-support-for-visual-studio-extenders"></a>Podpora sledování na sledování pro rozšíření sady Visual Studio

Verze starší než Visual Studio 2019 měl svým kontextem povědomí o DPI nastavena na systém vědět, než na za sledování DPI vědět (PMA). Spouštění v systému sledování je v degradovaném stavu vizuální prostředí (například fuzzy písma nebo ikony) pokaždé, když Visual Studio došlo k vykreslení na monitorech s jinou měřítko nebo vzdáleně se připojte k počítačům s jiným zobrazením konfigurace (například různé Windows škálování).

Kontext povědomí o DPI. 2019 Visual Studio je sada jako clustery, což Visual Studio k vykreslení závislosti na konfiguraci zobrazení, kde se hostuje na monitorování spíše než Konfigurace obecného definovaná systémem. Takže v konečném důsledku překládá na ostrý uživatelského rozhraní pro plochy, které implementují PMA podporu.

Odkazovat [vysoké rozlišení DPI Desktop Application Development na Windows](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) dokumentaci pro další informace o podmínkách a celkové scénáře popsané v tomto dokumentu.

## <a name="quickstart"></a>Rychlý start
- Zkontrolujte, Visual Studio běží v režimu PMA (naleznete v tématu **povolení PMA**)

- Byly správně ověřeny vaše rozšíření funguje mezi sadu běžné scénáře (viz **testování rozšíření pro problémy PMA**)

- Pokud narazíte na problémy, budete potřebovat přidat nový balíček nuget PMA diagnostikovat a opravit problémy s použitím strategie a doporučení popsaných v tomto dokumentu

## <a name="enabling-pma"></a>Povolení PMA
Pokud chcete povolit PMA v sadě Visual Studio, musí být splněny následující požadavky:
1)  Windows 10. dubna 2018 Update (v1803 RS4) nebo novější
2)  Rozhraní .NET framework 4.8 RTM nebo novější (aktuálně se dodává jako samostatné ve verzi preview nebo svazku s poslední Windows Insider sestavení)
3)  Visual Studio 2019 s ["Optimalizace vykreslování obrazovky s jinou hustoty"](https://docs.microsoft.com/visualstudio/ide/reference/general-environment-options-dialog-box?view=vs-2019) povolenou možnost

Jakmile jsou splněny tyto požadavky, Visual Studio automaticky povolí PMA celém procesu.

## <a name="testing-your-extensions-for-pma-issues"></a>Testování rozšíření PMA problémů

Visual Studio oficiálně podporuje rozhraní WPF, Windows Forms, Win32 a HTML/JS uživatelského rozhraní. Když Visual Studio přejde do režimu PMA, různé balíky uživatelského rozhraní se chovat jinak. Bez ohledu na architekturu uživatelského rozhraní, proto doporučujeme, že průchodu testů se provádí za účelem Ujistěte se, že je v souladu s PMA všechny uživatelského rozhraní.

Vaše rozšíření podporuje bez ohledu na architekturu uživatelského rozhraní, se doporučuje ověřit následující běžné scénáře:

1. Změna faktoru škálovací sady jednoho monitoru prostředí, když je aplikace spuštěná *
    - V tomto scénáři pomáhá otestovat, zda uživatelské rozhraní reaguje na dynamické změny Windows DPI

2. Ukotvení/vyjímání přenosný počítač, kde připojené monitorování změní primárním serverem a připojenými monitorování má jiné než primární koeficient když aplikace běží.
    - V tomto scénáři pomáhá otestovat, zda reaguje uživatelského rozhraní zobrazení změnit DPI, jakož i dynamicky zpracování zobrazí přidávání nebo odebírání

3. S více monitorů s jinou měřítko a přesun aplikace mezi nimi.
    - V tomto scénáři pomáhá otestovat, zda uživatelské rozhraní reaguje na změnu zobrazení DPI
    
4. Vzdálená komunikace k počítači, když místní a vzdálené počítače mají různé měřítko pro primární monitorování.
    - V tomto scénáři pomáhá otestovat, zda uživatelské rozhraní reaguje na dynamické změny Windows DPI

Vhodný předběžný test pro Určuje, zda uživatelské rozhraní může mít problémy se určuje, jestli kód využívá buď *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper* nebo *Microsoft.VisualStudio.PlatformUI.DpiHelper* třídy. Tyto třídy staré DpiHelper podporují jenom systému rozpoznání nastavení dpi a nebude vždy fungovat správně, když je proces PMA.

Typické použití těchto DpiHelpers bude vypadat takto:

```cs
Point screenTopRight = logicalBounds.TopRight.LogicalToDeviceUnits();

POINT screenIntTopRight = new POINT
{
    x = (int)screenTopRIght.X,
    y = (int)screenTopRIght.Y
}

IntPtr monitor = NativeMethods.MonitorFromPoint(screenIntTopRight, NativeMethods.Monitor_DEFAULTTONEARST);
```

V předchozím příkladu obdélník představující logické hranice okna je převedena na jednotky zařízení tak, aby může být předán do nativní metody MonitorFromPoint, která očekává souřadnice zařízení, aby bylo možné vrátit zpět ukazatel přesné monitorování.

### <a name="classes-of-issues"></a>Třídy problémů

Pokud PMA je povolené pro Visual Studio, uživatelské rozhraní může replikovat problémy běžné způsoby. Většina. Pokud ne, z těchto problémů může dojít v některém z Visual Studia podporované architektury uživatelského rozhraní. Kromě toho tyto problémy se může stát i když část uživatelského rozhraní je hostované v kombinovaném režimu DPI škálování scénáře (odkazovat Windows [dokumentaci](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) Další). 

#### <a name="win32-window-creation"></a>Vytváření oken Win32
Při vytváření oken s CreateWindow() nebo CreateWindowEx(), běžným postupem je vytvoření panelu na souřadnicích 0; 0 (/ levého horního rohu primárního), přesuňte ji na poslední pozici. Díky tomu může způsobit okno k aktivaci DPI však změnit zprávy nebo událost, která můžete znovu aktivovat neúspěšnou dalších zpráv uživatelského rozhraní nebo události a nakonec vést k nežádoucímu chování nebo vykreslování.

#### <a name="wpf-element-placement"></a>Umístění prvku WPF
Při přesouvání elementů WPF pomocí staré Microsoft.VisualStudio.Utilities.Dpi.DpiHelper, souřadnice levého horního rohu nemusí být nevypočte správně pokaždé, když jsou prvky v případě neprimární DPI.

#### <a name="serialization-of-ui-element-sizes-or-positions"></a>Serializace velikosti prvku uživatelského rozhraní nebo umístění
Pokaždé, když obnovení uživatelského rozhraní velikosti nebo pozice v jiném kontextu DPI než co byl uložen v bude umístěn a velikosti nesprávně. K tomu dochází, protože logické hranice okna jsou převedeny na jednotky zařízení tak, aby může být předán metodě Win32 MonitorFromPoint, která očekává souřadnice zařízení, aby bylo možné vrátit zpět ukazatel přesné monitorování.

#### <a name="incorrect-scaling"></a>Nesprávné měřítko
Prvky uživatelského rozhraní vytvářené na primární DPI škálovaly správně, ale když přesune na monitor s jinou DPI, není měřítko a díky tomu se jejich obsah končí nebuďte příliš velký či příliš malý.

#### <a name="incorrect-bounding"></a>Nesprávný ohraničující
Podobně škálování problému prvky uživatelského rozhraní bude počítat jejich rozsah správně v daném kontextu se primární DPI, ale při přesunu na neprimární DPI, jejich nových mezí nevypočte správně. V důsledku toho okno obsahu končí je příliš malá nebo příliš velké ve srovnání s hostování uživatelského rozhraní, jehož výsledkem je prázdný nebo oříznutí.

#### <a name="drag--drop"></a>Přetažením
Vždy, když ve scénářích DPI ve smíšeném režimu (například různé prvky uživatelského rozhraní vykreslování v DPI kontextu primární i jiné než primární), přetáhněte souřadnice může být nesprávně vypočteny, výsledkem je konečné rozevírací koncové pozici nahoru nesprávné.

#### <a name="out-of-process-ui"></a>Uživatelského rozhraní na více instancí procesu
Některé uživatelské rozhraní se vytvoří na více instancí procesu a pokud vytvoření externího procesu je v jiném režimu povědomí o DPI než Visual Studio, což může představovat všechny předchozí problémů vykreslování.

#### <a name="windows-forms-controls-images-or-windows-not-displaying"></a>Ovládací prvky Windows Forms, Image nebo windows nejsou zobrazena
Jedním z hlavní příčiny tohoto problému je vývojáři, chcete-li změnit nadřazenou položku pro ovládací prvek nebo okno s jeden DpiAwarenessContext do jiného okna DpiAwarenessContext. 

Následující obrázky ukazují aktuální omezení operačního systému Windows v nadřazenosti windows, pokud vlákno hostování chování je explicitně:

![Snímek obrazovky vztahy k nadřazeným položkám správné chování](../../extensibility/ux-guidelines/media/PMA-parenting-behavior.PNG)

V důsledku toho pokud je nastavit vztah nadřazenosti a podřízenosti mezi nepodporované režimy, se nezdaří a okna ovládacího prvku nebo nemusí být vykreslen podle očekávání.

### <a name="diagnosing-issues"></a>Diagnostika problémů
Existuje celá řada faktorů, které je třeba zvážit při identifikaci problémů souvisejících se PMA: 

1. Provádí uživatelského rozhraní nebo rozhraní API očekává logickou nebo hodnoty zařízení.
    - Rozhraní API a rozhraní WPF obvykle používají logické hodnoty (ale ne vždy)
    - Uživatelského rozhraní Win32 API se obvykle používá hodnoty zařízení

2. Pokud jsou hodnoty pocházející z?
    - Pokud se zobrazuje hodnoty z jiných uživatelského rozhraní nebo rozhraní API, je to zařízení předávání nebo logické hodnoty.
    - Pokud se zobrazuje hodnoty z více zdrojů, všechny použijte/očekávají stejné typy hodnot nebo převody nemusíte být smíšený a odpovídající?

3. Jsou konstanty uživatelské rozhraní používá a jaké formuláře jsou v?

4. Vlákno je ve správném kontextu pro hodnoty DPI přijímá?
    - Změny, které chcete povolit CLMM by měly obecně put cesty kódu ve správném kontextu, však může spustit práce mimo hlavní zprávy smyčky nebo událost toku v chybném kontextu DPI.

5. Hodnoty překračují hranice kontextu DPI?
    - Přetáhnout je běžné situace, ve kterém můžete souřadnice napříč kontexty DPI. Okno se pokouší provést správnou věc, ale v některých případech možná muset práci převod zajistit odpovídající hranice kontext hostitele uživatelského rozhraní.

### <a name="pma-nugget-package"></a>Balíček Nuget PMA
Nové knihovny DpiAwarness můžete najít na balíček Microsoft.VisualStudio.DpiAwareness NuGet.

### <a name="recommended-tools"></a>Doporučené nástroje
Následující nástroje vám mohou pomoci ladit problémy související s PMA v některé z různých zásobníky uživatelské rozhraní nepodporuje sady Visual Studio.

#### <a name="snoop"></a>Sledování
Sledování je nástroj ladění XAML, který má některé další funkce, která nemá integrované nástroje Visual Studio XAML. Kromě toho stará není potřeba aktivně ladění sady Visual Studio, abyste mohli zobrazit a upravit jeho uživatelské rozhraní WPF. Dva hlavní způsoby sledování může být užitečné při diagnostikování potíží PMA je pro ověření souřadnice logické umístění nebo velikost hranice a pro ověření rozhraní má správné DPI.
 
#### <a name="visual-studio-xaml-tools"></a>Nástroje sady Visual Studio XAML
Třeba sledování můžete nástroje XAML v sadě Visual Studio usnadnění diagnostiky potíží se PMA. Po nalezení pravděpodobnou můžete nastavit zarážky a použít ke kontrole hranice uživatelského rozhraní a aktuální DPI Live Visual Tree okna, jakož i ladicích oknech.

## <a name="strategies-for-fixing-pma-issues"></a>Strategie pro řešení problémů PMA

### <a name="replacing-dpihelper-calls"></a>Nahrazení DpiHelper volání
Ve většině případů opravit problémy uživatelského rozhraní v PMA boils na nahrazení volání ve spravovaném kódu původní: *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper* a *Microsoft.VisualStudio.PlatformUI.DpiHelper* tříd pomocí volání do nového *Microsoft.VisualStudio.Utilities.DpiAwareness* pomocná třída. 

Pro nativní kód, bude mít nahrazení volání do starého *VsUI::CDpiHelper* třídy pomocí volání do nového *VsUI::CDpiAwareness* třídy. Nové třídy DpiAwareness a CDpiAwareness nabízí stejné převod pomocné rutiny třídy DpiHelper ale vyžadovat další vstupní parametr: prvku uživatelského rozhraní, který chcete použít jako referenci pro operaci převodu. 

Spravované třídy DpiAwareness nabízí pomocné rutiny pro Vizuály WPF, ovládacích prvků Windows Forms a Win32 HWND a HMONITORs (i ve formě IntPtrs), při nativní CDpiAwareness nabídky HWND a HMONITOR pomocné rutiny třídy.

### <a name="windows-forms-dialogs-windows-or-controls-displayed-in-the-wrong-dpiawarenesscontext"></a>Dialogová okna Windows Forms, windows nebo ovládací prvky zobrazují v chybě DpiAwarenessContext
I potom, co úspěšném vztahy k nadřazeným položkám systému windows s jinou DpiAwarenessContext (z důvodu výchozí chování windows), může i nadále uvidí škálování problémy podle různých windows DpiAwarenessContext škálovat jinak. V důsledku toho mohou uživatelům zobrazovat fuzzy/zarovnání textu nebo obrázků problémy v Uživatelském rozhraní.

Řešením je nastavit správný obor DpiAwarenessContext pro všechna okna a ovládací prvky v aplikaci.

### <a name="tlmm-dialogs"></a>Dialogová okna TLMM
Při vytváření oknům nejvyšší úrovně, jako je například modální dialogová okna, je důležité zajistit, aby že vlákno je ve správném stavu před HWND vytváří. Vlákno můžou být přepnuté do systému povědomí o použití pomocné rutiny CDpiScope v nativní nebo spravovaný DpiAwareness.EnterDpiScope pomocné rutiny v. (TLMM doporučujeme používat pro jiné WPF dialogů/windows.)

### <a name="child-level-mixed-mode-clmm"></a>Podřízená úroveň ve smíšeném režimu (CLMM)

Ve výchozím nastavení podřízená okna zobrazí stejný režim sledování DPI jako jejich nadřazené položky. Ale SetThreadDpiHostingBehavior můžete přepsat a podřízená okna spustili v škálování jiný režim než jejich nadřazené nebo hostitele.


#### <a name="clmm-issues"></a>CLMM problémy
Většina práce výpočtu uživatelského rozhraní, ke které dochází jako součást hlavní zasílání zpráv smyčky nebo událost řetězce by již být spuštěné ve správném kontextu DPI. Nicméně pokud souřadnice nebo výpočty velikosti dokončení mimo tyto hlavní pracovní postupy (např. během úlohu dobu nečinnosti, nebo mimo vlákno uživatelského rozhraní, může být nesprávný, což vede k misplacement uživatelského rozhraní nebo chybně velikosti problémy s aktuálním kontextu DPI. Uvedení vlákna do správného stavu pro uživatelské rozhraní pracovní obecně vyřeší daný problém.
 
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
```cplusplus
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

**POZNÁMKA:**: Visual Studio podporuje pouze PerMonitorV2 povědomí, tak hodnota výčtu PerMonitor překládá na hodnotu Windows DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2.

## <a name="known-issues"></a>Známé problémy

### <a name="windows-forms"></a>Windows Forms

Optimalizovat pro nové scénáře ve smíšeném režimu, Windows Forms změnit způsob, jak ho vytvořit ovládací prvky a windows pokaždé, když se jejich nadřazené nebyl explicitně nastaven. Ovládací prvky bez explicitní nadřazené dříve, použít interní "parkovací oknem" jako dočasné nadřazený ovládací prvek nebo vytváří okno. 

"Parkovací okno" získá jeho DpiAwarenessContext z procesu, který je aplikace spuštěna v rámci. Ovládací prvek dědí stejné DpiAwarenessContext jako okno parkovací a pak by být potomkům nadřazené původní/očekávanímu vývojářem aplikace.  To nebude fungovat, pokud zamýšlený nadřazeného ovládacího prvku není stejný DpiAwarenessContext jako ovládací prvek, který vytváří.

Od .NET 4.8 Pokud nadřazená není explicitně nastavena na ovládací prvek nebo v okně, Windows Forms bude dotazovat na parkovací okna, která odpovídá DpiAwarenessContext vláken, ve které je požadováno vytvoření ovládacího prvku nebo v okně a použít jako dočasné nadřazený objekt. Jinými slovy při vytvoření ovládacího prvku je vytvořený pomocí zamýšlený DpiAwarenessContext. Ovládací prvek nebo okno se pak být potomkům očekávaný nadřazený vývojářem aplikace.
