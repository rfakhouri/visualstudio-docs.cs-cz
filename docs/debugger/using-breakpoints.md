---
title: "Použití zarážek v ladicím programu v sadě Visual Studio | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.breakpointswin
- vs.debug.disassembly.insert
- vs.debug.sourcewin.edit
- vs.debug.file
- vs.debug.breakpt.new
- vs.debug.whenbreakpointishit
- vs.debug.breakpt.choose
- vs.debug.breakpt.location.address
- vs.debug.breakpt.constraints
- vs.debug.breakpoints.delete
- vs.debug.breakpt.location.data
- vc.breakpoints
- vs.debug.breakpt.condition
- vs.debug.breakpt.location.function
- vs.debug.breakpoints
- vs.debug.menu.insert
- vs.debug.filenames
- vs.debug.breakpt.action
- vs.debug.sourcewin.insert
- vs.debug.address
- vs.debug.data
- vs.debug.func
- vs.debug.breakpt.location.file
helpviewer_keywords: breakpoints, about breakpoints
ms.assetid: 020b2e97-3b3e-4b2c-872d-b5c6025e120e
caps.latest.revision: "57"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 844b1378866bdd66b11494f01ff4762909408af7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="use-breakpoints-in-the-visual-studio-debugger"></a>Použití zarážek v ladicím programu sady Visual Studio
Pokud chcete zastavit provádění ladicí program, případně zobrazíte stav proměnných kódu nebo pro zobrazení v zásobníku volání, můžete nastavit zarážky. Jsou jedním z nejdůležitějších techniky ladění v sadě nástrojů pro vývojáře.  
  
##  <a name="BKMK_Overview"></a>Nastavení zarážek řádku ve zdrojovém kódu  
 Nastavte zarážky řádku ve zdrojovém kódu, kliknutím na levém okraji souboru zdrojového kódu nebo vložení kurzor na řádek kódu a stisknutím klávesy F9. Zarážce se zobrazí jako červené tečky na levém okraji a řádek kódu je také barevný:  
  
 ![Nastavit zarážky](../debugger/media/basicbreakpoint.png "BasicBreakpoint")  
  
 Když spustíte tento kód v ladicím programu, zastaví spuštění při každém průchodu zarážkou, před provedením kódu na tomto řádku. Řádek zdrojového kódu se žlutou:  
  
 ![Zastavit provádění zarážek](../debugger/media/breakpointexecution.png "BreakpointExecution")  
  
 V tomto okamžiku hodnota `testInt` je stále 1.  
  
 Můžete zobrazit aktuální stav aplikace, včetně hodnot proměnných a zásobníku volání. Další informace o zásobník volání najdete v tématu [postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md).  
  
 Na každý řádek spustitelného kódu, můžete nastavit zarážky. Například v jazyce C# kód výše je můžete nastavit zarážky deklarace proměnné, `for` smyčky, nebo žádný kód uvnitř `for` smyčky, ale nelze nastavit zarážky deklarace oboru názvů nebo třídy nebo podpis metody.  
  
##  <a name="BKMK_Set_a_breakpoint_in_a_source_file"></a>Nastavení jiné druhy zarážky  
 Můžete také nastavit zarážky v zásobníku volání, v okně zpětný překlad a, v nativním kódu C++, podmínky dat nebo s adresou paměti.  
  
## <a name="BKMK_Set_a_breakpoint_in_the_call_stack_window"></a>Nastavení boru přerušení v okně zásobník volání  
 Může dojít k narušení provádění na pokyn nebo na řádek, který volání funkce vrátí nastavením zarážky v **zásobníkem volání** okno. Další informace o zásobník volání najdete v tématu [postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md). Ladicí program musí být zastaven provádění.  
  
1.  Spusťte ladění aplikace a provádění čekání je zastaveno (například na zarážku). Otevřete **zásobníkem volání** okno (**ladění > Windows > zásobníkem volání**, nebo **CTRL + ALT + C**).  
  
2.  Klikněte pravým tlačítkem na volání funkce a potom vyberte **zarážek > Vložit zarážku**, nebo použijte klávesovou zkratku **F9**.  
  
3.  Symbol zarážek se zobrazí na levém okraji zásobníku volání, vedle názvu funkce volání.  
  
 V **zarážky** okně se zobrazí jako adresu s umístění paměti, která odpovídá další instrukce spustitelného souboru ve funkci zarážek zásobníku volání. Ladicí program dělí na pokyn provádění.  
  
 Vizuální trasování zarážky během provádění kódu, najdete v tématu [mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
## <a name="setting-a-breakpoint-in-the-disassembly-window"></a>Nastavení boru přerušení v okně zpětný překlad  
 Pokud chcete nastavit zarážky instrukce sestavení, musí být ladicí program v režimu pozastavení.  
  
1.  Spusťte ladění aplikace a provádění čekání je zastaveno (například na zarážku). Otevřete **zpětný překlad** okno (**ladění > Windows > zpětný překlad**, nebo **Ctrl + Alt + D**).  
  
2.  Kliknutím na levém okraji u instrukce, kterou chcete ukončit u nebo nastavte kurzor na instrukce a stiskněte klávesu **F9**.  
  
## <a name="BKMK_set_a_data_breakpoint_native_cplusplus_only"></a>Nastavení zarážek dat (pouze nativní C++)  
 Data zarážky přerušit provádění po hodnotu, která je uloží změny zadaná paměťová adresy. Pokud hodnota číst, ale nebyl změněn, nemá rozdělit provádění. Pokud chcete nastavit zarážky data, musí být ladicí program v režimu pozastavení.  
  
1.  Spuštění ladění aplikace a počkejte, dokud nebude dosaženo zarážky. Na **ladění** nabídce zvolte **nové zarážek > dat zarážek** (nebo otevřít **zarážky** okno a zvolte **nový > dat zarážek**.  
  
2.  V **adresu** zadejte adresu paměti nebo výraz, který se vyhodnocuje adresu paměti. Můžete například zadat `&avar` pro přerušení, když obsah proměnné `avar` změny.  
  
3.  V **počet bajtů** rozevíracího seznamu, vyberte počet bajtů, které chcete, aby ladicí program ke sledování. Například, pokud vyberete **4**, ladicího programu bude sledovat čtyři bajtů počínaje `&avar` a přerušení, pokud žádné z těchto bajtů změňte hodnotu.  
  
 Mějte na paměti, že data zarážky závisí na použitelnost adres konkrétní paměti.  
  
-   Adresy proměnné se mění z jedné relaci ladění na další. Data zarážky jsou automaticky zakázán na konci každé relaci ladění.  
  
-   Pokud nastavení zarážky data na místní proměnné, zůstanou zarážek povolena při ukončení funkce, ale adresa paměti není nadále vhodné a nepředvídatelné chování zarážku. Pokud nastavíte zarážku data na místní proměnné, musí odebrat ani vypnout zarážek před ukončením funkce.  
  
 Data zarážky nefungují za těchto podmínek:  
  
-   Proces, který není laděné zapisuje do umístění v paměti  
  
-   Umístění v paměti jsou sdílena mezi dva nebo více procesů  
  
-   Umístění v paměti je aktualizovat v rámci jádra. Například pokud paměti je předán do systému Windows 32-bit `ReadFile` funkce, paměť, se budou aktualizovat z režimu jádra a ladicí program nebude přerušena v paměti zápisu.  
  
## <a name="setting-a-breakpoint-with-a-memory-address-native-c-only"></a>Nastavení zarážek s adresu paměti (pouze nativní C++)  
 Adresu objektu také můžete nastavit zarážky metodu s názvem na konkrétní instanci třídy.  Tady je příklad:  
  
 Například zadaný objekt typu `my_class` s adresou, můžete nastavit zarážky funkce metodu s názvem `my_method` volat z této instance.  
  
1.  Někde nastavení boru přerušení po vytvoření instance dané instance třídy.  
  
2.  Najít adresu instance (budete říkáme má `0xcccccccc`).  
  
3.  Klikněte na tlačítko **ladění > Nový zarážek > funkce zarážek** (nebo **ALT + F9, B**).  
  
4.  Přidejte následující text, který má **název funkce** pole:  
  
    ```C++  
    ((my_class *) 0xcccccccc)->my_method  
    ```  
  
##  <a name="BKMK_Specify_advanced_properties_of_a_breakpoint_"></a>Správa zarážky  
 Můžete použít **zarážky** okno (**ladění > Windows > zarážky**, nebo **CTRL + ALT + B**) zobrazíte všechny zarážky jste nastavili ve vašem řešení:  
  
 ![Okno zarážky](../debugger/media/breakpointswindow.png "BreakpointsWindow")  
  
 **Zarážky** okno získáte centrální místo, kam můžete spravovat všechny body přerušení, může být obzvláště užitečné v na velkých projektech nebo komplexní ladění scénář, kde jsou důležité zarážky. Pokud potřebujete uložit nebo ke sdílení stavu a umístění sady zarážky, můžete exportovat a importovat zarážky pouze z **zarážky** okno.  
  
##  <a name="BKMK_Specify_a_breakpoint_condition_using_a_code_expression"></a>Pokročilé zarážky  
  
## <a name="breakpoint-conditions"></a>Breakpoint – podmínky  
 Můžete ovládat, kdy a kde zarážku provede nastavením podmínky.  
  
1.  Klikněte pravým tlačítkem na bod přerušení, nebo pozastavte ukazatel myši nad zarážce a zvolte ikonu nastavení.  
  
2.  V místní nabídce vyberte **podmínky**. Tím se otevře **nastavení zarážek** okno:  
  
 ![Nastavení zarážek](../debugger/media/breakpointsettings.png "BreakpointSettings")  
  
 Když zaškrtnete **podmínky** dialogovém okně se rozbalí a zobrazí různé druhy podmínky.  
  
 **Podmíněným výrazem:** když vyberete podmíněným výrazem, můžete zvolit dvě podmínky: **platí** a **při změně**. Zvolte **platí** Pokud chcete rozdělit při výraz je splněna, nebo zvolte **při změně** Pokud chcete rozdělit při změně hodnoty výrazu.  
  
 V následujícím příkladu jsme nastavit bod přerušení zadat pouze tehdy, když hodnota `testInt` je **4**:  
  
 ![Je splněna podmínka zarážek](../debugger/media/breakpointconditionistrue.png "BreakpointConditionIsTrue")  
  
 V následujícím příkladu jsme nastavit bod přerušení zadat pouze tehdy, když hodnota `testInt` změny:  
  
 ![Breakpoint – při změně](../debugger/media/breakpointwhenchanged.png "BreakpointWhenChanged")  
  
 Chování změněné pole tím, kdy je jiný pro různé programovací jazyky. Pokud se rozhodnete **při změně** pro nativní kód ladicího programu nepovažuje první vyhodnocení podmínku, která má být změnu, takže zarážce nedosáhnete stropu na první vyhodnocení. Pokud se rozhodnete **při změně** pro spravovaný kód, je na první vyhodnocení po průchodu zarážkou **při změně** je vybrána.  
  
 Pokud jste nastavili podmínku zarážek s neplatnou syntaxi, zobrazí se zpráva s upozorněním. Pokud zadáte podmínku zarážek s platnou syntaxi ale neplatnou sémantikou, upozornění se zobrazí při prvním, které je průchodu zarážkou. V obou případech ladicího programu dělí spuštění, když je dosaženo neplatný zarážek. Zarážce je přeskočen pouze v případě, že podmínka je platný a vyhodnocuje `false`.  
  
 Podmínka může být libovolný platný výraz, který rozpozná ladicího programu. Další informace o platné výrazy najdete v tématu [výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md).  
  
## <a name="using-object-ids-in-breakpoint-conditions-c-and-f"></a>Pomocí ID objektů v podmínkách zarážek (C# a F #)  
 Nastanou chvíle, kdy chcete pozorovat chování určitého objektu; Například můžete chtít zjistit, proč byl objekt vložit více než jednou do kolekce. V C# a F #, můžete vytvořit ID objektů pro určité instance [odkazové typy](/dotnet/csharp/language-reference/keywords/reference-types) a použijte je v zarážek podmínky. ID objektu je generované common language runtime (CLR) ladění služeb a přidružená k objektu.  Pokud chcete vytvořit ID objektu, postupujte takto:  
  
1.  Nastavte zarážky v kódu delší dobu, po vytvoření objektu.  
  
2.  Spuštění ladění a při spuštění, zastavení v zarážce, najděte zarážka v **místní hodnoty –** okně pravým tlačítkem a vyberte **Zkontrolujte ID objektu**.  
  
     Měli byste vidět  **$**  plus číslo **místní hodnoty –** okno. Toto je ID objektu.  
  
3.  Přidáte nové podmíněné zarážky v bodě, že který chcete prozkoumat, například pokud má být přidán do kolekce objektu.  
  
4.  V poli podmíněným výrazem použití ID objektu. Například, pokud je proměnná `item` odkaz na objekt, který má být přidán do kolekce, by měla být umístěna **položky == $n**, kde  **n**  je číslo ID objektu.  
  
     Provádění dojde k přerušení v místě, pokud je chcete přidat do kolekce.  
  
 Pokud chcete později odstranit ID objektu, kliknete pravým tlačítkem na proměnné v **místní hodnoty –** a vyberte **Delete. ID objektu**.  
  
 Upozorňujeme, že ID objektů vytvořit slabé odkazy a nezabrání objekt se uvolnění z paměti. Jsou platné pouze pro aktuální relaci ladění.  
  
## <a name="hit-count"></a>Počet volání  
 Pokud máte podezření, že začne smyčku ve vašem kódu chovají po překročení určitého počtu opakování, můžete nastavit zarážky zastavit provádění po zadaný počet přístupů k přidružený řádek kódu, než vynucené opakovaně stiskněte **F5**  na úroveň iterací.  
  
 V **nastavení zarážek** okně podmínku na **dosáhl počet**. Zadejte počet opakování. V následujícím příkladu jsme nastavení zarážek narazí na každý další iterace:  
  
 ![Počet volání zarážek](../debugger/media/breakpointhitcount.png "BreakpointHitCount")  
  
## <a name="filter"></a>Filtr  
 Můžete omezit zarážek má provést pouze na zadané zařízení nebo v zadanou procesy a vlákna.  
  
 V **nastavení zarážek**okno s podmínku na **filtru**. Zadejte nejméně jeden z těchto výrazů.  
  
-   MachineName = "name"  
  
-   ID procesu = hodnota  
  
-   Název_procesu = "name"  
  
-   ID podprocesu = hodnota  
  
-   ThreadName = "name"  
  
 Uzavřete řetězcové hodnoty v uvozovkách. Zkombinováním pomocí klauzule `&` (a), `||` (nebo), `!` (ne) a kulaté závorky.  
  
##  <a name="BKMK_Print_to_the_Output_window_with_tracepoints"></a>Akce zarážek a Tracepoints  
 Tracepoint je zarážek, který zobrazí zprávu, která se ve výstupním okně. Tracepoint může fungovat jako příkaz dočasné trasování v programovacím jazyce.  
  
 V **nastavení zarážek** okno, zkontrolujte **akce** pole. Zvolte **protokolu zprávu do okna výstupu** v **akce** skupiny. Můžete si ho vytisknout obecný řetězec, například **jedná se o testovací**. Zahrnout hodnotu proměnné nebo výrazu, uzavřete ji do složených závorek.  
  
 Chcete-li přerušit běh, když je dosaženo tracepoint, zrušte **pokračovat v provádění** zaškrtávací políčko. Když **pokračovat v provádění** je zaškrtnuto, není-li zastavit provádění. V obou případech je vytištěno zprávy.  
  
 Můžete použít následující zvláštní klíčová slova v **zpráva**.  
  
|||  
|-|-|  
|**$ADDRESS**|Aktuální instrukcí|  
|**$CALLER**|Název funkce volání|  
|**$CALLSTACK**|Zásobník volání|  
|**$FUNCTION**|Aktuální název funkce|  
|**$PID**|Id procesu|  
|**$PNAME**|Název procesu|  
|**$TID**|Id podprocesu|  
|**$TNAME**|Název vlákna|  
|**$TICK**||  
|**$TNAME**||  
  
##  <a name="BKMK_Set_a_breakpoint_at_a_function_return_in_the_Call_Stack_window"></a>Popisky zarážek  
 Popisky zarážek se používají pouze v **zarážky** okno řadit a filtrovat seznam zarážky. Chcete-li přidat zarážky štítek, vyberte řádek zarážek a poté zvolte **popisek** v místní nabídce.  
  
## <a name="export-and-import-breakpoints"></a>Export a Import zarážky  
 Zarážku můžete exportovat do souboru XML tak, že kliknete pravým tlačítkem na zarážce a výběr **exportovat**. Soubor je uložen ve výchozím nastavení v adresáři řešení. Chcete-li importovat zarážky, otevřete **zarážky** okno (**CTRL + ALT + B**) a na panelu nástrojů klikněte na šipku vpravo (popisek je **zarážky importovat ze souboru**) .  
  
## <a name="troubleshoot-breakpoints"></a>Řešení potíží s zarážky  
  
### <a name="i-deleted-a-breakpoint-but-i-continue-to-hit-it-when-i-start-debugging-again"></a>Po odstranění zarážku, ale I nadále stiskněte tlačítko při spuštění ladění znovu  
 Pokud jste odstranili zarážku při ladění, v některých případech můžete narazit zarážek znovu při příštím spuštění ladění. Pokud chcete zastavit stiskne tento bod přerušení, zajistěte, aby všechny instance zarážce se odeberou z **zarážky** okno.  
  
### <a name="the-debugger-cant-locate-the-correct-version-of-the-source-file-for-a-breakpoint"></a>Ladicí program nemůže nalézt správnou verzi zdrojového souboru pro zarážky  
 Pokud došlo ke změně zdrojového souboru a zdroj už neodpovídá kódu, kterou ladíte, může ladicího programu najít zdrojový soubor, který odpovídá zarážku, i když zdrojový soubor existuje.  
  
1.  Pokud chcete zobrazit zdrojový kód, který neodpovídá verzi sady Visual Studio jsou ladění, zvolte **ladění > Možnosti a nastavení**. Na **ladění nebo Obecné** zrušte zaškrtnutí políčka **vyžadují zdrojové soubory, které přesně odpovídají původní verze** možnost.  
  
2.  Můžete také navázat zarážce ke zdrojovému souboru. Vyberte zarážce a zvolte **podmínky** v místní nabídce. Zkontrolujte **povolit zdrojovém kódu, aby se liší od originálu** v **nastavení zarážek** okno.  
  
### <a name="breakpoints-dont-work-in-a-dll"></a>Zarážky nefungují v knihovně DLL  
 Nelze nastavit zarážky ve zdrojovém souboru při ladicího programu nebyl načíst informace o ladění pro modul kde se nachází kódu. Zprávy mohou zahrnovat například příznaky **nenastaví zarážce**. Glyfy zarážek upozornění se zobrazí v zarážek umístění. Tyto zarážky upozornění však budou skutečné zarážky po načtení kód. Další informace o načtení symbolů najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="see-also"></a>Viz také  
 [Procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md)
