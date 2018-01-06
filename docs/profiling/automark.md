---
title: "Pro automatické označování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2fc5b0e69d5df203bc78cbfaf9981c550192a824
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="automark"></a>AutoMark
**Pro automatické označování** možnost určuje počet milisekund, po mezi kolekce událostí čítače výkonu softwaru systému Windows. Čítače výkonu systému Windows jsou určené v **WinCounter** možnost.  
  
 Pouze jeden **pro automatické označování** možnost lze zadat na příkazovém řádku. Všimněte si, že **WinCounter** intervalu vzorkování určeného **pro automatické označování** je nezávislý na hlavní vzorkování intervalu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parametry  
 `Milliseconds`  
 Určuje počet milisekund, po mezi kolekce událostí čítače výkonu systému Windows.  
  
## <a name="required-options"></a>Požadované možnosti  
 **WinCounter:**`Path`  
 Určuje čítačů výkonu systému Windows ke shromažďování. Při použití metody instrumentace, lze zadat více čítačů systému Windows. Při použití metody vzorkování, lze zadat pouze jeden čítač softwaru. **WinCounter** možnost je nutné zadat na příkazovém řádku, který obsahuje **spustit** možnost.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu je interval vzorkování na 1000 milisekund nastavit pro dvě čítačů výkonu systému Windows.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)