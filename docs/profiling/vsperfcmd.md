---
title: VSPerfCmd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, VSPerfCmd tool
- command-line tools, VSPerfCmd tool
- command line, tools
- profiling tools,VSPerfCmd
- VSPerfCmd tool
ms.assetid: 778bc105-7643-46c4-a338-f3620e31125a
caps.latest.revision: "49"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: af5636866e2d91cc5aac5c8054a92961aeb3d042
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vsperfcmd"></a>VSPerfCmd
**VSPerfCmd.exe** nástroj se používá ke spuštění a zastavení shromažďování dat výkonu. Používá následující syntaxi:  
  
```  
VSPerfCmd [/U] [/options]  
```  
  
 Následující tabulky popisují **VSPerfCmd.exe** nástroj možnosti.  
  
|Možnost|Popis|  
|------------|-----------------|  
|**U**|Výstup konzoly přesměrovaného je zapsána jako kódování Unicode. Musí být první možnost zadat.|  
|[Spustit](../profiling/start.md) **:**`mode`|Spustí službu profilování v zadané režimu.|  
|[Výstup](../profiling/output.md) **:**`filename`|Určuje název výstupního souboru. Použít pouze s **spustit**.|  
|[CrossSession &#124; CS](../profiling/crosssession.md)|Povolí použití profilů napříč relacemi Windows. Použít pouze s **spustit**, **připojit**, **nebo spusťte**.|  
|[Uživatel](../profiling/user-vsperfcmd.md) **:**[`domain\`]`username`|Umožňuje zadaný účet přístup ke službě profileru. Použít pouze s **spustit**.|  
|[WaitStart](../profiling/waitstart.md)[**:**`n`]|Čeká na protokoly kolekce dat k chybě při inicializaci. Pokud `n` není zadaný, **VSPerfCmd** vyčká maximálně `n` sekund. Pokud `n` není zadán, **VSPerfCmd** vyčká po neomezenou dobu. To usnadňuje použití **VSPerfCmd** jako součást zpracování balíku.|  
|[Čítač](../profiling/counter.md) **:**`cfg`|Pokud ukázka metoda profilace se používá, určuje čítačů procesoru a počet událostí, které chcete použít jako intervalu vzorkování. Můžete zkusit pouze jednu hodnotu čítače.<br /><br /> Pokud se používá metoda profilování instrumentace, určuje čítačů procesoru, které se mají shromažďovat u každého bodu instrumentace. Použít pouze s **Start:**`Trace`, **připojit**, nebo **spusťte**.|  
|[QueryCounters](../profiling/querycounters.md)|Zobrazí seznam čítačů platný procesoru pro aktuální počítač.|  
|[WinCounter](../profiling/wincounter.md) **:** *cesta*|Určuje událost čítače výkonu systému Windows mají být součástí značky data profilu. Použít pouze s **spustit**.|  
|[Pro automatické označování](../profiling/automark.md) **:***n*|Určuje časový interval (v milisekundách) mezi události shromažďování dat čítačů výkonu systému Windows. Použití s **WinCounter**.|  
|[Události](../profiling/events-vsperfcmd.md) **:**`option`|Ovládací prvky kolekce zadané události trasování událostí pro Windows (ETW). Trasování událostí pro Windows data jsou shromažďována do .itl souboru, který není profilování soubor dat (.vsp).|  
|[Status](../profiling/status.md)|Zobrazuje stav profileru, informace o procesy, které jsou aktuálně profilovaný a účty, které mají oprávnění k řízení profileru.|  
|[Vypnutí](../profiling/shutdown.md)[**:**`n`]|Zavře profilování datový soubor a vypne profileru.|  
|[GlobalOn](../profiling/globalon-and-globaloff.md)|Obnoví shromažďování dat po volání **VSPerfCmdGlobalOff**.|  
|[GlobalOff](../profiling/globalon-and-globaloff.md)|Zastaví všechny shromažďování dat, ale nemá na konci relace profilování.|  
|[ProcessOn](../profiling/processon-and-processoff.md) **:**`pid`|Obnoví shromažďování dat pro zadaný proces po profilace byla pozastavena voláním **VSPerfCmdProcessOff**.|  
|[ProcessOff](../profiling/processon-and-processoff.md) **:**`pid`|Zastaví sběr dat pro zadaný proces.|  
|[ThreadOn a ThreadOff](../profiling/threadon-and-threadoff.md) **:** *tid*|Obnoví profilace pro proces zadaný po profilace byla pozastavena voláním **VSPerfCmdThreadOff**. Použití **ThreadOn** jenom v případě, že profilace pomocí metody instrumentace.|  
|[ThreadOn a ThreadOff](../profiling/threadon-and-threadoff.md) **:** *tid*|Pozastaví profilace pro zadaný vlákno. Použití **ThreadOff** jenom v případě, že profilace pomocí metody instrumentace.|  
|[Označit](../profiling/mark.md) **:** *MarkNum*[**,***MarkText***]**|Vloží značku do datového souboru profilování, volitelné textem.|  
  
## <a name="sampling-method-options"></a>Možnosti metody vzorkování  
 Tyto možnosti jsou k dispozici pouze při použití metoda profilování se vzorkováním.  
  
|Možnost|Popis|  
|------------|-----------------|  
|[Spusťte](../profiling/launch.md) **:** *spustitelný soubor*|Zadaná aplikace spustí a začne profilace.|  
|[Argumentů](../profiling/args.md) **:** *argumenty*|Určuje argumenty příkazového řádku mají být předána do spuštěného aplikace.|  
|[Console](../profiling/console.md)|Zadaný příkaz spustí v novém okně příkazového řádku.|  
|[Připojit](../profiling/attach.md) **:** *PID*[**,***PID*]|Zahájí profilace zadaný procesy. Procesy lze identifikovat podle id procesu nebo podle názvu procesu.|  
|[Odpojení](../profiling/detach.md)[**:***PID*[,*PID*]]|Zastaví profilace zadaný procesy. Procesy lze identifikovat podle id procesu nebo podle názvu procesu. Pokud není zadaný žádný proces, profilace je zastaveno pro všechny procesy.|  
|[Globální Katalog](../profiling/gc-vsperfcmd.md)[**:**{**přidělení**`&#124;`**životnost**}]|Shromažďuje data paměti .NET přidělení a objekt životního cyklu. Použít pouze **VSPerfCmdLaunch** možnost.|  
  
### <a name="sampling-interval-options"></a>Možnosti intervalu vzorkování  
 Následující možnosti zadat typ a doba vzorkování intervalech. Výchozí hodnota je **časovače**. Můžete také zadat čítačů procesoru jako interval pomocí **čítač** možnost. Tyto možnosti lze zadat pouze s **spusťte** nebo s prvním **Attach** profilování relace.  
  
|Možnost|Popis|  
|------------|-----------------|  
|[PF](../profiling/pf.md)[**:***n*]|Ukázky na každý n tý stránkování (výchozí = 10).|  
|[Sys](../profiling/sys-vsperfcmd.md)[**:***n*]|Ukázky při každém volání n tý systému (výchozí = 10).|  
|[Časovač](../profiling/timer.md)[**:***n*]|Ukázky na každý procesor n tý cyklus (výchozí = 10000000).|  
  
## <a name="service-component-and-kernel-mode-device-options"></a>Součást služby a možností zařízení režimu jádra  
 Následující možnosti správy podporovat profilování součásti služby nebo ovladačů zařízení v režimu jádra. Možnosti správy nastavení oprávnění profilování a řídit PROFILOVANÉHO služby nebo ovladače zařízení.  
  
 Možnosti správy, je třeba spustit na příkazovém řádku, která je spuštěna s přihlašovacími údaji správce.  
  
|Možnost|Popis|  
|------------|-----------------|  
|**Admin:Security** \< **Povolit &#124; ODEPŘÍT**> *vpravo*[ *vpravo*] \< *uživatele* &#124; *Skupiny*>|Povoluje nebo zakazuje zadaného uživatele nebo skupiny přístup k profilování služeb.<br /><br /> `Right`může být:<br /><br /> CrossSession - umožní uživateli přístup ke službě a křížové profilace relace.<br /><br /> SampleProfiling – poskytuje přístup uživatele k ovladač, který chcete povolit profilace vzorkování. Také se používá pro přístup k informacím přechod jádra během trasování profilace.<br /><br /> Umožňuje uživateli FullAccess - CrossSession a SampleProfiling přístup.|  
|**Admin:Security seznamu**|Uvádí aktuální stav profilování služeb a seznam oprávnění uživatele.|  
|**Správce:** \< *služby*&#124; *Ovladač*>\<**spustit**&#124; **Zastavit**&#124; **NAINSTALUJTE**&#124; **ODINSTALACE**>|Spustí, zastaví, instaluje nebo odinstaluje profilování součást služby (service) nebo ovladač zařízení v režimu jádra (ovladač).|  
|**Správce:** \< *služby*&#124; *Ovladač*>**automatické spuštění**\<**ON**&#124; **VYPNOUT**>|Povolí nebo zakáže automatické spuštění profilování služby (service) nebo ovladač zařízení v režimu jádra (ovladač) po restartu.|  
  
## <a name="vsperfcmd-driver"></a>/ Driver VSPerfCmd  
 **/Driver VSPerfCmd** možnost je nyní zastaralá. Použití **VsPerfCmdAdmin** možnosti pro tuto funkci.  
  
## <a name="see-also"></a>Viz také  
 [Vsinstr –](../profiling/vsinstr.md)   
 [Vsperfmon –](../profiling/vsperfmon.md)   
 [VSPerfReport](../profiling/vsperfreport.md)