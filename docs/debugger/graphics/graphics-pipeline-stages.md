---
title: Zřetězení grafiky | Dokumentace Microsoftu
ms.date: 02/09/2017
ms.topic: conceptual
f1_keywords:
- vs.graphics.pipeline
ms.assetid: 2bf5c12e-2a00-401c-8163-4e373d08ad3f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ba192d5ec897a1914ef0ba70188930c8c4ae7ecc
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56679512"
---
# <a name="graphics-pipeline-stages"></a>Fáze zřetězení grafiky
V okně fáze zřetězení grafiky pomáhá pochopit, jak je transformovat volání draw jednotlivé každá fáze zřetězení grafiky Direct3D.

 Toto je v okně fáze zřetězení:

 ![3D objekt prochází fáze zřetězení.](media/gfx_diag_demo_pipeline_stages_orientation.png)

## <a name="understanding-the-graphics-pipeline-stages-window"></a>Principy v okně fáze zřetězení grafiky
 V okně fáze zřetězení vizualizuje výsledek každé fáze zřetězení grafiky samostatně, pro každé volání draw. Za normálních okolností jsou skryté výsledky fáze uprostřed kanálu, kvůli tomu obtížné zjistit, kde k problému vykreslování spuštěna. Každá fáze samostatně vizualizací, v okně fáze zřetězení umožňuje snadno zjistit, kde začíná problém – například můžete snadno vidět při fázi vertex shader neočekávaně způsobí, že objekt chcete kreslit obrazovku.

 Po identifikaci fáze, ve kterém k problému dochází, můžete prozkoumat, jak se data interpretovat nebo transformovat dalších analyzátoru grafiky sady nástrojů. Problémů s vykreslováním, které se zobrazují v fáze zřetězení jsou často související nesprávné vrcholu formátu popisovače, obsahujícím chyby shaderu programy nebo nesprávně nakonfigurované stavu.

### <a name="links-to-related-graphics-objects"></a>Odkazy na související grafických objektů
 Někdy další kontext je potřeba zjistit, proč volání draw komunikuje s zřetězení grafiky určitým způsobem. Pro usnadnění tohoto další kontext najít odkazy okna fáze zřetězení grafiky na jeden nebo více objektů, které poskytnete další kontext související co se děje v zřetězení grafiky.

- V Direct3D 12 tento objekt je obvykle seznam příkazů.

- V Direct3D 11 tento objekt je obvykle kontextu zařízení grafiky.

  Tyto odkazy jsou součástí aktuálního podpisu událostí grafiky, který se nachází v levém horním rohu okna fáze zřetězení grafiky. Postupovat podle některého z těchto odkazů prozkoumat další podrobnosti o objektu.

### <a name="viewing-and-debugging-shader-code"></a>Zobrazení a ladění kódu shaderu
 Můžete prozkoumat a ladění kódu pro vrchol, trupu, domény, geometrie a pixel shadery pomocí ovládacích prvků na konci jejich odpovídajících fází v okně fáze zřetězení.

#### <a name="to-view-a-shaders-source-code"></a>Chcete-li zobrazit zdrojový kód shaderu

-   V **fáze zřetězení grafiky** okně vyhledejte fázi shaderu, který odpovídá shaderu chcete prověřit. Pak níže image ve verzi preview použijte odkaz na název fázi shaderu – například pomocí následujícího odkazu **Vertex Shader obj:30** Chcete-li zobrazit zdrojový kód shaderu vrcholu.

    > [!TIP]
    >  Číslo objektu **obj:30**, identifikuje tento shader v celém rozhraní analyzátoru grafiky sady například v okně objekt tabulky a pixel historie.

#### <a name="to-debug-a-shader"></a>K ladění shaderu

-   V **fáze zřetězení grafiky** okně vyhledejte fázi shaderu, který odpovídá shaderu chcete ladit. Zvolte níže obrázek náhledu **spustit ladění**. Tento vstupní bod do výchozí nastavení ladicího programu HLSL, aby před prvním vyvoláním služby shaderu pro odpovídající fázi, tedy první pixel, vrchol nebo primitivní hodnota, která zpracovává shaderu během volání příkazu pro vykreslení. Vyvolání tento shader pro konkrétní pixelů nebo vrchol je přístupná prostřednictvím **historie pixelů grafiky**.

### <a name="the-pipeline-stages"></a>Fáze zřetězení
 V okně fáze zřetězení vizualizuje pouze fáze kanálu, které byly aktivní během volání draw. Každá fáze zřetězení grafiky transformuje vstupu z předchozí fáze a předá výsledek do další fáze. Úplně první fáze – vstupního assembleru – přebírá index a vrcholu data z vaší aplikace jako vstup; poslední fáze – slučovací modul výstupu – kombinuje nově vykresleny spolu s aktuálním obsahu framebuffer pixelů nebo cíl vykreslování jako jeho výstup, chcete-li vytvořit finální image se zobrazí na obrazovce.

> [!NOTE]
>  Výpočetní shadery nepodporuje **fáze zřetězení grafiky** okna.

 **Vstupní Assembler** The vstupní Assembler načte index a vrcholu dat zadaný hodnotou vaší aplikace a sestavuje pro hardwarovou akceleraci.

 V okně fáze zřetězení je výstup assembleru vstup vizualizovat jako drátový model. Chcete-li podrobněji podíváme na výsledek, vyberte **vstupní Assembler** v **fáze zřetězení grafiky** okně deskách vrcholy v úplnou 3D pomocí Editoru modelů.

> [!NOTE]
>  Pokud `POSITION` sémantické se nenachází ve výstupu vstupní assembler a nezobrazí se v **vstupního assembleru** fázi.

 **Vertex Shader** vertex shader fáze zpracovává vrcholy, obvykle provádí operace, jako je transformace, změny vzhledu a osvětlení. Vrchol shaderů vytvořit stejný počet vrcholů, které tyto přebírá jako vstup.

 V okně fáze zřetězení je výstup Vertex Shader vizualizuje jako drátěný rastrového obrázku. Chcete-li podrobněji podíváme na výsledek, vyberte **Vertex Shader** v **fáze zřetězení grafiky** windows zobrazíte zpracovaných vrcholy v editoru obrázků.

> [!NOTE]
>  Pokud `POSITION` nebo `SV_POSITION` sémantiku nejsou k dispozici ve výstupu vertex shader a nezobrazí se v **Vertex Shader** fázi.

 **Shader trupu** (Direct3D 11 a Direct3D 12 pouze) fázi shaderu trupu zpracovává kontrolní body, které definují nižšího řádu surface například řádku, trojúhelník nebo quad. Jako výstup produkuje opravu vyššího řádu geometrie a konstanty opravy, které jsou předány do fáze teselace – funkce.

 Fázi shaderu trupu není vizualizovat v okně fáze zřetězení.

 **Fáze tessellator** (Direct3D 11 a Direct3D 12 pouze) tessellator fáze je jednotka hardwaru fixed – funkce (Neprogramovatelná), který upraví domény reprezentována výstup shaderu trupu. Jako výstup, vytvoří vzorkování model domény a sadu menších primitivy – body, řádky, trojúhelníky – připojení, které tyto ukázky.

 Fáze tessellator není vizualizovat v okně fáze zřetězení.

 **Shader domény** (Direct3D 11 a Direct3D 12 pouze) vyššího řádu geometrie opravy z shader trupu společně teselace z teselace fáze zpracovává fázi shaderu domény. Teselace, může být faktory zahrnují tessellator vstupních faktorů, stejně jako výstup faktorů. Jako výstup vypočítá pozici vrcholu bodu na opravě výstup podle tessellator faktorů.

 Fázi shaderu domény není vizualizovat v okně fáze zřetězení.

 **Shader geometrie** geometry shader fáze zpracovává celý primitivy – body, čáry nebo trojúhelníky – spolu s daty volitelné vrcholu pro okraje vedle primitiv. Na rozdíl od shader vrcholu shader geometrie můžete vytvořit více nebo méně primitivních elementů než přijímají jako vstup.

 V okně fáze zřetězení jsou vizualizována geometry shader výstup jako drátěný rastrového obrázku. Chcete-li podrobněji podíváme na výsledek, vyberte **Shader geometrie** v **fáze zřetězení grafiky** okně zpracovaných primitiv v editoru obrázků.

 **Stream výstup fáze** fáze výstupní datový proud může zachytávat transformovaný primitiv před rasterizační a zapisovat do paměti; z něj data můžete posbírán jako vstup pro předchozí fáze zřetězení grafiky nebo číst zpět procesoru.

 Fáze výstupní datový proud není vizualizovat v okně fáze zřetězení.

 **Fáze rasterizéru** rasterizéru fáze je jednotka fixed – funkce (Neprogramovatelná) hardwaru, který převádí primitivních elementů vektorové – body, řádky, trojúhelníky – do rastrových obrázků pomocí provádí převod kontroly řádku. Během rasterizační vrcholy se transformuje na homogenní prostoru klipu a oříznut. Jako výstup jsou mapovány pixel shaderů a atributy na vrcholu jsou interpolovaných napříč primitivní vlastnost a přípravu k pixel shader.

 Fáze rasterizéru není vizualizovat v okně fáze zřetězení.

 **Pixel Shader** pixel shader fáze zpracovává rastrový primitivy spolu s daty interpolované vrcholu ke generování hodnoty jednotlivých pixelů, jako je barva a hloubka.

 V okně fáze zřetězení je výstup pixel shaderu vizualizovat jako barevné rastrového obrázku. Chcete-li podrobněji podíváme na výsledek, vyberte **Pixel Shader** v **fáze zřetězení grafiky** okně zpracovaných primitiv v editoru obrázků.

 **Výstup spojení** fáze fúze výstup kombinuje efekt pixelů nově vykresleny spolu s existující obsah své vyrovnávací paměti odpovídající – barva hloubky a vzorníku – k vytvoření nové hodnoty v těchto vyrovnávací paměti.

 V okně fáze zřetězení je výstup spojení výstup vizualizuje jako barevné rastrového obrázku. Abyste mohli na ně podívat výsledky, vyberte **slučovací modul výstupu** v **fáze zřetězení grafiky** okně sloučené framebuffer.

### <a name="vertex-and-geometry-shader-preview"></a>Vertex a Geometry shader ve verzi preview
 Když vyberete vrchol nebo geometry shader fáze v **fáze zřetězení** okně můžete zobrazit vstupy a výstupy z shaderu v panelu níže.  Tady najdete podrobnosti o seznam vrcholů zadaný pro se shadery, jakmile se zřizují podle fáze vstupního assembleru.

 ![Prohlížeč vstupní vyrovnávací paměť vrcholů shaderu fáze](media/gfx_diag_vertex_shader_inbuffers.png)

 Chcete-li zobrazit výsledek fázi vertex shaderu zvolte miniaturu fáze Vertex Shader zobrazíte reklamy, rastrový obrázek oka po jeho byly transformovány sadou vertex shader.

 ![Výsledek vertex shaderu fázi ve verzi preview](media/gfx_diag_vertex_shader_preview.png)

## <a name="see-also"></a>Viz také
- [Návod: Chybějící objekty kvůli vertex shaderu](walkthrough-missing-objects-due-to-vertex-shading.md)
- [Návod: Ladění chyb při vykreslování, které jsou způsobené stínováním](walkthrough-debugging-rendering-errors-due-to-shading.md)