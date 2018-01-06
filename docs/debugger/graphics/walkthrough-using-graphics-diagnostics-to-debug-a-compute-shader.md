---
title: "Návod: Použití diagnostiky grafiky k ladění výpočetního shaderu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69287456-644b-4aff-bd03-b1bbb2abb82a
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ef73c45b39c638b2dfc1f88be3323d083efa8493
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader"></a>Návod: Použití diagnostiky grafiky k ladění výpočetního shaderu
Tento návod ukazuje, jak používat nástroje Visual Studio diagnostiky grafiky k prošetření výpočetního shaderu, který generuje nesprávné výsledky.  
  
 Tento návod ukazuje tyto úlohy:  
  
-   Pomocí **seznam událostí grafiky** najít potenciální zdroje problému.  
  
-   Pomocí **zásobník volání událostí grafiky** k určení, které výpočetní shaderu spuštěný DirectCompute `Dispatch` událostí.  
  
-   Pomocí **fáze zřetězení grafiky** okno a HLSL ladicího programu a pomocí něj prozkoumat výpočetního shaderu, který je zdrojem problému.  
  
## <a name="scenario"></a>Scénář  
 V tomto scénáři jste napsali kapaliny dynamics simulace, která používá DirectCompute k provádění části simulace aktualizace se nejvíce náročných na výpočetní. Když se aplikace spustí, vykreslování datovou sadu a uživatelského rozhraní vypadat správný, ale simulaci není chovat podle očekávání. Pomocí diagnostiky grafiky můžete zaznamenat tyto potíže k protokolu grafiky tak, že ladíte aplikaci. Problém je v aplikaci vypadat třeba takto:  
  
 ![Simulované kapaliny se chová nesprávně. ] (media/gfx_diag_demo_compute_shader_fluid_problem.png "gfx_diag_demo_compute_shader_fluid_problem")  
  
 Informace o tom, jak zachytit grafiky problémy v protokolu grafiky najdete v tématu [zaznamenání grafických informací](capturing-graphics-information.md).  
  
## <a name="investigation"></a>Šetření  
 Nástroje diagnostiky grafiky můžete načíst soubor protokolu grafiky tak, aby si můžete prohlédnout zaznamenané rámce.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>K prozkoumání rámce v protokolu grafiky  
  
1.  V sadě Visual Studio načtěte grafiky protokol, který obsahuje rámeček, pro jehož nesprávný simulace výsledky. V sadě Visual Studio se zobrazí na nové záložce diagnostiky grafiky. V horní části na této kartě je výstup cíl vykreslení vybraného rámce. V dolní části je **rámce seznamu**, zobrazuje miniaturu každý zaznamenané rámce.  
  
2.  V **rámce seznamu**, vyberte snímek, který ukazuje chování nesprávný simulace. I když v simulaci kódu a není kód vykreslování se zobrazí chyba, budete nejdřív muset vybrat snímek, protože zaznamenání DirectCompute události na základě jednotlivých snímcích společně s Direct3D – události. V tomto scénáři protokolu grafiky karta vypadá takto:  
  
     ![Grafika protokolu dokumentu v sadě Visual Studio. ] (media/gfx_diag_demo_compute_shader_fluid_step_1.png "gfx_diag_demo_compute_shader_fluid_step_1")  
  
 Po výběru rámce, který ukazuje problém, můžete použít **seznam událostí grafiky** při diagnostice ho. **Seznam událostí grafiky** obsahuje událost pro každou DirectCompute volání a volání Direct3D – rozhraní API, která byla vytvořená během aktivního rámce – například volání rozhraní API na GPU spouštět výpočet nebo k vykreslení uživatelského rozhraní na datovou sadu. V takovém případě jsme mají zájem o `Dispatch` události, které představují části simulace, které běží na GPU.  
  
#### <a name="to-find-the-dispatch-event-for-the-simulation-update"></a>Najít odesílání událostí pro simulaci aktualizace  
  
1.  Na **diagnostiky grafiky** nástrojů vyberte **seznam událostí** otevřete **seznam událostí grafiky** okno.  
  
2.  Zkontrolujte **seznam událostí grafiky** pro kreslení událost, která vykreslí datovou sadu. Chcete-li usnadnit tuto činnost, zadejte `Draw` v **vyhledávání** pole v pravém horním rohu **seznam událostí grafiky** okno. Tento filtrování seznamu tak, aby obsahoval jenom události, které mají "Kreslení" v jejich názvy. V tomto scénáři zjistíte, že tyto kreslení události došlo k chybě:  
  
     ![Seznam událostí &#40; EL &#41; ukazuje zakreslit události. ] (media/gfx_diag_demo_compute_shader_fluid_step_2.png "gfx_diag_demo_compute_shader_fluid_step_2")  
  
3.  Pohyb jednotlivých událostí kreslení při sledování cíl vykreslení na kartě grafiky protokolu dokumentu.  
  
4.  Zastavte při vykreslení cíl nejprve zobrazí vykreslené datovou sadu. V tomto scénáři je vykreslen datovou sadu v první událost kreslení. Při simulaci se zobrazí:  
  
     ![To zakreslit událostí vykreslí simulace datové sady. ] (media/gfx_diag_demo_compute_shader_fluid_step_3.png "gfx_diag_demo_compute_shader_fluid_step_3")  
  
5.  Nyní zkontrolovat **seznam událostí grafiky** pro `Dispatch` událost, která aktualizuje simulace. Protože je pravděpodobné, že je před vykreslením aktualizovat simulace, nejprve můžete soustředit na `Dispatch` události, které nastaly před kreslení událost, která vykreslí výsledky. Chcete-li usnadnit tuto činnost, změňte **vyhledávání** pole ke čtení `Draw;Dispatch;CSSetShader(`. Tím se odfiltrují seznamu tak, aby také obsahuje `Dispatch` a `CSSetShader` události kromě kreslení události. V tomto scénáři je zjistit několik `Dispatch` před kreslení událostí došlo k události:  
  
     ![Kreslení ukazuje EL, odesílání a CSSetShader události](media/gfx_diag_demo_compute_shader_fluid_step_4.png "gfx_diag_demo_compute_shader_fluid_step_4")  
  
 Teď, když víte, které několika potenciálně mnoha `Dispatch` události může odpovídat problém, můžete je prozkoumat podrobněji.  
  
#### <a name="to-determine-which-compute-shader-a-dispatch-call-executes"></a>Chcete-li zjistit, které výpočetní shaderu volání odesílání provádí  
  
1.  Na **diagnostiky grafiky** nástrojů vyberte **zásobník volání událostí** otevřete **zásobník volání událostí grafiky** okno.  
  
2.  Od kreslení událost, která vykreslí výsledky simulace, pohyb v zpětně každý předchozí `CSSetShader` událostí. Potom v **zásobník volání událostí grafiky** okně vyberte funkci nejvyšší, přejděte na web volání. V lokalitě volání, můžete použít první parametr [CSSetShader](http://msdn.microsoft.com/library/ff476402.aspx) volání k určení, které výpočetní shaderu je provedený další funkce `Dispatch` událostí.  
  
 V tomto scénáři jsou tři páry `CSSetShader` a `Dispatch` události v každém snímku. Práce zpětné, třetí pár představuje integrace krok (kde plynulá práce částice ve skutečnosti přesunou), druhý pár představuje krok výpočtu force (kde jsou vypočítávány vynutí, které ovlivňují každého částice), a představuje první pár Krok hustotu výpočtu.  
  
#### <a name="to-debug-the-compute-shader"></a>K ladění výpočetního shaderu  
  
1.  Na **diagnostiky grafiky** nástrojů vyberte **fázemi kanálu** otevřete **fáze zřetězení grafiky** okno.  
  
2.  Vyberte třetí `Dispatch` událostí (ten, který okamžitě předchází kreslení událostí) a pak na **fáze zřetězení grafiky** okno, v části **výpočetní shaderu** dvoufázové instalace, zvolte  **Spuštění ladění**.  
  
     ![Výběr třetí odesílání událostí v EL.](media/gfx_diag_demo_compute_shader_fluid_step_6.png "gfx_diag_demo_compute_shader_fluid_step_6")  
  
     Ladicí program HLSL je spuštěn v shaderu, který provádí krok integrace.  
  
3.  Zkontrolujte výpočetního shaderu zdrojový kód pro integraci krok k vyhledání zdroji této chyby. Při použití diagnostiky grafiky k ladění kódu výpočetního shaderu HLSL, můžete krok prostřednictvím kódu a použít jiné známých nástrojů ladění například sledování systému windows. V tomto scénáři zjistíte, že existuje pravděpodobně není v výpočetního shaderu, který provádí krok integrace chybu.  
  
     ![Ladění výpočetního shaderu IntegrateCS. ] (media/gfx_diag_demo_compute_shader_fluid_step_7.png "gfx_diag_demo_compute_shader_fluid_step_7")  
  
4.  K ladění výpočetního shaderu na zastavení **ladění** nástrojů vyberte **Zastavte ladění** (klávesové: Shift + F5).  
  
5.  Potom vyberte druhý `Dispatch` událostí a spuštění ladění výpočetního shaderu, stejně jako v předchozím kroku.  
  
     ![Výběr druhý odesílání událostí v EL.](media/gfx_diag_demo_compute_shader_fluid_step_8.png "gfx_diag_demo_compute_shader_fluid_step_8")  
  
     Ladicí program HLSL je spuštěn v shaderu, která by vypočítala vynutí, které fungují v každé plynulá práce částice.  
  
6.  Zkontrolujte výpočetního shaderu zdrojový kód pro krok výpočtu force. V tomto scénáři zjistíte, že zdroji této chyby je tady.  
  
     ![Ladění ForceCS &#95; Jednoduché výpočetního shaderu. ] (media/gfx_diag_demo_compute_shader_fluid_step_9.png "gfx_diag_demo_compute_shader_fluid_step_9")  
  
 Po určení umístění k chybě, můžete ukončit ladění a upravit zdrojový kód výpočetního shaderu správně vypočítat vzdálenost mezi vzájemně komunikující částice. V tomto scénáři právě změňte řádek `float2 diff = N_position + P_position;` k `float2 diff = N_position - P_position;`:  
  
 ![Opravené výpočetní & č. 45; shaderu kódu. ] (media/gfx_diag_demo_compute_shader_fluid_step_10.png "gfx_diag_demo_compute_shader_fluid_step_10")  
  
 V tomto scénáři protože výpočetní shadery kompilované za běhu, můžete právě restartovat aplikaci po provedení změn, abyste viděli, jak ovlivňují simulace. Nemáte k opětovnému sestavení aplikace. Při spuštění aplikace, zjistíte simulaci teď chovat správně.  
  
 ![Simulované kapaliny chovat správně. ] (media/gfx_diag_demo_compute_shader_fluid_resolution.png "gfx_diag_demo_compute_shader_fluid_resolution")