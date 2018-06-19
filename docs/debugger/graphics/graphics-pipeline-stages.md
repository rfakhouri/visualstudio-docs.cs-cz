---
title: Grafika kanálu fázích | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.pipeline
ms.assetid: 2bf5c12e-2a00-401c-8163-4e373d08ad3f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c708320442c32158ef193ccf7f08669882135d82
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481298"
---
# <a name="graphics-pipeline-stages"></a>Fáze zřetězení grafiky
Fáze zřetězení grafiky okna pomáhá pochopit, jak je každá fáze kanálu grafiky Direct3D – transformovat volání na jednotlivé kreslení.  
  
 Toto je okno fázemi kanálu:  
  
 ![Objekt 3D projde fázemi kanálu.](media/gfx_diag_demo_pipeline_stages_orientation.png)
  
## <a name="understanding-the-graphics-pipeline-stages-window"></a>Principy okno fáze zřetězení grafiky  
 Okno fázemi kanálu vizualizuje výsledek každé fáze kanálu grafiky samostatně, pro každý kreslení volání. Za normálních okolností jsou skryté výsledky fázích uprostřed kanál, takže je obtížné zjistit, kde problém vykreslování spuštění. Vizualizací samostatně každé fáze, okno fázemi kanálu umožňuje snadno zjistit, kde problém spustí – například můžete snadno vidět, když fázi shaderu vrchol neočekávaně způsobí, že objekt, které se mají vykreslovat mimo obrazovku.  
  
 Poté, co jste označený fáze, ve které k problému dochází, můžete zkontrolovat, jak se data interpretovat nebo transformovat dalších analyzátor grafiky nástrojů. Vykreslování problémy, které se zobrazují v fázemi kanálu jsou často související s nesprávnou vrchol formátu popisovače, buggy shaderu programy nebo nesprávně nakonfigurované stavu.  
  
### <a name="links-to-related-graphics-objects"></a>Odkazy na související grafických objektů  
 Někdy další kontext je potřeba zjistit, proč volání kreslení komunikuje s kanálem grafiky určitým způsobem. Chcete-li tento další kontext snazší najít, související odkazy okno fáze zřetězení grafiky na jeden nebo více objektů, které poskytují další kontext co se děje v grafiky kanálu.  
  
-   V Direct3D – 12 tento objekt je obvykle seznam příkazů.  
  
-   V 11 Direct3D – tento objekt je obvykle grafiky kontextu zařízení.  
  
 Tyto odkazy jsou součástí aktuální podpisu událostí grafiky, který se nachází v levém horním rohu okna fáze zřetězení grafiky. Postupovat podle některého z následujících odkazech na zkontrolujte další podrobnosti o objektu.  
  
### <a name="viewing-and-debugging-shader-code"></a>Zobrazení a ladění kódu shaderu  
 Můžete zkontrolovat a ladění kódu pro vrchol, trupu, domény, geometry a pixelů shadery pomocí ovládacích prvků v dolní části jejich odpovídajících fázích v okně fázemi kanálu.  
  
#### <a name="to-view-a-shaders-source-code"></a>Chcete-li zobrazit zdrojový kód shaderu  
  
-   V **fáze zřetězení grafiky** okně Najít fázi shaderu, která odpovídá shaderu chcete prověřit. Pak níže náhled obrázku, použijte odkaz shaderu fáze název – například pomocí následujícího odkazu **obj:30 vrchol shaderu** zobrazíte zdrojový kód shaderu vrchol.  
  
    > [!TIP]
    >  Číslo objektu **obj:30**, identifikuje tento shaderu v celém rozhraní analyzátor grafiky například okno historie tabulky a pixelů objektu.  
  
#### <a name="to-debug-a-shader"></a>K ladění shaderu  
  
-   V **fáze zřetězení grafiky** okně Najít fázi shaderu, která odpovídá shaderu chcete ladit. Zvolte pod obrázek náhledu **spustit ladění**. Tento vstupní bod do výchozí nastavení ladicí program HLSL, aby první volání shaderu pro odpovídající fázi – to znamená, první pixelů, vrchol nebo primitivní zpracovává shaderu během tohoto hovoru kreslení. Volání této shaderu pro konkrétní pixelu nebo vrchol je možné přistupovat prostřednictvím **historie pixelů grafiky**.  
  
### <a name="the-pipeline-stages"></a>Fáze zřetězení  
 Fáze zřetězení okna vizualizuje pouze fáze kanálu, které byly v průběhu hovoru kreslení aktivní. Každá fáze v kanálu grafiky transformuje vstup z předchozí fáze a předá výsledek do další fáze. Úplně první fáze – vstupní assembleru – přebírá index a vrchol data z aplikace jako vstup; poslední fáze – výstupní fúze – kombinuje nově vykresluje pixelů spolu s aktuálním obsah framebuffer nebo vykreslení cíl jako výstup k vytvoření finální image se zobrazí na obrazovce.  
  
> [!NOTE]
>  Výpočetní shadery nepodporuje **fáze zřetězení grafiky** okno.  
  
 **Vstupní assembleru**  
 Vstup assembleru čte data indexu a vrchol zadané aplikace a sestaví grafiky hardwaru.  
  
 V okně fázemi kanálu assembleru vstup výstupu vizualizace jako obrázek model. Abyste mohli bližší pohled na výsledek, vyberte **vstup assembleru** v **fáze zřetězení grafiky** pro zobrazení v úplné 3D pomocí editoru Model sestavený vrcholy.  
  
> [!NOTE]
>  Pokud `POSITION` sémantického se nenachází ve výstupu vstupní assembleru a nezobrazí se v **vstupní assembleru** fáze.  
  
 **Vrchol shaderu**  
 Fáze shaderu vrchol zpracovává vrcholy, obvykle provádění operací, jako je například transformace, změny vzhledu a osvětlení. Vrchol shadery vytvořit stejný počet vrcholy, které se má jako vstup.  
  
 V okně fázemi kanálu výstup shaderu vrchol vizualizace jako image rastrový obrázek. Abyste mohli bližší pohled na výsledek, vyberte **vrchol shaderu** v **fáze zřetězení grafiky** windows zobrazíte zpracovaná vrcholy v editoru obrázků.  
  
> [!NOTE]
>  Pokud `POSITION` nebo `SV_POSITION` sémantiku nejsou k dispozici ve výstupu shaderu vrchol a nezobrazí se v **vrchol shaderu** fáze.  
  
 **Trupu shaderu** (Direct3D – 11 a Direct3D – 12 pouze)  
 Procesy trupu shaderu fázi řízení body, které definují prostor nejnižší například řádku, trojúhelníku nebo čtyřmi. Jako výstup vyvolá vyšší pořadí geometrie patch a konstanty opravy, které se předávají do fáze teselace – funkce.  
  
 Fáze shaderu trupu není vizualizuje v okně fázemi kanálu.  
  
 **Fáze tessellator** (Direct3D – 11 a Direct3D – 12 pouze)  
 Fáze tessellator je jednotkou hardwaru fixed – funkce (bez programovatelný), která upraví domény reprezentována výstup shaderu trupu. Jako výstup, vytvoří vzorkování vzor domény a sadu menší primitiv – body, řádky, trojúhelníčky – které připojovat tyto ukázky.  
  
 Fáze tessellator není vizualizuje v okně fázemi kanálu.  
  
 **Domény shaderu** (Direct3D – 11 a Direct3D – 12 pouze)  
 Fáze shaderu domény zpracovává vyšší pořadí geometrie opravy z trupu shaderu, faktory společně teselace z fázi teselace. Teselace, který může být faktory zahrnují tessellator vstupních faktorů a také výstup faktorů. Jako výstup vypočítá vrchol pozice bodu na výstup oprava podle tessellator faktorů.  
  
 V okně fázemi kanálu není vizualizuje fázi shaderu domény.  
  
 **Geometrie shaderu**  
 Fáze shaderu geometrie zpracuje celý primitiv – body, čáry nebo trojúhelníky – spolu s daty volitelné vrchol pro hraniční přiléhající primitiv. Na rozdíl od vrchol shadery geometrie shadery může vytvářet více nebo méně primitiv než jejich trvat jako vstup.  
  
 V okně fázemi kanálu výstup shaderu geometrie vizualizace jako image rastrový obrázek. Abyste mohli bližší pohled na výsledek, vyberte **geometrie shaderu** v **fáze zřetězení grafiky** okno zobrazení zpracovaná primitiv v editoru obrázků.  
  
 **Fáze výstupní datový proud**  
 Fáze výstupní datový proud může zachytávat transformovaných primitiv před rasterizační a jejich zápis do paměti; data z ní můžete posbírán jako vstup pro starší fázemi kanálu grafiky nebo číst zpět procesoru.  
  
 V okně fázemi kanálu není vizualizuje fázi výstupní datový proud.  
  
 **Umožňuje fáze**  
 Umožňuje fáze je jednotkou fixed – funkce (bez programovatelný) hardwaru, která převede vektoru primitiv – body, řádky, trojúhelníčky – pomocí bitové kopie rastrových provedením převod kontroly line. Během rasterizační jsou vrcholy převede na homogenního klip místa a oříznuta. Jako výstup jsou mapovány shadery pixelů a na vrchol atributy jsou interpolované napříč primitivní a přípravu k shaderu pixelů.  
  
 V okně fázemi kanálu není vizualizuje fázi umožňuje.  
  
 **Shaderu pixelů**  
 Například barvy a hloubku hodnoty pixelů shaderu fáze procesy rastrového primitiv společně s interpolované vrchol data pro generování za pixelů.  
  
 V okně fázemi kanálu výstup shaderu pixelů vizualizace jako barevné rastrového obrázku. Abyste mohli bližší pohled na výsledek, vyberte **pixelů shaderu** v **fáze zřetězení grafiky** okno zobrazení zpracovaná primitiv v editoru obrázků.  
  
 **Fúze výstup**  
 Fúze fázi výstup kombinuje účinku nově vykresluje pixelů společně s existující obsah jejich odpovídající vyrovnávací paměti – barvu, hloubku a vzorníku – k vytvoření nové hodnoty v těchto vyrovnávací paměti.  
  
 V okně fázemi kanálu výstup fúze výstup vizualizace jako barevné rastrového obrázku. Abyste mohli prohlédnout výsledky, vyberte **výstup fúze** v **fáze zřetězení grafiky** okno zobrazení sloučené framebuffer.  
  
### <a name="vertex-and-geometry-shader-preview"></a>Vrchol a Geometry shaderu preview  
 Když vyberete do vrchol nebo geometrie shaderu fáze **fázemi kanálu** okno, můžete zobrazit vstupy a výstupy z shaderu panelu níže.  Zde najdete podrobnosti o seznam vrcholy zadané shadery po se zřizují vstupní assembleru fázi.  

 ![V prohlížeči vrchol shaderu fáze vstupní vyrovnávací paměť](media/gfx_diag_vertex_shader_inbuffers.png)  
  
 Chcete-li zobrazit výsledek fázi shaderu vrchol, zvolte miniaturu fáze vrchol shaderu zobrazíte plné velikosti, obrázek rastrového oka po jeho byla transformovat shaderu vrchol.  
  
 ![Náhledu výsledku vrchol shaderu fáze](media/gfx_diag_vertex_shader_preview.png)  
  
## <a name="see-also"></a>Viz také  
 [Návod: Chybějící objekty z důvodu použití funkce Vertex Shading](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [Návod: Ladění chyb při vykreslování způsobených stínováním](walkthrough-debugging-rendering-errors-due-to-shading.md)