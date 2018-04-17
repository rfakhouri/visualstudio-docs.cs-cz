---
title: 'Návod: Chybějící objekty z důvodu použití funkce Vertex Shading | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: e42b54a0-8092-455c-945b-9ecafb129d93
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 226f6177b98aae8159de10f752cde37632dca901
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-missing-objects-due-to-vertex-shading"></a>Návod: Chybějící objekty z důvodu použití funkce vertex shading
Tento návod ukazuje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky nástrojům pro zkoumání objekt, který nebyl nalezen z důvodu chyby, ke kterému dochází během fáze shaderu vrchol.  
  
 Tento návod ukazuje tyto úlohy:  
  
-   Pomocí **seznam událostí grafiky** najít potenciální zdroje problému.  
  
-   Pomocí **fáze zřetězení grafiky** okně a zkontrolujte účinek `DrawIndexed` volání Direct3D – rozhraní API.  
  
-   Pomocí **ladicí program HLSL** Prozkoumat shaderu vrchol.  
  
-   Pomocí **zásobník volání událostí grafiky** pomohou najít zdroj nesprávné HLSL konstanty.  
  
## <a name="scenario"></a>Scénář  
 Jednou z běžných příčin chybějící objektu v 3D aplikace nastane, když shaderu vrchol transformuje objektu vrcholy způsobem nesprávné nebo neočekávané – například objekt může být nastavit na velmi malou velikost, nebo transformovat tak, aby se objeví za fotoaparátu , nikoli úrovních před ním.  
  
 V tomto scénáři při spuštění aplikace to vyzkoušíte, pozadí se vykresluje podle očekávání, ale jeden z objektů se nezobrazí. Pomocí diagnostiky grafiky zaznamenáte tyto potíže k protokolu grafiky tak, že ladíte aplikaci. Problém je v aplikaci vypadat třeba takto:  
  
 ![Objekt je nemohou vidět. ] (media/gfx_diag_demo_missing_object_shader_problem.png "gfx_diag_demo_missing_object_shader_problem")  
  
## <a name="investigation"></a>Šetření  
 Soubor protokolu grafiky kontrola rámce zaznamenané během testu můžete načíst pomocí diagnostiky grafiky nástrojů.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>K prozkoumání rámce v protokolu grafiky  
  
1.  V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst grafiky protokol, který obsahuje rámce, který vykazuje chybějící objekt. Novou kartu protokolu grafiky se zobrazí v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. V horní části na této kartě je výstup cíl vykreslení vybraného rámce. V dolní části je **rámce seznamu**, zobrazuje každou zaznamenané rámce jako miniatury.  
  
2.  V **rámce seznamu**, vyberte snímek, který ukazuje, že se nezobrazí, objekt. Cíl vykreslení je aktualizována tak, aby odrážela vybraný snímek. V tomto scénáři protokolu grafiky karta vypadá takto:  
  
     ![Grafika protokolu dokumentu v sadě Visual Studio](media/gfx_diag_demo_missing_object_shader_step_1.png "gfx_diag_demo_missing_object_shader_step_1")  
  
 Po výběru rámce, který ukazuje problém, můžete začít diagnostikovat pomocí **seznam událostí grafiky**. **Seznam událostí grafiky** obsahuje každou Direct3D – volání rozhraní API, došlo k vykreslení active rámečku, například volání rozhraní API k nastavení stavu zařízení, abyste mohli vytvářet a aktualizovat vyrovnávací paměti a k vykreslení objekty, které se zobrazují v rámečku. Různé druhy volání je zajímavé, protože není často (ale ne vždy) odpovídající změnu cíl vykreslení, když aplikace funguje podle očekávání, například kreslení, odesílání, kopírování nebo zrušte volání. Kreslení volání jsou zvláště zajímavé, protože každé z nich představuje geometry, který vykreslí aplikace (volání odesílání může také zpracovat geometrie).  
  
 Protože víte, že chybí objekt není přitahuje k cíli vykreslení (v tomto případě) – ale, že zbývající scény vykreslením podle očekávání – můžete použít **seznam událostí grafiky** společně s **kanálu grafiky Fáze** nástroj k určení, které kreslení volání odpovídá geometrie chybějící objektu. **Fáze zřetězení grafiky** v okně se zobrazí geometry, který vám byl zaslán každé volání kreslení, bez ohledu na jeho dopad na cíl vykreslení. Při přesouvání prostřednictvím volání kreslení je fázemi kanálu se aktualizují zobrazíte geometry, který je přidružen toto volání a vykreslování cílový výstup se aktualizuje na Zobrazit stav cíl vykreslení po dokončení volání.  
  
#### <a name="to-find-the-draw-call-for-the-missing-geometry"></a>Najít kreslení volání pro chybějící geometrie  
  
1.  Otevřete **seznam událostí grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **seznam událostí**.  
  
2.  Otevřete **fáze zřetězení grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **fázemi kanálu**.  
  
3.  Jak přesunout iteraci v každém kreslení volání **seznam událostí grafiky** okno, sledovat **fáze zřetězení grafiky** okna pro objekt chybí. Chcete-li usnadnit tuto činnost, zadejte "Kreslení" v **vyhledávání** pole v pravém horním rohu **seznam událostí grafiky** okno. Tento filtrování seznamu tak, aby obsahoval jenom události, které mají "Kreslení" v jejich názvy.  
  
     V **fáze zřetězení grafiky** okně **vstup assembleru** fáze ukazuje geometrie objektu před jeho transformovaných a **vrchol shaderu** fáze zobrazuje stejné objekt po jeho transformaci. V tomto scénáři víte, že jste chybějícím objektu nalézt, jakmile se zobrazí v **vstup assembleru** fáze a nic se zobrazí v **vrchol shaderu** fáze.  
  
    > [!NOTE]
    >  Pokud dalších fázích geometrie – například fáze trupu shaderu, shaderu domény nebo geometrie shaderu – zpracovat objekt, by mohly být příčinou problému. Problém se obvykle týká nejdřívější fáze, ve kterém výsledek se nezobrazí, nebo způsobem, který se zobrazí.  
  
4.  Zastavte při dosažení kreslení volání, která odpovídá chybějícím objektu. V tomto scénáři **fáze zřetězení grafiky** okno označuje, že geometrie byl vydán pro grafický procesor (označená miniaturu assembleru vstup), ale nezobrazí v cílové vykreslování, protože došlo k chybě během fáze shaderu vrchol (označená miniaturu vrchol shaderu):  
  
     ![Událost DrawIndexed a jeho dopad na kanálu](media/gfx_diag_demo_missing_object_shader_step_2.png "gfx_diag_demo_missing_object_shader_step_2")  
  
 Po potvrzení, že aplikace vydala kreslení volání pro chybějící objekt geometrie a zjistit, že problém přetrvávat během fáze shaderu vrchol, můžete použít ladicí program HLSL sloužící ke zkoumání shaderu vrchol a zjistit, co se stalo s geometrie objektu. Můžete použít pro zjištění stavu proměnných HLSL během provádění krok prostřednictvím kód HLSL ladicí program HLSL a nastavit zarážky při diagnostice problému.  
  
#### <a name="to-examine-the-vertex-shader"></a>K prozkoumání vrchol shaderu  
  
1.  Spusťte ladění fázi shaderu vrchol. V **fáze zřetězení grafiky** okno, v části **vrchol shaderu** dvoufázové instalace, vyberte **spustit ladění** tlačítko.  
  
2.  Protože **vstup assembleru** fázi se zobrazí k poskytování dobrých dat shaderu vrchol a **vrchol shaderu** fáze se vytvořit žádný výstup, které chcete prověřit výstup shaderu vrchol struktura, `output`. Krocích kód HLSL pořídíte blíže vypadat při `output` je upravit.  
  
3.  Prvním `output` je změněn, člen `worldPos` je zapsán do.  
  
     ![Zobrazí se hodnota "output.worldPos" přiměřené](media/gfx_diag_demo_missing_object_shader_step_4.png "gfx_diag_demo_missing_object_shader_step_4")  
  
     Protože za přijatelné, zobrazí se jeho hodnota, budete pokračovat, procházení kódu až na další řádek, který upravuje `output`.  
  
4.  Při příštím `output` je změněn, člen `pos` je zapsán do.  
  
     ![Hodnota "output.pos" byla vynulován](media/gfx_diag_demo_missing_object_shader_step_5.png "gfx_diag_demo_missing_object_shader_step_5")  
  
     Tentokrát, hodnota `pos` člen – samými nulami – zdá se, že podezřelé. V dalším kroku, do které chcete určit, jak `output.pos` byly dodány s hodnotou samými nulami.  
  
5.  Zjistíte, že `output.pos` trvá svou hodnotu z proměnné, která se jmenuje `temp`. V předchozím řádku, můžete vidět, že hodnota `temp` je výsledkem násobení jejich předchozí hodnotu konstanta, která je s názvem `projection`. Máte podezření, že `temp`na podezřelé hodnota je výsledkem této násobení. Při přesunutí ukazatele myši na `projection`, si všimnete, že její hodnota je také samými nulami.  
  
     ![Projekce matice obsahuje chybný transformace](media/gfx_diag_demo_missing_object_shader_step_6.png "gfx_diag_demo_missing_object_shader_step_6")  
  
     V tomto scénáři, co zjistí, že `temp`na podezřelé hodnota je pravděpodobně způsobená jeho násobení podle `projection`a protože `projection` je konstanta, která má určené tak, aby obsahovala projekce matice, víte, že neměli obsahovat samými nulami.  
  
 Jakmile zjistíte, že konstanta HLSL `projection`– předaná do shaderu aplikace – je pravděpodobně zdroj problému, dalším krokem je možné vyhledat umístění ve zdrojovém kódu vaší aplikace kde vyplněno konstantní vyrovnávací paměti. Můžete použít **zásobník volání událostí grafiky** k vyhledání tohoto umístění.  
  
#### <a name="to-find-where-the-constant-is-set-in-your-apps-source-code"></a>Najít, kde je nastaven na konstantu ve zdrojovém kódu vaší aplikace  
  
1.  Otevřete **zásobník volání událostí grafiky** okno. Na **diagnostiky grafiky** nástrojů vyberte **zásobník volání událostí grafiky**.  
  
2.  Přejděte do zásobníku volání do zdrojového kódu vaší aplikace. V **zásobník volání událostí grafiky** okně zvolte volání nejvyšší chcete zobrazit, pokud existuje se naplní konstantní vyrovnávací paměti. Pokud není, dokud zjistíte, kde se naplní pokračujte zásobníkem volání. V tomto scénáři zjistíte, naplní konstantní vyrovnávací paměti – pomocí `UpdateSubresource` Direct3D rozhraní API – další až zásobníku volání ve funkci, která je s názvem `MarbleMaze::Render`, a že jeho hodnota pochází z objektu konstantní vyrovnávací paměti, který je pojmenován `m_marbleConstantBufferData` :  
  
     ![Kód, který nastaví vyrovnávací paměť konstantní objektu](media/gfx_diag_demo_missing_object_shader_step_7.png "gfx_diag_demo_missing_object_shader_step_7")  
  
    > [!TIP]
    >  Pokud jsou současně ladění aplikace, můžete nastavit zarážky v tomto umístění a při vykreslení další rámečku se setkají. Pak si můžete prohlédnout členů `m_marbleConstantBufferData` zkontrolujte, že hodnota `projection` člen je nastavený samými nulami, pokud je vyplněno konstantní vyrovnávací paměti.  
  
 Po vyhledat umístění, kde se naplní konstantní vyrovnávací paměti a zjistit, že jeho hodnoty pocházejí z proměnnou `m_marbleConstantBufferData`, dalším krokem je zjistit, kde `m_marbleConstantBufferData.projection` členů je nastaven na samými nulami. Můžete použít **najít všechny odkazy** rychle kontrolovala kód, který změní hodnotu `m_marbleConstantBufferData.projection`.  
  
#### <a name="to-find-where-the-projection-member-is-set-in-your-apps-source-code"></a>Najít, kde je nastaven člen projekce ve zdrojovém kódu vaší aplikace  
  
1.  Najít odkazy na `m_marbleConstantBufferData.projection`. Otevřete místní nabídku pro proměnnou `m_marbleConstantBufferData`a potom zvolte **najít všechny odkazy**.  
  
2.  Přejděte do umístění řádku ve zdrojovém kódu vaší aplikace kde `projection` člen je upravit, vyberte tento řádek ve **Najít výsledky Symbol** okno. Vzhledem k tomu, že na první výsledek, který mění člena projekce nemusí být příčinou problému, bude pravděpodobně nutné prozkoumat několika oblastech zdrojového kódu vaší aplikace.  
  
 Po nalezení umístění kde `m_marbleConstantBufferData.projection` není nastaven, můžete zkontrolovat okolního zdrojového kódu k určení původu nesprávnou hodnotu. V tomto scénáři je zjistit hodnotu `m_marbleConstantBufferData.projection` nastavena na místní proměnné s názvem `projection` před inicializací na hodnotu, která je dán kód `m_camera->GetProjection(&projection);` na následujícím řádku.  
  
 ![Před inicializací je nastaven mramor projekce](media/gfx_diag_demo_missing_object_shader_step_9.png "gfx_diag_demo_missing_object_shader_step_9")  
  
 Chcete-li problém vyřešit, je přesunout na řádek kódu, který nastaví hodnotu `m_marbleConstantBufferData.projection` po řádek, který inicializuje hodnoty místní proměnné `projection`.  
  
 ![Opravené C&#43; &#43; zdrojový kód](media/gfx_diag_demo_missing_object_shader_step_10.png "gfx_diag_demo_missing_object_shader_step_10")  
  
 Po opravě kód, můžete ho znovu sestavte a spusťte aplikaci znovu a zjistit, že se vyřešit problém vykreslování:  
  
 ![Objekt v nyní zobrazeny. ] (media/gfx_diag_demo_missing_object_shader_resolution.png "gfx_diag_demo_missing_object_shader_resolution")