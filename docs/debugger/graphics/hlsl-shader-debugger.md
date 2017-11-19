---
title: "Ladicí program shaderu HLSL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.graphics.shaderviewer
ms.assetid: 4ccec541-3c49-42bd-972a-686eb3a88fbc
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7d095d5dec0194f75d739899433c04439f08539
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="hlsl-shader-debugger"></a>Ladicí program shaderu HLSL
Ladicí program HLSL ve Visual Studio Graphics Analyzer pomáhá pochopit, jak funguje kódu shaderu HLSL v podmínkách reálného vaší aplikace.  
  
 Toto je ladicí program HLSL:  
  
 ![Ladění pomocí HLSL sledovat a okna zásobník volání. ] (media/gfx_diag_demo_hlsl_debugger_orientation.png "gfx_diag_demo_hlsl_debugger_orientation")  
  
## <a name="understanding-the-hlsl-debugger"></a>Principy ladicího programu HLSL  
 Ladicí program HLSL vám pomůže objasnit problémy, které vzniknou v kódu shaderu. Ladění kódu HLSL v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vypadá takto: ladění kód, který je zapsán v jiných jazycích – například C++, C# nebo Visual Basic. Můžete kontrolovat obsah proměnných, nastavit body přerušení, krokovat kód a procházet nahoru zásobníkem volání podobně jako při ladění jiných jazyků.  
  
 Ale protože grafickými procesory dosáhnout vysoký výkon při spuštění kódu shaderu na stovky vláken současně, ladicí program HLSL slouží k fungují společně s další nástroje Analyzátor grafiky pro všechny tyto informace k dispozici způsobem, který pomůže smysl pro ho. Analyzátor grafiky vytvoří zaznamenané rámce pomocí informace, které se zaznamenávají do protokolu grafiky; ladicí program HLSL nesleduje GPU provádění v reálném čase, při jeho spuštění shaderu kódu. Protože grafiky protokolu obsahuje dostatek informací k opětovnému vytvoření libovolná součást výstup a protože analýza grafických poskytuje nástroje, které vám mohou pomoci přesně určit přesnou pixelů a událostí, kde dojde k chybě, ladicí program HLSL má jenom k simulaci přesný shaderu vlákno, které vás zajímají. To znamená, že práce shaderu může být simulována procesorem, ve kterém jsou vnitřní mechanismy plně zobrazeny. Tímto ladicí program HLSL dosahuje možností ladění na úrovni procesoru.  
  
 Ladicí program HLSL je však aktuálně omezen následujícími způsoby:  
  
-   Ladicí program HLSL nepodporuje, upravit a pokračovat, ale můžete provést změny vašeho shadery a pak znovu vygenerovat rámečku a zobrazte si výsledky.  
  
-   Není možné současně ladit aplikaci a její kód shaderu. Můžete však mezi nimi přepínat.  
  
-   K oknu kukátka můžete přidat proměnné a registry, ale výrazy nejsou podporovány.  
  
 Nicméně ladicí program HLSL poskytuje lepší ladění více odpovídající CPU, které by jinak nebylo možné.  
  
## <a name="hlsl-shader-edit--apply"></a>Použít & Upravit shaderu HLSL  
 Ladicí program shaderu HLSL nepodporuje Upravit & pokračovat stejným způsobem, který provede ladicí program procesoru, protože model spouštění GPU neumožňuje shaderu stavu, nelze vrátit zpět. Místo toho ladicí program HLSL podporuje upravit a použít, které umožňuje upravit HLSL zdrojové soubory a potom zvolte **použít** znovu vygenerovat rámečku projevily provedené změny. Váš kód upravené shaderu je uložen v samostatném souboru zachovat integritu vašeho projektu původní HLSL zdrojový soubor, ale až budete spokojeni s vašimi změnami můžete **zkopírujte do...**  zkopírovat změny do projektu. Pomocí této funkce můžete rychle iterovat shaderu kód, který obsahuje chyby a eliminovat nákladná opětovné sestavení a zachycení kroky z vaší HLSL ladění pracovního postupu.  
  
## <a name="hlsl-disassembly"></a>Zpětný překlad HLSL  
 Ladicí program shaderu HLSL poskytuje seznam sestavení shaderu HLSL napravo od výpis HLSL zdrojového kódu.  
  
## <a name="debugging-hlsl-code"></a>Ladění kódu HLSL  
 Ladicí program HLSL můžete přistupovat z windows fázemi kanálu nebo historie pixelů.  
  
#### <a name="to-start-the-hlsl-debugger-from-the-graphics-pipeline-stages-window"></a>Spuštění ladicího programu HLSL z okna Fáze zřetězení grafiky  
  
1.  V **fáze zřetězení grafiky** okně Najít fáze kanálu, který je spojen s shaderu, kterou chcete ladit.  
  
2.  Pod nadpisem článku fáze kanálu, zvolte **spustit ladění**, která se zobrazí jako malé zelenou šipku.  
  
    > [!NOTE]
    >  Tento vstupní bod do ladicího programu HLSL ladí pouze první vlákno shaderu pro odpovídající fázi, tedy první vrchol nebo pixel, který je zpracován. Historie pixelu můžete použít pro přístup k jiná vlákna k těmto fázím shaderu.  
  
#### <a name="to-start-the-hlsl-debugger-from-the-graphics-pixel-history"></a>Spuštění ladicího programu HLSL z okna Historie pixelů grafiky  
  
1.  V **historie pixelů grafiky** okně rozbalte kreslení volání, který je spojen s shaderu, kterou chcete ladit. Každé volání draw může odpovídat více primitivům.  
  
2.  V podrobnostech volání draw rozbalte primitivum, jehož výsledný příspěvek barvy naznačuje chybu v kódu shaderu. Pokud na chyby poukazuje více primitiv, vyberte první primitivum, aby nedošlo ke hromadění chyb, které mohou ztížit diagnostiku problému.  
  
3.  V podrobnostech primitivní vyberte, zda chcete ladit **vrchol shaderu** nebo **pixelů shaderu**. Pokud máte podezření, že pixel shader je správný, ale generuje nesprávný příspěvek barvy, protože vertex shader mu předává nesprávné konstanty, proveďte ladění funkce vertex shader. V opačném případě proveďte ladění funkce pixel shader.  
  
     Napravo od zvolené shaderu, zvolte **spustit ladění**, která se zobrazí jako malé zelenou šipku.  
  
    > [!NOTE]
    >  Tento vstupní bod do ladicího programu HLSL ladí buď vlákno funkce pixel shader, které odpovídá zvolenému volání draw, primitivu a pixelu, nebo vlákna funkce vertex shader, jejichž výsledky jsou interpolovány voláním draw, primitivem a pixelem, které jste vybrali. U funkcí vertex shader můžete dále upřesnit vstupní bod do určitého vrcholu rozbalením podrobností funkce vertex shader.  
  
 Příklady o tom, jak používat ladicí program HLSL k ladění chyby shaderu najdete v tématu [příklady](graphics-diagnostics-examples.md) nebo názorné postupy propojeny v části Viz také.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Chybějící objekty z důvodu použití funkce Vertex Shading](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [Návod: Ladění chyb při vykreslování způsobených stínováním](walkthrough-debugging-rendering-errors-due-to-shading.md)   
 [Návod: Použití diagnostiky grafiky k ladění výpočetního shaderu](walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader.md)