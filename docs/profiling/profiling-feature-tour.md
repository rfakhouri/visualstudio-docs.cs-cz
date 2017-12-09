---
title: "Profilace prohlídka funkce | Microsoft Docs"
ms.custom: H1HackMay2017
ms.date: 05/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: d2ee0301-ea78-43d8-851a-71b7b2043d73
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4899f59362f623f6ecf92927e8a15ed4762fa367
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="profiling-feature-tour"></a>Prohlídka funkce profilace

Visual Studio poskytuje celou řadu profilace nástrojů při diagnostice různé druhy problémy s výkonem v závislosti na typu vaší aplikace.

V okně diagnostické nástroje jsou k dispozici nástrojů pro profilaci, kterým můžete přistupovat během relace ladění. Okno diagnostické nástroje se zobrazí automaticky, pokud jste vypnuli ho. Otevřete okno, klikněte na tlačítko **ladění / Windows / zobrazit diagnostické nástroje**. V otevřené okno můžete vybrat nástroje, pro které chcete shromažďovat data.

![Okno diagnostické nástroje](../profiling/media/prof-tour-diagnostic-tools.png "diagnostické nástroje")

Při ladění, můžete použít **diagnostické nástroje** okno k analýze CPU a využití paměti a můžete zobrazit události, které zobrazují informace související s výkonem.

![Zobrazení diagnostických nástrojů souhrnu](../profiling/media/prof-tour-cpu-and-memory-graph.gif "souhrn diagnostické nástroje")

**Diagnostické nástroje** okno je často upřednostňovaný způsob, jak profil aplikace, ale můžete také provést analýzu postmortální aplikace místo. Pokud chcete další informace o různý přístup, najdete v části [spuštění profilace nástroje s nebo bez ladicí program](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="analyze-cpu-usage"></a>Analýza využití procesoru

Tento nástroj využití procesoru je dobrým místem, kde spustit analýzu výkonu vaší aplikace. Oznámí, informace o prostředky procesoru, které využívala vaší aplikace. Podrobnější návod nástroje využití CPU najdete v tématu [začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md).

Z **Souhrn** zobrazení diagnostických nástrojů, zvolte **povolit profilace procesoru** (musíte být v relaci ladění).

![Povolit využití procesoru v diagnostických nástrojích](../profiling/media/prof-tour-enable-cpu-profiling.png "diagnostické nástroje povolit využití procesoru")

Použití nástroje efektivní, nastavte dvě zarážky v kódu, jeden na začátku a druhý na konci funkce nebo oblasti kód, který chcete analyzovat. Zkontrolujte data profilování, když jsou pozastavena u druhé zarážky.

**Využití procesoru** zobrazení uvidíte seznam funkcí, které jsou seřazené podle nejdelší spuštěna s nejdelší dobou funkce v horní části. To vám pomůže k funkcím kde jsou kritické body děje.

![Diagnostické nástroje využití CPU zobrazení](../profiling/media/prof-tour-cpu-usage.png "využití procesoru diagnostické nástroje")

Dvakrát klikněte na funkce, že máte zájem, a zobrazí podrobnější pohled na tři podokně "motýla", s vybrané funkce uprostřed okně volání funkce na levé straně a volat funkce na pravé straně. **Tělo funkce** část ukazuje celkové množství času (a procentuální hodnotu času) věnovaný tělo funkce bez doby věnovaný volání a funkce s názvem. Tato data můžete vyhodnotit, jestli je funkce, samotné kritických bodů výkonu.

![Diagnostické nástroje volající volaný "motýla" zobrazení](../profiling/media/prof-tour-cpu-usage-caller-callee.png "diagnostické nástroje volající volaný zobrazení")

## <a name="analyze-memory-usage"></a>Analýza využití paměti

Okno diagnostické nástroje také umožňuje vyzkoušet využití paměti v aplikaci. Například můžete si prohlédnout počet a velikost objektů v haldě. Podrobné pokyny k analýze paměti, najdete v části [analýza využití paměti](../profiling/memory-usage.md).

Chcete-li analýza využití paměti, vytvořte alespoň jeden snímek paměti při ladění. Často je nejlepší způsob, jak analyzovat paměti dvě vytváření snímků; první těsně před problém možného paměti a druhý snímku bezprostředně za podezřelé paměti problém nastane. Potom můžete zobrazit diferencovat dvě snímků a najdete v části přesně co se změnilo.

![Pořízení snímku v diagnostických nástrojích](../profiling/media/prof-tour-take-snapshots.gif "snímky trvat diagnostické nástroje")

Když vyberete jeden z odkazů šipku, budete mít rozdílové zobrazení haldy (červená šipka nahoru ![zvýšit využití paměti](../profiling/media/prof-tour-mem-usage-up-arrow.png "zvýšit využití paměti") zobrazuje (vlevo) roste počet objektů nebo zvýšení Velikost haldy (napravo)). Pokud kliknete na odkaz vpravo, získáte rozdílové haldy zobrazení seřazené podle objekty, které nejvíce zajímají, velikost haldy vyšší. To může pomoct přesné problémy s pamětí. Například na následující ilustraci bajtů používané `ClassHandlersStore` objekty zvýšit 3,492 bajtů ve druhé snímku.

![Diagnostické nástroje haldy zobrazení rozdílů](../profiling/media/prof-tour-mem-usage-diff-heap.png "zobrazení rozdílů haldy diagnostické nástroje")

Pokud kliknete na odkaz na levé straně místo v **využití paměti** zobrazení, zobrazení haldy jsou uspořádána podle počtu objektu; v horní části se zobrazí objekty určitého typu, které zvýšily nejvíce v číslo (seřazené podle **počet rozdílové** sloupce).

## <a name="examine-performance-events"></a>Vyhledejte události výkonu

**Události** zobrazení v diagnostických nástrojích ukazuje různé události, které nastaly při ladění, jako je nastavení boru přerušení nebo taktování operaci kódu. Můžete zkontrolovat informace, jako je doba trvání události (měřeno z kdy naposledy byla pozastavena ladicího programu, nebo při spuštění aplikace). Pokud krok prostřednictvím kódu (F10, F11), například **události** zobrazení uvidíte délka běhového prostředí aplikace z předchozího kroku operace pro stávající krok.

![Zobrazit události diagnostických nástrojů](../profiling/media/prof-tour-events.png "zobrazení události diagnostických nástrojů")

 > [!NOTE]
 > Pokud máte Visual Studio Enterprise, můžete také zjistit [události IntelliTrace](../debugger/intellitrace.md) na této kartě.

Stejné události také zobrazí v editoru kódu, který se zobrazí jako PerfTips.

![Profilace prohlídka PerfTips](../profiling/media/prof-tour-perf-tips.png "profilace PerfTips prohlídka")

## <a name="examine-ui-performance-and-accessibility-events-uwp"></a>Zkontrolujte výkon uživatelského rozhraní a usnadnění události (UWP)

V aplikacích pro UPW můžete povolit **uživatelského rozhraní Analysis** v okně diagnostické nástroje. Nástroj vyhledá běžné problémy s výkonem a usnadnění a zobrazí je v **události** zobrazení při ladění. Popisy událostí obsahují informace, které mohou pomoci vyřešit problémy.

![Zobrazit události Analysis uživatelského rozhraní v diagnostických nástrojích](../profiling/media/prof-tour-ui-analysis.png "diagnostických nástrojů zobrazení uživatelského rozhraní analýzy událostí")

## <a name="profile-release-builds-without-the-debugger"></a>Profil verze sestavení bez ladicí program

Profilace nástroje jako využití CPU a využití paměti lze použít s ladicím programem (viz předchozí části), nebo ji můžete spustit pomocí profileru výkonu, který je určen k poskytování analýz pro nástroje pro profilaci **verze** sestavení. V profileru výkonu můžete shromažďovat diagnostické informace, když aplikace běží a pak zkontrolujte shromážděné informace po zastavení aplikace. Další informace o těchto různý přístup, najdete v části [spuštění profilace nástroje s nebo bez ladicí program](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

![Výkon profileru](../profiling/media/prof-tour-performance-profiler.png "výkonu profileru")

Otevřete profileru výkonu výběrem **ladění nebo výkonu profileru**.

Okno vám umožní vybrat více nástrojů pro profilaci v některých scénářích. Nástroje, jako je využití procesoru může poskytovat doplňující data, která můžete použít při v analýzy.

## <a name="analyze-resource-consumption-xaml"></a>Analýza spotřeby prostředků (XAML)

V jazyce XAML aplikacích, jako třeba Windows desktop WPF aplikace a aplikace UWP můžete analyzovat spotřeby prostředků pomocí nástroje časová osa aplikace. Například můžete analyzovat čas strávený aplikací Příprava rámce uživatelského rozhraní (rozložení a vykreslování), sítě a disku požadavky obsluhy a v případech, jako je spuštění aplikace, stránka zatížení a změňte velikost okna. Chcete-li použít nástroj, zvolte **časová osa aplikace** v profileru výkonu a potom zvolte **spustit**. V aplikaci, projít scénář s vyčerpáním možného prostředků a potom vyberte **zastavit shromažďování** pro generování sestavy.

Nedostatek framerates v **Visual propustnost** graf může odpovídat visual problémy, které se zobrazí při spuštění aplikace. Podobně vysokou čísla v **využití vlákna uživatelského rozhraní** graf může také odpovídat problémy odezvy uživatelského rozhraní. V sestavě můžete vybrat časové období s problémem možného výkonu a pak zkontrolujte podrobné aktivity vlákna uživatelského rozhraní v zobrazení Podrobnosti o časová osa (dolní podokno).

![Časová osa aplikace profilace nástroj](../profiling/media/prof-tour-application-timeline.gif "časová osa aplikace profilace prohlídka")

V zobrazení Podrobnosti o časové ose najdete informace, jako je typ činnosti (nebo element uživatelského rozhraní související se situací) společně s doba trvání aktivity. Například v obrázku **rozložení** 57.53 ms výskytu události ovládacího prvku mřížky.

Další informace najdete v tématu [časová osa aplikace](../profiling/application-timeline.md).

## <a name="analyze-gpu-usage-direct3d"></a>Analýza využití GPU (Direct3D)

V aplikacích Direct3D (Direct3D součásti musí být v jazyce C++) můžete prověřit aktivity na GPU a analyzovat problémy s výkonem. Další informace najdete v tématu [využití GPU](../debugger/gpu-usage.md). Chcete-li použít nástroj, zvolte **využití GPU** v profileru výkonu a potom zvolte **spustit**. V aplikaci, projít scénář, který vás zajímá profilace a potom vyberte **zastavit shromažďování** k vygenerování sestavy.

Když vyberte časové období v v grafech a zvolte **zobrazit podrobnosti**, zobrazí se podrobné zobrazení v dolním podokně. V podrobném zobrazení můžete zkontrolovat, kolik aktivity se děje v každém procesoru a GPU. Vyberte události v podokně nejnižší získat automaticky otevíraná okna v časové ose. Vyberte například **přítomen** událostí zobrazíte **přítomen** volání automaticky otevíraná okna. (Světla šedé svislé čáry impulsu Vsync lze použít jako referenci zjistit, jestli určité **přítomen** volání provedena impulsu Vsync. Musí být jeden **přítomen** volání mezi každé dva Vsyncs v pořadí pro aplikaci vytrvale narazila na 60 FPS.)

![Využití GPU profilace nástroj](../profiling/media/prof-tour-gpu-usage.png "Diag využití GPU")

V grafech můžete také použít k určení, zda existují procesoru vázaný nebo GPU vázaný kritické body.

## <a name="analyze-performance-javascript"></a>Analýza výkonu (JavaScript)

Pro aplikace Windows Universal HTML můžete použít nástroje pro paměť jazyka JavaScript a HTML odezvy uživatelského rozhraní.

Nástroj paměť jazyka JavaScript je podobná nástroj využití paměti k dispozici pro jiné typy aplikací. Tento nástroj slouží k pochopení využití paměti a najít nevracení paměti v aplikaci. Další podrobnosti o tomto nástroji najdete v tématu [paměť jazyka JavaScript](../profiling/javascript-memory.md).

![Paměť jazyka JavaScript profilace nástroj](../profiling/media/diagjsmemory.png "DiagJSMemory")

Chcete-li diagnostikovat odezvy uživatelského rozhraní, pomalé načítání čas a pomalé visual aktualizace v aplikacích Windows Universal HTML, použijte nástroj odezvy uživatelského rozhraní HTML. Využití je podobná nástroje časová osa aplikace pro jiné typy aplikací. Další informace najdete v tématu [odezvy uživatelského rozhraní HTML](../profiling/html-ui-responsiveness.md).

![Profilace nástroj odezvy uživatelského rozhraní HTML](../profiling/media/diaghtmlresp.png "DiagHTMLResp")

## <a name="analyze-network-usage-uwp"></a>Analýza využití sítě (UWP)

V aplikacích pro UPW, můžete analyzovat síťových operací provést pomocí `Windows.Web.Http` rozhraní API. Tento nástroj můžete stáhnout výkonu a vyřešit problémy, jako je přístup a ověřování problémy, nesprávné použití mezipaměti a nízký zobrazení. Chcete-li použít nástroj, zvolte **sítě** v profileru výkonu a potom zvolte **spustit**. V aplikaci, projít scénář, který používá `Windows.Web.Http`a potom zvolte **zastavit shromažďování** pro generování sestavy.

![Profilace nástroj využívání sítě](../profiling/media/prof-tour-network-usage.png "Diag využití sítě")

Vyberte operaci v souhrnné zobrazení na Zobrazit další podrobnosti.

![Podrobné informace v nástroji využití sítě](../profiling/media/prof-tour-network-usage-details.png "Diag podrobnosti o použití sítě")

Další informace najdete v tématu [využití sítě](../profiling/network-usage.md).

## <a name="analyze-performance-legacy-tools"></a>Analýza výkonu (starší verze nástroje)

Pokud potřebujete například instrumentace funkce, které nejsou aktuálně nachází v nástrojích pro využití procesoru nebo využití paměti a používáte plocha nebo aplikace ASP.NET, můžete pro profilace prohlížeč výkonu. (Není podporována v aplikacích pro UPW). Další informace najdete v tématu [prohlížeč výkonu](../profiling/performance-explorer.md).

![Nástroj Průzkumník výkonu](../profiling/media/prof-tour-performance-explorer.png "prohlížeč výkonu")

## <a name="which-tool-should-i-use"></a>Který nástroj mám použít?  
Tady je tabulku, která obsahuje seznam různých nástrojů, které nabízí Visual Studio a typy jiný projekt můžete například vytvořit pomocí:
  
|Nástroj výkon|Windows desktop|Univerzální/úložiště systému Windows|ASP.NET/ASP.NET jádra|  
|----------------------|---------------------|------------------------------|-------------|  
|[Využití paměti](../profiling/memory-usage.md)|Ano|Ano|Ano|  
|[Využití procesoru](../profiling/cpu-usage.md)|Ano|Ano|Ano (ne pro .NET Core/ASP.NET Core)|  
|[Využití GPU](../debugger/gpu-usage.md)|Ano|Ano|Ne|  
|[Časová osa aplikace](../profiling/application-timeline.md)|Ano|Ano|Ne|  
|[PerfTips](../profiling/perftips.md)|Ano|Ano pro jazyk XAML, ne pro HTML|Ano|  
|[Prohlížeč výkonu](../profiling/performance-explorer.md)|Ano|Ne|Ano (ne pro ASP.NET Core)|  
|[IntelliTrace](../debugger/intellitrace.md)|Pouze .NET Enterprise|Pouze .NET Enterprise|Pouze .NET Enterprise|
|[Využití sítě](../profiling/network-usage.md)|Ne|Ano|Ne| 
|[Rychlost odezvy HTML UI](../profiling/html-ui-responsiveness.md)|Ne|Ano pro HTML, ne pro jazyk XAML|Ne|  
|[Paměť jazyka JavaScript](../profiling/javascript-memory.md)|Ne|Ano pro HTML, ne pro jazyk XAML|Ne|  

## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md)