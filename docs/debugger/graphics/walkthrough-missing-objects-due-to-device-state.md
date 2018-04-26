---
title: 'Návod: Chybějící objekty z důvodu stavu zařízení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 1b0d2bbd-0729-4aa5-8308-70c5bf1468c5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 295177c6ea34923668b4751ac2c9f5e0fcf9aeb9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="walkthrough-missing-objects-due-to-device-state"></a>Návod: Chybějící objekty z důvodu stavu zařízení
Tento návod ukazuje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky k prozkoumání objekt, který je z důvodu chybějící špatně nakonfigurovaný. stav zařízení.  
  
 Tento návod ukazuje, jak:  
  
-   Použití **seznam událostí grafiky** najít potenciální zdroje problému.  
  
-   Použití **fáze zřetězení grafiky** okna zkontrolovat dopad `DrawIndexed` volání Direct3D – rozhraní API.  
  
-   Použití **historie pixelů grafiky** okno konkrétně vyhledat potíže.  
  
-   Kontrola stavu zařízení pro potenciální problémy nebo nesprávné konfigurace.  
  
## <a name="scenario"></a>Scénář  
 Jedním z důvodů, se nemusí zobrazit objekty, kde se očekává v 3D aplikaci je chybné konfigurace grafiky zařízení, které způsobí, že objekty, které chcete vyloučit z vykreslování – například když vinutí pořadí způsobí trojúhelníčky k být vyřazeny v chybě , nebo když funkci test hloubka způsobí všechny pixelů objekt, který má být odmítnuta.  
  
 Ve scénáři, který je popsaný v tomto návodu právě dosáhli první milník 3D aplikace pro vývoj a funkčnost poprvé. Však při spuštění aplikace je vykreslen pouze uživatelské rozhraní k obrazovce. Pomocí diagnostiky grafiky zaznamenáte tyto potíže k souboru protokolu grafiky tak, že ladíte aplikaci. Problém je v aplikaci vypadat třeba takto:  
  
 ![Aplikace předtím, než bude problém vyřešen](media/vsg_walkthru1_firstview.png "vsg_walkthru1_firstview")  
  
 Informace o tom, jak zachytit grafiky problémy v protokolu grafiky najdete v tématu [zaznamenání grafických informací](capturing-graphics-information.md).  
  
## <a name="investigation"></a>Šetření  
 Soubor protokolu grafiky kontrola rámce zaznamenané během testu můžete načíst pomocí diagnostiky grafiky nástrojů.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>K prozkoumání rámce v protokolu grafiky  
  
1.  V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst grafiky protokol, který obsahuje rámce, který vykazuje chybějící modelu. Na nové záložce diagnostiky grafiky se zobrazí v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. V horní části na této kartě je výstup cíl vykreslení vybraného rámce. V dolní části je **rámce seznamu**, zobrazuje každou zaznamenané rámce jako miniatury.  
  
2.  V **rámce seznamu**, vyberte snímek, který ukazuje, že se nezobrazí modelu. Cíl vykreslení je aktualizována tak, aby odrážela vybraný snímek. V tomto scénáři protokolu grafiky karta vypadá takto:  
  
     ![.Vsglog karta framebuffer preview a rámce seznamu](media/vsg_walkthru1_experiment.png "vsg_walkthru1_experiment")  
  
 Po výběru rámce, který ukazuje problém, můžete použít **seznam událostí grafiky** při diagnostice ho. **Seznam událostí grafiky** obsahuje každou Direct3D – volání rozhraní API, došlo k vykreslení active rámečku, například volání rozhraní API k nastavení stavu zařízení, abyste mohli vytvářet a aktualizovat vyrovnávací paměti a k vykreslení objekty, které se zobrazují v rámečku. Různé druhy volání je zajímavé, protože není často (ale ne vždy) odpovídající změnu cíl vykreslení, když aplikace funguje podle očekávání, například kreslení, odesílání, kopírování nebo zrušte volání. Kreslení volání jsou zvláště zajímavé, protože každé z nich představuje geometry, který vykreslí aplikace (volání odesílání může také zpracovat geometrie).  
  
#### <a name="to-ensure-that-draw-calls-are-being-made"></a>Zajistit, že kreslení jsou určené volání  
  
1.  Otevřete **seznam událostí grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **seznam událostí**.  
  
2.  Zkontrolujte **seznam událostí grafiky** pro kreslení volání. Chcete-li usnadnit tuto činnost, zadejte "Kreslení" v **vyhledávání** pole v pravém horním rohu **seznam událostí grafiky** okno. Tento filtrování seznamu tak, aby obsahoval jenom události, které mají "Kreslení" v jejich názvy. V tomto scénáři zjistíte, že byly provedeny několik kreslení volání:  
  
     ![Seznam událostí grafiky zobrazující zaznamenané události](media/vsg_walkthru1_.png "vsg_walkthru1_")  
  
 Jakmile potvrdíte, že kreslení, které jsou určené volání, můžete určit, které z nich odpovídá chybějící geometrie. Protože jste si jisti, že chybí geometrie není přitahuje k cíli vykreslení (v tomto případě), můžete použít **fáze zřetězení grafiky** okno k určení, které kreslení volání odpovídá chybějící geometrie. **Fáze zřetězení grafiky** v okně se zobrazí geometry, který vám byl zaslán každé volání kreslení, bez ohledu na jeho dopad na cíl vykreslení. Při přesouvání prostřednictvím volání kreslení je fázemi kanálu se aktualizují zobrazíte geometry, který je přidružen toto volání a vykreslování cílový výstup se aktualizuje na Zobrazit stav cíl vykreslení po dokončení volání.  
  
#### <a name="to-find-the-draw-call-for-the-missing-geometry"></a>Najít kreslení volání pro chybějící geometrie  
  
1.  Otevřete **fáze zřetězení grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **fázemi kanálu**.  
  
2.  Pohyb v každém kreslení volání při sledování **fáze zřetězení grafiky** okna pro chybějící modelu. **Vstup assembleru** fáze zobrazuje data nezpracovaná modelu. **Vrchol shaderu** fáze zobrazuje data transformovaných modelu. **Pixelů shaderu** fáze se zobrazuje výstup shaderu pixelů. **Výstup fúze** fáze ukazuje sloučené vykreslení cíl toto volání kreslení a všech předchozích volání kreslení.  
  
3.  Zastavte při dosáhli kreslení volání, která odpovídá chybí model. V tomto scénáři **fáze zřetězení grafiky** okno znamená, že byl vykreslen geometrie, ale nezobrazilo v cílové vykreslení:  
  
     ![Kanál prohlížeč zobrazující chybějícím objektu](media/vsg_walkthru1_pipeline.png "vsg_walkthru1_pipeline")  
  
 Jakmile potvrdíte, že aplikace se vykresluje chybějící geometrie a vyhledejte odpovídající volání kreslení, můžete vybrat část vykreslování cílový výstup, který by měl zobrazit chybějící geometry a potom pomocí **historie pixelů grafiky** okno a zjistěte, proč vyloučené pixelů. Historie pixelu obsahuje seznam každé kreslení volání, která by mohla obsahovat vliv na konkrétní pixelů. Každý kreslení volání v **historie pixelů grafiky** okno je identifikována číslo, které se zobrazí také v **seznam událostí grafiky** okno. Díky tomu můžete potvrdit, že pixel zobrazí chybějící geometry a chcete zjistit, proč se vyloučila pixelech  
  
#### <a name="to-determine-why-the-pixel-was-excluded"></a>Chcete-li zjistit, proč se vyloučila pixelech  
  
1.  Otevřete **historie pixelů grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **historie pixelu**.  
  
2.  Na základě **pixelů shaderu** miniaturu, vyberte pixelů v framebuffer výstup by měl obsahovat část chybí geometrického útvaru. V tomto scénáři by mělo zahrnovat výstup shaderu pixelů většinu cíl vykreslení; Po výběru jeden bod se **historie pixelů grafiky** okno vypadá takto:  
  
     ![Okno historie pixelu zobrazující související kreslení volání](media/vsg_walkthru1_hist1.png "vsg_walkthru1_hist1")  
  
3.  Zkontrolujte, jestli pixelů cíl vybraný vykreslování obsahuje část geometrického útvaru. pomocí odpovídající počet volání kreslení, že zkontrolujete (z **seznam událostí grafiky** okno) na jedno z volání kreslení v **grafiky Historie pixelu** okno. Pokud není k dispozici volání v **historie pixelů grafiky** okno shodu kreslení volání, že probíhá kontrola, opakujte tyto kroky (s výjimkou kroku 1) dokud nalezena shoda. V tomto scénáři odpovídající volání kreslení vypadat třeba takto:  
  
     ![Zobrazuje informace o fragment okno historie pixelu](media/vsg_walkthru1_hist2.png "vsg_walkthru1_hist2")  
  
4.  Po nalezení shody, rozbalte položku odpovídající volání kreslení v **historie pixelů grafiky** okno a potvrďte, že pixelu vyloučil. Každý kreslení volání v **historie pixelů grafiky** okno odpovídá jeden nebo více geometrickou primitiv (body, čáry nebo trojúhelníky) které prolínají této pixel výsledkem geometrie odpovídající objekt. Každé takové průnik může přispět k posledním barvu pixelech. Primitivní, která je vyloučená, protože došlo k jeho selhání testu hloubka je reprezentována ikonu, která znázorňuje písmeno Z průběhu šipka dolů svažuje zleva doprava.  
  
5.  Rozbalte položku vyloučené primitivní a další kontrolu stavu, který způsobuje její neočekávané mají být vyloučeny. V **výstup fúze** skupině, přesuňte ukazatel myši **výsledek**. Popisek označuje, proč se vyloučila primitivní vlastnost. V tomto scénáři ukáže průzkum, že primitivní se vyloučilo, protože se nezdařilo hloubka test a proto není přispívání do konečné barvu pixelech.  
  
 Když zjistíte, že geometrie se nezobrazí, protože jeho primitivních elementů se nezdařily hloubka test, může předpokládat, že tento problém souvisí s stav konfigurace zařízení. Stav zařízení a jiných Direct3D – objekt dat může být prověřen pomocí **tabulka grafických objektů**.  
  
#### <a name="to-examine-device-state"></a>Pro zjištění stavu zařízení  
  
1.  Otevřete **tabulka grafických objektů** okno. Na **diagnostiky grafiky** nástrojů vyberte **tabulce objektů.**.  
  
2.  Vyhledejte **D3D10 zařízení** objekt v **tabulka grafických objektů**a pak otevřete **D3D10 zařízení** objektu. Nový **d3d10 zařízení** kartě se otevře v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Chcete-li usnadnit tuto činnost, můžete seřadit **tabulka grafických objektů** podle **typ**:  
  
     ![Tabulka grafických objektů a stavu související zařízení](media/vsg_walkthru1_objtable.png "vsg_walkthru1_objtable")  
  
3.  Zkontrolujte stav zařízení, která se zobrazí v **d3d10 zařízení** kartu pro potenciální problémy. Protože geometrie se nezobrazí, protože jeho primitivních elementů se nezdařily hloubka test, můžete se zaměřit na stavu zařízení, například vzorník hloubku, který ovlivňuje hloubka test. V tomto scénáři **hloubka vzorníku popis** (v části **výstup stavu fúze**) obsahuje neobvyklé hodnotu pro **hloubka funkce** člena, `D3D10_COMPARISON_GREATER`:  
  
     ![Okno zařízení D3D10 zobrazující hloubka vzorníku informace](media/vsg_walkthru1_devicestate.png "vsg_walkthru1_devicestate")  
  
 Když zjistíte, že může být příčinou problému vykreslování nesprávně nakonfigurované hloubka funkce, můžete tyto informace slouží společně s vašich znalostí kód zjistit, kde funkci hloubka byla nastavena nesprávně a pak problém opravte. Pokud jste obeznámeni s kódem, můžete pro problém vyhledat pomocí různá vodítka, které jste shromáždili během byly ladění – například na základě **hloubka vzorníku popis** v tomto scénáři můžete vyhledat kód pro slova jako "Hloubka" nebo "GREATER". Po opravě kód ho znovu sestavte a spusťte aplikaci znovu a zjistit, že se vyřešit problém vykreslování:  
  
 ![Aplikaci po opravení problému](media/vsg_walkthru1_finalview.png "vsg_walkthru1_finalview")