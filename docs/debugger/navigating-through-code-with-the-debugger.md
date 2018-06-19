---
title: Procházení kódu s ladicím programem v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.execution
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 759072ba-4aaa-447e-8e51-0dd1456fe896
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae96b360620a58fa323d080e6262c7f2966fa160
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479735"
---
# <a name="navigate-code-with-the-visual-studio-debugger"></a>Procházení kódu s ladicím programu sady Visual Studio
Seznamte se s příkazy a zkratky přejděte kódu v ladicím programu a který bude rychlejší a snazší najít a vyřešte problémy v aplikaci. Když přejdete kódu v ladicím programu, můžete zkontrolovat stav vaší aplikace nebo Další informace o toku jeho spuštění.  
  
## <a name="start-debugging"></a>Spuštění ladění  
 Často spustit ladění pomocí relace **F5** (**ladění** > **spustit ladění**). Tento příkaz spustí vaše aplikace s ladicím programem připojen.  
  
 Na zelenou šipku také spuštění ladicího programu (stejné jako **F5**).  
  
 ![DBG&#95;Basics&#95;Start&#95;Debugging](../debugger/media/dbg_basics_start_debugging.png "DBG_Basics_Start_Debugging")  
  
 Zahrnují několik způsobů spuštění aplikace s ladicím programem připojené **F11** ([kroku do kódu](#BKMK_Step_into__over__or_out_of_the_code)), **F10** ([krok přes kód](#BKMK_Step_over_Step_out)), nebo pomocí **spustit ke kurzoru**.  Na co dělat tyto možnosti najdete v dalších částech tohoto tématu informace.  
  
 Při ladění, žlutý řádek zobrazuje kód, který provede další.  
  
 ![DBG&#95;Basics&#95;Break&#95;Mode](../debugger/media/dbg_basics_break_mode.png "DBG_Basics_Break_Mode")  
  
 Při ladění, můžete přepínat mezi příkazy, jako je **F5**, **F11** a používat další funkce popsané v tomto tématu (například zarážky) rychle získat na kód, který chcete zobrazit v.  
  
 Většinu funkcí ladicího programu, například zobrazení hodnot proměnných v místní hodnoty – okno nebo vyhodnocení výrazů v okně sledovat jsou k dispozici pouze tehdy, když je pozastaven ladicího programu (také nazývané *režimu pozastavení*). Když ladicího programu je pozastavena, vaše aplikace stav je pozastaveno při funkce a proměnné, a objekty zůstanou v paměti. V režimu pozastavení, můžete zkontrolovat elementy pozic a stavy jejich vyhledání porušení nebo oznámení chyb. Pro některé typy projektů můžete také provádět úpravy aplikace v režimu pozastavení. Pokud chcete přehrát video, zobrazuje tyto funkce, najdete v části [Začínáme s ladicím programem](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6).
  
##  <a name="BKMK_Step_into__over__or_out_of_the_code"></a> Krok do kódu, řádek po řádku  
 Chcete-li zastavit na každém řádku kódu (každý příkaz) při ladění, použijte **F11** klávesové zkratky (nebo **ladění** > **Krokovat s vnořením** v nabídce).  
  
> [!TIP]
>  Při spuštění všech řádků kódu, můžete podržet přes proměnné najdete v části jejich hodnoty, nebo používat [místní hodnoty –](../debugger/autos-and-locals-windows.md) a [sledovat](../debugger/autos-and-locals-windows.md) windows můžete sledovat jejich hodnoty změnit.  
  
 Tady jsou některé podrobnosti o chování **Krokovat s vnořením**:  
  
-   Při volání vnořené funkce **Krokovat s vnořením** kroky do nejvíce hluboko vnořené funkce. Pokud používáte **Krokovat s vnořením** při volání jako `Func1(Func2())`, ladicí program do funkce `Func2`.  
  
-   Ve skutečnosti ladicí program prostřednictvím kódu příkazy spíše než fyzické řádky. Například `if` klauzule lze zapisovat na jeden řádek:  
  
    ```csharp  
    int x = 42;  
    string s = "Not answered";  
    if( int x == 42) s = "Answered!";  
    ```  
  
    ```VB  
    Dim x As Integer = 42  
    Dim s As String = "Not answered"  
    If x = 42 Then s = "Answered!"  
    ```  
  
     Když zanořte se do tohoto řádku, ladicí program považuje za jeden krok a důsledkem jako jiné podmínku (v tomto příkladu je podmínka true).  
  
 Vizuální sledování zásobníku volání při zanoříte se do funkce, najdete v tématu [mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
##  <a name="BKMK_Step_over_Step_out"></a> Krok prostřednictvím kódu, přeskočení funkce  
 Při spuštění kódu v ladicím programu, často se zjistíte, že nemusíte najdete, co se stane, že v konkrétní funkce (vám nezáleží ho nebo vy víte, že funguje, jako například dobře otestované knihovny kódu). Pomocí následujících příkazů můžete přeskočit prostřednictvím kódu (funkce spustit, samozřejmě, ale je přeskočen ladicího programu).  
  
|Příkaz klávesnice|Příkaz nabídky|Popis|  
|----------------------|------------------|-----------------|  
|**F10**|**Krok přes**|Pokud aktuální řádek obsahuje volání funkce, **Krokovat s přeskočením** spustí kód pak pozastaví spuštění na prvním řádku kódu po vyvolání funkce vrátí hodnotu.|  
|**Shift+F11**|**Krok**|**Krokovat s Vystoupením** pokračuje spuštění kódu a pozastaví spuštění, když aktuální funkce vrátí hodnotu (ladicí program přeskočí prostřednictvím funkci current).|  
  
> [!TIP]
>  Pokud potřebujete nalézt vstupní bod v aplikaci, začínat **F10** nebo **F11**. Tyto příkazy jsou často užitečné při kontrole stavu vaší aplikace nebo při pokusu o další informace o toku jeho spuštění.  
  
##  <a name="BKMK_Break_into_code_by_using_breakpoints_or_Break_All"></a> Spustit na konkrétní umístění nebo funkce  
 Často preferovanou metodu ladění kódu, tyto metody jsou užitečné, když víte přesně co kód, který chcete zkontrolovat nebo alespoň víte, ve které chcete spustit ladění.  
  
-   **Nastavit zarážky v kódu**  
  
     Pokud chcete nastavit jednoduché zarážky v kódu, otevření zdrojového souboru v editoru Visual Studio. Nastavit kurzor na řádek kódu, kde chcete pozastavit provádění, klikněte pravým tlačítkem v okně kód, který chcete zobrazit kontextovou nabídku a vyberte možnost **zarážek > Vložit zarážku** (nebo stiskněte klávesu **F9**). Ladicí program pozastaví spuštění vpravo před provedením řádku.  
  
     ![Nastavit zarážky](../debugger/media/dbg_basics_setbreakpoint.png "DBG_Basics_SetBreakpoint")  
  
     Zarážky v sadě Visual Studio poskytují širokou škálu další funkce, například podmíněné zarážky a tracepoints. V tématu [použití zarážek](../debugger/using-breakpoints.md).  
  
-   **Spustit, aby se umístění kurzoru**  
  
     Spustit na umístění kurzoru, umístěte kurzor na spustitelný soubor řádku kódu v okně zdroje. V okně editor kontextovou nabídku (v editoru klikněte pravým tlačítkem), zvolte **spustit ke kurzoru**. Toto je jako nastavení dočasné zarážky.

-   **Spustit kliknutím** 

    Pokud chcete spustit na bod v kódu při pozastavena v ladicím programu, vyberte **spuštění zde** ikonu zelenou šipku (při se zobrazí ikona ukazatele myši na řádek kódu). Tím se eliminuje potřeba nastavit dočasné zarážky.

    ![Ladicí program je spustit kliknutím](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

    > [!NOTE]
    > **Spustit kliknutím** je nového v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].
  
-   **Ručně rozdělit na kód**  
  
     Chcete-li rozdělit na další řádky kódu v aplikaci, provádění, zvolte **ladění**, **přerušení všech** (klávesnice: **Ctrl + Alt + Break**). 
  
     Pokud jste rozdělit při provádění kódu bez odpovídající zdroj nebo symbolu (.pdb) soubory), zobrazí ladicího programu **soubory nebyl nalezen zdroj** nebo **symboly nebyl nalezen** stránky, které vám pomůžou najít odpovídající soubory. V tématu [zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md). Pokud máte přístup k podpůrné soubory, můžete stále ladění sestavení pokyny v okně zpětný překlad.  
  
-   **Spusťte funkci v zásobníku volání**  
  
     V **zásobníkem volání** okno (k dispozici při ladění), vyberte funkce, klikněte pravým tlačítkem myši a zvolte **spustit ke kurzoru**. Vizuální sledování zásobníku volání, najdete v tématu [mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
-   **Spusťte funkci zadaný podle názvu**  
  
     Ladicí program na aplikaci spustit, dokud nebude dosaženo zadaná funkce se dá zjistit. Funkce lze zadat pomocí názvu nebo je možné v zásobníku volání.  
  
     Určit název funkce, vyberte **ladění**, **nové zarážek**, **rozdělit na funkce**, pak zadejte název funkce a další identifikační informace.  
  
     ![Dialogové okno Nový zarážek](../debugger/media/dbg_execution_newbreakpoint.png "DBG_Execution_NewBreakpoint")  
  
     Pokud funkce je přetížena, nebo je v více názvů, můžete vybrat funkce, které chcete v **vybrat zarážky** dialogové okno.  
  
     ![Vybrat zarážky – dialogové](../debugger/media/dbg_execution_overloadedbreakpoints.png "DBG_Execution_OverloadedBreakpoints")  
  
##  <a name="BKMK_Set_the_next_statement_to_execute"></a> Přesuňte ukazatel na tok provádění změn  
 Při ladicího programu je pozastavena, můžete přesunout ukazatel instrukce nastavit další příkaz kódu, které by šlo spustit. Žlutý šipku na okraji zdroj nebo okno zpětný překlad označuje umístění další příkaz má být proveden. Přesunutím tento šipku, můžete přeskočit část kódu nebo vrátit do řádku dříve provést. Můžete použít pro situace, jako je přeskočení části kódu, který obsahuje známé chyby.  
  
 ![Přesunutí ukazatele](../debugger/media/dbg_basics_example3.gif "DBG_Basics_Example3")
  
 Pokud chcete nastavit další příkaz provést, použijte jeden z následujících postupů:  
  
-   V okně zdroj přetáhněte šipku žlutý do umístění, kde chcete nastavit další příkaz ve stejném souboru zdroje  
  
-   V okně zdroj, nastavte kurzor na řádek, který chcete spustit další, klikněte pravým tlačítkem a vyberte možnost **další příkaz Set**.  
  
-   V okně zpětný překlad nastavte kurzor na pokyn sestavení, který chcete spustit další, klikněte pravým tlačítkem na a zvolte **další příkaz Set**.  
  
> [!CAUTION]
>  Nastavení další příkaz způsobí, že čítač program přejít přímo do nového umístění. Použijte tento příkaz s upozorněním:  
>   
>  -   Pokyny mezi body staré a nové spuštění nebudou provedeny.  
> -   Pokud přesunete bodu spuštění zpětné, nejsou použité pokyny vrátit zpět.  
> -   Přesunutí další příkaz jiné funkce nebo oboru obvykle za následek poškození zásobníku volání, způsobí spuštění chyby nebo výjimky. Pokud se pokusíte přesunutí další příkaz do jiného oboru, ladicího programu otevře dialogové okno s upozorněním a můžete tak na tlačítko Storno. V jazyce Visual Basic nelze přesunout do jiného oboru nebo funkce další příkaz.  
> -   V nativním kódu C++ Pokud máte kontroly runtime povoleno, nastavení další příkaz může způsobit výjimku vyvolána, pokud se spuštění dosáhne konce metodu.  
> -   Když upravit a pokračovat, je povoleno, **další příkaz Set** nezdaří, pokud jste provedli úpravy, které upravit a pokračovat nelze přemapovat okamžitě. Tato situace může nastat, například pokud jste upravili kódu do bloku catch. V takovém případě se zobrazí chybovou zprávu, která sděluje, že operace není podporována.  
  
> [!NOTE]
>  Ve spravovaném kódu nemůžete přesunout další příkaz za následujících podmínek:  
>   
>  -   Další příkaz je v jinou metodu než aktuální příkaz.  
> -   Ladění byl spuštěn s použitím těsně za běhu ladění.  
> -   Probíhá unwind zásobník volání.  
> -   Byla vyvolána výjimka System.StackOverflowException nebo System.Threading.ThreadAbortException.  
  
 Další příkaz nelze nastavit, když aktivně vaše aplikace běží. Pokud chcete nastavit další příkaz, musí být ladicí program v režimu pozastavení.  
  
## <a name="BKMK_Restrict_stepping_to_Just_My_Code"></a>Krok do neuživatelských kódu  
 Ve výchozím nastavení, ladicí program pokusí tak, aby zobrazovalo pouze kódu aplikace při ladění, což je dáno ladicí program názvem *pouze můj kód*. (Viz [pouze můj kód](../debugger/just-my-code.md) jak to funguje pro různé typy projektů a jazyky a jak může přizpůsobit chování.) Ale někdy při ladění, můžete se podívat na framework kódu, kód třetích stran knihovny nebo volání do operačního systému (systémová volání).  
  
 Pouze můj kód můžete vypnout tak, že přejdete do **nástroje** > **možnosti** > **ladění** a zrušte zaškrtnutí **povolit volbu pouze vlastní kód** zaškrtávací políčko.  
  
 Pouze můj kód zakázána, ladicího programu můžete kroku do kódu neuživatelských a bez uživatelského kódu se zobrazí v ladicího programu.  
  
> [!NOTE]
>  Pouze můj kód není podporována pro projekty zařízení.  
  
 **Krokovat s vnořením systémová volání**  
  
 Pokud načtený symboly pro ladění pro kód systému a pouze můj kód není povolena, můžete se stejně jako ostatní volání do systémového volání okna krok.  
  
 Pro přístup k souborům symbol Microsoft, najdete v části [používat servery symbolů najít soubory symbolů není na místním počítači](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Use_symbol_servers_to_find_symbol_files_not_on_your_local_machine) v [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) tématu.  
  
 Načtení symbolů pro určité součásti systému při ladění:  
  
1.  Otevřete okno moduly (klávesové: **Ctrl + Alt + U**).  
  
2.  Vyberte modul, který chcete načíst symboly pro.  
  
     Můžete zjistit, které moduly mají symboly načíst prohlížením **Symbol stav** sloupce.  
  
3.  Zvolte **zatížení symboly** v místní nabídce.  
  
##  <a name="BKMK_Step_into_properties_and_operators_in_managed_code"></a> Krok do vlastnosti a operátory ve spravovaném kódu  
 Ladicí program přes operátory ve spravovaném kódu a vlastnosti ve výchozím nastavení. Ve většině případů to poskytuje lepší ladění prostředí. Chcete-li povolit zanoříte se do vlastnosti nebo operátory, zvolte **ladění** > **možnosti**. Na **ladění** > **Obecné** zrušte zaškrtnutí políčka **krok přes vlastnosti a operátory (pouze spravované)** zaškrtávací políčko