---
title: 'Návod: Ladění chyb při vykreslování způsobených stínováním | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 01875b05-cc7b-4add-afba-f2b776f86974
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51ede4eb054a942676df8f2a37e357d95b363b92
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-debugging-rendering-errors-due-to-shading"></a>Návod: Ladění chyb při vykreslování způsobených stínováním
Tento návod ukazuje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky k prozkoumání objekt, který je nesprávně barevný z důvodu chyby shaderu.  
  
 Tento návod ukazuje, jak:  
  
-   Zkontrolujte dokument grafických protokolů k identifikaci pixelů, které se zobrazí problém.  
  
-   Použití **historie pixelů grafiky** okno přesněji prozkoumat stav pixelů.  
  
-   Použití **ladicí program HLSL** prozkoumat shadery pixelů a vrcholy.  
  
## <a name="scenario"></a>Scénář  
 Nesprávný barevné zvýrazňování na objekty běžně nastane, když vrchol shaderu předá pixel shaderu nesprávné nebo neúplné informace.  
  
 V tomto scénáři jste nedávno přidali objekt do vaší aplikace, spolu s nový vrchol a shadery pixelů pro transformaci objektu a pojmenujte ho jedinečný vzhled. Při spuštění aplikace během testu, objekt je vykreslen v plné černé. Pomocí diagnostiky grafiky zaznamenáte tyto potíže k protokolu grafiky tak, že ladíte aplikaci. Problém je v aplikaci vypadat třeba takto:  
  
 ![Objekt je vykreslen pomocí nesprávné barvy. ] (media/gfx_diag_demo_render_error_shader_problem.png "gfx_diag_demo_render_error_shader_problem")  
  
## <a name="investigation"></a>Šetření  
 Dokument grafických protokolů kontrola rámce zaznamenané během testu můžete načíst pomocí nástroje diagnostiky grafiky.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>K prozkoumání rámce v protokolu grafiky  
  
1.  V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst grafiky protokol, který obsahuje rámce, který vykazuje chybějící modelu. Okno nového dokumentu protokolu grafiky se zobrazí v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. V horní části tohoto okna je výstup cíl vykreslení vybraného rámce. V dolní části je **rámce seznamu**, zobrazuje každou zaznamenané rámce jako miniatury.  
  
2.  V **rámce seznamu**, vybrat rámec, ve kterém objekt nemá správný vzhled. Cíl vykreslení je aktualizována tak, aby odrážela vybraný snímek. V tomto scénáři protokolu grafiky dokumentu okno vypadá takto:  
  
     ![Grafika protokolu dokumentu v sadě Visual Studio. ] (media/gfx_diag_demo_render_error_shader_step_1.png "gfx_diag_demo_render_error_shader_step_1")  
  
 Po výběru rámce, který ukazuje problém, můžete použít **historie pixelů grafiky** okno diagnostiky ho. **Historie pixelů grafiky** v okně se zobrazí primitivních elementů, které by mohly mít mají vliv na konkrétní pixelů, jejich shadery a co jejich důsledky pro vykreslení cíl byly, v chronologickém pořadí.  
  
#### <a name="to-examine-a-pixel"></a>K prozkoumání pixelů  
  
1.  Otevřete **historie pixelů grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **historie pixelu**.  
  
2.  Vyberte jeden bod prozkoumat. V okně dokumentu protokolu grafiky vyberte jednu z pixelů na objektu, která je nesprávně barevný:  
  
     ![Výběr pixel zobrazí informace o historii. ] (media/gfx_diag_demo_render_error_shader_step_2.png "gfx_diag_demo_render_error_shader_step_2")  
  
     **Historie pixelů grafiky** okno aktualizován, aby odrážel vybrané pixelů. V tomto scénáři **historie pixelů grafiky** okno vypadá takto:  
  
     ![Historie pixelu zobrazuje jeden DrawIndexed událostí. ] (media/gfx_diag_demo_render_error_shader_step_3.png "gfx_diag_demo_render_error_shader_step_3")  
  
     Všimněte si, že shaderu pixel výsledkem je plně neprůhledné černé (0, 0, 0, 1) a že **výstup fúze** o kombinaci **předchozí** barev pixelů tak, který **výsledek** je také plně neprůhledné černé.  
  
 Po zkontrolujte pixel, který je nesprávně barevný a zjistit, že výstup shaderu pixelů není očekávaný barvu, můžete použít ladicí program HLSL sloužící ke zkoumání shaderu pixelů a zjistit, co se stalo s barva objektu. Můžete použít pro zjištění stavu proměnných HLSL během provádění krok prostřednictvím kód HLSL ladicí program HLSL a nastavit zarážky při diagnostice problému.  
  
#### <a name="to-examine-the-pixel-shader"></a>K prozkoumání shaderu pixelů  
  
1.  Spusťte ladění shaderu pixelů. V **historie pixelů grafiky** okno, v rámci objektu je vedle primitivní, **pixelů shaderu**, vyberte **spustit ladění** tlačítko.  
  
2.  V tomto scénáři protože shaderu pixelů jednoduše předají barvu prostřednictvím z vrchol shaderu, je snadné pozorovat, že shaderu pixelů není zdroj problému.  
  
3.  Ukazatele myši na `input.color`. Všimněte si, že její hodnota je plně neprůhledné černé (0, 0, 0, 1).  
  
     ![Je černá "Barva" členem "vstup". ] (media/gfx_diag_demo_render_error_shader_step_5.png "gfx_diag_demo_render_error_shader_step_5")  
  
     V tomto scénáři ukáže průzkum barvu nesprávný je pravděpodobně výsledkem vrchol shaderu, která neposkytuje informace správná barva pro shaderu pixelů pracovat na.  
  
 Poté, co jste zjistili, že shaderu vrchol pravděpodobně není poskytuje náležité informace, které k shaderu pixelů, dalším krokem je prozkoumat shaderu vrchol.  
  
#### <a name="to-examine-the-vertex-shader"></a>K prozkoumání vrchol shaderu  
  
1.  Spusťte ladění shaderu vrchol. V **historie pixelů grafiky** okno, v rámci objektu je vedle primitivní, **vrchol shaderu**, vyberte **spustit ladění** tlačítko.  
  
2.  Vyhledejte struktura výstup shaderu vrchol – to je vstup shaderu pixelů. V tomto scénáři název tato struktura je `output`. Kontrola kódu shaderu vrchol a Všimněte si, že `color` členem `output` struktura byla explicitně nastavena na plně neprůhledné černé, pravděpodobně v důsledku z někdo je ladění úsilí.  
  
3.  Zkontrolujte, že je člen barva nikdy zkopírovány ve vstupní struktuře. Protože hodnota `output.color` je nastavena na plně neprůhledné černé těsně před `output` struktura je vrácena, je vhodné Ujistěte se, že hodnota `output` nebyla správně inicializována na předchozí řádek. Krok prostřednictvím kódu vrchol shaderu, dokud se nedostanete na řádek, který nastaví `output.color` do černé při sledování hodnotu `output.color`. Všimněte si, že hodnota `output.color` není inicializován, dokud je nastavený na černé. Tím se potvrzuje, že na řádek kódu, který nastaví `output.color` do černé by měla být upravena, nikoli odstranit.  
  
     ![Hodnota "output.color" je černá. ] (media/gfx_diag_demo_render_error_shader_step_7.png "gfx_diag_demo_render_error_shader_step_7")  
  
 Když zjistíte, že příčinu problému vykreslování je, že shaderu vrchol nenabízí hodnota správná barva k shaderu pixelů, můžete tyto informace k vyřešení problému. V tomto scénáři můžete je vyřešit ho změnou následující kód v vrchol shaderu  
  
```  
output.color = float3(0.0f, 0.0f, 0.0f);  
```  
  
 až  
  
```hlsl  
output.color = input.color;  
```  
  
 Tento kód jednoduše předají barvu vrchol prostřednictvím z objektu vrcholy ponechat beze změny – složitější shadery vrchol může změnit barvu před předáním prostřednictvím. Opravené vrchol shaderu kód by měl vypadat takto:  
  
 ![Kód shaderu opravené vrchol. ] (media/gfx_diag_demo_render_error_shader_step_8.png "gfx_diag_demo_render_error_shader_step_8")  
  
 Po opravě kód ho znovu sestavte a spusťte aplikaci znovu a zjistit, že se vyřešit problém vykreslování.  
  
 ![Objekt je vykreslen pomocí správné barvy. ] (media/gfx_diag_demo_render_error_shader_resolution.png "gfx_diag_demo_render_error_shader_resolution")