---
title: 'Návod: Chybějící objekty z důvodu nesprávné konfigurace zřetězení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ed8ac02d-b38f-4055-82fb-67757c2ccbb9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2833c3ae2a8f03b69314db9e3723a640c4327587
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="walkthrough-missing-objects-due-to-misconfigured-pipeline"></a>Návod: Chybějící objekty z důvodu nesprávné konfigurace zřetězení
Tento návod ukazuje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky nástrojům pro zkoumání objekt, který je chybějící z důvodu shaderu nenastavené pixelů.  
  
 Tento návod ukazuje tyto úlohy:  
  
-   Pomocí **seznam událostí grafiky** najít potenciální zdroje problému.  
  
-   Pomocí **fáze zřetězení grafiky** okna zkontrolujte účinek `DrawIndexed` volání rozhraní API Direct3D.  
  
-   Probíhá kontrola kontextu zařízení potvrďte, že fáze shaderu nebyla nastavena.  
  
-   Pomocí **fáze zřetězení grafiky** okno společně s **zásobník volání událostí grafiky** vám pomohou najít zdroj shaderu nenastavené pixelů.  
  
## <a name="scenario"></a>Scénář  
 Pokud objekt chybí v 3D aplikaci, je to někdy protože jeden z fází shaderu není nastaven před vykreslením objektu. V aplikacích, které mají jednoduchý vykreslování potřebám je obvykle někde umístěn v zásobníku volání objektu kreslení volání zdroji této chyby. Však jako optimalizace, některé aplikace batch společně objekty, které mají shaderu programy, textury nebo jiná data společné pro minimalizaci-změna stavu režie. V těchto aplikací zdroji této chyby může být schovaný v dávkování systému, a nikoli umístěný v zásobníku volání kreslení volání. Scénář v tomto průvodci ukazuje aplikaci, která má požadavky na jednoduchý vykreslení, a proto zdroji této chyby naleznete v zásobníku volání.  
  
 V tomto scénáři při spuštění aplikace to vyzkoušíte, pozadí se vykresluje podle očekávání, ale jeden z objektů se nezobrazí. Pomocí diagnostiky grafiky zaznamenáte tyto potíže k protokolu grafiky tak, že ladíte aplikaci. Problém je v aplikaci vypadat třeba takto:  
  
 ![Objekt je nemohou vidět](media/gfx_diag_demo_misconfigured_pipeline_problem.png "gfx_diag_demo_misconfigured_pipeline_problem")  
  
## <a name="investigation"></a>Šetření  
 Dokument grafických protokolů kontrola rámce zaznamenané během testu můžete načíst pomocí nástroje diagnostiky grafiky.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>K prozkoumání rámce v protokolu grafiky  
  
1.  V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst dokument grafických protokolů, obsahující rámce, který vykazuje chybějící objekt. Novou kartu protokolu grafiky se zobrazí v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. V horní části na této kartě je výstup cíl vykreslení vybraného rámce. V dolní části je **rámce seznamu**, zobrazuje každou zaznamenané rámce jako miniatury.  
  
2.  V **rámce seznamu**, vyberte snímek, který ukazuje, že se nezobrazí, objekt. Cíl vykreslení je aktualizována tak, aby odrážela vybraný snímek. V tomto scénáři protokolu grafiky karta vypadá takto:  
  
     ![Grafika protokolu dokumentu v sadě Visual Studio](media/gfx_diag_demo_misconfigured_pipeline_step_1.png "gfx_diag_demo_misconfigured_pipeline_step_1")  
  
 Po výběru rámce, který ukazuje problém, můžete začít diagnostikovat pomocí **seznam událostí grafiky**. **Seznam událostí grafiky** obsahuje každých volání Direct3D – rozhraní API, která byla vytvořená k vykreslení aktivní rámec – například k nastavení stavu zařízení, abyste mohli vytvářet a aktualizovat vyrovnávací paměti a k vykreslení objekty, které se zobrazují v rámečku. Různé druhy volání – například kreslení, odesílání, kopírovat nebo vymazat volání – je zajímavé, protože není často (ale ne vždy) odpovídající změnu cíl vykreslení, když aplikace funguje podle očekávání. Kreslení volání jsou zvláště zajímavé, protože každé z nich představuje geometry, který vykreslí aplikace.  
  
 Vzhledem k tomu, že víte, že cíl vykreslení neobsahuje chybějící objektu ale také, že se nezobrazí jako ostatní chyby, můžete použít **seznam událostí grafiky** společně s **fáze zřetězení grafiky**nástroj k určení, které kreslení volání odpovídá geometrie chybějící objektu. **Fáze zřetězení grafiky** v okně se zobrazí geometry, který vám byl zaslán každé volání kreslení, bez ohledu na jeho dopad na cíl vykreslení. Při přesouvání prostřednictvím volání kreslení je fázemi kanálu se aktualizují zobrazíte geometry, který je spojen s každou volání procházejících každé povolené fáze a vykreslování cílový výstup se aktualizuje na Zobrazit stav cíl vykreslení po dokončení volání.  
  
#### <a name="to-find-the-draw-call-for-the-missing-geometry"></a>Najít kreslení volání pro chybějící geometrie  
  
1.  Otevřete **seznam událostí grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **seznam událostí**.  
  
2.  Otevřete **fáze zřetězení grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **fázemi kanálu**.  
  
3.  Jak přesunout iteraci v každém kreslení volání **seznam událostí grafiky** okno, sledovat **fáze zřetězení grafiky** okna pro objekt chybí. Chcete-li usnadnit tuto činnost, zadejte "Kreslení" v **vyhledávání** pole v pravém horním rohu **seznam událostí grafiky** okno. Tento filtrování seznamu tak, aby obsahoval jenom události, které mají "Kreslení" v jejich názvy.  
  
     V **fáze zřetězení grafiky** okně **vstup assembleru** fáze ukazuje geometrie objektu předtím, než je transformován a **vrchol shaderu** fáze zobrazuje stejné objekt po jeho transformaci. V tomto scénáři, Všimněte si, že **fáze zřetězení grafiky** zobrazí okno **vstup assembleru** a **vrchol shaderu** zpracuje, ale ne **shaderu pixelů**  fáze jedno z volání kreslení.  
  
    > [!NOTE]
    >  Pokud jiné kanálu fázích – například trupu shaderu, shaderu domény nebo geometrie shaderu fázích – zpracovat objekt, některý z nich může být příčinou problému. Problém se obvykle týká nejdřívější fáze, ve kterém výsledek se nezobrazí, nebo způsobem, který se zobrazí.  
  
4.  Zastavte při dosažení kreslení volání, která odpovídá chybějícím objektu. V tomto scénáři **fáze zřetězení grafiky** okno znamená, že byl vydán geometrie na grafický procesor (indikován přítomnost **vstup assembleru** fáze) a transformovaná (označená  **Vrchol shaderu** fáze), ale nezobrazí v cíl vykreslení, protože není nejspíš shaderu active pixelů (indikován absenci **pixelů shaderu** fáze). V tomto scénáři i uvidíte obrysem chybějící objektu v **výstup fúze** fáze:  
  
     ![Událost DrawIndexed a jeho dopad na kanálu](media/gfx_diag_demo_misconfigured_pipeline_step_2.png "gfx_diag_demo_misconfigured_pipeline_step_2")  
  
 Po potvrzení, že aplikace vydala kreslení volání pro chybějící objekt geometrie a zjistit aktivní nebyl fázi shaderu pixelů, můžete zkontrolovat stav zařízení potvrďte zjištěnými informacemi. Můžete použít **tabulka grafických objektů** k prozkoumání kontextu zařízení a další data Direct3D – objektu.  
  
#### <a name="to-examine-device-context"></a>K prozkoumání kontextu zařízení  
  
1.  Otevřete **kontextu zařízení d3d11**. V **fáze zřetězení grafiky** okně zvolte **ID3D11DeviceContext** odkaz, který je součástí `DrawIndexed` volání, které se zobrazí v horní části okna.  
  
2.  Zkontrolujte stav zařízení, která se zobrazí v **kontextu zařízení d3d11** a ověřte, že žádné pixelů shaderu byl aktivní v průběhu hovoru kreslení. V tomto scénáři **shaderu obecné informace**– zobrazí v části **pixelů shaderu stavu**– označuje, že je shaderu **NULL**:  
  
     ![Kontext zařízení 11 D3D ukazuje stav shaderu pixelů](media/gfx_diag_demo_misconfigured_pipeline_step_4.png "gfx_diag_demo_misconfigured_pipeline_step_4")  
  
 Jakmile potvrdíte, že shaderu pixelů byla nastavena na hodnotu null. aplikace, dalším krokem je a vyhledejte umístění ve zdrojovém kódu vaší aplikace kde je nastaven shaderu. Můžete použít **seznam událostí grafiky** společně s **zásobník volání událostí grafiky** k vyhledání tohoto umístění.  
  
#### <a name="to-find-where-the-pixel-shader-is-set-in-your-apps-source-code"></a>Najít, kde je nastaven shaderu pixelů ve zdrojovém kódu vaší aplikace  
  
1.  Najít `PSSetShader` volání, která odpovídá chybějícím objektu. V **seznam událostí grafiky** okno, zadejte "kreslení; PSSetShader"v **vyhledávání** pole v pravém horním rohu **seznam událostí grafiky** okno. Tento filtrování seznamu tak, aby obsahoval pouze "PSSetShader" události a události, které mají "Kreslení" v jejich názvy. Zvolte první `PSSetShader` volání, které se zobrazí před voláním kreslení chybějící objektu.  
  
    > [!NOTE]
    >  `PSSetShader` se nebude zobrazovat na **seznam událostí grafiky** okno, pokud během tohoto rámce nebyl nastaven. Obvykle k tomu dochází pouze v případě, že pouze jeden pixelů shaderu se používá pro všechny objekty, nebo pokud `PSSetShader` volání přeskočila neúmyslně během tohoto snímku. V obou případech doporučujeme hledání aplikace zdrojového kódu pro `PSSetShader` volání a použijte tradiční techniky ladění prozkoumat chování těchto volání.  
  
2.  Otevřete **zásobník volání událostí grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **zásobník volání událostí grafiky**.  
  
3.  K vyhledání použít zásobníku volání `PSSetShader` volání ve zdrojovém kódu vaší aplikace. V **zásobník volání událostí grafiky** okně zvolte nejvyšší volání a zkontrolujte hodnotu, která shaderu pixelů je nastavena na. Shaderu pixelů může být nastaveno přímo na hodnotu null nebo null. hodnota může dojít z důvodu argument, který byl předán do funkce nebo jiný stav. Pokud není nastavena přímo, je možné najít zdroj hodnotu null někde zásobníkem volání. V tomto scénáři zjistíte, že shaderu pixelů je nastaven přímo na `nullptr` ve funkci nejvyšší, která má název `CubeRenderer::Render`:  
  
     ![Kód, který není inicializovat shaderu pixelů](media/gfx_diag_demo_misconfigured_pipeline_step_5.png "gfx_diag_demo_misconfigured_pipeline_step_5")  
  
    > [!NOTE]
    >  Pokud nemůže najít zdroj hodnotu null jenom tak, že prověří zásobníku volání, doporučujeme, aby nastavení podmíněné zarážky na `PSSetShader` volat, tak, aby spuštění programu dělí při shaderu pixelů bude nastavena na hodnotu null. Pak restartujte aplikaci v režimu ladění a používejte tradiční techniky ladění najít zdroj hodnotu null.  
  
 Chcete-li problém vyřešit, přiřaďte shaderu správné pixelů pomocí první parametr `ID3D11DeviceContext::PSSetShader` volání rozhraní API.  
  
 ![Opravené C&#43; &#43; zdrojový kód](media/gfx_diag_demo_misconfigured_pipeline_step_6.png "gfx_diag_demo_misconfigured_pipeline_step_6")  
  
 Po opravě kód, můžete ho znovu sestavte a spusťte aplikaci znovu k ověření, že se vyřešit problém vykreslování:  
  
 ![Objekt se nyní zobrazí](media/gfx_diag_demo_misconfigured_pipeline_resolution.jpg "gfx_diag_demo_misconfigured_pipeline_resolution")