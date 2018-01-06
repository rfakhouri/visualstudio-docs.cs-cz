---
title: "DA0038: Vysoká míra kolizí zámků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.38
- vs.performance.rules.DA0038
- vs.performance.DA0038
ms.assetid: ae0c8b2f-17b2-4f3d-a834-aa2f6371753b
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7ea9e12b32052169d6fb87b927735da071c96fb6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0038-high-rate-of-lock-contentions"></a>DA0038: Vysoká míra kolizí zámků
|||  
|-|-|  
|Id pravidla|DA0038|  
|Kategorie|Použití rozhraní .NET framework|  
|Metoda profilace|Vzorkování<br /><br /> Instrumentace<br /><br /> Využívání paměti rozhraním .NET|  
|Zpráva|Vysoká míra kolizí zámků .NET dochází. Prohlédněte si prosím důvod této spory uzamčení spuštěním profil souběžnosti.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 25 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Systém data výkonu, která se shromažďují se data profilování označuje, že výrazně vysoká míra kolizí zámků došlo k chybě při spuštění aplikace. Vezměte v úvahu profilace znovu pomocí metoda profilování souběžného zpracování nalézt příčinu kolizí.  
  
## <a name="rule-description"></a>Popis pravidla  
 Zámky slouží k ochraně důležitých části kódu, který musí být prováděny sériově jedním vláknem dobu vícevláknové aplikace. Microsoft .NET Common Language Runtime (CLR) poskytuje úplnou sadu synchronizace generuje a uzamyká primitiv. Například podporuje jazyka C# lock – příkaz (SyncLock v jazyce Visual Basic). Spravované aplikace můžete volat metody Monitor.Enter a Monitor.Exit v System.Threading – obor názvů a získat přímo uvolnit zámek. Rozhraní .NET Framework podporuje další synchronizace generuje a uzamyká primitiv, včetně třídy, které podporují mutex – třídy, ReaderWriterLocks a semaforů. Další informace najdete v tématu [přehled primitiv synchronizace](http://go.microsoft.com/fwlink/?LinkId=177867) v rozhraní .NET Framework Developer's Guide na webu MSDN. Samotné Vrstvená na nižší úrovni synchronizační služby, které jsou součástí operačního systému Windows jsou tříd rozhraní .NET Framework. Mezi ně patří kritická sekce objekty a mnoho různých počkejte a signalizace funkce události. Další informace najdete v tématu [synchronizace](http://go.microsoft.com/fwlink/?LinkId=177869) části Win32 a COM Development v MSDN Library  
  
 Základní třídy rozhraní .NET Framework i nativní Windows objekty, které jsou používány k synchronizaci a uzamyká jsou umístění sdílené paměti, které je potřeba změnit pomocí propojené operace. Propojený operace použití hardwaru pokyny, které působí na umístění sdílené paměti, chcete-li změnit jejich stavu pomocí atomické operací. Atomické operací jsou zaručena konzistentní do všech procesorů v počítači. Zámky a popisovačů WaitHandles jsou objekty .NET, které automaticky používají propojené operace, když jsou nastavit nebo obnovit. Mohou existovat další sdílené paměti datové struktury v aplikaci, která také vyžaduje použití propojené operace, aby bylo možné aktualizovat způsobem bezpečné pro přístup z více vláken. Další informace najdete v tématu [propojený Operations](http://go.microsoft.com/fwlink/?LinkId=177870) v rozhraní .NET Framework části MSND knihovny  
  
 Synchronizace a uzamyká jsou mechanismy, které používá k zajištění správně spustit více vláken aplikace. Každé vlákno vícevláknové aplikace je nezávislé spouštění jednotku, která je naplánováno nezávisle v operačním systému. Vždy, když podproces, který se snaží získat zámek je zpožděna, protože jiné vlákno je která nastavila zámek, dojde k uzamčení kolize.  
  
 Často jsou vnořeny zámky. Vnoření nastane, když vlákno provádění kritická sekce provede funkci, která pak vyžaduje další zámek. Některé množství zámku vnoření nevyhnutelné. Kritická sekce může volat metodu rozhraní .NET Framework, která závisí na zámky zajistit, že je bezpečné pro přístup z více vláken. Volání z některé důležité oddílu ve vaší aplikaci do Framework metodu, která také uzamkne pomocí různých zámku popisovače způsobí, že zámky. Chcete-li vnořit. Vnořené uzamčení podmínek může způsobit problémy s výkonem, které jsou často obtížné unravel a opravte.  
  
 Toto pravidlo aktivuje se při měření pořízených během spuštění profilování znamenat, že je příliš velká množství spory uzamčení. Kolizí zámků zpozdit provádění vláken, které čekají na zámek. Je třeba se zabývat i poměrně malé množství spory uzamčení při testování částí nebo v zátěžových testech spuštěna na hardwaru nižší end.  
  
> [!NOTE]
>  Když je příliš vysoká míra kolizí zámků hlášené v profilaci data [DA0039: velmi vysoká míra kolizí zámků](../profiling/da0039-very-high-rate-of-lock-contentions.md) upozornění je aktivována, místo tuto zprávu informace.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Dvakrát klikněte na zprávu, která se přejděte do [značky](../profiling/marks-view.md) zobrazení data profilování.  Najít **.NET CLR LocksAndThreads\Contention rychlost za sekundu** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde je větší než ostatní fáze spory uzamčení.  
  
 Toto pravidlo aktivuje jenom v případě, že nepoužíváte metoda profilování souběžného zpracování. Metoda profilace souběžného zpracování je nejvhodnější použít při diagnostice potíží spojených s spory uzamčení ve vaší aplikaci. Shromažďování dat porozumět chování aplikace při zamykání profilace souběžného zpracování. To zahrnuje pochopení, která zámky jsou výraznou tvrdil, jak dlouho dobu provádění vlákna je zpožděno. čekání tvrdil zámků a je podílející jaké konkrétního kódu. Concurrency profily shromáždí data na všech zamknout kolizí, včetně chování při zamykání nativní zařízení systému Windows, tříd rozhraní .NET Framework a další knihovny třetích stran aplikace odkazy. Informace o souběžnosti profilace z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, najdete v části [shromažďování vláken a zpracování dat souběžnosti](../profiling/collecting-thread-and-process-concurrency-data.md). Odkazy na informace o souběžnosti profilace z příkazového řádku najdete v tématu **pomocí metoda souběžného zpracování shromažďovat sporu prostředků a vlákna Data aktivit** části [pomocí profilace metody z Příkazový řádek](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md).