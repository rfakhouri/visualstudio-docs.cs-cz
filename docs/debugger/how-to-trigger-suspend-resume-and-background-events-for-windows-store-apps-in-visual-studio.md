---
title: "Jak aktivovat pozastavení, obnovení a události na pozadí při ladění aplikace UWP | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.background_task_activate_failure
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 824ff3ca-fedf-4cf5-b3e2-ac8dc82d40ac
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4380299fd37b456dd3be6da7cf37981ad89b1caf
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="how-to-trigger-suspend-resume-and-background-events-while-debugging-uwp-apps-in-visual-studio"></a>Jak aktivovat pozastavení, obnovení a události na pozadí při ladění aplikace UWP v sadě Visual Studio
Pokud jste nejsou ladění, Windows **správu životního cyklu procesu** (PLM) řídí stav spuštění aplikace – spuštění, pozastavení, obnovení a ukončení aplikace v odpovědi na akce uživatelů a stavu zařízení. Při ladění, systém Windows vypíná tyto aktivační události. Toto téma popisuje, jak má provést tyto události v ladicím programu.  
  
 Toto téma také popisuje, jak ladit **úlohy na pozadí**. Úlohy na pozadí umožňují provádění některých operací v procesech na pozadí, i když není aplikace spuštěna. Ladicí program můžete použít pro umístění vaší aplikace v režimu ladění a potom – bez spuštění uživatelského rozhraní – spuštění a ladění úloh na pozadí.  
  
 Další informace o úlohách správy životního cyklu procesu a pozadí najdete v části [spuštění, obnovení a multitasking](https://docs.microsoft.com/en-us/windows/uwp/launch-resume/index).  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [Události správu životního cyklu proces spuštění](#BKMK_Trigger_Process_Lifecycle_Management_events)  
  
 [Aktivační události úlohy na pozadí](#BKMK_Trigger_background_tasks)  
  
-   [Aktivační událost úloh na pozadí z standardní ladicí relace](#BKMK_Trigger_a_background_task_event_from_a_standard_debug_session)  
  
-   [Aktivují úlohy na pozadí, když není aplikace spuštěna](#BKMK_Trigger_a_background_task_when_the_app_is_not_running)  
  
 [Aktivovat události procesu správy životního cyklu a úlohy z aplikace nainstalované na pozadí](#BKMK_Trigger_Process_Lifetime_Management_events_and_background_tasks_from_an_installed_app)  
  
 [Diagnostika chyb aktivace úlohy pozadí](#BKMK_Diagnosing_background_task_activation_errors)  
  
##  <a name="BKMK_Trigger_Process_Lifecycle_Management_events"></a>Události správu životního cyklu proces spuštění  
 Windows můžete pozastavit vaší aplikace, když uživatel přepíná směrem od nebo když Windows vstupuje do stavu snížené spotřeby energie. Může reagovat `Suspending` události uložení příslušné aplikace a uživatelská data do trvalého úložiště a k uvolnění prostředků. Když je aplikace byl obnoven z **pozastaveno** stavu, přejde **systémem** stavu a bude pokračovat, kde bylo při bylo pozastaveno. Může reagovat `Resuming` událostí obnovte nebo aktualizujte stav aplikace a uvolnit prostředky.  
  
 I když se Windows pokusí mějte na paměti nejdříve tolik pozastavenou aplikace, můžete Windows ukončit vaší aplikace, pokud nejsou k dispozici dostatek prostředků, aby v paměti. Uživatele můžete také explicitně zavřít aplikaci. Neexistuje žádná speciální událost označující, že uživatel zavřel aplikace.  
  
 V ladicím programu sady Visual Studio můžete ručně pozastavit, obnovit a ukončení aplikace k ladění události životního cyklu procesu. Chcete-li ladit životního cyklu událost procesu:  
  
1.  Nastavte breakpooint v obslužná rutina události, která chcete ladit.  
  
2.  Stiskněte klávesu **F5** spustit ladění.  
  
3.  Na **ladění umístění** nástrojů vyberte události, kterou chcete provést:  
  
     ![Pozastavit, pokračovat, ukončete a úlohy na pozadí](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
     Všimněte si, že **pozastavení a ukončení** aplikace se zavře a ukončení relace ladění.  
  
##  <a name="BKMK_Trigger_background_tasks"></a>Aktivační události úlohy na pozadí  
 Jakékoli aplikaci, můžete zaregistrovat úlohy na pozadí reagovat na určité události systému, i když není aplikace spuštěna. Úlohy na pozadí nelze spustit kód, který přímo aktualizuje rozhraní; Místo toho se zobrazují informace pro uživatele s dlaždice aktualizace, aktualizace oznámení "BADGE" a informační zprávy. Další informace najdete v tématu [podpora vaší aplikace pomocí úlohy na pozadí](http://msdn.microsoft.com/en-us/4c7bb148-eb1f-4640-865e-41f627a46e8e)  
  
 Můžete aktivovat události, které začínají ladicího programu úlohy na pozadí pro aplikaci.  
  
> [!NOTE]
>  Ladicí program lze spustit pouze události, které neobsahují data, jako jsou události, které označují změnu stavu v zařízení. Je nutné ručně spustit úlohy na pozadí, které vyžadují vstup uživatele nebo jiná data.  
  
 Nejvíce realistické způsob, jak můžete aktivovat události úlohy na pozadí je, pokud aplikace není spuštěna. Nicméně aktivuje událost ve standardní relaci ladění je také podporována.  
  
###  <a name="BKMK_Trigger_a_background_task_event_from_a_standard_debug_session"></a>Aktivační událost úloh na pozadí z standardní ladicí relace  
  
1.  Nastavte zarážky v kódu úloh pozadí, kterou chcete ladit.  
  
2.  Stiskněte klávesu **F5** spustit ladění.  
  
3.  V seznamu událostí na **ladění umístění** nástrojů vyberte pozadí úloha, kterou chcete spustit.  
  
     ![Pozastavit, pokračovat, ukončete a úlohy na pozadí](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
###  <a name="BKMK_Trigger_a_background_task_when_the_app_is_not_running"></a>Aktivují úlohy na pozadí, když není aplikace spuštěna  
  
1.  Nastavte zarážky v kódu úloh pozadí, kterou chcete ladit.  
  
2.  Otevřete stránku vlastnosti ladění pro projekt spuštění. V Průzkumníku řešení vyberte projekt. Na **ladění** nabídce zvolte **vlastnosti**.  
  
     Pro projekty C++, možná budete muset Rozbalit **vlastnosti konfigurace** a potom zvolte **ladění**.  
  
3.  Proveďte jednu z těchto akcí:  
  
    -   Projekty Visual C# a Visual Basic, zvolte **nespouštějí, ale po jeho spuštění ladění vlastního kódu**  
  
         ![C &#35; &#47; Vlastnosti aplikace spuštění ladění jazyka Visual Basic](../debugger/media/dbg_csvb_dontlaunchapp.png "DBG_CsVb_DontLaunchApp")  
  
    -   Projekty Visual C++ a používání jazyka JavaScript, zvolte **ne** z **spuštění aplikace** seznamu.  
  
         ![C & č. 43; & č. 43; &#47; Spusťte VB vlastnosti ladění aplikace](../debugger/media/dbg_cppjs_dontlaunchapp.png "DBG_CppJs_DontLaunchApp")  
  
4.  Stiskněte klávesu **F5** uvést aplikace v režimu ladění. Poznámka: **proces** na seznamu **ladění umístění** panelu nástrojů zobrazí název balíčku aplikace k označení, že jste v režimu ladění.  
  
     ![Seznam úloh procesu pozadí](../debugger/media/dbg_backgroundtask_processlist.png "DBG_BackgroundTask_ProcessList")  
  
5.  V seznamu událostí na **ladění umístění** nástrojů vyberte pozadí úloha, kterou chcete spustit.  
  
     ![Pozastavit, pokračovat, ukončete a úlohy na pozadí](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
##  <a name="BKMK_Trigger_Process_Lifetime_Management_events_and_background_tasks_from_an_installed_app"></a>Aktivovat události procesu správy životního cyklu a úlohy z aplikace nainstalované na pozadí  
 Použijte dialogové okno ladění aplikace nainstalována načíst aplikaci, která je již nainstalován do ladicího programu. Může například ladění aplikace nainstalovaná z Microsoft Store nebo ladění aplikace, když máte zdrojové soubory pro aplikace, ale ne projekt Visual Studio pro aplikaci. Dialogové okno ladění nainstalované aplikace umožňuje že spuštění aplikace v režimu ladění v sadě Visual Studio počítači nebo na vzdáleném zařízení, nebo chcete-li nastavit aplikaci spustit v režimu ladění, ale nespustí se. Najdete v článku **nainstalovanou aplikaci spustit v ladicím programu** části buď [JavaScript](../debugger/start-a-debugging-session-for-store-apps-in-visual-studio-javascript.md#BKMK_Start_an_installed_app_in_the_debugger) nebo [Visual C++, Visual C# a Visual Basic](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md#BKMK_Start_an_installed_app_in_the_debugger) verze **spuštění ladicí relace** Další informace.  
  
 Jakmile aplikace je načten do ladicího programu, můžete použít některý z výše popsaných postupů.  
  
##  <a name="BKMK_Diagnosing_background_task_activation_errors"></a>Diagnostika chyb aktivace úlohy pozadí  
 Diagnostické protokoly v prohlížeči událostí systému Windows pro infrastrukturu pozadí obsahuje podrobné informace, které můžete použít při diagnostice a řešení chyb úlohy pozadí. Chcete-li zobrazit protokol:  
  
1.  Otevřete Prohlížeč událostí aplikace.  
  
2.  V **akce** podokně vyberte **zobrazení** a zajistěte, aby **zobrazit protokoly pro ladění a** je zaškrtnuté.  
  
3.  Na **prohlížeče událostí (místní)** stromu, rozbalte uzly **protokoly aplikací a služeb** > **Microsoft** > **Windows**   >  **BackgroundTasksInfrastructure**.  
  
4.  Vyberte **diagnostiky** protokolu.  
  
## <a name="see-also"></a>Viz také  
 [Testování aplikací pro UPW pomocí sady Visual Studio](../test/testing-store-apps-with-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   
 [Životní cyklus aplikace](http://msdn.microsoft.com/en-us/53cdc987-c547-49d1-a5a4-fd3f96b2259d)   
 [Spuštění, obnovení a multitasking](http://msdn.microsoft.com/en-us/04307b1b-05af-46a6-b639-3f35e297f71b)