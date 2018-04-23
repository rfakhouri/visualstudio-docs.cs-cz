---
title: Ladění více procesů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.programs
- vs.debug.processes.attaching
- vs.debug.activeprogram
- vs.debug.attaching
- vs.debug.attachedprocesses
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: bde37134-66af-4273-b02e-05b3370c31ab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08a089feceb6ba66791358096e3c4663df06494e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debug-multiple-processes"></a>Ladění více procesů
Chcete-li spustit ladění procesy, přepínat mezi procesy, rozdělit a pokračovat v provádění, projděte zdroje, zastavte ladění a ukončení nebo odpojení od procesy.  
  
##  <a name="BKMK_Configure_the_execution_behavior_of_multiple_processes"></a> Konfigurace chování při spuštění více procesů  
 Ve výchozím nastavení pokud více procesy spuštěné v ladicím programu, ukončování řádků, krokování a příkazů ladicího programu zastavení obvykle ovlivnit všechny procesy. Například když jeden proces je pozastaven na zarážce, spouštění jiných procesů je taky pozastaveno. Můžete změnit toto výchozí chování získat lepší kontrolu nad cíle provádění příkazů.  
  
1.  Klikněte na tlačítko **ladění > Možnosti a nastavení**.  
  
2.  Na **ladění**, **Obecné** zrušte zaškrtnutí políčka **přerušení všech procesů, když jeden proces dělí** zaškrtávací políčko.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Find_the_source_and_symbol___pdb__files"></a> Najít zdroj a symbolu (.pdb) soubory  
 Ladicí program přejděte zdrojový kód procesu, potřebuje přístup ke zdrojové soubory a soubory symbolů procesu. V tématu [zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
 Pokud nemůžete použít soubory pro proces, můžete přejít pomocí okno zpětný překlad. V tématu [postupy: použití okna zpětného překladu](../debugger/how-to-use-the-disassembly-window.md)  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Start_multiple_processes_in_a_VS_solution__attach_to_a_process__automatically_start_a_process_in_the_debugger"></a> V řešení VS spouští více procesů, se připojit k procesu, automaticky spustí proces v ladicím programu  
  
-   [Spuštění ladění více procesů v řešení sady Visual Studio](#BKMK_Start_debugging_multiple_processes_in_a_Visual_Studio_solution)  
  
-   [Změnit počáteční projekt](#BKMK_Change_the_startup_project)  
  
-   [Spustit konkrétní projekt v řešení](#BKMK_Start_a_specific_project_in_a_solution)  
  
-   [Spuštění více projektů v určitém řešení](#BKMK_Start_multiple_projects_in_a_solution)  
  
-   [Připojit k procesu](#BKMK_Attach_to_a_process)  
  
-   [Automaticky spustit proces v ladicím programu](#BKMK_Automatically_start_an_process_in_the_debugger)  
  
> [!NOTE]
>  Ladicí program není automaticky připojit k podřízeného procesu, který se spustil vyladěnou procesem, i když je projekt podřízené ve stejném řešení. Chcete-li ladit podřízený proces:  
>   
>  -   Připojte k podřízeného procesu po jeho spuštění.  
>   
>      -nebo-  
> -   Konfigurace systému Windows na automatické spuštění podřízeného procesu v novou instanci třídy ladicího programu.  
  
###  <a name="BKMK_Start_debugging_multiple_processes_in_a_Visual_Studio_solution"></a> Spuštění ladění více procesů v řešení sady Visual Studio  
 Pokud máte více než jeden projekt v sadě Visual Studio řešení, které můžete spustit nezávisle (projekty, které běží v oddělených procesech), můžete vybrat, které projekty spuštění ladicího programu.  
  
 ![Změna typu spuštění pro projekt](../debugger/media/dbg_execution_startmultipleprojects.png "DBG_Execution_StartMultipleProjects")  
  
####  <a name="BKMK_Change_the_startup_project"></a> Změnit počáteční projekt  
 Chcete-li změnit počáteční projekt pro řešení, vyberte projekt v Průzkumníku řešení a potom zvolte **nastavit jako spouštěný projekt** v místní nabídce.  
  
####  <a name="BKMK_Start_a_specific_project_in_a_solution"></a> Spustit konkrétní projekt v řešení  
 Ke spuštění projektu pro řešení beze změny výchozí projekt po spuštění, vyberte projekt v Průzkumníku řešení a potom zvolte **ladění** v místní nabídce. Pak si můžete vybrat **spustit novou instanci** nebo **krok do nové instance**.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [spuštění více procesy v VS řešení, se připojit k procesu, automaticky spustí proces v ladicím programu](../debugger/debug-multiple-processes.md#BKMK_Start_multiple_processes_in_a_VS_solution__attach_to_a_process__automatically_start_a_process_in_the_debugger)  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
####  <a name="BKMK_Start_multiple_projects_in_a_solution"></a> Spuštění více projektů v určitém řešení  
  
1.  Vyberte v Průzkumníku řešení a potom zvolte **vlastnosti** v místní nabídce.  
  
2.  Vyberte **společných vlastností**, **spouštěný projekt** na **vlastnosti** dialogové okno.  
  
3.  Pro každý projekt, který chcete změnit, vyberte buď **spustit**, **spustit bez ladění**, nebo **žádné**.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [spuštění více procesy v VS řešení, se připojit k procesu, automaticky spustí proces v ladicím programu](../debugger/debug-multiple-processes.md#BKMK_Start_multiple_processes_in_a_VS_solution__attach_to_a_process__automatically_start_a_process_in_the_debugger)  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Attach_to_a_process"></a> Připojit k procesu  
 Ladicí program můžete také *připojit* programy, které jsou spuštěny v procesy mimo Visual Studio, včetně programů, které běží na vzdáleném zařízení. Po připojení k programu, použijte příkazy spuštění ladicího programu, zkontrolovat stav programu a tak dále. Schopnost kontrolovat program může být omezená, v závislosti na tom, jestli se program byl sestaven s informace o ladění a toho, jestli mají přístup ke zdrojovému kódu programu a jestli je běžné kompilátoru JIT runtime jazyka ladicí informace o sledování.  
  
 V tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md) Další informace.  
  
 **Připojit k procesu, který je spuštěn v místním počítači**  
  
 Klikněte na tlačítko **ladění > připojit k procesu**. Na **připojit k procesu** dialogovém okně vyberte procesu z **procesy k dispozici** seznamu a potom vyberte **Attach**.  
  
 ![Připojit k procesu – dialogové](../debugger/media/dbg_attachtoprocessdlg.png "DBG_AttachToProcessDlg")  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Automatically_start_an_process_in_the_debugger"></a> Automaticky spustit proces v ladicím programu  
 V některých případech budete muset ladit kód po spuštění programu, který je spuštěn jiný proces. Mezi příklady patří služby a vlastní instalace akce. V těchto scénářích můžete mít spuštění ladicího programu a automaticky připojit při spuštění aplikace.  
  
1.  Spusťte Editor registru (**regedit.exe**).  
  
2.  Přejděte na **možnosti spuštění souboru HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Image** složky.  
  
3.  Vyberte složku, aplikace, kterou chcete spustit v ladicím programu.  
  
     Pokud název aplikace není uvedena jako podřízenou složku, vyberte **možnosti spuštění souboru bitové kopie** a potom zvolte **nový**, **klíč** v místní nabídce. Vyberte nový klíč, zvolte **přejmenovat** v místní nabídce a potom zadejte název aplikace.  
  
4.  V místní nabídce složky pro aplikace, vyberte **nový**, **řetězcovou hodnotu**.  
  
5.  Změňte název nové hodnoty z **nová hodnota** k `debugger`.  
  
6.  V místní nabídce položky ladicí program, zvolte **upravit**.  
  
7.  V dialogovém okně Upravit řetězec zadejte `vsjitdebugger.exe` v **údaj hodnoty** pole.  
  
     ![Řetězec dialogové okno Upravit](../debugger/media/dbg_execution_automaticstart_editstringdlg.png "DBG_Execution_AutomaticStart_EditStringDlg")  
  
 ![Ladicí program automatické spuštění položku v regedit.exe](../debugger/media/dbg_execution_automaticstart_result.png "DBG_Execution_AutomaticStart_Result")  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Switch_processes__break_and_continue_execution__step_through_source"></a> Přepněte procesy, rozdělit a pokračovat v provádění, krok prostřednictvím zdroje  
  
-   [Přepínání mezi procesy](#BKMK_Switch_between_processes)  
  
-   [Rozdělit krok a pokračujte příkazy](#BKMK_Break__step__and_continue_commands)  
  
###  <a name="BKMK_Switch_between_processes"></a> Přepínání mezi procesy  
 Můžete se připojit k více procesů při ladění, ale v každém okamžiku je aktivní v ladicím programu pouze jeden proces. Můžete nastavit aktivní nebo *aktuální* procesů v panelu nástrojů ladění umístění nebo **procesy** okno. Chcete-li přepnout mezi procesy, musí být oba tyto procesy v režimu pozastavení.  
  
 **Nastavit aktuální proces**  
  
-   Na panelu nástrojů ladění umístění, zvolte **proces** zobrazíte **proces** pole se seznamem. Vyberte proces, který chcete určit jako aktuální proces.  
  
     ![Přepínání mezi procesy](../debugger/media/dbg_execution_switchbetweenmodules.png "DBG_Execution_SwitchBetweenModules")  
  
     Pokud **ladění umístění** nástrojů není zobrazen, zvolte **nástroje**, **přizpůsobit**. Na **panely nástrojů** , zvolte **ladění umístění**.  
  
-   Otevřete **procesy** okno (zástupce **Ctrl + Alt + Z**), vyhledejte proces, který chcete nastavit jako aktuální proces a dvakrát na ni klikněte.  
  
     ![Okno procesy](../debugger/media/dbg_processeswindow.png "DBG_ProcessesWindow")  
  
     Aktuální proces je označena kvalifikátorem žlutý šipku.  
  
 Přepnutí do projektu ji nastaví aktuální proces pro účely ladění. Zobrazí všechny ladicí program okno, které můžete zobrazit stav pro aktuální proces a ovlivňují všechny příkazy taktování pouze aktuální proces.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [přepínač procesy, rozdělit a pokračovat v provádění, krok prostřednictvím zdroje](../debugger/debug-multiple-processes.md#BKMK_Switch_processes__break_and_continue_execution__step_through_source)  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Break__step__and_continue_commands"></a> Rozdělit krok a pokračujte příkazy  
  
> [!NOTE]
>  Ve výchozím nastavení, pozastavení, i nadále a příkazů ladicího programu krok vliv na všechny procesy, které se právě ladí. Chcete-li toto chování změnit, [nakonfigurovat chování při spuštění více procesů](#BKMK_Configure_the_execution_behavior_of_multiple_processes)  
  
||||  
|-|-|-|  
|**příkaz**|**Přerušení všech procesů, když jeden proces dělí**<br /><br /> Checked (výchozí)|**Přerušení všech procesů, když jeden proces dělí**<br /><br /> Vymazat|  
|**Ladění** nabídky:<br /><br /> -   **Rozdělit všechny**|Došlo k přerušení všech procesů.|Došlo k přerušení všech procesů.|  
|**Ladění** nabídky:<br /><br /> -   **Pokračovat**|Obnovit všechny procesy.|Obnovte všechny pozastavené procesy.|  
|**Ladění** nabídky:<br /><br /> -   **Krok do**<br />-   **Krok přes**<br />-   **Krok**|Všechny procesy spustit při aktuální kroků procesu.<br /><br /> Potom všechny procesy dělit.|Aktuální kroků procesu.<br /><br /> Obnoví pozastavenou procesy.<br /><br /> Spuštěné procesy pokračovat.|  
|**Ladění** nabídky:<br /><br /> -   **Krokování s vnořením aktuální proces**<br />-   **Krok přes aktuální proces**<br />-   **Krok na aktuální proces**|Není k dispozici|Aktuální kroků procesu.<br /><br /> Jiné procesy zachovat jejich stávající stavu (pozastaven nebo spuštění).|  
|Okno zdroje<br /><br /> -   **Zarážek**|Došlo k přerušení všech procesů.|Okno proces zalomení pouze zdroje.|  
|Kontextová nabídka okna zdroje:<br /><br /> -   **Spustit ke kurzoru**<br /><br /> Okno zdroje musí být v aktuálním procesu.|Všechny procesy spustit při zdroj okno proces spouští, pro kurzor a pak dělí.<br /><br /> Potom všechny ostatní procesy dělit.|Zdroj okno proces běží na kurzoru.<br /><br /> Jiné procesy zachovat jejich stávající stavu (pozastaven nebo spuštění).|  
|**Procesy** okno místní nabídce:<br /><br /> -   **Rozdělit procesu**|Není k dispozici|Vybrat proces konce.<br /><br /> Jiné procesy zachovat jejich stávající stavu (pozastaven nebo spuštění).|  
|**Procesy** okno místní nabídce:<br /><br /> -   **Pokračovat v procesu**|Není k dispozici|Vybraný proces obnoví.<br /><br /> Jiné procesy zachovat jejich stávající stavu (pozastaven nebo spuštění).|  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [přepínač procesy, rozdělit a pokračovat v provádění, krok prostřednictvím zdroje](../debugger/debug-multiple-processes.md#BKMK_Switch_processes__break_and_continue_execution__step_through_source)  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Stop_debugging__terminate_or_detach_from_processes"></a> Zastavte ladění, ukončit nebo odpojení od procesy  
  
-   [Zastavit, ukončete a odpojit příkazy](#BKMK_Stop__terminate__and_detach_commands)  
  
 Ve výchozím nastavení, když zvolíte **ladění**, **Zastavte ladění** více procesů jsou otevřené v ladicím programu, ladicí program, ukončí nebo odpojení od všech procesů v závislosti na tom, jak byl zahájen proces v ladicí program:  
  
-   Pokud aktuální proces byl spuštěn v ladicím programu, ukončení tohoto procesu.  
  
-   Pokud připojení ladicího programu pro aktuální proces ladicího programu odpojí z procesu a opustí proces běží.  
  
 Například pokud spustíte ladění procesu v řešení sady Visual Studio, připojení k jiným procesem, který je již spuštěna a zvolte **Zastavte ladění**, ladicí relace skončí, proces, který byl spuštěn v sadě Visual Studio je ukončeno, když je proces, který jste připojili ponechat spuštěnou. Následující postupy můžete použít k řízení způsobu, jakým zastavíte ladění.  
  
> [!NOTE]
>  **Přerušení všech procesů, když jeden proces dělí** možnost nemá vliv na zastavení ladění nebo ukončení a probíhá odpojování od procesy.  
  
 **Chcete-li změnit, zastavte ladění jak ovlivňuje jednotlivých procesů**  
  
-   Otevřete **procesy** okno (zástupce **Ctrl + Alt + Z**). Vyberte proces a potom vyberte nebo zrušte **odpojit při ladění zastavení** zaškrtávací políčko.  
  
###  <a name="BKMK_Stop__terminate__and_detach_commands"></a> Zastavit, ukončete a odpojit příkazy  
  
|||  
|-|-|  
|**příkaz**|**Popis**|  
|**Ladění** nabídky:<br /><br /> -   **Zastavte ladění**|Pokud se tím změní chování **procesy** okno **odpojit při ladění zastaví** možnost:<br /><br /> 1.  Procesy spuštěné ladicí program budou ukončeny.<br />2.  Připojené procesy jsou odpojit od ladicího programu.|  
|**Ladění** nabídky:<br /><br /> -   **Ukončit všechny**|Všechny procesy budou ukončeny.|  
|**Ladění** nabídky:<br /><br /> -   **Odpojte všechny**|Ladicí program odpojí od všech procesů.|  
|**Procesy** okno místní nabídce:<br /><br /> -   **Odpojit proces**|Ladicí program umožňuje odpojit z vybraného procesu.<br /><br /> Jiné procesy zachovat jejich stávající stavu (pozastaven nebo spuštění).|  
|**Procesy** okno místní nabídce:<br /><br /> -   **Ukončit proces**|Vybrané proces je ukončen.<br /><br /> Jiné procesy zachovat jejich stávající stavu (pozastaven nebo spuštění).|  
|**Procesy** okno místní nabídce:<br /><br /> -   **Odpojení při ladění zastaví**|Přepíná chování **ladění**, **Zastavte ladění** u vybraného procesu:<br /><br /> -Zaškrtnutí: Ladicí program odpojí z procesu.<br />-Vymazat: Ukončení procesu.|  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [Zastavte ladění, ukončit nebo odpojení od procesy](../debugger/debug-multiple-processes.md#BKMK_Stop_debugging__terminate_or_detach_from_processes)  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
## <a name="see-also"></a>Viz také  
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md)   
 [Ladění za běhu](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)