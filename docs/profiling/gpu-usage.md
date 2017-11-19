---
title: "Využití GPU | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 957fed3c-4ded-4e05-87c6-ccc33de65349
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2c265fde65ae20012e2846d99b86c71254d5b44
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="gpu-usage"></a>Využití GPU
Použijte nástroj využití GPU ve Visual Studio výkon a diagnostiku pro lepší pochopení využití základní hardware Direct3D – aplikace. Můžete ji určit, zda je vázané na procesor nebo GPU vazby a získat přehled o použití platforma hardwaru efektivněji výkon vaší aplikace. Využití GPU podporuje aplikace, které používají Direct3D – 12, Direct3D – 11 a Direct3D – 10; nepodporuje se jiné grafické rozhraní API, například Direct2D nebo OpenGL.  
  
 Toto je **sestav využití GPU** okno:  
  
 ![Využití GPU sestavu, s procesoru a GPU časové osy](media/gfx_diag_gpu_usage_report.png "gfx_diag_gpu_usage_report")  
  
## <a name="requirements"></a>Požadavky  
 Dále jsou v nástroji využití GPU požadavky, které doplňují diagnostiky grafiky požadavky.  
  
-   Grafický procesor a ovladačů podporující instrumentace nezbytné časování.  
  
    > [!NOTE]
    >  Další informace o podporovaný hardware a ovladače, najdete v části [hardwaru a ovladače, které podporují](#hwsupport) na konci tohoto dokumentu.  
  
 Další informace o požadavcích na diagnostiky grafiky najdete v tématu [Začínáme](../debugger/graphics/getting-started-with-visual-studio-graphics-diagnostics.md).  
  
## <a name="using-the-gpu-usage-tool"></a>Pomocí nástroje využití GPU  
 Při spuštění aplikace v rámci využití GPU nástroj Visual Studio vytvoří relaci diagnostiky grafech souhrnné informace o vaší aplikace vykreslování výkonu a využití GPU v reálném čase.  
  
#### <a name="to-start-the-gpu-usage-tool"></a>Chcete-li spustit nástroj pro využití GPU:  
  
1.  V hlavní nabídce zvolte **ladění**, pak **výkonu a Diagnostika** (klávesové: stisknutím Alt + F2).  
  
2.  V centru výkonu a Diagnostika, zaškrtněte políčko vedle **využití GPU**. V případě potřeby zaškrtněte políčka vedle dalších nástrojů, které vás zajímají. Můžete spustit několik výkonu a diagnostických nástrojů souběžně na získat úplnější přehled o výkonu vaší aplikace.  
  
     ![Zvolte diagnostické nástroje, které chcete použít. ] (media/gfx_diag_diagsession_tools.png "gfx_diag_diagsession_tools")  
  
    > [!NOTE]
    >  Ne všechny výkonu a diagnostických nástrojů můžete použít ve stejnou dobu.  
  
3.  Zvolte modrý **spustit** tlačítko v dolní části výkonu a Diagnostika rozbočovače ke spouštění vaší aplikace v nabídce Nástroje, které jste vybrali.  
  
 Souhrnné informace, které se zobrazí v reálném čase zahrnuje načasování rámečku, obnovovací frekvence a využití GPU. Všechny tyto údaje vykreslovacích samostatně, ale používat běžné časovou, takže můžete snadno týkají mezi nimi.  
  
 **Rámce čas (ms)** a **snímků za sekundu (FPS)** grafy obsahují dva red, vodorovných čar s cílem výkonu představují 60 a 30 snímků za sekundu. V **rámce čas** grafu, vaše aplikace je překročení cílové výkonu po grafu pod čarou a chybějící ho po výše ose grafu. Pro počet snímků za druhé grafu je jako opak – vaše aplikace je překročení cílové výkonu po výše ose grafu a chybějící ho po grafu pod čarou. Především se stává tyto grafy se používají k získat základní představu o výkonu vaší aplikace a identifikaci slow-downs, které chcete prozkoumat – například, nečekané pokles v obnovovací frekvence nebo špička využití GPU.  
  
 Zatímco vaše aplikace běží pod nástroj využití GPU, relace diagnostiky taky shromažďuje podrobné informace o grafiky události, které byly provedeny u GPU. Tyto informace slouží ke generování podrobnější sestavu jak vaše aplikace využívá hardwaru. Vzhledem k tomu tato sestava používá chvíli generování na základě shromážděných informací, je k dispozici pouze po dokončení shromažďování informací relace diagnostiky.  
  
 Když chcete podívejte se na výkonu nebo využití přesněji vystavování, zastavte shromažďování informací o výkonu, tak, aby se dá vygenerovat sestavu.  
  
#### <a name="to-generate-and-view-the-gpu-usage-report"></a>Umožňuje generovat a prohlížet sestavy využití GPU:  
  
1.  V dolní části okna relace diagnostiky, vyberte **zastavit kolekce** propojení nebo stiskněte klávesu **Zastavit** v levém horním rohu.  
  
     ![Shromážděte informace časování GPU a procesoru. ] (media/gfx_diag_gpu_usage_collect.png "gfx_diag_gpu_usage_collect")  
  
2.  V horní části sestavy vyberte oddíl z jednoho z grafů, které zobrazuje problém, že který chcete prozkoumat. Výběr může být až 3 sekund; delší oddíly se zkrátí na začátku.  
  
     ![Post & č. 45; kolekce, vybrat rozsah, chcete-li zobrazit podrobnosti o](media/gfx_diag_gpu_usage_select1.png "gfx_diag_gpu_usage_select1")  
  
3.  V dolní části sestavy, vyberte **zobrazit podrobnosti** na odkaz v **.. klikněte sem zobrazíte podrobnosti o využití GPU pro tento rozsah** zprávu zobrazíte podrobné časová osa vašeho výběru.  
  
     ![Post & č. 45; kolekce s vybraný rozsah](media/gfx_diag_gpu_usage_select2.png "gfx_diag_gpu_usage_select2")  
  
 Otevře se nové dokumentů s kartami, který obsahuje sestavu. Využití GPU sestava pomáhá při spuštění událostí grafiky na procesoru, až dorazí do GPU a jak dlouho trvalo grafický procesor s cílem provést. Tyto informace můžete identifikovat kritická místa a příležitosti pro vyšší paralelismus v kódu.  

<!-- VERSIONLESS -->
## <a name="export-to-gpuview-or-windows-performance-analyzer"></a>Exportovat do GPUView nebo Analyzátor výkonu Windows
Od verze Visual Studio 2017, tato data můžete otevřít pomocí [GPUView](/windows-hardware/drivers/display/using-gpuview) a [Analyzátor výkonu Windows](/windows-hardware/test/wpt/windows-performance-analyzer) kliknutím **otevřít v GpuView** nebo **otevřít WPA** odkazy nacházející se v pravém dolním rohu relace diagnostiky.

![Otevřít v...](media/gfx_diag_open_in.png)
<!-- /VERSIONLESS -->

## <a name="using-the-gpu-usage-report"></a>Pomocí sestavy využití GPU  
 Horní části sestavy využití GPU zobrazuje časové osy pro zatížení procesoru aktivity, aktivita vykreslování GPU a aktivita GPU kopírování. Tyto časové osy jsou dělený light šedá, svislých pruhů, které představují impulsu vsync v zobrazení; frekvence pruhů odpovídá obnovovací frekvence jedné zobrazuje (vybrali pomocí **zobrazení** rozevíracího seznamu) využití GPU data nebyla shromážděna z. Protože zobrazení může být vyšší obnovovací frekvence než výkonu cíl své aplikace nemusí být 1Na-1 vztah mezi impulsu vsync a chcete, aby vaše aplikace k dosažení frekvenci snímků. Ke splnění výkonu cíli musí dokončit všechny zpracování, proveďte vykreslování a volání Present() v cílové snímkový kmitočet aplikace, ale vykreslené rámečku nebude zobrazí až další impulsu vsync po Present().  
  
 Dolní část zobrazí seznam událostí grafiky, které nastaly během časového období sestavy.  
  
 Tady je **sestav využití GPU** okno:  
  
 ![Využití GPU sestavu, s procesoru a GPU časové osy](media/gfx_diag_gpu_usage_report.png "gfx_diag_gpu_usage_report")  
  
 Výběrem jedné z událostí v dolní části sestavy na odpovídající události v příslušné časové osy, obvykle jedné ve vlákně procesoru, který představuje volání rozhraní API a další události na jednom GPU časových os, která představuje při umístí značku GPU dokončení úlohy. Výběrem jedné z událostí na časové ose, označuje odpovídající události v dolní části sestavy. Při zvětšení mimo časové osy v horní části sestavy, jsou viditelné pouze nejvíce zdlouhavý události. Pokud chcete zobrazit události, které mají kratší dobu trvání, zvětšení pomocí kombinace kláves Ctrl + kolečka na zařízení nebo škálování ovládacího prvku v levém dolním rohu horním panelu časové osy. Můžete také přetáhnout obsah časová osa panelu, chcete-li procházet zaznamenané události.  
  
 A pomůže vám zjistit, co hledáte, můžete filtrovat na základě názvy, ID vlákna a název události; proces sestavy využití GPU Kromě toho můžete zvolit, které zobrazení obnovovací frekvence určuje vysnc čar a může seřadit události hierarchicky Pokud vaše aplikace používá rozhraní ID3DUserDefinedAnnotation skupiny vykreslování příkazy.  
  
 Zde jsou další informace:  
  
|Ovládací prvek filtru|Popis|  
|--------------------|-----------------|  
|**Proces**|Název procesu, které vás zajímají. V této rozevírací nabídce jsou zahrnuty všechny procesy, které používají GPU během relace diagnostiky. Barva spojených s procesem v této rozevírací je barva aktivity vlákna v níže uvedené časové osy.|  
|**Přístup z více vláken**|ID podprocesu, které vás zajímají. Vícevláknové aplikace to vám může pomoci identifikovat konkrétní vláken, které patří do procesu, který vás zajímá. Události spojené s vybranou posloupnost jsou vyznačené na každý časové osy.|  
|**Zobrazení**|Počet zobrazení se zobrazí jejichž obnovovací frekvence **Poznámka:** některé ovladače lze nakonfigurovat, aby k dispozici více fyzických zobrazí jako jeden, velké virtuální zobrazení. Jedním zobrazení v seznamu uvedena, může se zobrazit i v případě, že tento počítač má několik zobrazí připojen.|  
|**Filtr**|Klíčová slova, která vás zajímá. Události v dolní části sestavy bude obsahovat pouze ty, které odpovídají – klíčové slovo v celé nebo částečně. Více klíčových slov můžete určit jejich oddělením středníkem (;).|  
|**Řazení hierarchie**|Zaškrtávací políčko, která určuje, zda jsou události hierarchií – definovat přes uživatele značek – zachovaná nebo ignorovat.|  
  
 Seznam událostí v dolní části sestavy využití GPU zobrazí podrobnosti o jednotlivých událostí.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název události**|Název události grafiky. Událost obvykle odpovídá jedné v ose přístup z více vláken na procesor a jeden události na časové ose GPU.<br /><br /> Názvy událostí může být 'bez atributů, pokud využití GPU se nepodařilo zjistit název události. Další informace najdete v poznámce dál v této tabulce.|  
|**Spuštění procesoru (ns)**|Čas, události se inicializovala na procesor při volání rozhraní API Direct3D. Čas se měří v nanosekundách, vzhledem k při spuštění aplikace.|  
|**Spuštění grafický procesor (ns)**|Doba, která událost byla spuštěna ve GPU. Čas se měří v nanosekundách, vzhledem k při spuštění aplikace.|  
|**Doba trvání grafický procesor (ns)**|Doba, kterou trvalo dokončení na GPU v nanosekundách události.|  
|**Název procesu**|Název aplikace, ze kterého přišel události.|  
|**ID podprocesu**|ID vlákna, ze kterého přišel události.|  
  
> [!IMPORTANT]
>  Windows 8.1 se vyžaduje pro uvedení událostí. Kromě toho pokud GPU nebo ovladač nepodporují nezbytné instrumentace funkce, všechny události se zobrazí jako 'bez atributů'. Nezapomeňte aktualizovat ovladač GPU a zkuste to znovu, pokud k tomuto problému dochází. Další informace najdete v tématu [hardwaru a ovladače, které podporují](#hwsupport) níže.  
  
## <a name="gpu-usage-settings"></a>Nastavení využití GPU  
 Můžete nakonfigurovat nástroj využití GPU odložit kolekce profilace informace, namísto spuštění ke shromažďování informací při spuštění aplikace. Vzhledem k velikosti analytické informace můžou být důležité, to je užitečné, když víte, že zpomalení výkonu vaší aplikace se zobrazí až později.  
  
#### <a name="to-postpone-profiling-from-the-start-of-the-app"></a>Chcete-li odložit profilace od spuštění aplikace:  
  
1.  V hlavní nabídce zvolte **ladění**, pak **výkonu a Diagnostika** (klávesové: stisknutím Alt + F2).  
  
2.  V centru výkonu a Diagnostika, postupujte podle **nastavení** vedle **využití GPU**.  
  
3.  V části **GPU profilace konfigurace**na **Obecné** stránka vlastností, zrušte **začít profilace při spuštění aplikace** zaškrtávací políčko, chcete-li odložit profilace.  
  
     ![Konfigurace při spuštění shromažďování využití GPU](media/gfx_diag_gpu_usage_config.png "gfx_diag_gpu_usage_config")  
  
> [!IMPORTANT]
>  Odložení profilace není aktuálně podporován pro Direct3D – 12 aplikace.  
  
 Při shromažďování informací a profilování odložení pomocí tohoto nastavení, k dispozici v dolní části okna nástroje využití GPU dodatečný odkaz, po spuštění aplikace v rámci nástroje využití GPU. Pokud chcete spustit shromažďování analytické informace, vyberte **spustit** odkaz v **spuštění shromažďování další podrobné údaje o využití GPU** zprávy.  
  
##  <a name="hwsupport"></a>Podpora hardwaru a ovladače  
 Jsou podporovány následující hardwarové GPU a ovladače:  
  
|Dodavatele|Popis GPU|Požadovaná verze ovladače|  
|------------|---------------------|-----------------------------|  
|Intel®|4. generování Intel® jader procesorů (Haswell)<br /><br /> -Intel® HD grafiky (GT1)<br />-Intel® HD grafiky 4200 (GT2)<br />-Intel® HD grafiky 4400 (GT2)<br />-Intel® HD grafiky 4600 (GT2)<br />-Intel® HD grafiky P4600 (GT2)<br />-Intel® HD grafiky P4700 (GT2)<br />-Intel® HD grafiky 5000 (GT3)<br />-Intel® Iris™ grafiky 5100 (GT3)<br />-Intel® Iris™ Pro grafiky 5200 (GT3e)|--(použijte nejnovější ovladače)|  
|AMD®|Většina od AMD Radeon™ HD 7000-series (nezahrnuje AMD Radeon™ HD 7350 7670)<br /><br /> Grafický procesor AMD Radeon™, AMD FirePro™ grafickými procesory a grafický procesor AMD FirePro akcelerátorů s funkcí architektura grafiky základní další (GCN).<br /><br /> AMD® E-Series a AMD A-series Accelerated zpracování jednotky (APU) poskytuje funkci architektura grafiky základní další (GCN) ('Kaveri', 'Kabini', 'Temash', 'Beema', 'Mullins')|14.7 RC3 nebo vyšší|  
|NVIDIA®|Většina od NVIDIA® GeForce® 400-series.<br /><br /> NVIDIA® GeForce® grafickými procesory a grafickými procesory NVIDIA Quadro® NVIDIA® Tesla™ GPU akcelerátorů s funkcí Fermi™, Kepler™ nebo Maxwell™ architektura.|343.37 nebo vyšší|  
  
 Konfigurace více grafickými procesory, třeba NVIDIA® SLI™ a AMD Crossfire™ nejsou podporovány v tuto chvíli. Instalace hybridní grafiky, jako je například NVIDIA® Optimus™ a AMD Enduro™ jsou podporovány.  
  
## <a name="see-also"></a>Viz také  
  
-   [Řešení robustním grafiky problémů pomocí nástrojů hry s použitím rozhraní DirectX pro (video)](http://channel9.msdn.com/Events/GDC/GDC-2015/Solve-the-Tough-Graphics-Problems-with-your-Game-Using-DirectX-Tools)  
-   [Nástroj využití GPU v sadě Visual Studio (video)](http://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/715)  
-   [Využití GPU nástroj v aplikaci Visual Studio 2013 Update 4 CTP1 (blog)](http://blogs.msdn.com/b/vcblog/archive/2014/09/05/gpu-usage-tool-in-visual-studio-2013-update-4-ctp1.aspx)  
-   [Využití GPU pro rozhraní DirectX v sadě Visual Studio (blog)](http://blogs.msdn.com/b/ianhu/archive/2014/12/16/gpu-usage-for-directx-in-visual-studio.aspx)
- [GPUView](/windows-hardware/drivers/display/using-gpuview) 
- [Analyzátor výkonu Windows](/windows-hardware/test/wpt/windows-performance-analyzer)