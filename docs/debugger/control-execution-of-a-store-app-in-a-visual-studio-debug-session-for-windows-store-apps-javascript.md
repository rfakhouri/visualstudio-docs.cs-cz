---
title: "Řízení provádění aplikace UWP v sadě Visual Studio ladicí relace (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 60159535-61ec-466a-a4a6-115ec72a8af5
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 1e1e30400a630c7a5b01438e521b651f25ab3137
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="control-execution-of-a-uwp-app-in-a-visual-studio-debug-session-javascript"></a>Řízení provádění aplikace UWP v sadě Visual Studio ladicí relace (JavaScript)
Tento rychlý start ukazuje, jak se orientovat v ladicím programu sady Visual Studio a jak zobrazit stav programu v relaci.  
  
 Tento rychlý start je pro vývojáře, kteří jsou nové ladění pomocí sady Visual Studio a pro vývojáře, kteří chtějí získat další informace o navigace v sadě Visual Studio ladění relace. Neposkytuje obrázky o ladění sám sebe. Funkce v ukázkovém kódu jsou určena pouze pro předvedení ladění postupů popsaných v tomto tématu. Funkce nepoužívají osvědčené postupy při návrhu aplikace nebo funkce. Ve skutečnosti se rychle zjistit, že funkce a aplikace, není udělat nic většinu vůbec.  
  
 Části této úvodní byly navrženy tak, aby jako nezávislé nejmenší, můžete přeskočit všechny oddíl, který obsahuje informace, které jste již obeznámeni s. Také není nutné k vytvoření ukázkové aplikace. Ale doporučujeme ho a provedli proces co největší.  
  
 **Ladicí program klávesové zkratky.** Navigace v ladicím programu sady Visual Studio je optimalizovaná pro myši a klávesnice. Řada kroků v tomto tématu zahrnout klávesové zkratky nebo klávesovou zkratku shod Poznámka. Například (klávesové: F5) označuje zadáním klávesu F5, spustí nebo pokračuje v provádění ladicího programu.  
  
> [!NOTE]
>  **Vzor modulu**  
>   
>  Aplikace UWP často používají JavaScript *modulu vzor* k zapouzdření data a funkce na stránce. Vzor modulu pomocí jedné samoobslužné provádění a anonymní uzavření oddělit funkci stránky z globálního oboru názvů. V tomto tématu jsme volání této funkce *modulu*.  
  
## <a name="in-this-topic"></a>V tomto tématu  
 Další postup:  
  
 [Vytvoření ukázkové aplikace](#BKMK_Create_the_sample_app)  
  
 [Nastavit a spustit, aby se bod přerušení, krokování s vnořením funkce a zkontrolujte dat programu](#BKMK_Set_and_run_to_a_breakpoint__step_into_a_function__and_examine_program_data)  
  
 [Do, přes, a to z funkce](#BKMK_Step_into__over__and_out_of_functions)  
  
 [Nastavení podmíněné zarážky, spustit na pozici kurzoru a vizualizovat proměnné](#BKMK_Set_a_conditional_breakpoint__run_to_the_cursor__and_visualize_a_variable)  
  
 [Proměnné datové zobrazení v místní hodnoty – okno](#BKMK_View_variable_data_in_the_Locals_window)  
  
-   [Proměnné datové zobrazení a řetězec prototypu objektu](#BKMK_View_variable_data_and_the_prototype_chain_of_an_object)  
  
-   [Zkontrolujte data řetězu oboru](#BKMK_Examine_scope_chain_data)  
  
 [Přejít ke kódu pomocí okna zásobníkem volání.](#BKMK_Navigate_to_code_by_using_the_Call_Stack_window)  
  
##  <a name="BKMK_Create_the_sample_app"></a>Vytvoření ukázkové aplikace  
 Ladění je o kódu, takže ukázková aplikace používá rozhraní aplikace pro UPW jenom pro účely vytvoření zdrojový soubor, ve kterém uvidíte navigace na relaci ladění jak funguje a jak prozkoumat stav programu. Všechny kód, který bude vyvolán je volána z `module` funkce souboru default.js. Žádné události jsou zpracovávány a nebudou přidány žádné ovládací prvky.  
  
1.  **Vytvořte prázdnou aplikaci pro UPW v JavaScriptu.** Otevřete Visual Studio. Na domovské stránce vyberte **nový projekt** odkaz. Na **nový projekt** dialogovém okně vyberte **JavaScript** v **nainstalovaná** seznamu a potom zvolte **univerzální pro Windows**. V seznamu šablon projektu, zvolte **prázdná aplikace (univerzální pro Windows)**. Visual Studio vytvoří nové řešení a projektu a zobrazí soubor default.htm v editoru kódu.  
  
     Poznámka: soubory skriptu, které jsou načtené na stránku.  
  
    -   `base.js` a `ui.js` vytvořit soubory **knihovna Windows pro jazyk JavaScript**. Knihovna Windows pro jazyk JavaScript je sada JavaScript a CSS soubory, které usnadňují vytváření aplikace UWP pomocí jazyka JavaScript. Můžete tak používat společně s HTML, CSS a prostředí Windows Runtime k vytvoření aplikace.  
  
    -   Spustí kód v `default.js` souboru.  
  
2.  **Otevření zdrojového souboru default.js.** V Průzkumníku řešení otevřete **js** uzel a zvolte `default.js`.  
  
3.  **Obsah stránku nahraďte ukázkový kód.** Odstranit veškerý obsah z `default.js` souboru. Na tento odkaz: [ladicího programu navigační ukázkový kód (JavaScript)](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/debugger/samples/debugger-navigation-sample-code-javascript.js)a poté zkopírujte kód uvedený v části JavaScript do schránky. (Vyberte **zpět** v prohlížeči nebo programu help viewer se vraťte do této stránce Rychlý start.) V editoru Visual Studio vložte kód do prázdné nyní `default.js`. Zvolte **Ctrl + S** k uložení souboru.  
  
 Nyní můžete provést spolu s příklady v tomto tématu.  
  
##  <a name="BKMK_Set_and_run_to_a_breakpoint__step_into_a_function__and_examine_program_data"></a>Nastavit a spustit, aby se bod přerušení, krokování s vnořením funkce a zkontrolujte dat programu  
 Nejběžnější způsob, jak začít relaci ladění je vybrat **spustit ladění** z **ladění** nabídky (klávesové: F5). Aplikace spustí a pokračuje v provádění, dokud je dosaženo zarážku, ručně pozastavení provádění, dojde k výjimce, nebo ukončení aplikace.  
  
 Při spuštění je pozastavená v ladicím programu, můžete zobrazit hodnotu active proměnné v tip dat podle pozastavení myší na proměnnou.  
  
 Po pozastavení provádění aplikace (označovaný také rozdělení do ladicího programu), můžete k řízení způsobu, jakým provede zbytek kód programu. Můžete pokračovat řádek po řádku přesun z volání funkce do funkce samostatně, nebo volaná funkce můžete provést v jediném kroku. Tyto postupy se nazývají procházení aplikace. Můžete také obnovit standardní provádění spuštěné na další zarážku, který jste nastavili, nebo na řádek, kde je umístěn kurzor aplikace. Můžete zastavit relaci ladění kdykoli. Ladicí program je určen k provedení nezbytných operací čištění a ukončení provádění.  
  
###  <a name="BKMK_Example_1"></a>Příklad 1  
 V tomto příkladu nastavte zarážky v textu `module` fungovat v `default.js` jako zavolá první naše příkazy uživatele. Zobrazení hodnot proměnných v datových tipech ladicí program zanořte se do funkce a potom zastavte ladění.  
  
1.  **Nastavte zarážky.** Nastavte zarážky v příkaz `callTrack = "module function";` k tomu dojde hned po volání `app.start()`. Vyberte řádek v šedou barvou oddělovací mezery u editoru zdrojového kódu (klávesové: Umístěte kurzor na řádku a vyberte **F9** klíč).  
  
     ![Nastavte zarážky v test1](../debugger/media/dbg_jsnav_example1_breakpoint.png "DBG_JSNAV_example1_breakpoint")  
  
     Ikona zarážek se zobrazí v mřížky.  
  
2.  **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: F5).  
  
     Zahájí provádění a pozastaví spuštění bezprostředně před příkaz, ve kterém je nastavena zarážka aplikace. Ikonu aktuální řádek v mřížky identifikuje vaši polohu a zvýrazní aktuální příkaz.  
  
     ![Spustit na zarážek](../debugger/media/dbg_jsnav_example1_run_to_breakpoint.png "DBG_JSNAV_example1_run_to_breakpoint")  
  
     Jsou nyní v ovládacím prvku spuštění aplikace a zkontrolovat stav programu, v průběhu příkazy programu.  
  
3.  **Krok do funkce.** Na **ladění** nabídce zvolte **Krokovat s vnořením** (klávesové: **F11**).  
  
     ![Krokování s vnořením řádek kódu](../debugger/media/dbg_jsnav_example1_step_into.png "DBG_JSNAV_example1_step_into")  
  
     Všimněte si, že ladicí program přesune na další řádek, který je volání `example1` funkce. Zvolte **Krokovat s vnořením** znovu. Ladicí program přesune na první řádek kódu `example1` funkce. Zvýrazněný řádek nebyla provedena, ale funkce byla načtena v zásobníku volání a má přidělenou paměť pro místní proměnné.  
  
4.  Když je krok do řádek kódu, ladicí program provede jeden z následujících akcí:  
  
    -   Další příkaz není volání funkce ve vašem řešení, ladicí program spustí dotaz, přesune na další příkaz a potom pozastaví spuštění.  
  
    -   Pokud příkaz volání funkce ve vašem řešení, přesune na první řádek volaná funkce ladicího programu a potom pozastaví spuštění.  
  
     Přejděte ke kroku do prohlášení o `example1` dokud jste dosáhli místo přechodu. Ladicí program označuje pravé složené závorce složené funkce.  
  
5.  **Zobrazení hodnot proměnných v datových tipech.** Přejděte ke kroku do prohlášení o `example1` dokud jste dosáhli místo přechodu. Ladicí program označuje pravé složené závorce složené funkce. Když pozastavíte myši na název proměnné, název a hodnotu proměnné se zobrazují v data tip.  
  
     ![Zobrazit hodnoty proměnných v tipu data](../debugger/media/dbg_jsnav_data_tip.png "DBG_JSNAV_data_tip")  
  
6.  **Přidáte sledování pro proměnnou callTrack.** `callTrack` Proměnná se používá v rámci této úvodní k zobrazení funkce volané v příkladech. Aby bylo snazší zobrazíte hodnotu proměnné, přidejte ji do okna sledování. Vyberte název proměnné v editoru a potom zvolte **Přidat kukátko** z místní nabídky.  
  
     ![Podívejte se na proměnnou](../debugger/media/dbg_jsnav_watch_window.png "DBG_JSNAV_watch_window")  
  
     Můžete sledovat několika proměnných v okně Sledování. Hodnoty proměnných sledovaných, jako jsou hodnoty v systému windows tip dat, jsou aktualizovány při každém spuštění je pozastaveno. Sledované proměnných ukládají mezi relace ladění.  
  
7.  **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: **Shift + F5**). Tím končí relaci ladění.  
  
##  <a name="BKMK_Step_into__over__and_out_of_functions"></a>Do, přes, a to z funkce  
 Na rozdíl od zanoříte se do funkci s názvem nadřazené funkcí, krokování přes funkci spustí podřízené funkce a potom pozastaví spuštění ve volání funkce, jako nadřazený obnoví. Prostřednictvím funkce může krok, když se seznámíte se způsobem, jakým funkce funguje a si jisti, že jeho spuštění nebude mít vliv na problém, kterou zkoumáte.  
  
 Krokování s přes řádek kódu, který neobsahuje volání funkce provede řádku stejně jako zanoříte se do řádku.  
  
 Krokování s mimo funkci podřízené pokračuje v provádění funkce a potom pozastaví spuštění po funkce vrátí hodnotu jeho volání funkce. Může vystoupení ze dlouho funkce, když jste zjistili, že zbytek funkce není důležité.  
  
 Krokování s přes i krokování s mimo funkci spustit funkci.  
  
 ![Krok do, přes a mimo metody](../debugger/media/dbg_basics_stepintooverout.png "DBG_Basics_StepIntoOverOut")  
  
###  <a name="BKMK_Example_2"></a>Příklad 2  
 V tomto příkladu krok do, přes a mimo funkce.  
  
1.  **Volání funkce priklad2 ve funkci modulu.** Upravit `module` funkce a nahraďte tento řádek `var callTrack = "module function"` s `example2();`.  
  
     ![Volání funkce priklad2](../debugger/media/dbg_jsnav_example2.png "DBG_JSNAV_example2")  
  
2.  **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: F5). Ladicí program pozastaví spuštění u zarážky.  
  
3.  **Krok přes řádek kódu.** Na **ladění** nabídce zvolte **Krokovat s přeskočením** (klávesnice: F10). Ladicí program provede `var callTrack = "module function"` příkaz stejným způsobem jako zanoříte se do příkazu.  
  
4.  **Krokovat s vnořením priklad2 a example2_a.** Vyberte **F11** klíče k krokování s vnořením `example2` funkce. Krokovat s vnořením i nadále `example2` příkazy, dokud se nedostanete na řádku `var x = example2_a();`. Opakujte krok do tohoto řádku přesunout do vstupní bod `example2_a`. Přejděte ke kroku do každé prohlášení o `example2_a` až se vrátíte do `example2`.  
  
     ![Krok přes funkci](../debugger/media/dbg_jsnav_example2_a.png "DBG_JSNAV_example2_a")  
  
5.  **Krok přes funkci.** Všimněte si, že na další řádek v `example2`, `var y = example2_a();` je v podstatě stejný jako předchozí řádek. Můžete bezpečně přeskočit tento řádek. Vyberte **F10** klíč pro přesun z obnovení z `example2` do druhé volání `example2_a`. Všimněte si, že `callTrack` označuje řetězec `example2_a` funkce byla spuštěna dvakrát.  
  
6.  **Krok mimo funkci.** Vyberte **F11** klíče k krokování s vnořením `example2_b` funkce. Všimněte si, že `example2_b` není příliš neliší od `example2_a`. Chcete-li krok mimo funkci, zvolte **Krokovat s Vystoupením** na **ladění** nabídky (klávesnice: **Shift + F11**). Všimněte si, že `callTrack` proměnná Určuje, že `example2_b` byla spuštěna a zda ladicího programu vrátila do bodu kde `example2` obnoví.  
  
7.  **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: **Shift + F5**). Tím končí relaci ladění.  
  
##  <a name="BKMK_Set_a_conditional_breakpoint__run_to_the_cursor__and_visualize_a_variable"></a>Nastavení podmíněné zarážky, spustit na pozici kurzoru a vizualizovat proměnné  
 Podmíněné zarážky Určuje podmínku, která způsobí, že ladicí program na pozastavení provádění. Podmínka je zadaný libovolný kód výraz, který může být vyhodnocen jako true nebo false. Můžete například použít podmíněné zarážky pro zjištění stavu program v často volaná funkce jenom v případě, že proměnné dosáhne určitou hodnotu.  
  
 Jako nastavení jednorázové zarážek je spuštěná na pozici kurzoru. Při spouštění je pozastaveno, můžete vybrat řádek ve zdroji a pokračovat v provádění dokud nebude dosaženo vybraný řádek. Například je může krokování smyčku ve funkci a určit, že kód ve smyčce pracuje správně. Místo procházení každé iteraci smyčky, můžete spustit na kurzor, který je umístěn po provedení smyčky.  
  
 V některých případech je obtížné zobrazit hodnotu proměnné v řádku tip dat nebo jiných dat okna. Ladicí program, můžete zobrazit v vizualizér text, který představuje formátovaný zobrazení na hodnoty v posuvného okna řetězců, HTML a Xml.  
  
###  <a name="BKMK_Example_3"></a>Příklad 3  
 V tomto příkladu nastavíte podmíněné zarážky k přerušení na konkrétní iteraci smyčky a potom spusťte pro kurzor, který je umístěn za smyčky. Hodnota proměnné se také zobrazit v vizualizéru text.  
  
1.  **Volání funkce example3 ve funkci modulu.** Upravit `module` funkce a nahraďte tento řádek `var callTrack = "module function";` řádek `example3();`.  
  
     ![Volání example3](../debugger/media/dbg_jsnav_example3.png "DBG_JSNAV_example3")  
  
2.  **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: **F5**). Ladicí program pozastaví spuštění u zarážky v `module` funkce.  
  
3.  **Krok do funkce example3.** Zvolte **Krokovat s vnořením** na **ladění** nabídky (klávesové: **F11**) přesunout do vstupní bod `example3` funkce. Krokování do funkce, dokud nebude mít vstupní jedno nebo dvě smyčky z pokračovat `for` bloku. Všimněte si, že ho by vám neměl zabrat dlouhou dobu projděte všechny 1000 iterací.  
  
4.  **Nastavení podmíněné zarážky.** V levém oddělovací mezery u okno kódu, klikněte pravým tlačítkem na řádku `s += i.toString() + "\n";` a potom zvolte **podmínku** v místní nabídce.  
  
     Vyberte **podmínku** zaškrtněte políčko a potom zadejte `i == 500;` v textovém poli. Vyberte **platí** možnost a zvolte **OK**. Zarážce umožňuje zkontrolujte hodnotu v 500th iterace `for` smyčky. Ikona podmíněného zarážek lze určit podle jeho bílé mezi.  
  
     ![Ikona zarážek podmíněný](../debugger/media/dbg_jsnav_breakpoint_condition_icon.png "DBG_JSNAV_Breakpoint_Condition_icon")  
  
5.  **Spusťte na zarážku.** Na **ladění** nabídce zvolte **pokračovat** (klávesnice: **F5**). Ukazatele myši na `i` zkontrolujte, že aktuální hodnota `i` je 500. Všimněte si také, že proměnná `s` je reprezentován jako jeden řádek a je mnohem delší než okno tip data.  
  
6.  **Vizualizace proměnnou string.** Klikněte na ikonu lupy v špičky data `s`.  
  
     Zobrazí se okno vizualizér Text a hodnota řetězce, který se zobrazí jako řetězec s více řádky.  
  
     ![Ladění vizualizéru text](../debugger/media/dbg_jsnav_text_visualizer.png "DBG_JSNAV_Text_Visualizer")  
  
7.  **Spusťte na pozici kurzoru.** Vyberte řádek `callTrack += "->example3";` a potom zvolte **spustit ke kurzoru** v místní nabídce (klávesové: **Ctrl + F10**). Ladicí program dokončí iterace smyčky a potom na řádku pozastaví spuštění.  
  
8.  **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: **Shift + F5**). Tím končí relaci ladění.  
  
###  <a name="BKMK_Use_Run_to_Cursor_to_return_to_your_code_and_delete_a_breakpoint"></a>Použití spustit ke kurzoru se vrátíte do vašeho kódu odstranění zarážky  
 Spuštěná na pozici kurzoru může být velmi užitečná, když máte stupeň do knihovny kódu od společnosti Microsoft nebo třetích stran. Při procházení kód knihovny může být informativní, často může trvat dlouhou dobu. A obvykle vás zajímá mnohem víc v kódu. Toto cvičení se dozvíte, jak to udělat.  
  
1.  **Nastavte zarážky v app.start volání.** V `module` funkce, nastavení boru přerušení na řádku`app.start()`  
  
2.  **Spusťte na zarážku a zanořte se do funkce knihovny.**  
  
     Pokud krok do `app.start()`, zobrazí kód v editoru `base.js`. Krok do několika další řádky.  
  
3.  **Krok přes a mimo funkce.** Jako krok přes (**F10**) a z kroku (**SHIFT + F11**) kód na `base.js`, může dojít k závěru, že zkoumání složitost a délka funkce start je, není co chcete to.  
  
4.  **Nastavte kurzor na kód a spusťte na ni.** Přepněte zpátky na `default.js` souboru v editoru kódu. Vyberte první řádek kódu po `app.start()` (nemůžete spustit na komentář nebo prázdné řádky). Zvolte **spustit ke kurzoru** z místní nabídky. Ladicí program pokračuje v provádění funkce app.start a pozastaví spuštění u zarážky.  
  
##  <a name="BKMK_View_variable_data_in_the_Locals_window"></a>Proměnné datové zobrazení v místní hodnoty – okno  
 Místní hodnoty – windows je stromové zobrazení parametry a proměnné v oboru řetězu aktuálně prováděné funkce.  
  
###  <a name="BKMK_View_variable_data_and_the_prototype_chain_of_an_object"></a>Proměnné datové zobrazení a řetězec prototypu objektu  
  
1.  **Přidejte objekt array funkci modulu.** Upravit `module` funkce a nahraďte tento řádek `var callTrack = "module function"` s`var myArray = new Array(1, 2, 3);`  
  
     ![definice pole](../debugger/media/dbg_jsnav_myarray.png "DBG_JSNAV_myArray")  
  
2.  **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: **F5**). Ladicí program pozastaví spuštění u zarážky. Krokovat s vnořením na řádek.  
  
3.  **Otevřete okno lokální.** Na **ladění** nabídky, přejděte na příkaz **Windows**a potom zvolte **místní hodnoty –**. (Klávesové: Alt + 4).  
  
4.  **Zkontrolujte místní proměnné ve funkci modulu** místní hodnoty – windows zobrazí proměnné aktuálně prováděné funkce ( `module` funkce) jako nejvyšší úrovně uzly stromu. Po zadání funkce JavaScript vytvoří všech proměnných a poskytne jim hodnotu `undefined`. Funkce, které jsou definovány ve funkci mají jejich text jako hodnotu.  
  
     ![Místní hodnoty – okno](../debugger/media/dbg_jsnav_locals_window.png "DBG_JSNAV_Locals_window")  
  
5.  **Projděte definice callTrack a pole.** Najít callTrack a pole proměnných v místní hodnoty – okno. Krok přes (**F10**) dvě definice a Všimněte si, že **hodnotu** a **typ** došlo ke změně pole. Místní hodnoty – okno označuje hodnoty proměnných, které se změnily od poslední rozdělení.  
  
6.  **Zkontrolujte pole objekt** Rozbalit `myArray` proměnné. Každý element pole, je uvedena **[prototypu]** uzlu, který obsahuje hierarchii dědičnosti `Array` objektu. Tento uzel.  
  
     ![Řetězec prototypu v místní hodnoty – okno](../debugger/media/dbg_jsnav_locals_proto_chain.png "DBG_JSNAV_Locals_proto_chain")  
  
    -   **Metody** uzlu uvádí všechny metody `Array` objektu.  
  
    -   **[Prototypu]** uzel obsahuje prototyp z `Object` objekt, ze kterého `Array` je odvozený. **[prototypu]**  uzly mohou být rekurzivní. Každý nadřazený objekt v hierarchii objektu je podrobněji popsaná **[prototypu]** uzlu jeho podřízených.  
  
7.  **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: Shift + F5). Tím končí relaci ladění.  
  
##  <a name="BKMK_Examine_scope_chain_data"></a>Zkontrolujte data řetězu oboru  
 *Obor řetězu* funkce zahrnuje všechny proměnné, které jsou aktivní a dosažitelný pomocí funkce. Globální proměnné jsou součástí řetězce rozsahu jsou všechny objekty (včetně funkce), které jsou definované ve funkci, která definuje aktuálně prováděné funkce. Například `callTrack` proměnné, která je definována v `module` funkce `default.js` je dostupná pro všechny funkce, která je definována v `module` funkce. Každý obor je v místní hodnoty – okno uvedené odděleně.  
  
-   Proměnné aktuálně prováděné funkce jsou uvedeny v horní části okna.  
  
-   Proměnné každý rozsah funkce v řetězu oboru jsou uvedeny v seznamu **[oboru]** uzel pro funkci. Obor funkcí jsou uvedeny podle jejich pořadí v řetězu z funkce, která definuje funkci current pro nejzevnější funkce řetězu.  
  
-   **[Globals]** uzlu uvádí globální objekty, které jsou definovány mimo žádné funkce.  
  
 Obor řetězy může být matoucí a jsou nejlépe ukazuje příklad. V následujícím příkladu se zobrazí jak `module` funkce vytvoří vlastní rozsah a jak můžete vytvořit další úroveň oboru tak, že vytvoříte uzavření.  
  
###  <a name="BKMK_Example_4"></a>Příklad 4  
  
1.  **Volání funkce example4 z funkce modulu.** Upravit `module` funkce a nahraďte tento řádek `var callTrack = "module function"` s `example4()`:  
  
     ![Volání example4](../debugger/media/dbg_jsnav_example4.png "DBG_JSNAV_example4")  
  
2.  **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: **F5**). Ladicí program pozastaví spuštění u zarážky.  
  
3.  **Otevřete okno lokální.** V případě potřeby na **ladění** nabídky, přejděte na příkaz **Windows**a potom zvolte **místní hodnoty –**. (Klávesové: **Alt + 4**). Upozorňujeme, že okno obsahuje seznam všech proměnných a funkce `module` fungovat a také obsahuje **[Globals]** uzlu.  
  
4.  **Zkontrolujte globální proměnné.** Rozbalte **[Globals]** uzlu. Objekty a proměnných ve globální byly nastavené zásadami knihovně systému Windows pro jazyk JavaScript. Vlastní proměnné můžete přidat do globálního oboru.  
  
5.  **Krokovat s vnořením example4 a zkontrolujte jeho místní a obor proměnné** krok do (klávesové: **F11**) `example4` funkce. Protože `example4` je definována v `module` funkce, `module` funkce se změní na nadřazeném oboru. `example4`můžete volat funkce v `module` funkce a přístup k jeho proměnné. Rozbalte **[oboru]** uzlu v místní hodnoty – okno a Všimněte si, že obsahuje stejný a proměnné `module` funkce.  
  
     ![Obory metody example4](../debugger/media/dbg_jsnav_locals_example4_scope.png "DBG_JSNAV_Locals_example4_scope")  
  
6.  **Krokovat s vnořením example4_a a zkontrolujte jeho místní a obor proměnné** nadále krok do `example4` a do volání `example4_a`. Všimněte si, že místní proměnné jsou nyní z `example4_a`a že **[oboru]** uzlu pokračuje k uložení proměnné `module` funkce. I když proměnné `example4` jsou aktivní, nemůže být dosaženo pomocí `example4_a` a nadále již nebudou součástí řetězu oboru.  
  
7.  **Krokovat s vnořením multipyByA a zkontrolujte jeho místní a obor proměnné** krok procházení zbytku `example4_a` a do řádku `var x = multilpyByA(b);`.  
  
     Proměnná funkce `multipyByA` byla nastavena na `multiplyClosure` funkci, která je *uzavření*. `multipyClosure`definuje a vrátí vnitřní funkce, `mulitplyXby`a zachytí (zavře přes) proměnné a parametru. Vrácený vnitřní funkce v uzavřít, má přístup k datům vnější funkce a tak vytvoří vlastní úroveň oboru.  
  
     Pokud krok do `var x = multilpyByA(b);`, přesunete do `return a * b;` řádek v `mulitplyXby` vnitřní funkce.  
  
8.  V okně místních položek jenom parametr `b` je uveden jako místní proměnné v `multiplyXby`, ale nové **[oboru]** úroveň byla přidána. Rozbalením tohoto uzlu, uvidíte, že obsahuje parametry, funkce a proměnné `multiplyClosure`, včetně `a` proměnná volat v prvním řádku `multiplyXby`. Rychlá kontrola druhého **[oboru]** uzlu zjistí proměnné funkce modulu, který `multiplyXby` přistupuje v jeho další řádek.  
  
     ![Obory uzavření v místní hodnoty – okno](../debugger/media/dbg_jsnav_scope_mulitplyxby.png "DBG_JSNAV_scope_mulitplyXby")  
  
9. **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: **Shift + F5**). Tím končí relaci ladění.  
  
##  <a name="BKMK_Navigate_to_code_by_using_the_Call_Stack_window"></a>Přejít ke kódu pomocí okna zásobníkem volání.  
 V zásobníku volání je datová struktura, která obsahuje informace o funkcích, které jsou prováděny v aktuální vlákno aplikace. Při zásahu zarážku v okně zásobník volání se zobrazí seznam všech funkcí, které jsou aktivní v zásobníku. Aktuálně prováděné funkce je v horní části seznamu okna zásobník volání. Funkce, která zahájí vlákno je v dolní části seznamu. Funkce v mezi zobrazit cesty volání z Inicializace funkce na aktuální funkce.  
  
 Kromě zobrazení volání cestu k aktuálně prováděné funkce, okno zásobník volání lze přejít ke kódu v editoru kódu. Tato funkce může být užitečné, když pracujete s více soubory a chcete rychle přesunout do určité funkce.  
  
###  <a name="BKMK_Example_5"></a>Příklad 5  
 V tomto příkladu krok do volání cestu, která obsahuje pět uživatelsky definované funkce.  
  
1.  **Volání funkce example5 ve funkci modulu.** Upravit `module` funkce a nahraďte tento řádek `var callTrack = "module function";` řádek `example5();`.  
  
     ![Volání example5](../debugger/media/dbg_jsnav_example5.png "DBG_JSNAV_example5")  
  
2.  **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: **F5**). Ladicí program pozastaví spuštění u zarážky ve funkci modulu.  
  
3.  **Otevřete okno zásobník volání.** Na **ladění** nabídce zvolte **Windows**a potom zvolte **zásobníkem volání** (klávesové: Alt + 7). Všimněte si, že v okně zásobník volání zobrazí dvě funkce:  
  
    -   **Globální kód** je vstupní bod `module` funkce v dolní části zásobníku volání.  
  
    -   **Anonymní funkce** ukazuje na řádku `module` funkce, kde došlo k pozastavení. Toto je horní části zásobníku volání.  
  
4.  **Krok do funkcí k dosažení example5_d funkce.** Zvolte **Krokovat s vnořením** na **ladění** nabídky (klávesové: **F11**) k provádění volání v v cestě volání, dokud se nedostanete vstupní bod funkce example5_d. Všimněte si, že pokaždé, když, funkce volá funkci, číslo řádku volání funkce je uloženo a volaná funkce je umístěn v horní části zásobníku. Číslo řádku volání funkce je okamžiku, kdy má volající funkce pozastavený provádění. Žlutá šipka odkazuje na aktuálně prováděné funkce.  
  
     ![Okno zásobník volání](../debugger/media/dbg_jsnav_callstack_windows.png "DBG_JSNAV_CallStack_windows")  
  
5.  **Použití okna zásobník volání a přejít ke kódu example5_a nastavit zarážky.** V okně zásobník volání, vyberte `example5_a` položky seznamu a potom zvolte **přejít na zdrojové** v místní nabídce. Editor kódu nastaví jeho kurzor na návratový řádku funkce. Na tomto řádku nastavte zarážky. Všimněte si, že se změnila aktuálního řádku provádění. Pouze editor kurzor se přesunul.  
  
6.  **Krok do funkce a znovu spusťte na zarážku.** Pokračovat zanoříte se do `example5_d`. Všimněte si, že při návratu z funkce, je považován vypnout zásobníku volání. Stiskněte klávesu **F5** pokračujte spuštění programu. Zastavíte u zarážky vytvořili v předchozím kroku.  
  
7.  **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: **Shift + F5**). Tím končí relaci ladění.  
  
## <a name="see-also"></a>Viz také  
 [Spusťte relaci ladění (JavaScript)](../debugger/start-a-debugging-session-for-store-apps-in-visual-studio-javascript.md)   
 [Rychlý úvod: Ladicí program, navigační (JavaScript)](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md)   
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)   
 [Aktivovat pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)
