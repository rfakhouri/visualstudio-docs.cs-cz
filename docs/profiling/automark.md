---
title: AutoMark | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c2120fc6aa546261077aa19de5de298feddfec7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987720"
---
# <a name="automark"></a>AutoMark
**AutoMark** parametr určuje počet milisekund mezi kolekce událostí čítače výkonu Windows software. Čítače výkonu Windows jsou určené v **WinCounter** možnost.  
  
 Pouze jeden **AutoMark** možnost lze zadat na příkazovém řádku. Všimněte si, že **WinCounter** určený interval vzorkování **AutoMark** je nezávislá hlavní vzorkovací frekvence.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parametry  
 `Milliseconds`  
 Určuje počet milisekund mezi kolekce událostí čítače výkonu Windows.  
  
## <a name="required-options"></a>Požadované možnosti  
 **WinCounter:** `Path`  
 Určuje název čítače výkonu Windows shromažďování. Při použití metody instrumentace je možné zadat více čítačů Windows. Při použití metody vzorkování lze zadat pouze jeden čítač softwaru. **WinCounter** možnost musí být zadána v příkazovém řádku, který obsahuje **Start** možnost.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu je interval vzorkování na 1000 milisekund nastavena pro dva čítače výkonu Windows.  
  
```cmd  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)