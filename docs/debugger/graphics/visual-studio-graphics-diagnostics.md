---
title: Diagnostika grafiky sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: fa69c550-62a7-41b5-bb1f-7eb04af1a6e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1974480a2abefaaa38c05f4b1e4588eaddfd480e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-graphics-diagnostics"></a>Diagnostika grafiky sady Visual Studio
Visual Studio*diagnostiky grafiky* je sada nástrojů pro záznam a pak analýza vykreslování a výkonu problémům v Direct3D – aplikace. Diagnostika grafiky lze použít na aplikace, které běží místně na počítači s Windows v emulátoru Windows zařízení nebo na vzdálený počítač nebo zařízení.  
  
 Pracovní postup diagnostiky grafiky začíná zachytáváním záznamy o tom, jak vaše aplikace používá Direct3D – live, při jeho spuštění – tak, že její chování lze okamžitě analyzovat, sdílet nebo uložit pro pozdější. Zaznamenání relace lze inicializovat a řídit ručně ze sady Visual Studio nebo pomocí nástroje příkazového řádku zachycení **dxcap.exe**. Zaznamenání relace lze také zahájit a řídit programově pomocí zachycení diagnostiky grafiky rozhraní API.  
  
 Po zachycení relace byl zaznamenán jeho obsah je možné přehrát Visual Studio *analyzátor grafiky* kdykoli znovu vytvořit zaznamenané rámce pomocí přesně stejné prostředky a vykreslování příkazy aplikace použít. Potom pomocí nástrojů v okně Analyer grafiky, všechny zaznamenané snímků mohou být analyzovány podrobně. Tyto nástroje můžete použít k prozkoumání všech volání rozhraní API Direct3D –, prostředku, objekt kanálu stavu, fáze kanálu nebo i úplnou historii všech pixelů zaznamenané rámce. Pomocí těchto nástrojů ve vzájemné součinnosti vykreslování problém může být zkoumána intuitivně, od, jak se zobrazuje v zaznamenané rámečkem a přecházení na jeho hlavní příčinou aplikace zdrojového kódu, shadery nebo grafické prostředky.  
  
 Při diagnostice potíží s výkonem, zaznamenané rámce lze analyzovat pomocí *analýza snímků* nástroj. Tento nástroj prozkoumá potenciální optimalizací výkonu automaticky mění způsob aplikace používá Direct3D – a srovnávací testy všechny varianty za vás. V minulosti, jste zadali a ručně právě benchmarked změny tohoto typu najít se na ty, které provedené rozdíl. Rámce analýzy stačí provést změny, které už znáte, se vyplatí.  
  
 Diagnostika grafiky pomáhá aplikace graficky bohaté Direct3D – vzhled a spustit je nejlepší.  
  
 Nadále [přehled](overview-of-visual-studio-graphics-diagnostics.md) Další informace o co nabízí diagnostiky grafiky Visual Studio.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled](overview-of-visual-studio-graphics-diagnostics.md)  
 Představuje pracovního postupu diagnostiky grafiky a nástroje.  
  
 [Začínáme](getting-started-with-visual-studio-graphics-diagnostics.md)  
 V této části se dozvíte, jak nainstalovat diagnostiky grafiky Visual Studio a jak začít používat diagnostiky grafiky s vaší aplikací Direct3D –.  
  
 [Zaznamenání grafických informací](capturing-graphics-information.md)  
 Použití diagnostiky grafiky k prozkoumání vykreslování problém v aplikaci, byste nejprve zaznamenat informace o tom, jak aplikace používá rozhraní DirectX. Během relace záznam jako vaše aplikace běží za normálních okolností je *zaznamenat* (to znamená, vyberte) rámců, které vás zajímají. Zachytávání obsahují podrobné informace o způsobu vykreslení snímky. Součástí zaznamenaných informací můžete uložit jako grafiky protokolu dokumentu zkontrolujte později nebo sdílet s ostatními členy týmu.  
  
 [Využití GPU](gpu-usage.md)  
 Chcete-li použít diagnostiky grafiky k profilu aplikace, použijte nástroj využití GPU. Využití GPU ve vzájemné součinnosti pomocí jiných profilování nástrojů, jako je například využití procesoru, lze použít ke korelaci procesoru a GPU aktivity, která může přispět k problémům s výkonem v aplikaci.  
  
 [Dokument grafických protokolů](graphics-log-document.md)  
 Pokud chcete spustit zkoumání protokolu zaznamenaná grafiky, použijete pro výběr zaznamenané rámce okna dokumentu protokolu grafiky – nebo dokonce konkrétní pixelů – tak, aby můžete zkontrolovat podrobně *události* (to znamená DirectX volání rozhraní API), vliv na jeho .  
  
 [Analýza snímků](graphics-frame-analysis.md)  
 Po výběru rámečku, použijete analýza grafických snímků sloužící ke zkoumání a vyladit výkon vykreslování.  
  
 [Seznam událostí](graphics-event-list.md)  
 Když vyberete snímek, můžete použít **seznam událostí grafiky** a zkontrolujte jeho události, abyste zjistili, zda se jedná o problém vykreslování.  
  
 [Stav](graphics-state.md)  
 Okno Stav vám pomůže pochopit stav grafiky, která je aktivní v okamžiku aktuální událost.  
  
 [Fáze zřetězení](graphics-pipeline-stages.md)  
 V **fáze zřetězení grafiky** okně byste prozkoumat, jak aktuálně vybrané události zpracovává každá fáze v kanálu grafiky, aby mohli identifikovat, kde se nejprve zobrazí vykreslování problém. Zkoumání fázemi kanálu je zvláště užitečné, pokud objekt nezobrazí z důvodu nesprávné transformace, nebo pokud jeden z fází vytváří výstupu, který neodpovídá, jaké další fáze očekává.  
  
 [Zásobník volání událostí](graphics-event-call-stack.md)  
 Můžete použít **zásobník volání událostí grafiky** si prohlédnout zásobníku volání aktuálně vybrané události, můžete přejít na kód aplikace, který má vztah k vykreslování problém.  
  
 [Historie pixelu](graphics-pixel-history.md)  
 Pomocí **historie pixelů grafiky** okno analyzovat, jak je aktuálně vybrané pixelů ovlivňován události, které vliv, můžete identifikovat události nebo kombinaci událostí, které způsobí určité druhy problémů vykreslování. Historie pixelu je zvláště užitečné, pokud objekt je nesprávně vykreslit, protože výstup shaderu pixelů je buď nesprávný nebo zkombinovaná nesprávně s rámečkem vyrovnávací paměti, nebo když objekt nezobrazí i vzhledem k tomu, že byly vyřazeny jeho pixelů než dosáhnou vyrovnávací paměť snímku.  
  
 [Tabulka objektů](graphics-object-table.md)  
 Můžete použít **tabulka grafických objektů** prozkoumat vlastnosti a obsah objektů konkrétní Direct3D – a prostředky, které jsou platné pro aktuálně vybrané události. Objekt tabulky můžete určit kontextu zařízení grafiky, která je aktivní během události a zkontrolujte obsah grafických prostředků, jako jsou konstantní vyrovnávacích pamětí, vrchol vyrovnávací paměti a textury.  
  
 [Ladicí program HLSL](hlsl-shader-debugger.md)  
 Pro zjištění, jak kód shaderu pro aktuálně vybrané události a grafika kanálu fáze chová, můžete použít **ladicí program HLSL** ke krokování kódu, zkontrolujte obsah proměnných a provádět další typické úlohy ladění. Ladicí program HLSL můžete taky kontrola výpočetního shaderu kódu, bez ohledu na to, jestli výsledky se dále zpracovávat v kanálu grafiky nebo jen pro čtení zpět vaší aplikace.  
  
 [Nástroj příkazového řádku pro zachytávání](command-line-capture-tool.md)  
 Pomocí nástroje příkazového řádku zachycení rychle zachycení a přehrání grafických informací bez použití sady Visual Studio nebo zachytávání prostřednictvím kódu programu. Nástroj příkazového řádku zachycení, můžete pro automatizaci nebo v testovacím prostředí.  
  
 [Příklady](graphics-diagnostics-examples.md)  
 Několik příkladů ukazují, jak pomocí nástroje diagnostiky grafiky společně diagnostikovat různé druhy vykreslování problémy.  
  
## <a name="related-sections"></a>Související oddíly  
  
|Název|Popis|  
|-----------|-----------------|  
|[Prohlídka funkce ladicí program](../debugging-in-visual-studio.md)|Zavádí ladění funkce v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|  
|[Grafiky DirectX a herní](http://go.microsoft.com/fwlink/?LinkId=256498)|Obsahuje články, které popisují technologie grafiky DirectX.|