---
title: "Grafika rámce analýzy | Microsoft Docs"
ms.custom: 
ms.date: 02/09/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.frameanalysis
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fd3af414b5d59ec49ed6e042d6a656d322fe8a38
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="graphics-frame-analysis"></a>Analýza grafických snímků
Analýza grafických snímků použijte v sadě Visual Studio Graphics Analyzer k analýze a optimalizace výkonu vykreslování Direct3D – hry nebo aplikace.  

## <a name="frame-analysis"></a>Analýza snímků  
 Analýza snímků používá stejné informace, které je zachycené v souboru protokolu grafiky k diagnostickým účelům, ale používá ke shrnutí výkonu vykreslování místo. Informace o výkonu není do protokolu zaznamenána během zachycení; Místo toho informace o výkonu je generován později, při analýza snímků časování události a shromažďování statistik jako přehrání rámečku. Tento přístup má několik výhod oproti záznamu informace o výkonu během zachycení:  
  
-   Analýza snímků můžete průměrná výsledky z více jednotlivými cykly stejné rámce pro zajištění statisticky zvukové souhrnu výkonu.  
  
-   Analýza snímků mohou generovat informace o výkonu pro hardwarové konfigurace a jiná zařízení než ten, kde byla zaznamenána informace.  
  
-   Analýza snímků mohou generovat nové souhrny výkonu z dříve zaznamenaných informací – například když jsou optimalizované nebo odhalí další funkce ladění ovladače grafického procesoru.  
  
 Kromě tyto výhody analýza snímků můžete také provádět změny rámečku vykreslení při přehrávání tak, aby ho může být informace o tom, jak tyto změny mohou ovlivnit výkon vykreslování aplikace. Tyto informace můžete použít k rozhodování mezi potenciální optimalizace strategie bez nutnosti jejich všechny implementaci a pak zachytíte a porovnání všechny výsledky sami.  
  
 I když analýza snímků je primárně určen pro vám pomohou dosáhnout vyšší výkon vykreslování, může dosáhnout lepší visual kvality pro danou výkonu cíl nebo snížení spotřeby energie GPU stejně pomoct.  
  
 Pokud chcete zjistit, co můžete dělat analýza snímků pro vaši aplikaci ukázka, můžete sledovat [analýza grafických snímků Visual Studio](http://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) videa na webu Channel 9.  
  
## <a name="using-frame-analysis"></a>Pomocí analýza snímků  
 Než budete moct použít analýza snímků, budete muset zaznamenání grafických informací z vaší aplikace je spuštěna, stejně jako při použití některé z dalších nástrojů analyzátor grafiky. Zvolte v okně grafiky protokolu dokumentu (.vsglog) **analýza snímků** kartě.  
  
 ![Vyberte kartu analýza snímků.](media/pix_frame_analysis_select_tab.png "pix_frame_analysis_select_tab")  
  
 Po dokončení analýzy, se zobrazí výsledky. Horní část kartě rámce analýzy zobrazí časového harmonogramu a tabulku souhrnu. Dolní část zobrazí tabulky podrobností. Pokud při přehrávání byly vygenerovány chyby nebo výstrahy, jsou shrnuty výše časovou osu; odtud můžete pomocí odkazů se seznamte s chybami a upozorněními.  
  
### <a name="interpreting-results"></a>Interpretace výsledků  
 Interpretací výsledků jednotlivých variant lze odvodit, že je užitečné informace o vaší aplikaci vykreslování výkonu a chování. Další informace o vykreslování variant najdete v tématu [variant](#Variants) dále v tomto článku.  
  
 Některé výsledky přímo znamenat jak varianta ovlivňuje výkon vykreslování:  
  
-   Jestliže byl variant bilineární filtrování Texture zvýšení výkonu, pak pomocí bilineární texture filtrování ve vaší aplikaci se zobrazí podobné zvýšení výkonu.  
  
-   Pokud varianta zobrazení 1 × 1 vám ukázal, zvýšení výkonu, pak snižuje velikost cíle pro vykreslení ve vaší aplikaci se zvýší jeho výkon vykreslování.  
  
-   Jestliže byl variant BC Texture komprese zvýšení výkonu, pak ve vaší aplikaci pomocí komprese texture BC zobrazí podobné zvýšení výkonu.  
  
-   Pokud varianta 2xMSAA jako typ variant 0xMSAA téměř stejného výkonu, můžete povolit 2xMSAA ve vaší aplikaci zlepšit kvalitu vykreslování bez nákladů na výkon.  
  
 Další výsledky by mohla naznačovat hlubší, další menší dopadů na výkon vaší aplikace:  
  
-   Pokud varianta zobrazení 1 × 1 ukazuje velmi náročné na výkon, vaše aplikace pravděpodobně spotřebovává více fillrate, než je k dispozici. Pokud tato varianta zobrazuje žádné zvýšení výkonu, aplikace je pravděpodobně zpracování příliš mnoho vrcholy.  
  
-   Pokud varianta cílový formát vykreslení 16bpp zobrazuje výrazné zvýšení výkonu, vaše aplikace pravděpodobně využívala příliš velkou šířku pásma, paměti.  
  
-   Pokud varianta Half/Quarter Texture dimenze zobrazuje výrazné zvýšení výkonu, vaše textury pravděpodobně zabírají příliš mnoho paměti, využívat příliš velkou šířku pásma nebo neefektivnímu využití mezipaměti texture. Pokud se tato varianta zobrazovat žádná změna ve výkonu, pravděpodobně můžete větší, podrobného Další textury bez placení snížený výkon.  
  
 Pokud jsou k dispozici čítače hardwaru, můžete je používat ke shromažďování velmi podrobné informace o proč může mít problémy výkonu vykreslování vaší aplikace. Všechna zařízení 9.2 a vyšší úrovni funkcí podporu dotazů NF pásmová hloubku (**pixelů occluded** čítač) a časová razítka. Další čítače hardwaru může být k dispozici, v závislosti na tom, jestli má výrobce GPU implementována čítače hardwaru a je vystavený v jeho ovladače. Tyto čítače můžete použít k potvrzení přesné příčinu výsledky zobrazené v tabulce shrnutí – například můžete určit, jestli overdraw faktorem je to tak, že prověří procento pixelů, které byly occluded testem hloubka.  
  
### <a name="timeline-and-summary-table"></a>Časová osa a tabulku souhrnu  
 Ve výchozím nastavení časového harmonogramu a souhrnné tabulky se zobrazí a sbalené v dalších částech.  
  
#### <a name="timeline"></a>Časová osa  
 Časovou osu zobrazuje přehled volání kreslení časování relativně k jinému. Protože větší řádky odpovídají delší doby kreslení, můžete ji rychle vyhledat nejnákladnější volání kreslení v rámečku. Když zaznamenané rámečku obsahuje velký počet volání kreslení, kreslení více kreslení, které jsou volání zkombinované do jednoho panelu jehož délka je součtem těchto volání.  
  
 ![Časová osa ukazuje kreslení & č. 45; volání náklady. ] (media/pix_frame_analysis_timeline.png "pix_frame_analysis_timeline")  
  
 Na panelu zobrazíte která kreslení volání událost odpovídá panelu, přesuňte ukazatel. Výběr panelu způsobí, že seznam událostí na tuto událost synchronizovat.  
  
#### <a name="table"></a>Tabulka  
 V tabulce čísel níže časovou osu jsou relativní výkon jednotlivých vykreslování variant pro každé volání kreslení s ohledem na výchozí vykreslování vaší aplikace. Každý sloupec zobrazuje hodnotu typu variant různých vykreslování a každý řádek představuje různé kreslení volání identifikovanou v levém sloupci. Odsud můžete provést odkaz na událost v okně seznam událostí grafiky.  
  
 ![Tabulku souhrnu ukazuje různé varients. ] (media/pix_frame_analysis_summary.png "pix_frame_analysis_summary")  
  
 Druhý sloupec nejvíce vlevo v tabulce shrnutí zobrazí vaše aplikace základní vykreslování čas – to znamená, doba je potřebná pro vykreslování výchozí vaší aplikace k dokončení volání kreslení. Zbývající sloupce zobrazují relativní výkon jednotlivých vykreslování variant jako procento směrného plánu, aby bylo snazší zjistit, zda vyšší výkon. Procenta větší než 100 procent trvala déle než směrného plánu – tedy výkonu byl vypnut – a menší než 100 procent trvalo méně času procenta – zvýšil výkon.  
  
 Hodnoty absolutní načasování směrného plánu a relativní načasování vykreslování variant jsou ve skutečnosti střední průměry více spustí – 5 ve výchozím nastavení. Tato průměrování pomáhá zajistit dat časování spolehlivých a konzistentních. Umístěte ukazatel myši na jednotlivých buněk v tabulce prozkoumat minimální, maximální, střední a střední časování hodnoty, které byly zjištěnými při kreslení výsledky pro tento volání a vykreslování variant byly vygenerovány. Zobrazí se také načasování směrného plánu.  
  
#### <a name="hot-draw-calls"></a>"Horkých" kreslení volání  
 Aby pozornost k vykreslení volání, které využívají větší část z celkového času vykreslování nebo který může být neobvykle pomalé z důvodů, které by mohly být vyhnout, řádek, který obsahuje tyto "horkých" kreslení volání je šedou barvou red při vlastní časování směrného plánu je víc než jedna Směrodatná odchylka delší než střední načasování všechna volání kreslení v rámci směrného plánu.  
  
 ![Toto volání DrawIndexed má úrovněmi horkého a studeného varients. ] (media/pix_frame_analysis_hot_calls.png "pix_frame_analysis_hot_calls")  
  
#### <a name="statistical-significance"></a>Statistické násobek.  
 Aby pozornost vykreslování varianty, které mají nejvyšší relevance analýza snímků určuje statistické význam jednotlivých variant vykreslování a zobrazí významné ty jako tučné písmo. Zobrazuje ty, které zlepšit výkon zeleně a ty, které sníží výkon jako červený. Zobrazuje výsledky, které nejsou statisticky významný jako normální typu.  
  
 ![Statistické relevence varianty volání kreslení](media/pix_frame_analysis_summary_stats.png "pix_frame_analysis_summary_stats")  
  
 Pokud chcete zjistit statistické relevance, používá analýza snímků [Studentova t-test](http://www.wikipedia.org/wiki/Student%27s_t-test).  
  
### <a name="details-table"></a>Tabulka podrobností  
 Pod souhrnem tabulka je v tabulce Podrobnosti, který je standardně sbalená. Obsah v každé bude záviset na platformě hardwaru počítače přehrávání. Informace o podporovaných hardwarových platforem najdete v tématu [podporu hardwaru](#HardwareSupport).  
  
#### <a name="platforms-that-do-not-support-hardware-counters"></a>Platformy, které nepodporují čítače hardwaru  
 Většina platforem plně nepodporují čítače GPU hardwaru – mezi ně patří všechny grafickými procesory Intel, AMD a nVidia aktuálně nabízí. Pokud nejsou žádné čítače hardwaru shromažďovat, je zobrazena pouze jedna tabulka podrobnosti a obsahuje střední absolutní načasování všechny varianty.  
  
 ![Tabulka Podrobnosti a některé varients přehrávání. ] (media/pix_frame_analysis_details.png "pix_frame_analysis_details")  
  
#### <a name="platforms-that-support-hardware-counters"></a>Platformy, které podporují čítače hardwaru  
 Pro platformy, které podporují čítače GPU hardwaru – například nVidia T40 SOC a všechny SOCs Qualcomm – několik tabulky podrobností se zobrazují, jednu pro každý typ variant. Každý čítač dostupného hardwaru shromážděných pro každý typ variant vykreslování a zobrazit v tabulce vlastní podrobnosti.  
  
 ![Pokud je podporovaná, zobrazí se čítače hardwaru. ] (media/pix_frame.png "pix_frame")  
  
 Informace o hardwaru čítač poskytuje velmi podrobné zobrazení konkrétní hardware platformy chování pro každý kreslení volání, které vám pomůže určit příčinu kritické body velmi přesněji.  
  
> [!NOTE]
>  Jiný hardware platformy podporují různé čítače; neexistuje žádné standard. Čítače a co představují jsou určeny výhradně každého výrobce GPU.  
  
### <a name="marker-regions-and-events"></a>Značky oblasti a události  
 Analýza snímků podporuje uživatelem definované události značek a skupiny událostí. Jsou zobrazeny v souhrnné tabulka a tabulka podrobností.  
  
 Rozhraní API ID3DUserDefinedAnnotation nebo starší verze D3DPERF_ řadu rozhraní API slouží k vytvoření značky a skupiny. Pokud používáte rozhraní API D3DPERF_ rodiny, můžete přiřadit každé značky a skupiny barvu, která analýza snímků zobrazí jako barevnou vzdálené správy v rámci řádky, které obsahují značky události nebo značky zahájení a ukončení skupiny událostí a jejich obsah. Tuto funkci můžete rychle identifikovat důležité vykreslování události nebo skupin událostí.  
  
### <a name="warnings-and-errors"></a>Upozornění a chyb  
 Analýza snímků příležitostně dokončení s upozornění ani chyby, které jsou sumarizovány výše časovou osu a podrobné v dolní části kartu analýza snímků.  
  
 Obvykle upozornění a chyb jsou pouze pro informační účely a nevyžadují jakéhokoli zásahu.  
  
 Upozornění obvykle naznačují, že chybí některý podporu hardwaru, ale může být práce na incidentu kolem, nelze shromáždit čítače hardwaru, nebo nemusí být některé údaje o výkonu spolehlivé – například když řešení má negativní dopad na ho.  
  
 Chyby obvykle naznačují, že implementace rámce analýzy obsahuje chyby, ovladač obsahuje chyby, podporu hardware není splněn a nemůže být práce na incidentu kolem, nebo aplikaci pokusí něco, co nepodporuje přehrávání.  
  
### <a name="retries"></a>Opakování  
 Pokud GPU zde nevyskytlo přechod stavu napájení během analýza snímků, musí být opakována průchodu ovlivněných analysis, protože GPU clockspeed změnit a tím zrušena relativní časování výsledky.  
  
 Analýza snímků omezuje počet opakování do 10. Pokud vaši platformu řízení spotřeby agresivní nebo prostřednictvím brány hodiny, může způsobit analýza snímků služeb při selhání a zobrazovat chyby, protože se překročil limit opakování. Bude pravděpodobně možné zmírnění tohoto problému resetováním vaši platformu řízení spotřeby a taktovací omezování rychlosti být méně agresivní, pokud ji povolí platformu.  
  
##  <a name="HardwareSupport"></a>Podporu hardwaru  
  
### <a name="timestamps-and-occlusion-queries"></a>Časová razítka a NF pásmová dotazy  
 Časová razítka jsou podporovány ve všech platformách, které podporují analýza snímků. Hloubka NF pásmová dotazy – požadované pro čítač Occluded pixelů – jsou podporovány na platformách, které podporují funkce úrovní 9.2 nebo vyšší.  
  
> [!NOTE]
>  Ačkoliv je časová razítka na všech platformách, které podporují analýza snímků, přesnost a důslednost časová razítka na jednotlivých platformách liší.  
  
### <a name="gpu-counters"></a>Čítače GPU  
 Podpora pro čítače GPU hardwaru je závislé na hardwaru.  
  
 Vzhledem k tomu, že žádný počítač GPU aktuálně nabízená Intel, AMD nebo nVidia podporuje GPU hardwaru čítače spolehlivě, není analýza snímků shromažďování čítače z nich. Analýza snímků však shromažďování čítače hardwaru z následující grafický procesor, která je spolehlivě podporuje:  
  
-   nVidia T40 (Tegra4)
  
 Žádné jiné platforma, která podporuje analýza snímků shromažďuje GPU hardwaru čítače.  
  
> [!NOTE]
>  Protože GPU hardwaru čítače jsou hardwarové prostředky, může trvat několik předává shromážděte kompletní sadu čítače hardwaru pro každý typ vykreslování variant. V důsledku toho neurčené pořadí, ve které GPU se shromažďují čítače.  
  
## <a name="unsupported-scenarios"></a>Nepodporované scénáře  
 Některé z mnoha možností použití analýza snímků nejsou podporovány nebo jsou právě vhodné.  
  
### <a name="playback-of-high-feature-level-captures-on-down-level-devices"></a>Zaznamená přehrávání horní úrovni funkcí na zařízeních s nižší úrovně  
 V analyzátoru grafiky při přehrávání grafiky protokolového souboru, který používá vyšší úroveň funkce než počítače pro přehrávání podporuje, se automaticky vrátí k OSNOVĚ. V analýza snímků ji explicitně nepřecházely k OSNOVĚ a vygeneruje se chyba – je užitečné pro zkoumání správnost Direct3D – aplikace, ale ne pro zkoumání jeho výkon.  
  
> [!NOTE]
>  I když je důležité problémy úrovni funkcí mějte na paměti, můžete zachytit a přehrání, že grafiky soubory protokolu na různé konfigurace hardwaru a zařízení. Protokol grafiky můžete přehrát zpět, pokud není soubor protokolu obsahovat rozhraní API nebo použít funkci úrovně, které nejsou podporovány na počítače pro přehrávání.  
  
### <a name="direct3d-10-and-lower"></a>Direct3D – 10 a nižší  
 Pokud aplikace zavolá rozhraní API Direct3D – 10, nebude analýza snímků rozpoznat nebo je profil, i když jsou rozpoznána a používá další nástroje Analyzátor grafiky.
  
> [!NOTE]
>  To platí pouze pro rozhraní API Direct3D – volání, které používáte, není funkce úrovně.

### <a name="warp"></a>OSNOVA  
 Analýza snímků je určena pro použití profilu a zlepšíte výkon vykreslování na skutečné hardwaru. Analýza snímků systémem OSNOVĚ zařízení není zabránit, ale není obvykle smysl výkon protože systémem vyšší kategorie procesoru je nižší než i nejmenší podporující moderní grafickými procesory a protože OSNOVĚ výkonu může značně lišit v závislosti na konkrétní procesoru je spuštěn na.  
  
##  <a name="Variants"></a>Variant  
 Každé změně, která vytváří analýza snímků pro rámeček je vykreslen při přehrávání způsob je známý jako *variant*. Varianty, které hledá analýza snímků odpovídají na běžné, je poměrně snadné změny, které by mohly zvýšit ke zlepšení výkonu vykreslování nebo visual kvality aplikace – například zmenšení velikosti textury, pomocí textury komprese nebo povolení různé druhy vyhlazení. Variant přepsat obvyklé vykreslování kontextu a parametry vaší aplikace. Zde je souhrn:  
  
|Variant|Popis|  
|-------------|-----------------|  
|**Velikosti zobrazovacího okna 1 × 1**|Snižuje dimenze zobrazení na všechny cíle vykreslování do 1 x 1 pixel.<br /><br /> Další informace najdete v tématu [Variant velikost zobrazení 1 × 1](1x1-viewport-size-variant.md)|  
|**0x MSAA**|Zakáže více ukázku vyhlazení (MSAA) na všechny cíle vykreslení.<br /><br /> Další informace najdete v tématu [0 x / 2 x / 4 x MSAA variant](0x-2x-4x-msaa-variants.md)|  
|**2x MSAA**|Umožňuje 2 x více ukázku vyhlazení (MSAA) na všechny cíle vykreslení.<br /><br /> Další informace najdete v tématu [0 x / 2 x / 4 x MSAA variant](0x-2x-4x-msaa-variants.md)|  
|**4x MSAA**|Umožňuje 4 x více ukázku vyhlazení (MSAA) na všechny cíle vykreslení.<br /><br /> Další informace najdete v tématu [0 x / 2 x / 4 x MSAA variant](0x-2x-4x-msaa-variants.md)|  
|**Filtrování bodu textury**|Nastaví režim filtrování `DXD11_FILTER_MIN_MAG_MIP_POINT` (bodu texture filtrování) pro všechny příslušné texture vzorky.<br /><br /> Další informace najdete v tématu [bod, bilineární, Trilinear a volba Texture filtrování variant](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Filtrování bilineární textury**|Nastaví režim filtrování `DXD11_FILTER_MIN_MAG_LINEAR_MIP_POINT` (bilineární texture filtrování) pro všechny příslušné texture vzorky.<br /><br /> Další informace najdete v tématu [bod, bilineární, Trilinear a volba Texture filtrování variant](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Filtrování trilinear textury**|Nastaví režim filtrování `DXD11_FILTER_MIN_MAG_MIP_LINEAR` (trilinear texture filtrování) pro všechny příslušné texture vzorky.<br /><br /> Další informace najdete v tématu [bod, bilineární, Trilinear a volba Texture filtrování variant](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Volba Texture filtrování**|Nastaví režim filtrování `DXD11_FILTER_ANISOTROPIC` a `MaxAnisotropy` k `16` (16 x volba texture filtrování) pro všechny příslušné texture vzorky.<br /><br /> Další informace najdete v tématu [bod, bilineární, Trilinear a volba Texture filtrování variant](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Formát vykreslení cílového 16bpp**|Nastaví Pixelový formát `DXGI_FORMAT_B5G6R5_UNORM` (16bpp 565 formátu) pro všechny vykreslení cílů a backbuffers.<br /><br /> Další informace najdete v tématu [16bpp vykreslení cílový formát typu Variant](16bpp-render-target-format-variant.md)|  
|**Generování MIP mapy**|Umožňuje mapy mip na všechny textury, které nejsou vykreslení cíle.<br /><br /> Další informace najdete v tématu [Mip mapy generování Variant](mip-map-generation-variant.md).|  
|**Dimenze poloviční textury**|Snižuje dimenze texture na všechny textury, které nejsou vykreslení cíle polovinu jejich původní velikost v Každá dimenze. Například 256 × 128 texture sníží texels 128 x 64.<br /><br /> Další informace najdete v tématu [Half/Quarter Texture dimenze Variant](half-quarter-texture-dimensions-variant.md).|  
|**Dimenze čtvrtletí textury**|Snižuje dimenze texture na všechny textury, které nejsou vykreslení cíle čtvrtletí jejich původní velikost v Každá dimenze. Například 256 × 128 texture sníží texels 64 x 32.<br /><br /> Další informace najdete v tématu [Half/Quarter Texture dimenze Variant](half-quarter-texture-dimensions-variant.md).|  
|**Komprese BC textury**|Umožňuje blokovat kompresi na všechny textury, které mají B8G8R8X8, B8G8R8A8 nebo R8G8B8A8 variant formátu pixelů. Formát variant B8G8R8X8 jsou komprimována pomocí BC1; Pomocí BC3 jsou komprimované B8G8R8A8 a R8G8B8A8 formátu variant.<br /><br /> Další informace najdete v tématu [BC Texture komprese Variant](bc-texture-compression-variant.md).|  
  
 Výsledek pro většina variant je doporučený: "snížení velikosti texture o polovinu je 25 procent rychlejší" nebo "2 x MSAA je povolit pouze 2 procent něco pomalejší". Ostatní varianty může vyžadovat další výklad – například pokud variant, která změní zobrazení dimenzí 1 × 1 ukazuje velké výkonnější, může to znamenat, že vykreslování je omezené o míru nízkou výplně; případně pokud neexistuje žádné významné změny ve výkonu, může to znamenat, že vykreslování je omezené vrchol zpracování.