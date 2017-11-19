---
title: "Přehled diagnostiky grafiky sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/09/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddd429d9-ac70-4ac4-9e69-299c6ea2df09
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f713a1ced59ea1ed0eaf01a3d9630aa96e4c6bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="overview-of-visual-studio-graphics-diagnostics"></a>Přehled diagnostiky grafiky sady Visual Studio
Visual Studio *diagnostiky grafiky* je sada nástrojů pro záznam a pak analýza vykreslování a výkonu problémům v Direct3D – aplikace. Diagnostika grafiky lze použít na aplikace, které běží místně na počítači s Windows v emulátoru Windows zařízení nebo na vzdálený počítač nebo zařízení.  
  
## <a name="using-graphics-diagnostics-to-debug-rendering-problems"></a>Použití Diagnostiky grafiky k ladění problémů s vykreslováním  
 Ladění problémů s vykreslováním v aplikaci s bohatou grafikou není tak přímočaré jako spuštění ladicího programu a krokování kódu. V každém snímku jsou produkovány stovky tisíc jedinečných pixelů podle komplexní sady stavu, dat, parametrů a kódu. Z těchto pixelů může problém, který chcete diagnostikovat, vykazovat pouze několik málo pixelů. A aby věci byly ještě složitější, kód, který generuje každý pixel, je spouštěn na specializovaném hardwaru, který paralelně zpracovává stovky pixelů. Tradiční nástroje a techniky ladění, které je obtížné využít i v kódu s malým počtem vláken, jsou v případě velkého množství dat neúčinné.  
  
 Diagnostika grafiky nástroje v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jsou navržené tak, abychom vám pomohli najít vykreslování problémy od visual artefakty, který indikuje problém a pak trasování zpět na zdroj problému se zaměříte jenom na příslušné shaderu kód kanálu Kreslení fázích, volání, prostředky a stavu zařízení – ve zdrojovém kódu aplikace vlastní.  
  
## <a name="directx-version-compatibility"></a>Kompatibilita verzí DirectX  
 Diagnostika grafiky podporuje aplikace, které používají Direct3D – 10 nebo vyšší a poskytuje omezenou podporu pro aplikace, které používají Direct2D. Nepodporuje aplikace, které používají starší verze rozhraní Direct3D, DirectDraw nebo jiné grafické rozhraní API.  
  
### <a name="windows-10-and-direct3d-12"></a>Windows 10 a Direct3D – 12  
 Windows 10 zavedená *Direct3D – 12*, které se podstatně liší od Direct3D – 10 a Direct3D 11. Tyto rozdíly navrácení DirectX zarovnaný moderní grafiky hardwaru a unleashing plný výkon, ale také uvést big změny rozhraní API a umístěte větší odpovědnost na programátorů ke správě prostředků životnosti a kolizí. Bez ohledu rozdíly udržuje diagnostiky grafiky s Direct3D – 12 parity funkcí s diagnostikou grafiky s Direct3D – 11.2.
  
 Windows 10 se také zachová podporu pro předchozí verze Direct3D – a hry a aplikace, které závisí na ně. Diagnostika grafiky v sadě Visual Studio i nadále podporuje Direct3D – 10 a 11 Direct3D – ve Windows 10, a také na Windows 8.1.  
  
### <a name="windows-81-and-direct3d-112"></a>Windows 8.1 a Direct3D 11.2  
 V [!INCLUDE[win81](../includes/win81_md.md)], DirectX 11.2 zavádí nové funkce, které zahrnují podporu pro zaznamenání grafických informací prostřednictvím jeho runtime. [!INCLUDE[win81](../includes/win81_md.md)]používá nové zachytávání založených na prostředí runtime – označuje jako *robustní zachycení*– výhradně pro všechny verze rozhraní DirectX, [!INCLUDE[win81](../includes/win81_md.md)] podporuje. Robustní zachycení také podporuje nové funkce Direct3D – 11.2.  
  
### <a name="limited-direct2d-support"></a>Omezená podpora rozhraní Direct2D  
 Protože Direct2D uživatelského režimu rozhraní API, které je postavená na Direct3D, můžete diagnostiky grafiky pomáhají ladit vykreslování problémy s aplikací, které používají Direct2D. Protože jsou však zaznamenány pouze základní události rozhraní Direct3D namísto událostí rozhraní Direct2D na vyšší úrovni, události Direct2D se na seznamu událostí grafiky nezobrazí. A protože vztah mezi událostmi rozhraní Direct2D a výslednými událostmi rozhraní Direct3D není vždy jasný, použití Diagnostiky grafiky k ladění problémů s vykreslováním v aplikacích, které používají Direct2D, není vždy přímočaré. Nadále můžete Diagnostiku grafiky použít k získání informací o problémech s vykreslováním na nízké úrovni v aplikacích, které používají rozhraní Direct2D.  
  
## <a name="graphics-diagnostics-features-in-visual-studio"></a>Funkce diagnostiky grafiky sady Visual Studio  
 Diagnostika grafiky má vyhrazené rozhraní - okno analyzátor grafiky - pro diagnostiku problémů vykreslování, ale také přidá některé nástroje rozhraní sady Visual Studio.  
  
### <a name="the-graphics-toolbar-visual-studio"></a>Panel nástrojů grafiky (Visual Studio)  
 Panel nástrojů grafiky poskytuje rychlý přístup k příkazům diagnostiky grafiky.  
  
 **Spustit diagnostické nástroje** tlačítko aplikace v rámci diagnostiky grafiky spouští. Když aplikace běží v rámci diagnostiky grafiky **zaznamenat další vykreslené rámečku** tlačítko je k dispozici.  
  
### <a name="diagnostics-capture-interface"></a>Zachycení diagnostiky rozhraní  
 Při spuštění aplikace v rámci diagnostiky grafiky sady Visual Studio zobrazí rozhraní relace diagnostiky, můžete použít k zachycení snímků a také zobrazuje aktuální zatížení procesoru a GPU. Zatížení procesoru a GPU zobrazí se vám pomůže identifikovat rámce, který chcete zaznamenat z důvodu jejich výkonové charakteristiky, nikoli chyb při vykreslování.  
  
 Tato akce není jediný způsob, jak ale zachycení snímků. Rámce můžete zachytit pomocí rozhraní zachytávání prostřednictvím kódu programu, nebo pomocí příkazového řádku zachycení programu dxcap.exe.  
  
 V tématu [zaznamenání grafických informací](capturing-graphics-information.md) Další informace.  
  
### <a name="gpu-usage"></a>Využití GPU  
 Diagnostika grafiky můžete také profil výkon aplikace Direct3D –. Protože profilace dat by být asymetrické zaznamenávání podrobností událostí grafiky, to je oddělená od zaznamenání rámce, který se má použít se Graphics Analyzeru.  
  
 V tématu [využití GPU](gpu-usage.md) Další informace.  
  
### <a name="directx-control-panel"></a>Ovládací panel rozhraní DirectX  
 Ovládací panel rozhraní DirectX je součástí rozhraní DirectX, které můžete použít ke změně způsobu, jakým se rozhraní DirectX chová – například povolit verzi ladění runtime komponent rozhraní DirectX a výběr druhu zpráv ladění, které jsou zaznamenány, a zakázat použití určitých funkcí hardwaru grafiky k emulaci hardwaru s méně funkcemi. Tato úroveň kontroly nad rozhraním DirectX vám může pomoct ladit a testovat vaši aplikaci DirectX. Ovládací panel rozhraní DirectX zobrazíte ze sady Visual Studio.  
  
#### <a name="to-open-the-directx-control-panel"></a>Otevření ovládacího panelu rozhraní DirectX  
  
-   Na řádku nabídek zvolte **ladění**, **grafiky**, **DirectX ovládací panely**.  
  
## <a name="graphics-analyzer"></a>Analyzátor grafiky  
 Visual Studio Graphics Analyzer je rozhraní, které je vyhrazený pro zkoumání problémů vykreslování a výkonu v snímků, které jste již zaznamenat. Uvnitř analyzátor grafiky najdete několik nástrojů, které vám pomohou prozkoumat a pochopit vykreslování chování vaší aplikace. Každý nástroj zpřístupní jiný druh informací o rámce, který je ke kontrole a nástroje jsou určeny k použití ve vzájemné součinnosti k intuitivně úzké in na zdroj problému vykreslování, od jeho zobrazení framebuffer.  
  
 Tento obrázek ukazuje typické rozložení nástrojů v Graphics Analyzeru.  
  
 ![Všechny grafiky ladicího programu windows](media/graphicsdebuggerwindows.png "GraphicsDebuggerWindows")  
  
### <a name="the-graphics-toolbar-graphics-analyzer"></a>Panel nástrojů grafiky (Analyzátor grafiky)  
 Panel nástrojů grafiky poskytuje rychlý přístup k systému windows nástroj Analyzátor grafiky.  
  
 ![Panel nástrojů grafiky v režimu diagnostiky grafiky](media/vsg_toolbar.png "vsg_toolbar")  
  
### <a name="graphics-log-document"></a>Dokument grafických protokolů  
 Dokument grafických protokolů uvnitř analyzátor grafiky je nejvýraznější okno nástroje. Toto okno představuje všechny snímky, které můžete zaznamenat spuštěním aplikace v rámci diagnostiky grafiky. Tady můžete vybrat jiné rámce ověření nebo vyberte konkrétní pixelů, který chcete prozkoumat pomocí nástroje historie pixelů. Obrázek framebuffer zobrazí v tomto dokumentu tak, aby odrážela aktuálně vybrané události, aby mohli zobrazit, jak má vliv framebuffer v čase.  
  
 [Dokument grafických protokolů](graphics-log-document.md) je také vstupní bod, který nástroj Analýza snímků, který vám pomůže pochopit výkon rámeček mění způsob jsou nakonfigurované konkrétních aspektů vykreslování a poskytnutím výsledky srovnávacího testu porovnání s původní.  
  
### <a name="event-list"></a>Seznam událostí  
 Grafické události označit každé volání rozhraní API Direct3D – a uživatelem definované události.  
  
 [Seznam událostí](graphics-event-list.md) zobrazí všechny grafiky události, které byly zaznamenané během jste zkoumání rámečku. A pomůže vám zjistit, co je důležité, lze hierarchicky zobrazit seznam událostí – s poslední změny stavu pod následné kreslení volání – nebo jako časové osy. Kromě toho události jsou rozlišené barevně podle fronty, ke které patří, a můžete filtrovat, aby obsahoval pouze událostem, které vás zajímají.  
  
 Když vyberete událost v seznamu, zbytek analýza grafických nástrojů odrážet stav rámce v době této události. Tímto způsobem uvidíte na GPU účinku žádné události. Například se zobrazí okamžitý účinek žádné kreslení volání na framebuffer, i když se stane po volání následné kreslení skryt. Některé události také obsahují hypertextové odkazy postupovat, chcete-li zobrazit další podrobnosti o jeho parametry nebo objekty související prostředek.  
  
### <a name="pipeline-stages"></a>Fáze zřetězení  
 Každé volání kreslení ve vaší aplikaci projde kanálu grafiky poskytované Direct3D. V každé fázi v kanálu výstup z předchozí fáze transformovat malé programem, názvem shaderu a následně předán do další fáze, dokud je nakonec vykreslen na obrazovku. V hranici mezi fázemi kanálu při výstupní formát je jiný než očekává další fáze, nebo když jakékoli jeden fázi jednoduše vytvoří nesprávné výsledky dojít k chybám mnoho vykreslování. Za normálních okolností pouze získání konečných výsledků se zobrazí na vaší obrazovce a nelze snadno zjistit, kde v kanálu došlo k chybě.  
  
 [Fázemi kanálu](graphics-pipeline-stages.md) okno vizualizuje výsledek každé fáze nezávisle, takže můžete snadněji určit, které fázi vykreslování problém se nejprve zobrazí v. Jakmile jste zjistili, která Příprava to znamená, můžete spustit ladění jeho shaderu přímo z okna fázemi kanálu.  
  
### <a name="graphics-state"></a>Stav grafiky  
 Vykreslování operace závisí na velké množství stavu, který je obvykle rozloženy více objektů. Různé druhy vykreslování problémy jsou způsobeny nesprávně nakonfigurované stavu.  
  
 [Stavu](graphics-state.md) okno shromažďuje informace o stavu, která je relevantní pro každý kreslení volání společně na jednom místě, aby je snazší najít, a také označuje změny stavu, které došlo od předchozího kreslení volání.  
  
### <a name="pixel-history"></a>Historie pixelu  
 V komplexní scény není u pixelů, chcete-li být stínování více než jednou. jeden snímek neobvyklé. Někdy barvu starší je právě přepsána, ale jiné časy se zkombinují barvy společně k dosažení efekty jako průhlednost. Pokud výsledkem kombinace je společně není pravé vzhled nelze zjistit snadno Pokud je to způsobeno jedním z barvy byl nesprávný, nebo pokud došlo k potížím se způsobem byly kombinaci. Jinou dobu objekt může vypadat jako chybět, protože jeho příspěvku o bod byl odmítnut z nějakého důvodu.  
  
 [Historie pixelu](graphics-pixel-history.md) okno vizualizuje dokončení shaderu historii každý pixel v rámečku, včetně odmítnutých příspěvky. Pro příspěvky, které nebyly odmítnuty zobrazuje výsledky nezpracovaná shaderu a jak se každý nový barva kombinovat s předchozí. Pomocí těchto informací je mnohem snazší najít zdroj chyby v pixelech, přizpůsobte shaderu výsledky, nebo když chybí objekt vykreslené protože nesprávně odmítl jeho příspěvku pixel.  
  
### <a name="event-call-stack"></a>Zásobník volání událostí  
 Kód shaderu není jediný zdroj vykreslování problémů v aplikaci Direct3D, někdy zdrojového kódu vaší aplikace předá nesprávný parametr nebo neprovede konfiguraci Direct3D tak. Jeden typ chyby, která dříve popsaných funkce historie pixelů, můžete najít je při vykreslené objekt nebyl nalezen, protože byly odmítnuty všechny jeho pixelů. Tento druh chyby obvykle se stane, když je špatně nakonfigurovaný. nastavení, například ten, který řídí, jak se provádí test hloubky a obvykle lze najít váš chybu někde v zásobníku volání chybějící objektu kreslení volání.  
  
 [Zásobník volání událostí](graphics-event-call-stack.md) zásobníku volání dokončení každé události grafiky okně se zobrazí v seznamu těchto událostí a i umožňuje přejít do vaší aplikace zdrojový kód, pokud ladicí informace je k dispozici. Toto je výkonný nástroj pro následující chybu ze kterých se nejprve zobrazí, na GPU zpět na místo původu ve zdrojovém kódu vaší aplikace.  
  
### <a name="object-table"></a>Tabulce objektů.  
 Každý snímek vykreslí vaše aplikace je pravděpodobně zajištěna stovky nebo dokonce tisíce objektů prostředků. Tyto zahrnout back vyrovnávací paměti a vykreslit cíle, textury, vrchol vyrovnávací paměť, vyrovnávací paměti index, obecné vyrovnávací paměti – téměř všechno pamatuje Direct3D – je objektem.  
  
 [Tabulce objektů](graphics-object-table.md) zobrazí všechny objekty, které existují v době událostí grafiky vybrali v seznamu událostí. Vzhledem k tomu, že většinu objektů v typické aplikaci jsou textury, seznamu těchto událostí je optimalizovaná tak, aby zobrazit podrobnosti relevantní pro bitové kopie na první pohled. Sloupce typu zjistíte, jaký druh objektu v každém řádku a další sloupec formátu zobrazí dílčí typ nebo verze objektu. Další podrobnosti jsou také uvedené. Některé objekty mají také hypertextové odkazy, můžete postupovat podle zobrazíte objekt s více specializované prohlížeč, jako je například textury (můžete zobrazit texture jako obrázek) nebo vyrovnávací paměti (můžete zvolit, jak v prohlížeči vyrovnávací paměti analyzuje a zobrazuje počet bajtů nezpracovaná vyrovnávací paměti definováním vyrovnávací paměti Formát).  
  
### <a name="frame-analysis"></a>Analýza snímků  
 Grafika vaše aplikace právě nemusí být správný – je potřeba je příliš rychlé. Dokonce i v méně výkonná zařízení, jako jsou přenosné počítače s integrovanou grafikou nebo mobilních telefonů. A stále potřebují vypadat příliš velký.  
  
 [Analýza snímků](graphics-frame-analysis.md) nástroj prozkoumá potenciální optimalizací výkonu automaticky mění způsob aplikace používá Direct3D – a poskytnutím výsledků srovnávacího testu pro porovnání. Analýza snímků můžete například povolit mip mapování na každý texture, což může odhalit textury, které může využívat mip mapování, ale aktuálně nemáte, povolené. Na hardwaru, která ho podporuje, analýza snímků také uvede informace shromážděné z čítače výkonu na grafický procesor – tato úroveň informací můžete identifikovat problémy s výkonem úrovni hardwaru, jako je vysoký počet míst načítání texture nebo Neúspěšné přístupy do mezipaměti.  
  
 Ale analýza snímků není jenom o přejdete rychlého – jde o získání většina výkonu můžete při zkoušet minimem kvality. Někdy je nákladné efekt vypadá skvělé na velké zobrazení neznamená, že dopad na stejné při prohlížení na malou obrazovku telefonu, kde jednodušší vliv může vypadat stejně dobrým bez vyprazdňování baterie. Automatické změny a výsledkům srovnávacích testů, které poskytuje analýza grafických vám může pomoct najít rovnováhu mezi, které je nejvhodnější pro vaši aplikaci napříč celou řadu zařízení.  
  
## <a name="see-also"></a>Viz také  
 [Nástroj příkazového řádku zachycení](command-line-capture-tool.md)   
 [Ladicí program HLSL](hlsl-shader-debugger.md)