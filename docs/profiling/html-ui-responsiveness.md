---
title: "Analýza odezvy uživatelského rozhraní HTML v aplikacích pro UPW | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- performance, JavaScript [UWP apps]
- performance tools, JavaScript [UWP apps]
- UI Responsiveness Profiler [JavaScript]
- profiler, UI responsiveness [JavaScript]
- profiler, JavaScript [UWP apps]
ms.assetid: da13070a-ba40-47dd-a846-ad72eed70d0b
caps.latest.revision: "47"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bee8bdc56586f1c79ff10d8d2b70e30801f54254
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="analyze-html-ui-responsiveness-in-universal-windows-apps"></a>Analýza odezvy uživatelského rozhraní HTML v univerzálních aplikací pro Windows
Toto téma popisuje, jak izolovat problémy s výkonem ve svých aplikacích pomocí Profiler odezvy uživatelského rozhraní, nástroj výkonu k dispozici pro univerzální aplikace pro Windows.  
  
 Profiler odezvy uživatelského rozhraní vám může pomoci identifikovat problémy, třeba problémy odezvy uživatelského rozhraní nebo vedlejší účinky platformy, které obvykle ke kterým dochází u tyto příznaky:  
  
-   Chybí odezvy v uživatelském rozhraní. Aplikace může být pomalé reagovat, pokud je blokován vlákna uživatelského rozhraní. Některé věci, které by mohly blokovat vlákna uživatelského rozhraní zahrnovat nadměrné synchronní kódu jazyka JavaScript, nadměrné rozložení šablon stylů CSS nebo pracovní výpočtu šablon stylů CSS, synchronní XHR požadavky, uvolňování paměti, nadměrné Malování časy nebo kód jazyka JavaScript náročná na výkon procesoru.  
  
-   Pomalé načítání čas pro aplikace nebo stránky. To je obvykle způsobena nadměrné čas strávený načítání prostředků.  
  
-   Visual aktualizace, které jsou méně časté, než se očekávalo. K tomu dojde, pokud je příliš zaneprázdněn udržovat smooth obnovovací frekvence vlákna uživatelského rozhraní. Například pokud je zaneprázdněné vlákna uživatelského rozhraní, může vyřadit rámce. Některé non-UI vlákno pracovat, jako jsou síťové požadavky, dekódování, bitové kopie a barvy můžete také omezit četnosti aktualizací visual. (Ne všechny Malování se provádí ve vlákně UI.)  
  
##  <a name="RunningProfiler"></a>Spusťte nástroj odezvy uživatelského rozhraní HTML  
 Pokud máte pracovní UWP nebo Windows 8.1 aplikaci otevřete v sadě Visual Studio nebo nainstalovat do počítače se systémem Windows 8 nebo novější, můžete použít nástroj odezvy uživatelského rozhraní HTML.  
  
1.  Pokud spouštíte aplikaci ze sady Visual Studio na **standardní** panelu nástrojů v **spustit ladění** vyberte cíl nasazení, jako je například jeden z Windows Phone emulátorů, **místního počítače** , **Simulátoru**, nebo **vzdáleného počítače**.  
  
2.  Na **ladění** nabídce zvolte **profileru výkonu...** .  
  
     Pokud chcete změnit cíl analýzy pro profileru, zvolte**změnit cíl**.  
  
     ![Změna cílové analysis](../profiling/media/js_tools_target.png "JS_Tools_Target")  
  
     Jsou k dispozici pro cíl analysis následující možnosti:  
  
    -   **Spouštěný projekt**. Vyberte tuto možnost k analýze aktuální projekt po spuštění. Pokud spouštíte aplikaci na vzdáleném počítači nebo zařízení, musíte použít tato nastavení, což je výchozí hodnota.  
  
    -   **Spuštění aplikace**. Tuto volbu vyberte aplikaci UWP ze seznamu spuštěných aplikací. Tuto možnost nelze použít, když používáte aplikaci na zařízení nebo vzdáleném počítači.  
  
         Tuto možnost můžete použít k analýze výkonu aplikací, které jsou spuštěné v počítači, pokud nemáte přístup ke zdrojovému kódu.  
  
    -   **Nainstalované aplikace**. Vyberte tuto možnost vyberte nainstalovanou aplikaci, která chcete analyzovat. Tuto možnost nelze použít, když používáte aplikaci na zařízení nebo vzdáleném počítači.  
  
         Tuto možnost můžete analyzovat výkon aplikací, které jste nainstalovali v počítači, pokud nemáte přístup ke zdrojovému kódu. Tato možnost může být také užitečné, když chcete analyzovat výkon všech aplikací mimo váš vlastní vývoj aplikací.  
  
3.  Z **nástroje**, vyberte **odezvy uživatelského rozhraní HTML**a potom zvolte **spustit**.  
  
4.  Když spustíte Profiler odezvy uživatelského rozhraní, okno Řízení uživatelských účtů si mohou vyžádat vaše oprávnění ke spuštění Collector.exe trasování událostí pro Windows Visual Studio. Zvolte **Ano**.  
  
     Komunikovat s aplikaci pro otestování tohoto scénáře relevantní výkonu. Podrobný postup najdete v části [izolovat problém odezvy uživatelského rozhraní](#Workflow) a [izolovat problém visual propustnost](#IsolateVisualThroughput).  
  
5.  Přepněte do sady Visual Studio stisknutím Alt + Tab.  
  
6.  Chcete-li zastavit profilace aplikace a zobrazení data, která profileru shromáždit, zvolte **zastavit shromažďování**.  
  
##  <a name="IsolateAnIssue"></a>Izolovat problém  
 V následujícím oddílu najdete návrhy můžete izolovat problémy s výkonem. Podrobné vysvětlení, jak identifikovat a opravit problémy s výkonem pomocí výkonu ukázka testování aplikace najdete v tématu [návod: odezvy zlepšení uživatelského rozhraní (HTML)](../profiling/walkthrough-improving-ui-responsiveness-html.md).  
  
###  <a name="Workflow"></a>Izolovat problém odezvy uživatelského rozhraní  
 Tyto kroky obsahují návrhy pracovního postupu, které můžou pomoct efektivněji využívat Profiler odezvy uživatelského rozhraní:  
  
1.  Otevřete aplikaci v sadě Visual Studio.  
  
2.  Testování aplikace problémů odezvy uživatelského rozhraní. (Stisknutím Ctrl + F5 a spusťte aplikaci bez ladění.)  
  
     Pokud narazíte na problém, pokračujte, testování a pokuste se zúžit časový rámec, ve kterém k danému problému dojde, nebo zkuste k identifikaci aktivační události, které způsobují chování.  
  
3.  Přepněte do sady Visual Studio (stiskněte klávesy Alt + Tab) a zastavit aplikace (Shift + F5).  
  
4.  Můžete přidat uživatele značky kódu pomocí [označit kód pro analýzu](#ProfileMark).  
  
    > [!TIP]
    >  Značky uživatele můžete identifikovat problém odezvy při zobrazení dat profileru. Například můžete přidat uživatele označit na začátku a konci části kódu, který je příčinou problém odezvy.  
  
5.  Spusťte Profiler odezvy uživatelského rozhraní podle pokynů v předchozí části.  
  
6.  Uvést aplikaci do stavu, který má za následek chybu odezvy uživatelského rozhraní.  
  
7.  Přepněte do sady Visual Studio (stiskněte klávesy Alt + Tab) a zvolte **zastavit shromažďování** na kartě profileru Profiler odezvy uživatelského rozhraní.  
  
8.  Pokud jste přidali uživatele značky, se objeví v [zobrazení časové osy relace diagnostiky](#Ruler) z profileru. Následující obrázek znázorňuje značka jednoho uživatele umožňuje zadat konkrétní operace v kódu.  
  
     ![Diagnostika pravítka zobrazující označit uživatele](../profiling/media/js_htmlvizprofiler_usermark.png "JS_HTMLVizProfiler_UserMark")  
  
9. Oblast zájmu o časové ose a grafy profileru identifikujte pomocí značky uživatele, události životního cyklu aplikace nebo data zobrazená v v grafech. Zde jsou některé pokyny, které vám usnadní analýzu a používat data při v grafech:  
  
    -   Použití [zobrazení časové osy relace diagnostiky](#Ruler) zobrazíte [označit kód pro analýzu](#ProfileMark), události životního cyklu aplikace a související časovou osu pro tyto události a časovou osu pro data v jiných grafy.  
  
    -   Použití [graf využití procesoru](#CPUutilization) Chcete-li zobrazit obecné informace o procesoru aktivitu a typu práce je zpracování během určitého časového období. Období aktivity nadměrnému využití procesoru pravděpodobně mít za následek odezvy problémy a vyřadit rámce.  
  
    -   Pokud vyvíjíte herní nebo bohatý mediální aplikace, použijte [zobrazení visual propustnost (FPS)](#VisualThroughput) k určení období času, ve kterém vyřadit snímků za sekundu.  
  
10. Vyberte oblast zájmu v jednom z v grafech součástí grafu kliknutím a přetažením má ukazatel na příslušnou položku (nebo pomocí klávesy Tab a klávesy se šipkami). Když vyberete časové období pomocí voleb, časová osa grafu podrobnosti v dolním podokně okna profilování změny zobrazit pouze vybrané časové období.  
  
     Následující obrázek znázorňuje graf využití procesoru s určitou oblast zájmu zvýrazněná.  
  
     ![Graf využití procesoru](../profiling/media/js_htmlvizprof_cpu_util.png "JS_HTMLVizProf_CPU_Util")  
  
11. Použití [zobrazit podrobnosti časová osa](#TimelineDetails) získat podrobné informace o událostech, které se spouští příliš často nebo trvá příliš dlouho dokončení. Například vyhledejte následující:  
  
    -   Naslouchacích procesů událostí, časovačů a zpětná volání rámce animace. V závislosti na konkrétní události může zahrnovat data poskytnutá ID upravené elementů modelu DOM, název změněné vlastnosti CSS, odkaz na zdrojové umístění a název přidružené události nebo zpětného volání funkce.  
  
    -   Rozložení nebo skriptování události, jejichž výsledkem vykreslování elementů, například volání `window.getComputedStyles`. Je k dispozici přidružená elementu DOM pro událost.  
  
    -   Stránky nebo adresa URL zdroje, které jsou načteny aplikací, jako je například skript hodnocení pro analýzu událostí HTML. Je zadaný název souboru nebo prostředků.  
  
    -   Další události, zadaný v [profileru událostí odkaz](#ProfilerEvents).  
  
    > [!TIP]
    >  Většina využitelné informace v profileru se zobrazí v grafu podrobnosti časové osy.  
  
12. K oblasti pro využití procesoru nebo diagram visual propustnosti (FPS), zvolte **přiblížit** (tlačítko nebo kontextu nabídky) Chcete-li získat podrobnější informace. Časová osa grafu změny se zobrazí pouze vybrané časové období.  
  
13. Při přiblížení, vyberte část využití procesoru nebo visual propustnost grafu. Pokud provedete výběr, časová osa grafu podrobnosti v okna profilování dolním podokně změny zobrazit pouze vybrané časové období.  
  
###  <a name="IsolateVisualThroughput"></a>Izolovat problém visual propustnost  
 Období nadměrné využití výkonu procesoru může způsobit nízkou nebo k nekonzistentnímu rámce sazby. Pokud vyvíjíte bohatý mediální aplikace a hry, mohou poskytnout grafu visual propustnost dat důležitější než graf využití procesoru.  
  
 Pokud chcete izolovat visual propustnost problém, postupujte podle kroků popsaných v předchozí části, ale použít visual propustnost grafu jako jeden z klíčů datových bodů.  
  
###  <a name="ProfileMark"></a>Označit pro analýzu kódu  
 Snažte se určit oddíl kód aplikace, který je spojen s daty, která se zobrazí v grafech, přidáte volání funkce ve vaší aplikaci obsahující pokyn profileru pole uživatele – Inverzní trojúhelník – časovou osu v tuto chvíli získá funkci spustit. Označte všechny uživatele, které přidáte, se zobrazí v časovou osu pro graf využití procesoru a graf podrobnosti časové osy grafu visual propustnost.  
  
 Přidání značka uživatele, přidejte následující kód do vaší aplikace. Tento příklad používá "získávání dat" jako popis události.  
  
```javascript  
if (performance && performance.mark) {  
    performance.mark("getting data");  
}  
  
```  
  
 Popis události se zobrazí jako popisek, když ukazatel myši nad označit uživatele. Můžete přidat libovolný počet značek uživatele podle potřeby.  
  
> [!NOTE]
>  `console.timeStamp`, příkaz Chrome, se rovněž zobrazuje jako značku uživatele.  
  
 Následující obrázek znázorňuje pravítka diagnostiky značkou jednoho uživatele a jeho popis.  
  
 ![Diagnostika pravítka zobrazující označit uživatele](../profiling/media/js_htmlvizprofiler_usermark.png "JS_HTMLVizProfiler_UserMark")  
  
 Můžete také vytvořit událostí generovaných nástroj v zobrazení Podrobnosti o časová osa zobrazíte trvání čas, který uplyne mezi dvěma značky uživatele. Následující kód přidá druhý uživatel označit a měření jejich čas, který uplyne mezi provádění značky ve dvou uživatele (předchozí kód ukazuje označit první uživatel).  
  
```javascript  
if (performance.mark && performance.measure) {  
    performance.mark("data retrieved");  
    performance.measure("data measure", "getting data", "data retrieved");  
}  
```  
  
 Pokud není zadán druhý uživatel označit, `performance.measure` používá časového razítka jako druhý uživatel značky. První označit uživatele je povinný.  
  
 Doba trvání měření se zobrazí jako **uživatele měr** událostí v časové ose zobrazení podrobností a jsou uvedeny podrobné informace při výběru.  
  
 ![Zobrazení podrobností události měr uživatele v časové ose](../profiling/media/js_htmlvizprofiler_user_measure.png "JS_HTMLVizProfiler_User_Measure")  
  
##  <a name="AnalyzeData"></a>Analýza dat  
 Následující části obsahují informace, které pomohou interpretovat data, která se zobrazí v profileru.  
  
###  <a name="Ruler"></a>Zobrazení časové osy relace diagnostiky  
 Pravítka v horní části profileru ukazuje osy PROFILOVANÉHO informace. Tuto časovou osu se vztahuje na graf využití procesoru a propustnost visual grafu.  
  
 Zde je, jak časovou osu relace diagnostiky vypadá s popisek zobrazí několik události životního cyklu aplikace:  
  
 ![Relace diagnostiky pravítka](../profiling/media/js_htmlvizprof_ruler.png "JS_HTMLVizProf_Ruler")  
  
 Časová osa zobrazí, když dojde k událostem lifecyle aplikace, jako jsou aktivační události, a zobrazuje značky uživatel (uživatel značky trojúhelníčky), můžete přidat do vašeho kódu. Můžete vybrat události, které chcete zobrazit tipy s dalšími informacemi. Další informace o značky uživatele najdete v tématu [označit kód pro analýzu](#ProfileMark) v tomto tématu.  
  
 Události životního cyklu aplikace se zobrazí jako kosočtverec symboly. Toto jsou DOM – události, které zahrnují následující:  
  
-   `DOMContentLoaded`a `Load` události, které většinou dochází v obslužné rutině aktivované události do vašeho kódu. Popisek pro událost ukazuje konkrétní události a adresy URL.  
  
-   Událost navigace, která nastane, když přejdete na jinou stránku. Cílová adresa URL stránky zobrazuje popis tlačítka pro událost.  
  
###  <a name="CPUUtilization"></a>Zobrazení procesoru využití  
 Graf využití procesoru umožňuje určit dobu, ve kterém je aktivita nadměrnému využití procesoru. Poskytuje informace o aplikace průměrné spotřeby procesoru nad v časovém intervalu. Informace, které jsou rozlišené barevně představují následující specifických kategorií: **načítání**, **skriptování**, uvolňování paměti (**GC**), **stylů**, **Vykreslování**, a **Image dekódování**. Další informace o těchto kategorií najdete v tématu [profileru událostí odkaz](#ProfilerEvents) dál v tomto tématu.  
  
 Graf využití procesoru ukazuje množství času strávené na všechny aplikace vláken, kombinace hodnoty využití procesoru pro jeden nebo více procesorů do jednoho procentuální hodnotu. Hodnota využití procesoru může překročit 100 procent, když se používá více než jeden procesor.  
  
> [!NOTE]
>  Využití GPU nezobrazí v grafu.  
  
 Tento příklad ukazuje, jak vypadá graf využití procesoru:  
  
 ![Graf využití procesoru](../profiling/media/js_htmlvizprof_cpu_util.png "JS_HTMLVizProf_CPU_Util")  
  
 Použijte tento graf tak, aby:  
  
-   Identifikujte obecné oblastí zájmu.  
  
-   Zvolte konkrétní časové období pro zobrazení v grafu podrobnosti časové osy. Časové období, vyberte součástí grafu a výběr na přetažením proveďte výběr.  
  
-   Získat podrobnější zobrazení vybrané časové období výběrem **přiblížit** tlačítko.  
  
 Další informace o používání grafu najdete v tématu [izolovat problém odezvy uživatelského rozhraní](#Workflow) v tomto tématu.  
  
###  <a name="VisualThroughput"></a>Zobrazení visual propustnost (FPS)  
 Diagram visual propustnosti umožňuje určit dobu, ve kterém obnovovací frekvence vyřadit. Zobrazuje počet snímků za sekundu (FPS) pro aplikaci. Tento graf je velmi užitečné pro vývoj her a bohatý mediální aplikace.  
  
 Zobrazená hodnota FPS může lišit od skutečné snímků za sekundu. Tyto informace při mějte prověřují se data v tomto grafu:  
  
-   Graf zobrazuje FPS, že je schopné dosáhnout kdykoli konkrétní aplikace. Při nečinnosti aplikace FPS je stejný jako obnovovací frekvence monitoru.  
  
-   Graf zobrazuje skutečné FPS, pokud aplikace provádí práci, kterou vyžaduje visual aktualizace.  
  
-   Graf zobrazuje hodnota nula, pokud jsou vyřazována rámce.  
  
 Tento příklad ukazuje, jak vypadá visual propustnost grafu:  
  
 ![Diagram Visual propustnosti](../profiling/media/js_htmlvizprof_vizthru.png "JS_HTMLVizProf_VizThru")  
  
 Pomocí visual propustnost graf tak, aby:  
  
-   Identifikujte obecné oblastí zájmu.  
  
-   Zvolte konkrétní časové období pro zobrazení v grafu podrobnosti časové osy. Časové období, vyberte součástí grafu a výběr na přetažením proveďte výběr.  
  
-   Získat podrobnější zobrazení vybrané časové období výběrem **přiblížit** tlačítko.  
  
###  <a name="TimelineDetails"></a>Zobrazit podrobnosti časové osy  
 Podrobnosti o časová osa grafu se zobrazí v dolním podokně Profiler odezvy uživatelského rozhraní. Poskytuje postupného a hierarchické informace o událostech, které spotřebovávají nejvíce času procesoru během vybrané časové období. Tento graf vám pomohou určit, co aktivuje určitá událost a pro některé události, jak událost mapuje zpět ke zdrojovému kódu. Tento graf také vám pomůže určit čas potřebný k vyplnění visual aktualizace na obrazovce.  
  
 Graf zobrazuje pracovního vlákna uživatelského rozhraní a pracovních na vlákna na pozadí, které může přispívat k zpomalit visual aktualizace. Graf přestane zobrazovat pracovní JavaScript JIT, asynchronní GPU pracovní, práce mimo proces hostitele (například RuntimeBroker.exe a dwm.exe pracovní) nebo práci pro prostředí Windows Runtime oblasti, které ještě nebyly byla instrumentována pro službu profilace (například v/v disku).  
  
> [!TIP]
>  Pokud se vyskytne událost vlákna na pozadí, zobrazí se v závorkách vedle názvu události ID vlákna.  
  
 Tento příklad ukazuje, jaké časovou osu grafu podrobnosti vypadá po kliknutí na naslouchací proces událostí pro DOM je vybrána událostí:  
  
 ![Časová osa grafu podrobnosti](../profiling/media/js_htmlvizprof_timelinedet.png "JS_HTMLVizProf_TimelineDet")  
  
 V tomto obrázku **spinAction** obslužné rutiny událostí v **název události** sloupec je odkaz, pokud vybraná, přejdete k obslužné rutině událostí ve zdrojovém kódu. V pravém podokně klikněte **funkce zpětného volání** vlastnost poskytuje stejné připojení ke zdrojovému kódu. Informace o události, jako je například přidružené elementu DOM přinést také další vlastnosti.  
  
 Pokud vyberete část časovou osu pro využití procesoru a graf visual propustnost (FPS), časové osy grafu podrobnosti jsou uvedeny podrobné informace pro vybrané časové období.  
  
 Události v časová osa grafu podrobnosti jsou rozlišené barevně představují stejnou kategorií práce, které se zobrazují v graf využití procesoru. Další informace o události kategorie a určitých událostí najdete v tématu [profileru událostí odkaz](#ProfilerEvents) v tomto tématu.  
  
 Použijte časová osa podrobnosti graf tak, aby:  
  
-   Zobrazit časy zahájení Přibližná doba trvání a koncový čas pro událost v zobrazení časové osy a mřížky. Časová osa grafu podrobnosti můžete zobrazit období od 30 MS až 30 sekund v zobrazení mřížky, v závislosti na stavu přiblížení. Pro hodnoty typu duration:  
  
    -   Představují včetně doby trvání události, včetně podřízených objektů událostí. V zobrazení mřížky zobrazí se tato hodnota první.  
  
    -   Výhradní časy představují doby trvání události, není včetně podřízených objektů událostí. Tato hodnota se zobrazí v závorkách v zobrazení mřížky.  
  
-   Rozbalte událost v hierarchii k zobrazení podřízených prvků události. Podřízené objekty události jsou ostatní události, které jsou vydané události nadřazené. Například událostí DOM může mít naslouchacích procesů událostí, které se zobrazují jako podřízené objekty. Naslouchací proces událost může mít další události, které jsou výsledkem, jako je událost rozložení.  
  
-   Události řazení podle počáteční čas (výchozí) nebo doba trvání. Použití **seřadit** seznamu vyberte způsob řazení.  
  
-   Zobrazit podrobnosti pro každou jednotlivou událost v podokně podrobností (pravé podokno). Vlastnosti lišit v závislosti na konkrétní události, jak ukazují tyto příklady:  
  
    -   Časovače, naslouchacích procesů událostí (DOM událostí) a zpětná volání rámce animace **funkce zpětného volání** vlastnost obsahuje odkaz na zdrojové umístění kód společně s názvem událostí obslužná rutina nebo zpětného volání funkce.  
  
    -   Časovače, naslouchacích procesů událostí (událostí DOM), rozložení událostí a zpětná volání animace rámečku, barevně souhrn vybrané události a všechny její podřízené položky v zobrazí **včetně čas shrnutí** část (barevně okruh). Každý řez barevně obrázku představuje typ události. Popisy tlačítek zadejte název typu události.  
  
    > [!TIP]
    >  Časová osa grafu podrobnosti a **včetně čas shrnutí** můžete identifikovat oblasti pro optimalizaci. Pokud některý z těchto zobrazení ukazuje velké množství malých úlohy, může být událost kandidátem pro optimalizaci. Například aplikace může být aktualizace elementů modelu DOM často, což vede k velkým počtem rozložení a analýzu událostí HTML. Bude pravděpodobně možné za účelem optimalizace výkonu pomocí dávkování činnost.  
  
###  <a name="FilterTimelineDetails"></a>Podrobnosti o filtru časové osy  
 Můžete filtrovat zobrazení v podrobnostech časovou osu pro konkrétní událost výběrem **filtr událostí** z kontextové nabídky pro konkrétní události. Pokud vyberete tuto možnost, časového harmonogramu a mřížky zobrazení jsou vymezeny pro zvolenou událost. Výběr v graf využití procesoru rozsahy taky na konkrétní události.  
  
 ![Filtrování časovou osu pro událost](../profiling/media/js_htmlvizprofiler_filtertoevent.png "JS_HTMLVizProfiler_FilterToEvent")  
  
###  <a name="FilterEvents"></a>Filtrování událostí  
 Můžete filtrovat na některé události z časová osa grafu podrobnosti ke snížení šumu v datech, nebo omezit data, která není zajímavé pro váš scénář výkonu. Můžete filtrovat podle názvu události nebo trvání události nebo podle konkrétní filtry, které jsou zde popsané.  
  
 Chcete-li filtrovat dekódování bitové kopie, spekulativní stahování a GC – události, zrušte **aktivita na pozadí** možnost na ikonu filtru v dolním podokně. Protože tyto události nejsou velmi níž lze provést akci, jsou skrytá ve výchozím nastavení.  
  
 ![Filtrování událostí v časové ose](../profiling/media/js_htmlvizprofiler_event_filter.png "JS_HTMLVizProfiler_Event_Filter")  
  
 Chcete-li filtrovat události žádostí protokolu HTTP, zrušte **přenos v síti** možnost na ikonu filtru v dolním podokně. Ve výchozím nastavení jsou tyto události uvedené v časová osa grafu podrobnosti.  
  
 Chcete-li filtrovat aktivity vlákna uživatelského rozhraní, zrušte **činnosti uživatelského rozhraní** možnost.  
  
> [!TIP]
>  Zrušte zaškrtnutí tohoto políčka a vyberte možnost provoz sítě můžete prozkoumat problémy související s latencí sítě.  
  
 Chcete-li filtrovat uživatele míry, zrušte **uživatele míry** možnost. Uživatel míry jsou nejvyšší úrovně události se žádné podřízené objekty.  
  
###  <a name="GroupFrames"></a>Skupina události podle rámečku  
 Můžete seskupit události, které se zobrazují v zobrazení Podrobnosti o časová osa pro jednotlivé snímky. Tyto události rámce jsou události, nástroj vygeneruje a představovat nejvyšší úrovně událostí kontejnery pro všechny pracovní vlákna uživatelského rozhraní, která probíhá mezi Malování události. Chcete-li toto zobrazení, vyberte **nejvyšší úrovně události seskupit rámce**.  
  
 ![Seskupit podle rámce nejvyšší úrovně události](../profiling/media/js_htmlvizprofiler_frame_grouping_button.png "JS_HTMLVizProfiler_Frame_Grouping_Button")  
  
 Při seskupování událostí podle rámečku, nejvyšší úrovně události v podrobnostech časová osa zobrazení jednotlivých představují rámce.  
  
 ![Časová osa události seskupené podle rámce](../profiling/media/js_htmlvizprofiler_frame_grouping.png "JS_HTMLVizProfiler_Frame_Grouping")  
  
##  <a name="SaveSession"></a>Uložení relace diagnostiky  
 V sadě Visual Studio můžete uložit relaci diagnostiky, když zavřete kartu, která je přidružená k relaci. Později můžete znovu otevřít uložených relací.  
  
##  <a name="ProfilerEvents"></a>Odkaz na události profileru  
 Profileru události jsou zařazené do kategorie a barevné kódování v Profiler odezvy uživatelského rozhraní. Toto jsou kategorie události:  
  
-   **Načítání.** Označuje, že čas strávený načítání prostředků aplikace a analýzy HTML a CSS poprvé načte aplikaci. To může zahrnovat síťové požadavky.  
  
-   **Skriptování.** Označuje čas strávený analýzy a spouštění JavaScript. To zahrnuje událostí DOM, časovače, vyhodnocení skriptu a pracovní rámce animace. Obsahuje uživatelský kód a kód knihovny.  
  
-   **GLOBÁLNÍ KATALOG.** Označuje čas strávený uvolňování paměti.  
  
-   **Stylů.** Označuje, že čas strávený analýzy šablon stylů CSS a výpočet element prezentace a rozložení.  
  
-   **Vykreslování.** Označuje čas strávený vykreslování na obrazovce.  
  
-   **Dekódování bitové kopie.** Označuje, že čas strávený dekompresi a dekódování bitové kopie.  
  
 Skriptů a stylů kategorií Profiler odezvy uživatelského rozhraní můžete získat data, která může fungovat na v grafu podrobnosti časové osy. Pokud jako problém identifikovat problémy skriptování, můžete spustit procesoru vzorkování profileru s Profiler odezvy uživatelského rozhraní. Alternativně můžete použít profileru funkce sady Visual Studio můžete získat podrobnější data. Další informace najdete v tématu [paměť jazyka JavaScript](../profiling/javascript-memory.md).  
  
 V jiných kategoriích událostí je možné identifikovat vedlejší účinky platformy, které jsou výsledkem přidání funkcí do vaší aplikace, ale v těchto případech nemusí být schopni vyřešit konkrétní výkonem pomocí Profiler odezvy uživatelského rozhraní.  
  
 Tato tabulka obsahuje události a jejich popisy:  
  
|Událost|Kategorie události|Nastane při|  
|-----------|--------------------|-----------------|  
|Analýza šablon stylů CSS|Načítání|Byl nalezen nový obsah šablon stylů CSS a došlo pokusu o analyzovat obsah šablon stylů CSS.|  
|Analýza HTML|Načítání|Byl nalezen nový obsah HTML a analyzovat obsah do uzlů a vložit obsah do stromu modelu DOM byl učiněn pokus.|  
|Požadavek HTTP|Načítání|V modelu DOM byl nalezen vzdálený prostředek, nebo XMLHttpRequest byl vytvořen, jejichž výsledkem požadavku HTTP.|  
|Spekulativní stahování|Načítání|Obsah HTML stránky se hledali požadované prostředky tak, aby následné žádosti HTTP pro prostředky, které mohou být naplánovány rychle.|  
|Funkce zpětného volání rámce animace|Skriptování|Vykreslení jiného snímku, bude v prohlížeči, a tento stav aktivován funkce zpětného volání zadané aplikace.|  
|Události modelu DOM|Skriptování|Události modelu DOM došlo k chybě a byla spuštěna.<br /><br /> `context` Vlastnost DOM události, jako například `DOMContentLoaded` nebo `click`, se zobrazí v závorkách.|  
|Naslouchací proces událostí|Skriptování|Naslouchací proces událostí byl vyvolávány a spuštěny.|  
|Naslouchací proces dotazu média|Skriptování|Registrovaný media dotaz byla zrušena, čímž vznikl provádění jeho přidružené listener(s).|  
|Mutace pozorovatel|Skriptování|Jeden nebo více zaznamenali, že DOM elementy byly upraveny, což vedlo ke spuštění MutationObserver přidružené zpětného volání.|  
|Vyhodnocení skriptu|Skriptování|Nový element SCRIPT byla nalezena v modelu DOM a byl proveden pokus o analyzovat a spustit skript.|  
|Časovač|Skriptování|Uplynulý čas naplánované časovač, a to bylo způsobeno v provádění jeho přidružené zpětného volání funkce.|  
|Funkce zpětného volání asynchronních prostředí Windows Runtime|Skriptování|Asynchronní operace, který aktivoval `Promise` funkce zpětného volání byla dokončena objekt prostředí Windows Runtime.|  
|Prostředí Windows Runtime událostí|Skriptování|Událost, která v prostředí Windows Runtime objektu došlo k aktivaci registrované naslouchací proces.|  
|Uvolnění paměti|Uvolňování paměti|Byl stráven čas shromažďování paměti pro objekty, které se už používá.|  
|Výpočet šablon stylů CSS|Práce se styly|Byly provedeny změny DOM, který požadované vlastnosti stylu všechny dotčené elementů být přepočítána.|  
|Rozložení|Práce se styly|Byly provedeny změny DOM, který vyžaduje velikost nebo pozice všech elementů ovlivněných být přepočítána.|  
|Malování|Vykreslování|Byly provedeny změny Visual modelu DOM a došlo pokusu o znovu zpracovat části stránky.|  
|Vykreslení vrstvy|Vykreslování|Visual fragment nezávisle vykreslené modelu DOM (označovaný jako vrstva) byly provedeny změny a změny potřebné část stránky k vykreslení.|  
|Dekódování bitové kopie|Dekódování bitové kopie|Obrázek je zahrnutý v modelu DOM a byl proveden pokus o dekomprimovat a dekódovat bitovou kopii z původním formátu do bitmapy.|  
|Rámec|Není k dispozici|Byly provedeny změny Visual DOM, který vyžaduje všechny příslušné části stránky překreslit. Toto je nástroj vygeneruje událost používat k vytváření skupin.|  
|Míra uživatele|Není k dispozici|Scénářem specifické pro aplikace se měří pomocí `performance.measure` metoda. Toto je nástroj vygeneruje událost použít pro analýzu kódu.|  
  
##  <a name="Tips"></a>Další informace  
  
-   Kukátko [toto video](http://channel9.msdn.com/Events/Build/2013/3-316) z konference Build 2013 o Profiler odezvy uživatelského rozhraní.  
  
-   Přečtěte si tipy pro zvýšení výkonu pro aplikace UWP vytvořená pro systém Windows pomocí jazyka JavaScript. Další informace najdete v tématu [osvědčené postupy z hlediska výkonu pro aplikace UWP pomocí jazyka JavaScript](http://msdn.microsoft.com/library/windows/apps/hh465194.aspx).  
  
-   Informace o model spouštění jednovláknové kódu a výkonu najdete v tématu [provádění kódu](http://msdn.microsoft.com/library/windows/apps/hh781217.aspx).  
  
## <a name="see-also"></a>Viz také  
 [Nástroje pro profilaci](../profiling/profiling-tools.md)