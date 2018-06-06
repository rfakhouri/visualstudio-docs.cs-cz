---
title: 'DA0039: Velmi vysoká míra kolizí zámků | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.39
- vs.performance.DA0039
- vs.performance.rules.DA0039
ms.assetid: 5a9fc57d-9097-413b-af0c-8726b1a57048
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 153b979dffed48dbce355faae7125f2bd338fd08
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750438"
---
# <a name="da0039-very-high-rate-of-lock-contentions"></a>DA0039: Velmi vysoká míra kolizí zámků
|||  
|-|-|  
|Id pravidla|DA0039|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Instrumentace<br /><br /> Využívání paměti rozhraním .NET|  
|Zpráva|Dochází k velmi vysoká míra kolizí zámků .NET. Prohlédněte si prosím důvod této spory uzamčení spuštěním profil souběžnosti.|  
|Typ pravidla|Upozornění|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 25 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Systém data výkonu, která se shromažďují se data profilování označuje, že nadměrně vysoká míra kolizí zámků došlo k chybě při spuštění aplikace. Vezměte v úvahu profilace znovu pomocí metoda profilování souběžného zpracování najít příčinu sporu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Zámky slouží k ochraně důležitých části kódu, který musí být prováděny sériově jedním vláknem dobu vícevláknové aplikace. Microsoft .NET Common Language Runtime (CLR) poskytuje úplnou sadu synchronizace generuje a uzamyká primitiv. Například podporuje jazyka C# lock – příkaz (SyncLock v jazyce Visual Basic). Spravované aplikace můžete volat metody Monitor.Enter a Monitor.Exit v System.Threading – obor názvů a získat přímo uvolnit zámek. Rozhraní .NET Framework podporuje další synchronizace generuje a uzamyká primitiv, včetně třídy, které podporují mutex – třídy, ReaderWriterLocks a semaforů. Další informace najdete v tématu [přehled primitiv synchronizace](http://go.microsoft.com/fwlink/?LinkId=177867) v rozhraní .NET Framework Developer's Guide na webu MSDN. Samotné Vrstvená na nižší úrovni synchronizační služby, které jsou součástí operačního systému Windows jsou tříd rozhraní .NET Framework. Mezi ně patří kritická sekce objekty a mnoho různých počkejte a signalizace funkce události. Další informace najdete v tématu [synchronizace](http://go.microsoft.com/fwlink/?LinkId=177869) části Win32 a COM Development v MSDN Library.  
  
 Základní třídy rozhraní .NET Framework i nativní Windows objekty, které jsou používány k synchronizaci a uzamyká jsou umístění sdílené paměti, které je potřeba změnit pomocí propojené operace. Propojený operace použití hardwaru pokyny, které působí na umístění sdílené paměti, chcete-li změnit jejich stavu pomocí atomické operací. Atomické operací jsou zaručena konzistentní do všech procesorů v počítači. Zámky a popisovačů WaitHandles jsou objekty .NET, které automaticky používají propojené operace, když jsou nastavit nebo obnovit. Mohou existovat další sdílené paměti datové struktury v aplikaci, která také vyžaduje použití propojené operace, aby bylo možné aktualizovat způsobem bezpečné pro přístup z více vláken. Další informace najdete v tématu [propojený Operations](http://go.microsoft.com/fwlink/?LinkId=177870) v části rozhraní .NET Framework v knihovně MSDN.  
  
 Synchronizace a uzamyká jsou mechanismy, které používá k zajištění správně spustit více vláken aplikace. Každé vlákno vícevláknové aplikace je nezávislé spouštění jednotku, která je naplánováno nezávisle v operačním systému. Vždy, když podproces, který se snaží získat zámek je zpožděna, protože jiné vlákno je která nastavila zámek, dojde k uzamčení kolize.  
  
 Často jsou vnořeny zámky. Vnoření nastane, když vlákno provádění kritická sekce provede funkci, která pak vyžaduje další zámek. Některé množství zámku vnoření nevyhnutelné. Kritická sekce může volat metodu rozhraní .NET Framework, která závisí na zámky zajistit, že je bezpečné pro přístup z více vláken. Volání z některé důležité oddílu ve vaší aplikaci do Framework metodu, která také uzamkne pomocí různých zámku popisovače způsobí, že zámky. Chcete-li vnořit. Vnořené uzamčení podmínek může způsobit problémy s výkonem, které jsou často obtížné unravel a opravte.  
  
 Toto pravidlo aktivuje se při měření pořízených během spuštění profilování znamenat, že je příliš velká množství spory uzamčení. Kolizí zámků zpozdit provádění vláken, které čekají na zámek. Je třeba se zabývat i poměrně malé množství spory uzamčení při testování částí nebo v zátěžových testech spuštěna na hardwaru nižší end.  
  
> [!NOTE]
>  Pokud frekvence kolizí zámků hlášené v profilaci dat je zásadní, ale ne příliš velké, [DA0038: vysoká míra kolizí zámků](../profiling/da0038-high-rate-of-lock-contentions.md) informační zprávu je aktivována, místo tuto zprávu upozornění.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Dvakrát klikněte na zprávu, která se přejděte do [značky](../profiling/marks-view.md) zobrazení data profilování.  Najít **.NET CLR LocksAndThreads\Contention rychlost za sekundu** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde je větší než ostatní fáze spory uzamčení.  
  
 Toto pravidlo aktivuje jenom v případě, že nepoužíváte metoda profilování souběžného zpracování. Metoda profilace souběžného zpracování je nejvhodnější použít při diagnostice potíží spojených s spory uzamčení ve vaší aplikaci. Shromažďování dat porozumět chování aplikace při zamykání profilace souběžného zpracování. To zahrnuje pochopení, která zámky jsou výraznou tvrdil, jak dlouho dobu provádění vlákna je zpožděno. čekání tvrdil zámků a je podílející jaké konkrétního kódu. Concurrency profily shromáždí data na všech zamknout kolizí, včetně chování při zamykání nativní zařízení systému Windows, tříd rozhraní .NET Framework a další knihovny třetích stran aplikace odkazy. Informace o souběžnosti profilace z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, najdete v části [shromažďování dat souběžnosti vláken a procesů](../profiling/collecting-thread-and-process-concurrency-data.md). Odkazy na informace o souběžnosti profilace z příkazového řádku najdete v tématu **použít metodu souběžného zpracování ke shromažďování dat prostředků kolizí a vlákno aktivity** části [použití metod profilace z příkazový řádek](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md).