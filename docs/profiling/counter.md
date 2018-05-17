---
title: Čítač | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: aa4b4cdb-e6ea-433a-9579-56f3785e1385
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 55e9519946dae36fcf8c9bc8808a23fbfaa985b8
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2018
---
# <a name="counter"></a>Čítač
**Čítač** možnost shromažďuje data z čítače výkonu procesoru (hardwaru).  
  
-   Pokud používáte vzorkování profilace metody **čítač** Určuje čítače výkonu na čipu a počet událostí čítače sloužící jako interval vzorkování. Při použití vzorkování, můžete zadat pouze jeden čítač.  
  
-   Při použití metoda profilování instrumentace, číslo události čítače, které došlo k chybě v intervalu mezi událostmi předchozí a aktuální kolekci jsou uvedeny jako samostatné pole v sestavách profileru. Více **čítač** možnosti lze zadat, když používáte instrumentace.  
  
 Každý typ procesoru má svou vlastní sadu čítačů výkonu hardwaru. Profileru definuje sadu Obecné čítače, které jsou společné pro téměř všechny procesory. K zobrazení seznamu čítače obecné a specifické pro procesor v počítači, použijte VSPerfCmd **QueryCounters** příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName | /Attach PID} /Counter:Name[,Reload[,FriendlyName]][Options]  
```  
  
```cmd  
VSPerfCmd.exe /Start:Method /Counter:Name[,Reload[,FriendlyName]][/Counter:Name[,Reload[,FriendlyName]]][Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Name`  
 Název čítače. Použít VSPerfCmd.exe **/QueryCounters** možnost seznamu názvů čítačů k dispozici v počítači.  
  
 `Reload`  
 Počet událostí čítače v intervalu vzorkování. Nepoužívejte pomocí metody instrumentace.  
  
 `FriendlyName`  
 (Volitelné) Řetězec, který má používat místě `Name` v záhlaví sloupců sestav profileru a zobrazení.  
  
## <a name="required-options"></a>Požadované možnosti  
 Čítač možnost lze použít pouze s jednou z následujících možností:  
  
 **Spusťte:** `Trace`  
 Inicializuje lze pomocí metody instrumentace profileru.  
  
 **Spusťte:** `AppName`  
 Spustí zadané aplikace a profileru. Profileru musí být inicializován lze pomocí metody vzorkování.  
  
 **Připojení:** `PID`  
 Spustí profileru a připojí jej k proces zadaný pomocí ID procesu. Profileru musí být inicializován lze pomocí metody vzorkování.  
  
## <a name="example"></a>Příklad  
 Ukázka metody vzorkování ukazuje, jak ukázková aplikace na každých 1000 výskytů čítače obecné profileru NonHaltedCycles.  
  
 Příklad metoda instrumentace ukazuje, jak k chybě při inicializaci profileru shromažďování událostí čítače L2InstructionFetches. Název čítače L2InstructionFetches je specifické pro procesor.  
  
```cmd  
; Sample Method Example  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Counter:NonHaltedCycles,1000,"Non-Halted Cycles"  
  
;INSTRUMENTATION METHOD EXAMPLE  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /Counter:L2InstructionFetches,,"L2 Cache Instruction Fetches"  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)